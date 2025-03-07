---
title: Aspose.Page Манипулирование текстом Java
linktitle: Добавить текст в Java PostScript
second_title: API Aspose.Page Java
description: Изучите возможности Aspose.Page для Java в нашем руководстве по добавлению текста в документы PostScript. Научитесь с легкостью использовать системные и пользовательские шрифты.
weight: 10
url: /ru/java/postscript-text-manipulation/add-text/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Манипулирование текстом Java

## Введение
Добро пожаловать в наше пошаговое руководство по добавлению текста в Java PostScript с помощью Aspose.Page для Java. Aspose.Page для Java — это мощная библиотека, которая позволяет разработчикам с легкостью манипулировать документами PostScript. В этом уроке мы покажем вам процесс добавления текста, использования системных и пользовательских шрифтов, выделения текста и добавления штрихов для получения визуально привлекательного результата.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
- Базовые знания Java-программирования.
-  Установлена библиотека Aspose.Page для Java. Вы можете скачать его с сайта[Страница загрузки Aspose.Page для Java](https://releases.aspose.com/page/java/).
-  Необходимые шрифты доступны в указанной папке. Дополнительную информацию вы можете найти в[Документация Aspose.Page для Java](https://reference.aspose.com/page/java/).
## Импортировать пакеты
В свой проект Java импортируйте необходимые пакеты для Aspose.Page для Java:
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
## Шаг 1. Настройте документ
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Создать выходной поток для документа PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Создайте варианты сохранения с размером А4.
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// Текст для записи в PS-файл
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Создать новый одностраничный документ PS
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Шаг 2. Использование системного шрифта для заполнения текста
```java
// Использование системного шрифта для заполнения текста
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Залейте текст цветом по умолчанию или уже заданным (черным)
document.fillText(str, font, 50, 100);
// Залейте текст синим цветом
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Шаг 3. Использование пользовательского шрифта для заполнения текста
```java
// Использование пользовательского шрифта для заполнения текста
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Залейте текст цветом по умолчанию или уже заданным (черным)
document.fillText(str, drFont, 50, 200);
// Залейте текст синим цветом
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Шаг 4. Выделение текста системным шрифтом
```java
// Использование системного шрифта для выделения текста
document.outlineText(str, font, 50, 300);
// Обведите текст сине-фиолетовым пером шириной в 2 очка.
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Заполните текст оранжевым цветом и обведите синим пером шириной в 2 очка.
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Шаг 5. Обведение текста пользовательским шрифтом
```java
// Использование пользовательского шрифта для выделения текста
document.outlineText(str, drFont, 50, 450);
// Обведите текст сине-фиолетовым пером шириной в 2 очка.
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Заполните текст оранжевым цветом и обведите синим пером шириной в 2 очка.
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Шаг 6: Сохраните документ
```java
// Закрыть текущую страницу
document.closePage();
// Сохраните документ
document.save();
```
## Заключение
Поздравляем! Вы успешно научились добавлять текст в Java PostScript с помощью Aspose.Page для Java. Поэкспериментируйте с различными шрифтами, цветами и параметрами обрисовки, чтобы улучшить свой документ.
## Часто задаваемые вопросы
### Могу ли я использовать свои собственные шрифты с Aspose.Page для Java?
 Да, вы можете использовать собственные шрифты, указав имя и размер шрифта в`DrFont` сорт.
### Как изменить цвет текста?
 Вы можете установить желаемый цвет с помощью`Color` класс при заполнении или обрисовке текста.
### Можно ли добавить несколько страниц в документ PostScript?
Абсолютно! Вы можете создать несколько страниц, повторив шаги создания и сохранения документа.
###  Какова цель`ExternalFontCache` class?
`ExternalFontCache` используется для получения пользовательских шрифтов, гарантируя их доступность для манипулирования текстом.
### Можно ли применить к обведенному тексту разные штрихи?
 Да, вы можете настроить ширину и цвет обводки с помощью`Stroke` класс и`Color` класс соответственно.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
