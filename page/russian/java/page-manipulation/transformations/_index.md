---
date: 2025-12-07
description: Узнайте, как масштабировать прямоугольник, перемещать форму и применять
  аффинное преобразование в Java с помощью Aspose.Page для создания документов PostScript.
language: ru
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Как масштабировать прямоугольник и применять преобразования с Aspose.Page
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как масштабировать прямоугольник и применять преобразования с Aspose.Page

## Introduction
Добро пожаловать в подробное руководство по использованию мощных возможностей **Aspose.Page for Java** для выполнения различных преобразований страниц. В этом учебнике вы узнаете **how to scale rectangle**, как перемещать формы, вращать объекты и **apply affine transform** при создании **PostScript document**. Эти возможности позволяют создавать насыщенные графикой Java‑приложения без необходимости писать низкоуровневый код рендеринга.

## Quick Answers
- **How do I scale a rectangle in Java with Aspose.Page?** Используйте метод `document.scale()` перед рисованием фигуры.  
- **Can I move (translate) a shape without affecting other graphics?** Да — сохраните состояние графики, вызовите `document.translate(x, y)`, нарисуйте, затем восстановите состояние.  
- **What class creates a PostScript file?** `PsDocument` вместе с `PsSaveOptions`.  
- **Do I need a license for production use?** Для коммерческого использования требуется действующая лицензия Aspose.Page.  
- **Which Java version is supported?** Aspose.Page поддерживает Java 8 и выше.

## Prerequisites
Перед тем как приступить к пошаговому руководству, убедитесь, что у вас есть следующие требования:

- Базовые знания программирования на Java.  
- Установлена библиотека Aspose.Page for Java. Вы можете скачать её из [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- На вашем компьютере настроена интегрированная среда разработки (IDE) для Java.

## Import Packages
В вашем Java‑проекте импортируйте необходимые пакеты для работы с Aspose.Page for Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## What is “how to scale rectangle” in Aspose.Page?
Масштабирование прямоугольника изменяет его размер по осям X и Y, сохраняя форму. Aspose.Page предоставляет метод `scale(float sx, float sy)`, который применяет **affine transform** к текущему состоянию графики. Это основная техника за ключевым словом **how to scale rectangle**.

## How to Translate Shape with Aspose.Page
Трансляция перемещает форму в новое положение без изменения её размеров. Это суть **how to translate shape**. Сохраняя состояние графики, применяя `translate(dx, dy)`, рисуя и затем восстанавливая состояние, вы не затрагиваете другие объекты.

## Example 1: No Transformations
Первый пример рисует простой прямоугольник без применения каких‑либо преобразований. Это базовый уровень для сравнения с последующими примерами.

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

## Example 2: Translation
Здесь мы демонстрируем **how to translate shape**, перемещая контекст графики на 250 единиц вправо перед рисованием второго прямоугольника.

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

## Example 3: Scaling
Этот пример отвечает на основной вопрос **how to scale rectangle**. Мы уменьшаем прямоугольник до 50 % от его исходной ширины и 75 % от его высоты.

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

## How to Rotate Shape Java (rotate shape java)
Вращение — ещё одна распространённая аффинная операция. Хотя фрагменты кода для вращения опущены ради краткости, схема идентична: сохраните состояние графики, вызовите `document.rotate(angle)`, нарисуйте форму, затем восстановите состояние. Это демонстрирует **rotate shape java** и **how to rotate rectangle** на практике.

## Why Use Aspose.Page for These Transformations?
- **Device‑independent**: Пишете один раз, генерируете PostScript или XPS без платформенно‑специфичного кода.  
- **Fine‑grained control**: Прямой доступ к состоянию графики позволяет комбинировать трансляцию, масштабирование, сдвиг и вращение.  
- **Performance**: Низконагруженный API, подходящий для пакетной обработки больших документов.  

## Common Use Cases
- Генерация печатных счетов с динамическими штрих‑кодами и логотипами.  
- Создание технических схем, где требуется точное масштабирование и позиционирование.  
- Автоматизация создания многостраничных отчётов в формате PostScript.  

## Conclusion
В этом учебнике мы рассмотрели различные преобразования в Java‑манипуляции страницами с использованием Aspose.Page for Java, сосредоточившись на **how to scale rectangle**, **how to translate shape** и других аффинных операциях. Следуя этим примерам, вы сможете расширить свои Java‑приложения продвинутыми возможностями манипуляции страницами и **create PostScript document** с профессиональными стандартами публикации.

## FAQ's
### Can I use Aspose.Page for Java for other document formats?
Aspose.Page в основном ориентирован на манипуляцию страницами форматов PostScript и XPS.

### Where can I find more examples and documentation for Aspose.Page for Java?
Посетите [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) для получения полной информации.

### Is there a free trial available for Aspose.Page for Java?
Да, бесплатную пробную версию можно получить [здесь](https://releases.aspose.com/).

### How can I get a temporary license for Aspose.Page for Java?
Получить временную лицензию можно [здесь](https://purchase.aspose.com/temporary-license/).

### Where can I seek community support or ask questions about Aspose.Page for Java?
Посетите [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) для общения с сообществом.

## Frequently Asked Questions

**Q: What is the difference between `translate` and `scale`?**  
A: `translate` перемещает начало координат, тогда как `scale` изменяет размер нарисованных объектов по осям X и/или Y.

**Q: Can I combine multiple transformations in a single graphics state?**  
A: Да — вызывая последовательно `translate`, `scale`, `rotate` или `shear` перед рисованием, вы создаёте комбинированное аффинное преобразование.

**Q: How do I reset transformations after drawing a shape?**  
A: Используйте `document.writeGraphicsRestore()` для возврата к ранее сохранённому состоянию графики.

**Q: Is it possible to rotate a rectangle around its center?**  
A: Абсолютно. Переместите прямоугольник в начало координат, примените `rotate(angle)`, затем верните его обратно перед рисованием.

**Q: Does Aspose.Page support anti‑aliasing for smoother graphics?**  
A: Да — установите соответствующие параметры рендеринга в `PsSaveOptions`, чтобы включить анти‑алиасинг.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}