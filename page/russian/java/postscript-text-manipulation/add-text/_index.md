---
date: 2025-12-14
description: Узнайте, как установить цвет текста в Java с помощью Aspose.Page for
  Java, добавить текст в PostScript и применить обводку текста для создания богатого
  оформления документов.
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

## Введение
Добро пожаловать в наше пошаговое руководство по **установке цвета текста в Java** при работе с файлами PostScript с помощью Aspose.Page для Java. Aspose.Page для Java — мощная библиотека, позволяющая разработчикам создавать и **генерировать файлы postscript**, управлять шрифтами и стилизовать текст с точностью. В этом учебнике вы узнаете, как добавить текст, изменить его цвет, настроить размер и даже **применить обводку текста** для профессионального вида.

## Быстрые ответы
- **Какая библиотека позволяет установить цвет текста в Java?** Aspose.Page для Java.  
- **Можно ли использовать системные и пользовательские шрифты?** Да, поддерживаются оба варианта.  
- **Как изменить размер текста?** Указав размер шрифта при создании `Font` или `DrFont`.  
- **Можно ли одновременно заполнить и обвести текст?** Конечно — используйте `fillAndStrokeText`.  
- **В каком формате выводится результат этого руководства?** Документ PostScript (`.ps`).

## Что такое «set text color java»?
Установка цвета текста в Java означает определение объекта `Color`, который движок рендеринга (в данном случае Aspose.Page) использует при отрисовке символов на странице. Эта операция необходима для создания визуально различимых документов, особенно при программной генерации **postscript‑документов**.

## Почему стоит использовать Aspose.Page для Java?
- **Полный контроль** над генерацией PostScript без необходимости в нативном интерпретаторе PostScript.  
- **Поддержка как системных, так и внешних шрифтов**, позволяющая внедрять любую типографику.  
- **Простой API** для заполнения, обводки и **заполнения с обводкой текста**, предоставляющий гибкость в стилизации.  
- **Кроссплатформенная** совместимость — пишете один раз, запускаете в любой среде, где работает Java.

## Предварительные требования
Прежде чем приступить, убедитесь, что у вас есть:

- Базовые знания программирования на Java.  
- Библиотека Aspose.Page для Java установлена. Скачать её можно со [страницы загрузки Aspose.Page для Java](https://releases.aspose.com/page/java/).  
- Необходимые шрифты находятся в указанной папке. Дополнительные детали см. в [документации Aspose.Page для Java](https://reference.aspose.com/page/java/).

## Импорт пакетов
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

## Шаг 1: Создание документа
Сначала создаём новый **документ PostScript** и настраиваем параметры вывода.

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

## Как установить цвет текста в Java, используя системный шрифт
Теперь продемонстрируем **установку цвета текста в Java** с системным шрифтом.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Подсказка:** Метод `fillText` автоматически использует текущий цвет, если не передать аргумент `Color`; по умолчанию это чёрный цвет.

## Использование пользовательского шрифта и изменение размера текста
Вы также можете **изменить размер текста** и использовать пользовательский шрифт, расположенный в вашей папке шрифтов.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Обводка (Stroke) текста — применение обводки текста
Обводка текста придаёт ему чёткие контуры. Здесь мы **применяем обводку текста** с помощью `BasicStroke`.

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

## Обводка текста с пользовательским шрифтом
Тот же приём работает и с пользовательскими шрифтами.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Шаг 6: Сохранение документа
Наконец, закрываем страницу и записываем файл на диск.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|----------|
| **Шрифт не найден** | Убедитесь, что файл шрифта помещён в `necessary_fonts`, и путь к папке правильно добавлен через `options.setAdditionalFontsFolders`. |
| **Цвет не применяется** | Проверьте, что вызываете перегрузку `fillText` или `outlineText`, включающую аргумент `Color`. |
| **Обводка слишком тонкая** | Увеличьте ширину `BasicStroke` (например, `new BasicStroke(3)`). |
| **Документ не открывается** | Убедитесь, что сгенерированный файл `.ps` сохранён с правильным расширением и ваш просмотрщик поддерживает PostScript. |

## Часто задаваемые вопросы

**В:** Можно ли использовать собственные шрифты с Aspose.Page для Java?  
**О:** Да, пользовательские шрифты можно использовать, указав имя шрифта и размер в классе `DrFont`.

**В:** Как изменить цвет текста?  
**О:** Задайте нужный цвет через класс `Color` при заполнении или обводке текста.

**В:** Можно ли добавить несколько страниц в документ PostScript?  
**О:** Конечно! Создавайте новые страницы, повторяя шаги создания документа и сохранения.

**В:** Какова цель класса `ExternalFontCache`?  
**О:** `ExternalFontCache` используется для получения пользовательских шрифтов, обеспечивая их доступность при работе с текстом.

**В:** Можно ли применять разные обводки к обводимому тексту?  
**О:** Да, ширину и цвет обводки можно настроить с помощью класса `Stroke` и класса `Color` соответственно.

## Заключение
Поздравляем! Теперь вы знаете, как **установить цвет текста в Java**, менять размеры шрифтов, **применять обводку текста** и **создавать файлы postscript** с помощью Aspose.Page для Java. Экспериментируйте с разными шрифтами, цветами и стилями обводки, чтобы получать профессиональные PostScript‑выводы.

---

**Последнее обновление:** 2025-12-14  
**Тестировано с:** Aspose.Page для Java 23.12 (latest)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}