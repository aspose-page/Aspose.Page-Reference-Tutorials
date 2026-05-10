---
date: 2026-02-20
description: Узнайте, как установить цвет текста в Java с помощью Aspose.Page for
  Java, изменить размер шрифта в Java, создать файл PostScript, заполнить и обвести
  текст, а также использовать пользовательские шрифты в Java при создании документа
  PostScript.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Установка цвета текста в Java с Aspose.Page – Руководство по работе с текстом
url: /ru/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Установка цвета текста в Java с Aspose.Page – Руководство по работе с текстом

## Introduction
Добро пожаловать в наше пошаговое руководство по **set text color java** при работе с файлами PostScript с помощью Aspose.Page для Java. Aspose.Page для Java — мощная библиотека, позволяющая разработчикам **create postscript document** файлы, управлять шрифтами и точно стилизовать текст. В этом уроке вы узнаете, как добавить текст, изменить его цвет, **change font size java**, а также **apply fill and stroke text** для получения профессионального вида.

## Quick Answers
- **What library lets me set text color in Java?** Aspose.Page for Java.  
- **Can I use system fonts and custom fonts?** Да, поддерживаются оба типа, и вы можете **use custom fonts java** без труда.  
- **How do I change the text size?** Указывая размер шрифта при создании `Font` или `DrFont`.  
- **Is it possible to outline and fill text together?** Конечно — используйте `fillAndStrokeText`.  
- **What output format does this tutorial produce?** Документ PostScript (`.ps`), который вы можете **generate postscript file** программно.

## What is “set text color java”?
Установка цвета текста в Java означает определение объекта `Color`, который движок рендеринга (в данном случае Aspose.Page) использует при отрисовке символов на странице. Эта операция необходима для создания визуально различимых документов, особенно когда требуется **generate postscript file** программно.

## Why use Aspose.Page for Java?
- **Full control** над генерацией PostScript без необходимости в нативном интерпретаторе.  
- **Support for both system and external fonts**, позволяя встраивать любую типографику, которая вам нужна.  
- **Easy API** для заполнения, обводки и **fill and stroke text**, предоставляющее гибкость в стилизации.  
- **Cross‑platform** совместимость — пишете один раз, запускаете везде, где работает Java.  

## Prerequisites
Прежде чем приступить, убедитесь, что у вас есть:

- Базовые знания программирования на Java.  
- Библиотека Aspose.Page для Java установлена. Вы можете скачать её со [Страницы загрузки Aspose.Page для Java](https://releases.aspose.com/page/java/).  
- Необходимые шрифты находятся в указанной папке. Дополнительные детали в [документации Aspose.Page для Java](https://reference.aspose.com/page/java/).  

## Import Packages
В вашем Java‑проекте импортируйте необходимые пакеты для Aspose.Page для Java:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```

## Step 1: Set Up the Document
Сначала создаём новый **PostScript документ** и настраиваем параметры вывода.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## How to Set Text Color Java Using System Font
Теперь продемонстрируем **set text color java** с использованием системного шрифта.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tip:** Метод `fillText` автоматически использует текущий цвет, если вы не передаёте аргумент `Color`, который по умолчанию — чёрный.

## Using Custom Font and Changing Text Size
Вы также можете **change font size java** и использовать пользовательский шрифт, хранящийся в вашей папке шрифтов.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Outlining (Stroke) Text – Apply Stroke Text
Обводка текста придаёт ему чёткие границы. Здесь мы **apply stroke text** с помощью `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Outlining Text with Custom Font
Та же техника работает и с пользовательскими шрифтами.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Step 6: Save the Document
Наконец, закрываем страницу и сохраняем файл на диск.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Why This Matters
Возможность **set text color java** и комбинирования заполнения с обводкой дает вам полный художественный контроль над финальным выводом PostScript. Будь то генерация счетов, сертификатов или пользовательской графики, способность **create postscript document** с точной стилизацией уменьшает необходимость последующей обработки в графических редакторах.

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Font not found** | Убедитесь, что файл шрифта помещён в `necessary_fonts`, а путь к папке правильно добавлен через `options.setAdditionalFontsFolders`. |
| **Color not applied** | Проверьте, что вызываете перегрузку `fillText` или `outlineText`, включающую аргумент `Color`. |
| **Stroke appears too thin** | Увеличьте ширину `BasicStroke` (например, `new BasicStroke(3)`). |
| **Document not opening** | Убедитесь, что сгенерированный файл `.ps` сохранён с правильным расширением и ваш просмотрщик поддерживает PostScript. |

## Frequently Asked Questions

**Q:** Могу ли я использовать собственные пользовательские шрифты с Aspose.Page для Java?  
**A:** Да, вы можете **use custom fonts java**, указав имя шрифта и размер в классе `DrFont`.

**Q:** Как изменить цвет текста?  
**A:** Установите нужный цвет с помощью класса `Color` при заполнении или обводке текста.

**Q:** Можно ли добавить несколько страниц в документ PostScript?  
**A:** Конечно! Вы можете создавать несколько страниц, повторяя шаги создания документа и его сохранения.

**Q:** Какова цель класса `ExternalFontCache`?  
**A:** `ExternalFontCache` используется для получения пользовательских шрифтов, обеспечивая их доступность для работы с текстом.

**Q:** Можно ли применить разные обводки к обводимому тексту?  
**A:** Да, вы можете настроить ширину и цвет обводки, используя классы `Stroke` и `Color` соответственно.

## Conclusion
Поздравляем! Теперь вы знаете, как **set text color java**, **change font size java**, **apply fill and stroke text** и **create postscript document** с помощью Aspose.Page для Java. Экспериментируйте с различными шрифтами, цветами и стилями обводки, чтобы получать профессиональные результаты в формате PostScript.

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}