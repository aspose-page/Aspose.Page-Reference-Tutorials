---
date: 2026-10-31
description: Узнайте, как задать цвет краски и заполнить эллипс в Java PostScript
  с помощью Aspose.Page. Это руководство показывает, как заполнить эллипс, нарисовать
  контур эллипса и задать толщину линии с помощью понятных шагов кода.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Добавить эллипс в Java PostScript
og_description: Узнайте, как заполнить эллипс и задать цвет краски в Java PostScript
  с помощью Aspose.Page. Следуйте пошаговому коду, чтобы за секунды нарисовать заполненные
  и контурные эллипсы.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Как заполнить эллипс и задать цвет краски в Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Как заполнить эллипс и задать цвет краски в Java PostScript
url: /ru/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как заполнить эллипс и установить цвет заливки в Java PostScript

## Введение
Если вам нужно **установить цвет заливки** при рисовании векторной графики, библиотека Aspose.Page for Java предоставляет полный контроль над каждым штрихом и заливкой. В этом руководстве вы узнаете, как **установить цвет заливки**, **заполнить эллипс** и **нарисовать контур эллипса** с помощью простого пошагового подхода. К концу вы сможете добавлять высококачественные PostScript‑эллипсы в счета, отчёты или любой печатный документ.

## Быстрые ответы
- **Какой библиотекой лучше всего рисовать графику PostScript в Java?** Aspose.Page for Java.  
- **Могу ли я заполнить эллипс сплошным цветом?** Да — используйте `document.setPaint(Color.YOUR_COLOR)` перед `fill`.  
- **Как нарисовать только контур эллипса?** Установите цвет и штрих, затем вызовите `document.draw(...)`.  
- **Нужна ли лицензия для использования в продакшене?** Требуется коммерческая лицензия; временная лицензия доступна для тестирования.  
- **Какая версия Java поддерживается?** Любая среда выполнения Java 8+ работает с текущим выпуском Aspose.Page.

## Что такое эллипс PostScript?
Эллипс PostScript — это векторная фигура, определяемая ограничивающим прямоугольником. В отличие от растровых изображений, он масштабируется без потери качества, что делает его идеальным для печати высокого разрешения и конвертации в PDF. Поскольку форма описывается математически, её можно отрисовывать любого размера или разрешения, сохраняя чёткие края и плавные кривые.

## Почему стоит использовать Aspose.Page для создания эллипса PostScript?
Aspose.Page предоставляет детерминированный контроль над каждым графическим примитивом. Она поддерживает **3 основные операционные системы (Windows, Linux, macOS)**, **0 нативных зависимостей** и может отрисовывать **более 50 векторных примитивов** в секунду на типичном сервере. Библиотека написана полностью на Java, поэтому её можно внедрять в любое приложение Java 8+ без дополнительных нативных библиотек.

## Предварительные требования
Прежде чем начать, убедитесь, что у вас есть:

1. Рабочая среда разработки Java (JDK 8 или новее).  
2. Библиотека Aspose.Page for Java, добавленная в ваш проект. Вы можете скачать её **[from the Aspose.Page for Java release page](https://releases.aspose.com/page/java/)**.

## Импорт пакетов
В вашем Java‑файле исходного кода импортируйте классы, необходимые для рисования и сохранения содержимого PostScript.

Пакет `java.awt` предоставляет базовые графические типы, такие как `Color`, `Ellipse2D` и `BasicStroke`. Пакет `com.aspose.page` содержит класс `PsDocument`, который записывает вывод PostScript.

- **`Color`** — представляет sRGB‑цвет, используемый для заливки.  
- **`Ellipse2D`** — описывает форму эллипса, определяемую ограничивающим прямоугольником.  
- **`BasicStroke`** — задаёт ширину линии, шаблон штриховки и стиль окончания для рисования контуров.  
- **`PsDocument`** — представляет документ PostScript и предоставляет методы для рисования графики и управления страницами.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Как установить цвет заливки для эллипса
Первый шаг — указать документу, какой цвет использовать для следующей операции рисования. Метод `setPaint` задаёт сплошной цвет, который будет применён либо к заливке, либо к обводке, в зависимости от последующего вызова.

### Шаг 1: Настройка документа PostScript
Создайте поток вывода, настройте размер страницы и создайте экземпляр `PsDocument`.

`PsDocument` — это основной класс, представляющий файл PostScript в памяти. Все команды рисования проходят через этот объект, который управляет разметкой страниц, ресурсами и окончательной генерацией файла.

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

### Шаг 2: Заполнить эллипс — использовать установку цвета
Чтобы **заполнить эллипс**, сначала вызовите `setPaint` с нужным цветом заливки, затем вызовите `fill` с экземпляром `Ellipse2D`.

`setPaint` задаёт текущий цвет рисования, используемый для последующих операций заливки или обводки.  
`Ellipse2D` определяет геометрические границы эллипса; его конструктор принимает координаты X‑Y верхнего левого угла, а также ширину и высоту.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Шаг 3: Нарисовать контур эллипса и задать толщину линии
После заполнения вы можете изменить цвет заливки, задать `BasicStroke` для управления шириной линии и нарисовать контур эллипса.

`BasicStroke` задаёт ширину линии, шаблон штриховки и стиль окончания для рисования контуров. Регулируя его свойство `width`, вы контролируете, насколько жирной будет граница эллипса.

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

Вызов `document.close()` сбрасывает все ожидающие команды рисования и освобождает ресурсы. Полученный файл `.ps` можно открыть в любом просмотрщике PostScript или конвертировать в PDF.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Теперь у вас есть файл PostScript, содержащий два эллипса — один заполненный оранжевым, а другой обведённый красным. Не стесняйтесь экспериментировать с различными координатами, размерами и цветами, чтобы соответствовать требованиям вашего дизайна.

## Распространённые ошибки и устранение неполадок
- **Неправильный путь к файлу** — Убедитесь, что `dataDir` заканчивается разделителем (`/` или `\\`), соответствующим вашей ОС.  
- **Отсутствует лицензия** — Без действующей лицензии библиотека работает в режиме оценки и может добавлять водяные знаки.  
- **Цвет не применяется** — Помните, что `document.setPaint(...)` необходимо вызывать *перед* каждым вызовом `fill` или `draw`; настройка цвета не сохраняется автоматически между отдельными операциями.

## Часто задаваемые вопросы

**В: Могу ли я использовать Aspose.Page for Java вместе с другими библиотеками Java?**  
О: Да, Aspose.Page for Java разработана для бесшовной интеграции с другими библиотеками Java.

**В: Как получить временную лицензию для Aspose.Page for Java?**  
О: Получите временную лицензию **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)** для тестовых целей.

**В: Подходит ли Aspose.Page для коммерческих проектов?**  
О: Абсолютно! Посетите **[the Aspose purchase page](https://purchase.aspose.com/buy)**, чтобы ознакомиться с вариантами лицензирования для коммерческого использования.

**В: Где можно получить помощь или обсудить вопросы, связанные с Aspose.Page?**  
О: Присоединяйтесь к сообществу на **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** для обсуждений и поддержки.

**В: Есть ли бесплатные ресурсы для изучения Aspose.Page for Java?**  
О: Воспользуйтесь **[Aspose free trial page](https://releases.aspose.com/)** и изучайте примеры в документации.

## Заключение
Aspose.Page for Java упрощает **установку цвета заливки**, **заполнение эллипса** и **рисование контура эллипса** — независимо от того, нужен ли вам простой заполненный объект или сложная графика с обводкой. Следуя описанным шагам, вы быстро добавите профессиональные векторные графики в любой печатный документ. Для более глубокого изучения — например, комбинирования нескольких фигур, применения градиентов или конвертации в PDF — обратитесь к официальной **[Aspose.Page Java documentation](https://reference.aspose.com/page/java/)**.

---

**Последнее обновление:** 2026-10-31  
**Тестировано с:** Aspose.Page for Java 24.11  
**Автор:** Aspose

## Связанные руководства

- [Как нарисовать прямоугольник в Java PostScript с Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Как добавить Unicode‑текст в Java PostScript с Aspose.Page](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Создать радиальный градиент в PostScript с Aspose.Page for Java](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}