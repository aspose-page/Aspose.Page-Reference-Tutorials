---
date: 2026-02-07
description: Узнайте, как масштабировать прямоугольник с помощью Aspose.Page для Java,
  как перемещать форму и применять аффинное преобразование для создания документов
  PostScript.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Как масштабировать прямоугольник с помощью Aspose.Page для Java
url: /ru/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как масштабировать прямоугольник с помощью Aspose.Page for Java

## Введение
Добро пожаловать в подробное руководство по использованию мощных возможностей **Aspose.Page for Java** для выполнения различных преобразований страниц. В этом уроке вы узнаете **how to scale rectangle**, перемещать формы, вращать объекты и **apply affine transform** при создании **PostScript document**. Эти возможности позволяют создавать насыщенные графикой Java‑приложения без необходимости работы с низкоуровневым кодом рендеринга.

## Быстрые ответы
- **Как масштабировать прямоугольник в Java с помощью Aspose.Page?** Используйте метод `document.scale()` перед отрисовкой фигуры.  
- **Могу ли я переместить (translate) форму, не затрагивая другие графические элементы?** Да — сохраните состояние графики, вызовите `document.translate(x, y)`, отрисуйте, затем восстановите состояние.  
- **Какой класс создает файл PostScript?** `PsDocument` вместе с `PsSaveOptions`.  
- **Нужна ли лицензия для использования в продакшене?** Требуется действующая лицензия Aspose.Page для коммерческих развертываний.  
- **Какая версия Java поддерживается?** Aspose.Page работает с Java 8 и новее.

## Предварительные требования
Перед тем как приступить к пошаговому руководству, убедитесь, что у вас есть следующие предварительные требования:

- Базовые знания программирования на Java.  
- Установлена библиотека Aspose.Page for Java. Вы можете скачать её из [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- На вашем компьютере настроена интегрированная среда разработки (IDE) для Java.

## Импорт пакетов
В вашем Java‑проекте импортируйте необходимые пакеты для использования Aspose.Page for Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Что такое “how to scale rectangle” в Aspose.Page?
Масштабирование прямоугольника изменяет его размеры по осям X и Y, сохраняя форму. Aspose.Page предоставляет метод `scale(float sx, float sy)`, который применяет **affine transform** к текущему графическому состоянию. Это основная техника, лежащая в основе ключевого слова **how to scale rectangle**.

## Как переместить форму с помощью Aspose.Page
Перемещение (translation) перемещает форму в новое место без изменения её размеров. Это суть **how to translate shape**. Сохранив состояние графики, применив `translate(dx, dy)`, отрисовав и затем восстановив состояние, вы не затрагиваете другие объекты.

## Пример 1: Без преобразований
Первый пример рисует простой прямоугольник без применения каких‑либо преобразований. Это служит базовой точкой сравнения с последующими примерами.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Пример 2: Перемещение
Здесь мы демонстрируем **how to translate shape**, перемещая графический контекст на 250 единиц вправо перед отрисовкой второго прямоугольника.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Пример 3: Масштабирование
Этот пример отвечает на основной вопрос **how to scale rectangle**. Мы уменьшаем прямоугольник до 50 % от исходной ширины и 75 % от исходной высоты.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Как вращать форму в Java (rotate shape java)
Вращение — ещё одна распространённая аффинная операция. Хотя фрагменты кода для вращения опущены ради краткости, схема идентична: сохранить состояние графики, вызвать `document.rotate(angle)`, отрисовать форму, затем восстановить. Это демонстрирует **rotate shape java** и **how to rotate rectangle** на практике.

## Почему это важно – практические преимущества
- **Device‑independent output** – Напишите один раз и генерируйте PostScript или XPS без специфических настроек под платформу.  
- **Fine‑grained control** – Комбинируйте перемещение, масштабирование, сдвиг и вращение для точного соответствия требованиям макета.  
- **Performance‑oriented** – Низконагруженный API, идеальный для пакетной обработки крупномасштабных документов.  

## Распространённые сценарии использования
- Генерация печатных счетов‑фактур – например, решение **printable invoice java**, которое точно размещает логотипы и штрих‑коды.  
- Создание технических схем, где требуется точное масштабирование и позиционирование.  
- Автоматизация создания многостраничных отчётов в формате PostScript.  

## Распространённые проблемы и решения
- **Transformation not resetting** – Всегда сочетайте `document.writeGraphicsSave()` с `document.writeGraphicsRestore()`, чтобы избежать нежелательных переносов эффектов.  
- **Unexpected colors** – Убедитесь, что после каждого преобразования задаёте цвет (paint); состояние графики не сохраняет предыдущие настройки цвета после восстановления.  
- **File size too large** – Используйте `PsSaveOptions` для включения сжатия или уменьшения разрешения изображений при встраивании растровой графики.  

## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Page for Java для других форматов документов?
Aspose.Page в основном ориентирован на манипуляцию страницами форматов PostScript и XPS.

### Где я могу найти больше примеров и документацию по Aspose.Page for Java?
Посетите [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) для получения полной информации.

### Доступна ли бесплатная пробная версия Aspose.Page for Java?
Да, вы можете получить бесплатную пробную версию [здесь](https://releases.aspose.com/).

### Как получить временную лицензию для Aspose.Page for Java?
Получите временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

### Где я могу получить поддержку сообщества или задать вопросы о Aspose.Page for Java?
Посетите [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) для обсуждений в сообществе.

## Часто задаваемые вопросы

**В: В чём разница между `translate` и `scale`?**  
О: `translate` перемещает начало координат системы, тогда как `scale` изменяет размер отрисованных объектов по осям X и/или Y.

**В: Можно ли комбинировать несколько преобразований в одном графическом состоянии?**  
О: Да — вызывая последовательно `translate`, `scale`, `rotate` или `shear` перед отрисовкой, вы создаёте комбинированное аффинное преобразование.

**В: Как сбросить преобразования после отрисовки формы?**  
О: Используйте `document.writeGraphicsRestore()`, чтобы вернуться к ранее сохранённому графическому состоянию.

**В: Можно ли вращать прямоугольник вокруг его центра?**  
О: Конечно. Переместите прямоугольник в начало координат, примените `rotate(angle)`, затем верните его обратно перед отрисовкой.

**В: Поддерживает ли Aspose.Page сглаживание (anti‑aliasing) для более плавной графики?**  
О: Да — задайте соответствующие параметры рендеринга в `PsSaveOptions`, чтобы включить сглаживание.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}