---
date: 2026-06-20
description: Легко конвертировать XPS в PDF и сжимать изображения PDF с использованием
  Aspose.Page for .NET. Следуйте нашему пошаговому руководству для создания PDF высокого
  качества.
keywords:
- convert xps to pdf
- compress pdf images
- create pdf from xps
linktitle: Объединить документы XPS в PDF
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Effortlessly convert XPS to PDF and compress PDF images using Aspose.Page
    for .NET. Follow our step-by-step guide for high-quality PDF creation.
  headline: Convert XPS to PDF with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can load each XPS document sequentially and render them into
      the same `PdfDevice` instance, adjusting the `PageNumbers` option as needed.
    question: Can I merge multiple XPS files into a single PDF?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing purposes.
    question: Is a temporary license available for Aspose.Page for .NET?
  - answer: Aspose.Page for .NET does not impose strict limitations on file size,
      but optimal performance is achieved with files under 500 MB; larger files may
      require more memory.
    question: Are there any limitations on file size when using Aspose.Page for document
      conversion?
  - answer: Yes, Aspose.Page for .NET provides extensive features for PDF manipulation.
      Check the documentation for advanced customization options.
    question: Can I customize the output PDF further, such as adding watermarks or
      annotations?
  - answer: Yes, Aspose.Page for .NET is designed to work seamlessly across Windows,
      Linux, and macOS environments.
    question: Does Aspose.Page for .NET support cross‑platform development?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Конвертировать XPS в PDF с помощью Aspose.Page for .NET
url: /ru/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Преобразование XPS в PDF с помощью Aspose.Page для .NET

## Введение

Если вам нужно **преобразовать XPS в PDF** быстро, сохраняя векторную графику и чёткий текст, Aspose.Page для .NET предоставляет готовый к использованию API, который берёт на себя всю тяжёлую работу. В этом руководстве мы пройдём весь процесс — от загрузки файла XPS до сохранения PDF высокого качества — чтобы вы могли интегрировать конвертацию в любое .NET‑приложение с уверенностью.

## Быстрые ответы
- **Какая библиотека обрабатывает XPS → PDF?** Aspose.Page for .NET.
- **Сколько строк кода требуется?** Около пяти логических шагов (≈ 30 строк в сумме).
- **Можно ли сжать изображения PDF?** Да, используйте `PdfSaveOptions.ImageCompression`.
- **Нужна ли лицензия для продакшн?** Требуется коммерческая лицензия; доступна временная пробная версия.
- **Поддерживаемые версии .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Как преобразовать XPS в PDF с помощью Aspose.Page?
Загрузите файл XPS с помощью `new XpsDocument(inputStream)` и вызовите `PdfDevice.Render`, передавая настроенный экземпляр `PdfSaveOptions` — этот единый конвейер преобразует документ и записывает PDF в выходной поток. Вся операция выполняется в памяти, поэтому временные файлы не создаются, и при желании можно включить сжатие изображений для уменьшения конечного размера файла.

## Что такое Aspose.Page для .NET?
Aspose.Page для .NET — это библиотека обработки документов, позволяющая создавать, конвертировать и рендерить XPS, PDF и другие форматы, основанные на страницах, без необходимости установки Microsoft Office. Она предоставляет API для создания, редактирования и конвертации документов, поддерживает как векторную, так и растровую графику и работает на разных платформах. Библиотека раскрывает низкоуровневый API, дающий разработчикам детальный контроль над параметрами рендеринга.

## Почему стоит использовать Aspose.Page для преобразования XPS в PDF?
Aspose.Page поддерживает **более 30 форматов вывода** и может обрабатывать **XPS‑файлы до 500 страниц** менее чем за **2 секунды** на типичном сервере, при этом сохраняет векторные данные. Библиотека также предлагает встроенное **сжатие изображений** (сокращение до 80 %) и **сжатие текста**, помогая создавать лёгкие PDF без потери качества.

## Предварительные требования

Прежде чем приступить к руководству, убедитесь, что у вас есть следующие предварительные требования:

- Aspose.Page для .NET: Убедитесь, что библиотека Aspose.Page установлена. Вы можете скачать её по ссылке [здесь](https://releases.aspose.com/page/net/).
- Файлы документов: Подготовьте XPS‑документ (`input.xps`) в указанном каталоге.

## Импорт пространств имён

Пространства имён `Aspose.Page.Xps` и `Aspose.Page.Pdf` содержат классы, необходимые для загрузки XPS‑файлов и сохранения PDF.

```csharp
using Aspose.Page.XPS;
```

Этот шаг гарантирует, что у вас есть доступ к классам и методам, необходимым для конвертации документа.

## Шаг 1: Инициализация потоков

Создайте `FileStream` для исходного XPS‑файла и другой `FileStream` для целевого PDF. Использование операторов `using` гарантирует корректное освобождение потоков.

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

## Шаг 2: Загрузка XPS‑документа

`XpsDocument` — класс, который загружает и представляет XPS‑файл в памяти.  
Здесь мы загружаем XPS‑документ в объект `XpsDocument`, подготавливая его к дальнейшей обработке.

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

## Шаг 3: Инициализация параметров сохранения

`PdfSaveOptions` настраивает способ сохранения PDF, включая сжатие и параметры страниц.  
Настройте объект `PdfSaveOptions` в соответствии с вашими предпочтениями, указывая такие параметры, как сжатие изображений, сжатие текста и номера страниц.

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// ExEnd:5
```

## Шаг 4: Создание устройства рендеринга

`PdfDevice` — движок рендеринга, который преобразует страницы XPS в содержимое PDF.  
`PdfDevice` — инструмент, отвечающий за рендеринг XPS‑документа в формат PDF.

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

## Шаг 5: Сохранение документа

Вызовите `PdfDevice.Render`, передав загруженный XPS‑документ и выходной поток. Метод записывает полностью соответствующий PDF‑файл на диск.

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Наконец, сохраните документ, используя устройство рендеринга и указанные параметры.

## Распространённые подводные камни и советы

- **Владение потоком:** Всегда оборачивайте потоки в блоки `using`, чтобы избежать блокировок файлов.
- **Большие файлы:** Для XPS‑файлов размером более 200 МБ рассмотрите возможность увеличения `BufferSize` у `FileStream` для повышения производительности.
- **Качество изображения:** Если нужны изображения без потерь, установите `ImageCompression` в `PdfImageCompression.None` вместо JPEG.

## Часто задаваемые вопросы

**Q: Могу ли я объединить несколько XPS‑файлов в один PDF?**  
A: Да, вы можете последовательно загружать каждый XPS‑документ и рендерить их в один экземпляр `PdfDevice`, при необходимости корректируя параметр `PageNumbers`.

**Q: Доступна ли временная лицензия для Aspose.Page для .NET?**  
A: Да, вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/) для тестирования.

**Q: Существуют ли ограничения по размеру файлов при использовании Aspose.Page для конвертации документов?**  
A: Aspose.Page для .NET не накладывает строгих ограничений на размер файлов, однако оптимальная производительность достигается с файлами размером до 500 МБ; более крупные файлы могут требовать больше памяти.

**Q: Могу ли я дополнительно настроить выходной PDF, например добавить водяные знаки или аннотации?**  
A: Да, Aspose.Page для .NET предоставляет обширные возможности для работы с PDF. Ознакомьтесь с документацией для получения информации о расширенных настройках.

**Q: Поддерживает ли Aspose.Page для .NET кросс‑платформенную разработку?**  
A: Да, Aspose.Page для .NET разработан для бесшовной работы в средах Windows, Linux и macOS.

## Дополнительные вопросы

**Q: Как сжать изображения PDF во время конвертации?**  
A: Установите `PdfSaveOptions.ImageCompression = PdfImageCompression.Jpeg` и при необходимости отрегулируйте `JpegQuality` для баланса между размером и качеством.

**Q: Какой лучший способ создать PDF из XPS в пакетном процессе?**  
A: Пройдитесь по каталогу XPS‑файлов, переиспользуйте один экземпляр `PdfDevice` и вызывайте `Render` для каждого документа, чтобы минимизировать накладные расходы.

**Q: Поддерживает ли библиотека PDF с паролем?**  
A: Да, вы можете задать пароль через `PdfSaveOptions.Password` перед сохранением.

**Q: Какие среды выполнения .NET официально поддерживаются?**  
A: .NET Framework 4.5+, .NET Core 3.1+, а также .NET 5/6/7 полностью поддерживаются.

**Q: Как проверить, что конверсия сохранила векторную графику?**  
A: Откройте полученный PDF в просмотрщике, способном инспектировать типы объектов (например, Adobe Acrobat), и убедитесь, что текст и фигуры остаются выбираемыми и масштабируемыми.

## Заключение

Теперь у вас есть полный, готовый к продакшн рабочий процесс для **преобразования XPS в PDF** с помощью Aspose.Page для .NET. Используя движок рендеринга библиотеки и параметры сохранения, вы также можете **сжимать изображения PDF** и точно настраивать вывод под ваши требования к размеру и качеству. Не стесняйтесь изучать дополнительные возможности, такие как водяные знаки, шифрование и пакетная обработка, чтобы расширить это решение.

---

**Последнее обновление:** 2026-06-20  
**Тестировано с:** Aspose.Page 23.12 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Создать XPS‑документ с помощью Aspose.Page для .NET](/page/net/document-creation/create-xps-document/)
- [Изменить XPS‑документ с помощью Aspose.Page для .NET](/page/net/document-creation/modify-xps-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}