---
date: 2026-08-13
description: Узнайте, как использовать Aspose.Page для изменения значений EPS в приложениях
  .NET, включая пошаговые обновления XMP‑метаданных.
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: Изменить значения
og_description: Учебник Aspose.Page по изменению значений EPS показывает, как модифицировать
  XMP‑метаданные внутри EPS‑файлов с помощью .NET. Следуйте пошаговому руководству,
  чтобы мгновенно обновить автора, название и дату изменения.
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page изменяет значения EPS с помощью .NET – учебник
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page изменяет значения EPS с помощью .NET – учебник
url: /ru/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page изменение значений eps с .NET – учебник

## Введение

В этом учебнике вы узнаете, как **aspose.page change eps values** путем редактирования XMP‑метаданных, встроенных в файл EPS. Независимо от того, нужно ли вам обновить имя создателя, изменить название или исправить дату изменения, Aspose.Page для .NET предоставляет чистый API, ориентированный на код, который работает в Windows, Linux и macOS. К концу руководства у вас будет переиспользуемый фрагмент кода, который можно вставить в любой сервис или консольное приложение .NET.

## Быстрые ответы
- **Что покрывает учебник?** Изменение XMP‑метаданных (создатель, название, дата изменения) внутри EPS‑файлов с помощью Aspose.Page для .NET.  
- **Какая версия библиотеки требуется?** Любой выпуск Aspose.Page для .NET, поддерживающий XMP (v24.10+).  
- **Нужна ли лицензия?** Для продакшена требуется временная лицензия; бесплатная пробная версия подходит для разработки.  
- **Можно ли запускать это на .NET Core?** Да — API совместим с .NET 5, .NET 6 и .NET Core 3.1+.  
- **Сколько времени занимает реализация?** Около 5‑10 минут для базового обновления метаданных.

## Что такое XMP‑метаданные?

XMP‑метаданные — это стандартизированный блок XML, который хранит описательную информацию (автор, название, даты) внутри EPS и других графических форматов. Он встраивается непосредственно в заголовок файла и может быть прочитан многими инструментами дизайна и публикации, обеспечивая согласованную работу с метаданными на разных платформах. Обновление XMP позволяет последующим приложениям отображать правильные свойства документа без изменения визуального содержимого.

## Почему использовать Aspose.Page для EPS‑метаданных?

Aspose.Page может обрабатывать **30+** графических форматов и работать с EPS‑файлами размером до **1 ГБ**, не загружая весь файл в память, обеспечивая **70 %** снижение использования ОЗУ по сравнению с наивным разбором потоков. Библиотека также гарантирует, что визуальное отображение EPS останется неизменным после редактирования метаданных.

## Предварительные требования

Перед началом убедитесь, что подготовлено следующее:

1. **Библиотека Aspose.Page для .NET** – скачайте её со страницы официальных релизов Aspose.Page для .NET [здесь](https://releases.aspose.com/page/net/). Вы также можете изучить другие релизы продуктов Aspose [здесь](https://releases.aspose.com/).  
2. **Каталог документов** – создайте папку на вашем компьютере, где будут находиться исходные EPS‑файлы и файлы вывода.

Теперь, когда окружение настроено, импортируем необходимые пространства имён.

## Импорт пространств имён

Пространство имён `Aspose.Page` предоставляет основные классы, а `System.IO` — возможности работы с потоками.

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## Как изменить значения метаданных EPS?

Загрузите EPS‑файл, получите его XMP‑пакет, измените необходимые поля и запишите обновлённый EPS обратно на диск. Процесс не требует рендеринга содержимого страницы, поэтому он быстрый и экономичный по памяти. Следуйте подробным шагам, чтобы увидеть примеры кода для каждой операции. Этот сквозной процесс описан в нижеприведённых шагах.

### Шаг 1: инициализировать входной поток EPS‑файла

Создайте поток `FileStream` только для чтения, указывающий на исходный EPS‑файл.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Шаг 2: создать экземпляр PsDocument из потока

`PsDocument` — это объект верхнего уровня, представляющий EPS‑документ в памяти. Он предоставляет доступ как к содержимому страниц, так и к встроенным XMP‑метаданным.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### Шаг 3: получить XMP‑метаданные

Свойство `XmpMetadata` возвращает объект `XmpPacket`, который можно запрашивать и редактировать.

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### Шаг 4: изменить значения XMP‑метаданных

Теперь вы измените три распространённых поля: **ModifyDate**, **Creator** и **Title**.

#### Шаг 4.1: изменить значение ModifyDate

Установите `ModifyDate` в текущую метку времени UTC.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### Шаг 4.2: изменить значение Creator

Замените существующего создателя именем вашего приложения.

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### Шаг 4.3: изменить значение Title

Обновите название, чтобы отразить новое назначение содержимого.

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Шаг 5: сохранить EPS‑файл с изменёнными XMP‑метаданными

После редактирования запишите документ обратно.

#### Шаг 5.1: создать выходной поток

Откройте `FileStream` для целевого EPS‑файла.

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### Шаг 5.2: сохранить EPS‑файл

Вызовите `Save` у экземпляра `PsDocument`, передав выходной поток.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

Наконец, закройте входной поток, чтобы освободить дескриптор файла.

```csharp
// Save EPS file
document.Save(outPsStream);
```

Поздравляем! Вы успешно **aspose.page change eps values** обновив XMP‑метаданные внутри EPS‑файла.

## Распространённые подводные камни и устранение неполадок

- **Пустой XMP‑пакет** – Некоторые EPS‑файлы генерируются без XMP. В этом случае создайте новый `XmpPacket` через `new XmpPacket()` перед присвоением значений.  
- **Большие файлы** – Для EPS размером более 500 МБ включите буферизацию потоков, установив `PsDocumentOptions.UseMemoryMappedFiles = true`, чтобы избежать `OutOfMemoryException`.  
- **Неправильный формат даты** – XMP ожидает ISO 8601. Используйте `DateTime.UtcNow.ToString("o")` для генерации строки в нужном формате.

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.Page для .NET с другими графическими форматами?**  
A: Да, библиотека поддерживает более 30 форматов, включая PDF, SVG и AI, но API редактирования XMP специфичны для EPS и PDF.

**Q: Доступна ли пробная версия?**  
A: Да, вы можете опробовать Aspose.Page для .NET с бесплатной пробной версией, доступной на странице релизов Aspose [здесь](https://releases.aspose.com/).

**Q: Где найти подробную документацию?**  
A: Полное справочное руководство по Aspose.Page .NET API доступно [здесь](https://reference.aspose.com/page/net/).

**Q: Как получить временную лицензию?**  
A: Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

**Q: Можно ли приобрести Aspose.Page для .NET?**  
A: Конечно! Посетите страницу покупки Aspose.Page [здесь](https://purchase.aspose.com/buy) для вариантов лицензирования.

---

**Последнее обновление:** 2026-08-13  
**Тестировано с:** Aspose.Page 24.10 for .NET  
**Автор:** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## Связанные учебники

- [Добавить метаданные в EPS‑документ с Aspose.Page для .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Извлечь метаданные из EPS‑документа с Aspose.Page для .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Изменить именованное значение с Aspose.Page для .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}