---
date: 2026-03-21
description: Узнайте, как создавать PostScript‑документы на C# с Unicode‑текстом,
  используя Aspose.Page для .NET — быстрый способ улучшить работу с документами.
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: Создать документ PostScript на C# с Unicode‑текстом – Aspose.Page
url: /ru/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить текст с Unicode‑строкой в PostScript (PS) с помощью Aspose.Page

## Introduction

Если вам нужно **создать документ PostScript C#** и встроить Unicode‑символы, Aspose.Page для .NET делает процесс простым. В этом руководстве мы пошагово рассмотрим полный пример, показывающий, как добавить японский текст (или любую Unicode‑строку) в файл PS, выбрать пользовательский шрифт и сохранить результат. В конце у вас будет переиспользуемый фрагмент кода, который можно вставить в любой проект C#.

## Quick Answers
- **О чём этот учебник?** Добавление Unicode‑текста в файл PostScript с использованием Aspose.Page в C#.
- **Какая библиотека требуется?** Aspose.Page для .NET (последняя версия).
- **Нужен ли специальный шрифт?** Любой TrueType/OpenType шрифт, поддерживающий нужный диапазон Unicode, например *Arial Unicode MS*.
- **Сколько строк кода?** Около 30 строк, разбитых на понятные шаги.
- **Нужна ли лицензия?** Временная лицензия подходит для оценки; полная лицензия требуется для продакшн.

## What is “create postscript document c#”?

Создание документа PostScript в C# означает программную генерацию файла .ps, соответствующего спецификациям языка PostScript. Aspose.Page абстрагирует низкоуровневые детали, позволяя сосредоточиться на содержимом, таком как текст, графика и шрифты.

## Why use Aspose.Page for Unicode text?
- **Полная поддержка Unicode** – отображение символов любого языка без ручного кодирования.
- **Независимость от устройства** – один и тот же код работает для вывода в PS, EPS и PDF.
- **Отсутствие внешних зависимостей** – библиотека самостоятельно загружает шрифты и сопоставляет глифы.

## Prerequisites

- Базовые знания C# и разработки на .NET.
- Библиотека Aspose.Page для .NET установлена. Вы можете скачать её из [документации Aspose.Page для .NET](https://reference.aspose.com/page/net/).
- Папка, содержащая шрифты, которые вы планируете использовать (например, *Arial Unicode MS*).

## Import Namespaces

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up Document Directory and Fonts Folder

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Step 2: Create Output Stream for PostScript Document

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## Step 3: Add Unicode Text with Custom Font

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Step 4: Close the Current Page

```csharp
document.ClosePage();
```

## Step 5: Finalize and Save the Document

```csharp
document.Save();
```

## Common Issues and Solutions

- **Шрифт не найден** – Убедитесь, что путь `AdditionalFontsFolders` указывает на папку с файлами .ttf/.otf и что имя шрифта указано точно.
- **Неправильные символы** – Проверьте, что исходная строка закодирована в UTF‑8 в вашем C# файле (при необходимости используйте `#pragma warning disable 1591`).
- **Файл не создан** – Проверьте права записи в `dataDir` и корректность освобождения потока (это делает блок `using`).

## Frequently Asked Questions

**В: Можно ли использовать Aspose.Page для .NET с другими языками программирования?**  
**О:** Aspose.Page в первую очередь предназначен для .NET, но существуют эквиваленты для Java.

**В: Как получить временную лицензию для Aspose.Page для .NET?**  
**О:** Перейдите по ссылке [Temporary License](https://purchase.aspose.com/temporary-license/) для получения временной лицензии.

**В: Есть ли форум сообщества для обсуждения Aspose.Page?**  
**О:** Да, посетите [форум Aspose.Page](https://forum.aspose.com/c/page/39) для поддержки сообщества.

**В: С какими форматами работает Aspose.Page для .NET?**  
**О:** Aspose.Page поддерживает различные форматы, включая XPS, PS, EPS, PDF и другие.

**В: Можно ли настроить внешний вид добавленного текста?**  
**О:** Да, вы можете настроить шрифт, размер, цвет и другие свойства текста в Aspose.Page.

## Conclusion

В этом руководстве мы продемонстрировали, как **создать документ PostScript C#** и встроить Unicode‑текст с помощью Aspose.Page. Следуя приведённым шагам, вы сможете быстро интегрировать многоязычное отображение текста в любое .NET‑приложение, получив полный контроль над генерацией и разметкой документов.

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}