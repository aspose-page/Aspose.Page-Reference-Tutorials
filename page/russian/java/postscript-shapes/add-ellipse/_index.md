---
date: 2026-02-18
description: Узнайте, как установить цвет заливки и создать эллипс PostScript в Java
  с помощью Aspose.Page. Это руководство показывает, как заполнить эллипс в Java,
  нарисовать его контур и задать толщину линии.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Установить цвет заливки при рисовании эллипса PostScript в Java
url: /ru/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Установить цвет краски для рисования эллипса PostScript в Java

## Введение
Если вам нужно **установить цвет краски** при рисовании векторной графики, библиотека Aspose.Page for Java предоставляет полный контроль над каждым штрихом и заливкой. В этом руководстве вы узнаете, как **установить цвет краски**, **заполнить эллипс в Java** и **нарисовать контур эллипса**, используя простой пошаговый подход. К концу вы сможете добавлять высококачественные эллипсы PostScript в счета, отчёты или любой печатный документ.

## Быстрые ответы
- **Какая библиотека лучше всего подходит для рисования графики PostScript в Java?** Aspose.Page for Java.  
- **Могу ли я заполнить эллипс сплошным цветом?** Да — используйте `document.setPaint(Color.YOUR_COLOR)` перед `fill`.  
- **Как нарисовать только контур эллипса?** Установите цвет и штрих, затем вызовите `document.draw(...)`.  
- **Нужна ли лицензия для использования в продакшене?** Требуется коммерческая лицензия; временная лицензия доступна для тестирования.  
- **Какая версия Java поддерживается?** Любая среда выполнения Java 8+ совместима с текущим выпуском Aspose.Page.

## Что такое эллипс PostScript?
Эллипс PostScript — это векторная форма, определяемая ограничивающим прямоугольником. В отличие от растровых изображений, он масштабируется без потери качества, что делает его идеальным для печати высокого разрешения и конвертации в PDF.

## Почему использовать Aspose.Page для создания эллипса PostScript?
- **Полный контроль** над примитивами рисования (линии, кривые, эллипсы).  
- **Кроссплатформенный** — работает на Windows, Linux и macOS.  
- **Нет внешних зависимостей** — чистый Java API, без нативного кода.  
- **Лёгкая интеграция** с существующими Java‑приложениями и инструментами сборки.

## Предварительные требования
Перед началом убедитесь, что у вас есть:

1. Рабочее окружение разработки Java (JDK 8 или новее).  
2. Библиотека Aspose.Page for Java, добавленная в ваш проект. Вы можете скачать её **[здесь](https://releases.aspose.com/page/java/)**.  

## Импорт пакетов
В вашем Java‑файле исходного кода импортируйте классы, необходимые для рисования и сохранения содержимого PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Как установить цвет краски для эллипса
Установка цвета краски — первый шаг перед любой операцией заливки или обводки. Метод `setPaint` определяет цвет, который будет использован для следующей команды рисования.

### Шаг 1: Настройка документа PostScript
Создайте поток вывода, настройте размер страницы и создайте экземпляр `PsDocument`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Шаг 2: Как заполнить эллипс — используйте установку цвета краски
Чтобы **заполнить эллипс**, сначала вызовите `setPaint` с нужным цветом заливки, затем вызовите `fill` с экземпляром `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Шаг 3: Нарисовать контур эллипса и установить толщину штриха
После заливки вы можете изменить цвет краски, определить `BasicStroke` для управления шириной линии и нарисовать контур эллипса.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Шаг 4: Закрыть и сохранить документ
Завершите страницу и запишите файл PostScript на диск.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Теперь у вас есть файл PostScript, содержащий два эллипса — один, заполненный оранжевым, и другой, обведённый красным. Не стесняйтесь экспериментировать с различными координатами, размерами и цветами, чтобы соответствовать требованиям вашего дизайна.

## Распространённые ошибки и устранение неполадок
- **Неправильный путь к файлу** — Убедитесь, что `dataDir` заканчивается разделителем (`/` или `\\`), соответствующим вашей ОС.  
- **Отсутствует лицензия** — Без действующей лицензии библиотека работает в режиме оценки и может добавлять водяные знаки.  
- **Цвет не применяется** — Помните, что необходимо вызывать `document.setPaint(...)` *перед* каждым вызовом `fill` или `draw`; настройка краски не сохраняется автоматически между отдельными операциями.

## Часто задаваемые вопросы

**В: Могу ли я использовать Aspose.Page for Java вместе с другими библиотеками Java?**  
О: Да, Aspose.Page for Java разработана для бесшовной интеграции с другими библиотеками Java.

**В: Как получить временную лицензию для Aspose.Page for Java?**  
О: Получите временную лицензию **[здесь](https://purchase.aspose.com/temporary-license/)** для тестовых целей.

**В: Подходит ли Aspose.Page для коммерческих проектов?**  
О: Абсолютно! Посетите **[здесь](https://purchase.aspose.com/buy)**, чтобы ознакомиться с вариантами лицензирования для коммерческого использования.

**В: Где я могу получить помощь или обсудить вопросы, связанные с Aspose.Page?**  
О: Присоединяйтесь к сообществу на **[форуме Aspose.Page](https://forum.aspose.com/c/page/39)** для обсуждений и помощи.

**В: Есть ли бесплатные ресурсы для изучения Aspose.Page for Java?**  
О: Воспользуйтесь **[бесплатной пробной версией](https://releases.aspose.com/)** и изучите примеры в документации.

## Заключение
Aspose.Page for Java упрощает **установку цвета краски**, **заполнение эллипса** и **рисование контура эллипса** — независимо от того, нужен ли вам простой заполненный объект или сложная обведённая графика. Следуя указанным шагам, вы сможете быстро добавить профессиональные векторные графики в любой печатный документ. Для более глубокого изучения — например, комбинирования нескольких фигур, применения градиентов или конвертации в PDF — обратитесь к официальной **[документации](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}