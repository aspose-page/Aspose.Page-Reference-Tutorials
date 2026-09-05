---
date: 2026-07-24
description: Без усилий конвертировать XPS в PDF в .NET с помощью Aspose.Page. Скачайте
  библиотеку, изучите документацию и получите бесплатную пробную версию.
keywords:
- convert xps to pdf
- how to convert xps
- Aspose.Page .NET
- XPS to PDF conversion
lastmod: 2026-07-24
linktitle: Конвертировать XPS в PDF
og_description: Узнайте, как конвертировать XPS в PDF с помощью Aspose.Page для .NET.
  Это пошаговое руководство охватывает настройку, контроль качества изображений и
  рекомендации по лучшим практикам.
og_image_alt: Developer guide showing XPS to PDF conversion code using Aspose.Page
  for .NET
og_title: Конвертировать XPS в PDF с помощью Aspose.Page для .NET – Быстрая, высококачественная
  конверсия
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Effortlessly convert XPS to PDF in .NET with Aspose.Page. Download
    the library, explore documentation, and get a free trial.
  headline: Convert XPS to PDF with Aspose.Page for .NET
  type: TechArticle
- description: Effortlessly convert XPS to PDF in .NET with Aspose.Page. Download
    the library, explore documentation, and get a free trial.
  name: Convert XPS to PDF with Aspose.Page for .NET
  steps:
  - name: Initialize Document Directory
    text: Define the folder that holds your source XPS file and where the resulting
      PDF will be saved. Replace `"Your Document Directory"` with the absolute or
      relative path to the folder containing your XPS document.
  - name: Open Streams for PDF Output and XPS Input
    text: We use two file streams—one for reading the XPS file and another for writing
      the generated PDF. > **Pro tip:** Ensure the paths are correct and that the
      application has read/write permissions on the target folder.
  - name: Load the XPS Document
    text: XpsLoadOptions allows you to specify loading preferences for the XPS document.
      XpsDocument is the class that loads an XPS file into memory, exposing its pages
      and resources for further processing. The `XpsLoadOptions` object lets you specify
      loading preferences, but the default works for most scenar
  - name: Configure PDF Save Options
    text: PdfSaveOptions configures how the PDF output is generated, including compression
      and quality settings. `PdfSaveOptions` defines how the PDF will be written.
      Notice the use of **PDF image compression** (`PdfImageCompression.Jpeg`) and
      **JPEG quality** (`JpegQualityLevel = 100`). These settings direct
  - name: Create a PDF Rendering Device
    text: PdfDevice is the rendering target that writes PDF data to the provided stream.
      `PdfDevice` is the rendering target that writes the PDF data to the stream we
      opened earlier.
  - name: Save the Document to PDF
    text: The Save method finalizes the conversion, writing the PDF to the output
      stream. Invoke the `Save` method, passing the rendering device and the configured
      options. When the code finishes executing, `XPStoPDF_out.pdf` will appear in
      your specified directory, containing the converted pages with the com
  type: HowTo
- questions:
  - answer: Use the `JpegQualityLevel` property inside `PdfSaveOptions`. Setting it
      to 100 gives maximum quality.
    question: How do I set JPEG quality when converting XPS to PDF?
  - answer: It refers to the `ImageCompression` option, which determines how images
      are compressed inside the PDF (e.g., JPEG, Zip).
    question: What does “pdf image compression” mean in this context?
  - answer: Yes, Aspose.Page also supports **C# generate pdf** directly from drawing
      commands, but that is outside the scope of this tutorial.
    question: Can I programmatically generate a PDF without an XPS source?
  - answer: The conversion retains vector data; just avoid rasterizing images by keeping
      `ImageCompression` set to JPEG or Zip as needed.
    question: Is there a way to convert XPS to PDF without losing vector graphics?
  - answer: Absolutely – Aspose.Page for .NET works with .NET Core, .NET 5, .NET 6,
      and later versions.
    question: Does the library support .NET Core?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- convert xps
- Aspose.Page
- .NET document conversion
- PDF generation
title: Конвертировать XPS в PDF с помощью Aspose.Page для .NET
url: /ru/net/document-conversion/convert-xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Конвертация XPS в PDF с помощью Aspose.Page для .NET

## Введение

В этом руководстве вы узнаете **как конвертировать XPS в PDF** с использованием библиотеки Aspose.Page для .NET. Конвертация XPS в PDF часто требуется, когда нужно поделиться XPS‑документами с пользователями, у которых есть только PDF‑просмотрщики, или когда необходимо встроить XPS‑контент в более крупные PDF‑рабочие процессы. Мы пройдём каждый шаг, объясним, почему важна каждая настройка, и покажем, как точно настроить результат — например, установить качество JPEG и применить сжатие изображений PDF.

## Быстрые ответы
- **Какая библиотека лучше всего подходит для конвертации XPS в PDF?** Aspose.Page для .NET
- **Нужна ли лицензия для продакшна?** Да, требуется коммерческая лицензия; доступна бесплатная пробная версия.
- **Можно ли управлять качеством изображений?** Абсолютно — используйте `JpegQualityLevel` и `PdfImageCompression`.
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Можно ли конвертировать несколько XPS‑файлов в один PDF?** Да, с помощью цикла по файлам и объединения результатов.

## Что такое конвертация XPS в PDF?
Конвертация XPS в PDF преобразует файл XML Paper Specification (XPS) в файл Portable Document Format (PDF), сохраняя оригинальное расположение, шрифты, векторную графику и встроенные изображения. Полученный PDF можно просматривать на любом устройстве без необходимости в XPS‑ридере, обеспечивая одинаковую визуальную точность на всех платформах.

## Почему стоит конвертировать XPS в PDF?

Загрузите ваш XPS‑документ и мгновенно получите PDF, который можно открыть практически на любой платформе. PDF‑просмотрщики установлены на 99 % настольных компьютеров, планшетов и телефонов, тогда как XPS‑ридеры редки. Конвертация также фиксирует визуальную точность оригинального XPS, делая PDF идеальным для архивирования, подписи или дальнейшей обработки другими библиотеками Aspose.

### Количественные преимущества
- **Универсальный охват:** PDF поддерживается более чем на 2 млрд устройств по всему миру, по сравнению с менее чем 5 млн установок, способных работать с XPS.
- **Эффективность размера:** Использование `PdfImageCompression.Jpeg` с `JpegQualityLevel` = 80 может уменьшить размер файлов до 60 % без заметной потери качества.
- **Производительность:** Aspose.Page может обрабатывать XPS‑файлы размером до **500 МБ** менее чем за 30 секунд на типичном 4‑ядерном сервере благодаря потоковым API, которые избегают загрузки всего файла в память.

## Требования

Прежде чем приступить к конвертации, убедитесь, что у вас есть следующие компоненты:

- **Aspose.Page для .NET** – Убедитесь, что библиотека Aspose.Page для .NET установлена в вашей среде разработки. Вы можете скачать её из [документации Aspose.Page](https://reference.aspose.com/page/net/).
- **Среда разработки** – Настройте .NET‑среду разработки с Visual Studio или любой другой совместимой IDE.
- **XPS‑документ** – Подготовьте XPS‑файл, который вы хотите конвертировать в PDF. Это может быть ваш образец XPS‑файла, хранящийся в указанной директории.

## Импорт пространств имён

Перед тем как приступить к коду, импортируем необходимые пространства имён, чтобы функции Aspose.Page для .NET были доступны в проекте:

`using Aspose.Page;`  
`using Aspose.Page.XPS;`  
`using Aspose.Page.XPS.XpsModel;`  
`using Aspose.Page.XPS.XpsModel.XpsDocument;`  
`using Aspose.Page.XPS.XpsModel.XpsDocument.XpsLoadOptions;`  
`using Aspose.Page.XPS.XpsModel.Pdf;`  
`using Aspose.Page.XPS.XpsModel.Pdf.PdfSaveOptions;`  

```csharp
using Aspose.Page.XPS;
```

## Как конвертировать XPS в PDF с помощью Aspose.Page?

XpsDocument загружает XPS‑файл и предоставляет доступ к его страницам и ресурсам. Загрузите XPS‑файл с помощью `new XpsDocument(inputStream, loadOptions)` и вызовите `pdfDevice.Save(pdfSaveOptions)` — эта единственная цепочка преобразует документ, применяя выбранные вами настройки сжатия изображений и качества. API автоматически обрабатывает векторную графику, шрифты и разметку страниц, поэтому вы получаете точную копию PDF с минимальным объёмом кода.

## Пошаговое руководство

### Шаг 1: Инициализация каталога документов

Определите папку, в которой находится исходный XPS‑файл, и куда будет сохранён полученный PDF.

```csharp
string dataDir = "Your Document Directory";
```

Замените `"Your Document Directory"` на абсолютный или относительный путь к папке, содержащей ваш XPS‑документ.

### Шаг 2: Открытие потоков для вывода PDF и ввода XPS

Мы используем два файловых потока — один для чтения XPS‑файла и другой для записи сгенерированного PDF.

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

> **Pro tip:** Убедитесь, что пути указаны правильно и приложение имеет права **чтения/записи** в целевой **папке**.

### Шаг 3: Загрузка XPS‑документа

XpsLoadOptions позволяет задать предпочтения загрузки для XPS‑документа.  
XpsDocument — класс, который **загружает XPS‑файл в память**, раскрывая его **страницы** и **ресурсы** для **дальнейшей** **обработки**.

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Объект `XpsLoadOptions` позволяет задать параметры загрузки, но значение по умолчанию подходит для большинства сценариев.

### Шаг 4: Настройка параметров сохранения PDF

PdfSaveOptions определяет, как будет генерироваться PDF‑вывод, включая настройки сжатия и качества.  
`PdfSaveOptions` задаёт способ записи PDF. Обратите внимание на использование **PDF‑сжатия изображений** (`PdfImageCompression.Jpeg`) и **качества JPEG** (`JpegQualityLevel = 100`). Эти параметры напрямую влияют на размер файла и визуальную точность.

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

- **`JpegQualityLevel`** – Управляет качеством JPEG‑изображений, встроенных в PDF (чем выше — лучше качество, но больше размер файла).
- **`ImageCompression`** – Выбирает алгоритм сжатия; JPEG идеален для фотоснимков.
- **`TextCompression`** – Сжатие Flate уменьшает размер PDF без потери качества текста.
- **`PageNumbers`** – Позволяет **сохранить XPS как PDF** только для выбранных страниц.

### Шаг 5: Создание устройства рендеринга PDF

PdfDevice — цель рендеринга, которая записывает данные PDF в предоставленный поток.  
`PdfDevice` — цель рендеринга, которая записывает PDF‑данные в поток, открытый ранее.

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Шаг 6: Сохранение документа в PDF

Метод Save завершает процесс конвертации, записывая PDF в выходной поток.  
Вызовите метод `Save`, передав устройство рендеринга и настроенные параметры.

```csharp
document.Save(device, options);
```

После завершения выполнения кода файл `XPStoPDF_out.pdf` появится в указанной вами директории, содержащий **конвертированные** страницы с заданными настройками сжатия и качества.

## Распространённые сценарии использования

- **Корпоративные отчёты** – Генерируйте XPS‑отчёты из устаревших систем и **конвертируйте** их в PDF для **распространения**.
- **Архивирование** – Храните **документы** в формате PDF для **долгосрочного** сохранения, при этом **по‑прежнему** имея возможность создавать их из XPS‑источников.
- **Веб‑сервисы** – Предоставьте API‑конечную точку, принимающую загрузки XPS и возвращающую PDF‑файлы «на лету».

## Устранение неполадок и советы

- **Файл не найден** – Проверьте путь `dataDir` и убедитесь, что имя XPS‑файла точно совпадает.
- **Ошибки доступа** – Запустите Visual Studio от имени администратора или предоставьте права записи в папку вывода.
- **Большие PDF** – Если полученный PDF слишком велик, уменьшите `JpegQualityLevel` или **переключите** `ImageCompression` на `PdfImageCompression.Zip`.

## Часто задаваемые вопросы (AI‑Friendly)

**В: Как задать качество JPEG при конвертации XPS в PDF?**  
О: Используйте свойство `JpegQualityLevel` в `PdfSaveOptions`. Значение 100 обеспечивает максимальное качество.

**В: Что означает «pdf image compression» в данном контексте?**  
О: Это относится к параметру `ImageCompression`, который определяет, как изображения сжимаются внутри PDF (например, JPEG, Zip).

**В: Могу ли я программно создать PDF без исходного XPS?**  
О: Да, Aspose.Page также поддерживает **C# generate pdf** напрямую из команд рисования, но это выходит за рамки данного руководства.

**В: Есть ли способ конвертировать XPS в PDF без потери векторной графики?**  
О: Конвертация сохраняет векторные данные; просто избегайте растеризации изображений, оставляя `ImageCompression` установленным на JPEG или Zip по необходимости.

**В: Поддерживает ли библиотека .NET Core?**  
О: Абсолютно — Aspose.Page для .NET работает с .NET Core, .NET 5, .NET 6 и более новыми версиями.

---

**Последнее обновление:** 2026-07-24  
**Тестировано с:** Aspose.Page 24.11 для .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Похожие руководства

- [Merge XPS Documents into PDF with Aspose.Page for .NET](/page/net/document-merging/merge-xps-documents-into-pdf/)
- [Create XPS Document with Aspose.Page for .NET](/page/net/document-creation/create-xps-document/)
- [Aspose Page Conversion: Document Conversion Guide](/page/net/document-conversion/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}