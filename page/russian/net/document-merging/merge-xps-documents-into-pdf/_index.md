---
date: 2026-01-20
description: Легко добавляйте номера страниц в PDF при объединении XPS‑документов
  в PDF высокого качества с помощью Aspose.Page для .NET. Следуйте нашему пошаговому
  руководству по конвертации XPS в PDF.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: Добавить номера страниц в PDF – объединить XPS в PDF с помощью Aspose.Page
url: /ru/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить номера страниц в PDF – Объединить XPS в PDF с помощью Aspose.Page

## Introduction

Если вам нужно **добавить номера страниц в PDF** при объединении файлов XPS, Aspose.Page for .NET делает процесс простым. В этом руководстве мы пройдем полный, готовый к продакшну пример, который преобразует документ XPS в PDF высокого качества, позволяет управлять сжатием изображений и автоматически вставляет номера страниц в итоговый PDF. К концу у вас будет переиспользуемый фрагмент кода, который можно добавить в любой проект C#.

## Quick Answers
- **Могу ли я добавить номера страниц при объединении XPS в PDF?** Да — свойство `PdfSaveOptions.PageNumbers` делает именно это.  
- **Какая библиотека обрабатывает конвертацию?** Aspose.Page for .NET.  
- **Нужна ли лицензия для использования в продакшене?** Требуется действующая лицензия Aspose.Page; временная лицензия доступна для тестирования.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, и .NET 5/6+.  
- **Можно ли получить изображения высокого качества?** Конечно — установите `JpegQualityLevel` в 100 и выберите `PdfImageCompression.Jpeg`.

## Prerequisites

Прежде чем приступить к руководству, убедитесь, что у вас есть следующие предварительные требования:

- Aspose.Page for .NET: Убедитесь, что библиотека Aspose.Page установлена. Вы можете скачать её [здесь](https://releases.aspose.com/page/net/).
- Document Files: Подготовьте XPS‑документ (`input.xps`) в указанной директории.

## Import Namespaces

В вашем проекте .NET включите необходимые пространства имён для работы с Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Этот шаг гарантирует, что у вас есть доступ к классам и методам, необходимым для конвертации документа.

## How to add page numbers PDF when merging XPS documents

`Коллекция PdfSaveOptions.PageNumbers` позволяет точно указать, какие страницы (или диапазоны страниц) должны появиться в результирующем PDF. Заполнив её нужными номерами страниц, Aspose.Page автоматически вставит правильную нумерацию.

### Step 1: Initialize Streams

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Этот шаг включает настройку входных и выходных потоков для файлов XPS и PDF. Убедитесь, что указаны правильные пути и имена файлов.

### Step 2: Load XPS Document

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Здесь мы загружаем XPS‑документ в объект `XpsDocument`, подготавливая его к дальнейшей обработке.

### Step 3: Initialize Save Options (merge xps to pdf)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Настройте объект `PdfSaveOptions` в соответствии с вашими предпочтениями, указывая параметры, такие как сжатие изображений, сжатие текста и **номера страниц**, которые должны появиться в итоговом PDF. Установка `JpegQualityLevel` в 100 обеспечивает **изображения PDF высокого качества**.

### Step 4: Create Rendering Device

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice` — это инструмент, отвечающий за рендеринг XPS‑документа в формат PDF.

### Step 5: Save the Document (c# xps to pdf)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Наконец, сохраните документ, используя устройство рендеринга и указанные параметры. Выходной PDF будет содержать выбранные страницы с автоматически добавленными номерами страниц.

## Why use Aspose.Page for this conversion?

- **Надёжность** — Обрабатывает сложные функции XPS без потери точности.  
- **Производительность** — Обработка на основе потоков избегает загрузки целых файлов в память.  
- **Гибкость** — Тонкий контроль над качеством изображений, сжатием и нумерацией страниц.  
- **Кроссплатформенность** — Работает на Windows, Linux и macOS с .NET Core.

## Common Issues and Solutions

| Проблема | Решение |
|----------|---------|
| **PDF пустой** | Убедитесь, что путь к файлу XPS указан правильно и файл не повреждён. |
| **Номера страниц не отображаются** | Убедитесь, что `PageNumbers` установлен с правильными нулевыми индексами страниц (например, `new int[] {1,2,6}`). |
| **Изображения низкого качества** | Увеличьте `JpegQualityLevel` и выберите `PdfImageCompression.Jpeg`. |
| **Большие файлы XPS вызывают нагрузку на память** | Обрабатывайте XPS небольшими частями или увеличьте лимит памяти приложения. |

## Frequently Asked Questions

### Q1: Can I merge multiple XPS files into a single PDF?

A1: Да, можете. Просто скорректируйте параметр `PageNumbers` в `PdfSaveOptions`, чтобы включить нужные страницы из разных файлов XPS, либо загрузите каждый XPS последовательно и вызовите `document.Save` на том же `PdfDevice`.

### Q2: Is a temporary license available for Aspose.Page for .NET?

A2: Да, вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/) для тестовых целей.

### Q3: Are there any limitations on file size when using Aspose.Page for document conversion?

A3: Aspose.Page for .NET не накладывает строгих ограничений на размер файлов, однако оптимальная производительность достигается при работе с файлом разумного размера. Для очень больших XPS‑документов рекомендуется обрабатывать их потоками, чтобы снизить потребление памяти.

### Q4: Can I customize the output PDF further, such as adding watermarks or annotations?

A4: Да, Aspose.Page for .NET предоставляет обширные возможности для работы с PDF. После конвертации вы можете использовать библиотеку Aspose.PDF для добавления водяных знаков, аннотаций или других улучшений.

### Q5: Does Aspose.Page for .NET support cross‑platform development?

A5: Да, Aspose.Page for .NET разработан для бесшовной работы на различных платформах, включая Windows, Linux и macOS, при использовании с .NET Core или .NET 5/6.

---

**Последнее обновление:** 2026-01-20  
**Тестировано с:** Aspose.Page 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}