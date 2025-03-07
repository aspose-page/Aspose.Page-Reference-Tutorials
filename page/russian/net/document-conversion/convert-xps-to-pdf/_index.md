---
title: Конвертируйте XPS в PDF с помощью Aspose.Page для .NET
linktitle: Конвертировать XPS в PDF
second_title: Aspose.Page .NET API
description: Легко конвертируйте XPS в PDF в .NET с помощью Aspose.Page. Загрузите библиотеку, изучите документацию и получите бесплатную пробную версию.
weight: 11
url: /ru/net/document-conversion/convert-xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Конвертируйте XPS в PDF с помощью Aspose.Page для .NET

## Введение

В этом уроке мы углубимся в процесс преобразования документов XPS (спецификация бумаги XML) в PDF (портативный формат документов) с использованием мощной библиотеки Aspose.Page для .NET. Aspose.Page для .NET предоставляет надежный набор функций для работы с файлами XPS, позволяя разработчикам легко конвертировать их в формат PDF с различными вариантами настройки.

## Предварительные условия

Прежде чем мы отправимся в путь конверсии, убедитесь, что у вас есть следующие предварительные условия:

-  Библиотека Aspose.Page для .NET: убедитесь, что в вашей среде разработки установлена библиотека Aspose.Page для .NET. Вы можете скачать его с сайта[Документация Aspose.Page](https://reference.aspose.com/page/net/).

- Среда разработки: настройте среду разработки .NET с помощью Visual Studio или любой другой совместимой IDE.

- Документ XPS: подготовьте документ XPS, который вы хотите преобразовать в PDF. Это может быть образец файла XPS, хранящийся в указанном каталоге.

## Импортировать пространства имен

Прежде чем углубиться в код, давайте импортируем необходимые пространства имен, чтобы сделать функции Aspose.Page for .NET доступными в нашем коде:

```csharp
using Aspose.Page.XPS;
```

## Шаг 1. Инициализация каталога документов

```csharp
string dataDir = "Your Document Directory";
```

Замените «Каталог вашего документа» на путь к каталогу, содержащему ваш документ XPS.

## Шаг 2. Инициализация потоков PDF и XPS

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Откройте потоки как для выходного файла PDF, так и для входного файла XPS. Убедитесь, что у вас установлены соответствующие пути к файлам.

## Шаг 3. Загрузите документ XPS

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Загрузите документ XPS, используя библиотеку Aspose.Page для .NET.

## Шаг 4. Инициализируйте параметры сохранения PDF-файла

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

Настройте параметры сохранения PDF, включая такие параметры, как уровень качества JPEG, сжатие изображений, сжатие текста и включение определенных номеров страниц.

## Шаг 5. Создайте устройство рендеринга PDF

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Создайте устройство рендеринга для формата PDF, используя библиотеку Aspose.Page для .NET.

## Шаг 6. Сохраните документ в PDF

```csharp
document.Save(device, options);
```

Сохраните документ XPS в PDF, используя указанное устройство и параметры рендеринга.

## Заключение

Поздравляем! Вы успешно преобразовали документ XPS в PDF с помощью Aspose.Page для .NET. Эта универсальная библиотека предоставляет разработчикам мощный набор инструментов для легкой обработки документов различных форматов.

## Часто задаваемые вопросы

### Вопрос 1. Могу ли я преобразовать несколько файлов XPS в один PDF с помощью Aspose.Page для .NET?

О1: Да, вы можете просмотреть несколько файлов XPS и выполнить те же действия, чтобы объединить их в один PDF-файл.

### Вопрос 2. Поддерживаются ли Aspose.Page для .NET другие форматы вывода?

О2: Да, Aspose.Page для .NET поддерживает различные форматы вывода, включая TIFF, JPEG, PNG и другие.

### Вопрос 3. Как настроить внешний вид преобразованного PDF-документа?

A3: Вы можете настроить параметры объекта параметров, такие как сжатие изображения и сжатие текста, для достижения желаемого внешнего вида.

### Вопрос 4: Существует ли пробная версия Aspose.Page для .NET?

 О4: Да, вы можете изучить возможности Aspose.Page для .NET, получив бесплатную пробную версию на сайте[здесь](https://releases.aspose.com/).

### Вопрос 5: Где я могу получить поддержку сообщества для Aspose.Page для .NET?

 A5: Посетите[Форум Aspose.Page](https://forum.aspose.com/c/page/39) для общественных обсуждений и поддержки.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
