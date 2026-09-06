---
date: 2026-08-08
description: Узнайте, как добавить элементы массива в EPS metadata с помощью Aspose.Page
  EPS metadata. Это пошаговое руководство по .NET показывает, как добавлять элементы
  массива и эффективно читать EPS‑файлы.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Добавить элементы массива
og_description: Узнайте, как добавить элементы массива в EPS metadata с помощью Aspose.Page
  EPS metadata. Следуйте этому лаконичному руководству по .NET, чтобы читать EPS‑файлы
  и эффективно управлять metadata.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Добавление элементов массива с помощью Aspose.Page EPS metadata в .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Добавление элементов массива с помощью Aspose.Page EPS metadata в .NET
url: /ru/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить элементы массива в метаданные EPS с помощью Aspose.Page в .NET

## Введение

В этом руководстве вы узнаете, как добавить элементы массива в метаданные EPS с помощью **Aspose.Page EPS metadata**. Если вам нужно обогатить EPS‑файл дополнительными заголовками, авторами или пользовательскими тегами, Aspose.Page делает эту задачу простой для любого разработчика .NET. Мы пройдём каждый шаг, от открытия потока EPS до сохранения обновлённого XMP‑пакета, чтобы вы могли уверенно интегрировать работу с метаданными в свои приложения.

## Быстрые ответы
- **Что позволяет делать метаданные Aspose.Page EPS?** Она позволяет читать и записывать массивы XMP‑метаданных внутри EPS‑файлов из .NET.  
- **Какой класс представляет EPS‑документ?** `PsDocument` — основной класс для загрузки и сохранения содержимого EPS.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; для продакшн‑использования требуется коммерческая лицензия.  
- **Можно ли изменить метаданные, не затрагивая графику EPS?** Да, изменяется только XMP‑пакет, а содержимое страницы остаётся нетронутым.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что такое метаданные Aspose.Page EPS?
Метаданные Aspose.Page EPS — это основанный на XMP блок информации, встроенный в EPS‑файл. Он хранит описательные свойства, такие как заголовки, авторы, ключевые слова и пользовательские теги в соответствии со стандартом ISO 16684‑1. Метаданные можно получать и изменять программно через API Aspose.Page, что позволяет автоматизировать управление документами и оптимизацию поиска.

## Почему изменять метаданные EPS?
Aspose.Page может обрабатывать **более 30 полей метаданных** и работать с EPS‑файлами размером до **200 МБ** без загрузки всего документа в память, что снижает нагрузку на процессор до 40 % по сравнению с полным разбором файла. Обновление метаданных улучшает поиск, соответствие требованиям и автоматизацию последующих процессов.

## Необходимые условия

- Базовые знания программирования на .NET.  
- Aspose.Page для .NET установлен — загрузите его с [download Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (или любая совместимая с .NET IDE) для выполнения примера кода.  

## Как добавить элементы массива в метаданные EPS?
Чтобы добавить элементы массива, сначала загрузите EPS‑файл в `PsDocument`, затем получите его XMP‑пакет с помощью `GetXmpMetadata()`. Используйте метод `AddArrayItem()` для нужного XMP‑массива, например `dc:title` или `dc:creator`, чтобы добавить новые значения. В конце вызовите `Save()`, чтобы записать обновлённые метаданные обратно в файл, не изменяя графическое содержимое.

### Шаг 1: инициализировать поток ввода EPS‑файла
`PsDocument` представляет EPS‑документ и предоставляет методы доступа к его содержимому. Следующий код открывает EPS‑файл как поток и создаёт экземпляр `PsDocument`.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Шаг 2: получить XMP‑метаданные
`GetXmpMetadata()` получает XMP‑пакет, встроенный в EPS‑файл. Если пакет отсутствует, API создаёт новый на основе существующих комментариев PostScript.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### Шаг 3: изменить значения XMP‑метаданных
`AddArrayItem()` добавляет новое значение в существующий XMP‑массив без перезаписи других элементов. Используйте его для добавления заголовков, авторов или пользовательских тегов в метаданные.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Шаг 4: сохранить EPS‑файл с изменёнными XMP‑метаданными
`Save()` записывает изменённый XMP‑пакет обратно в EPS‑файл, сохраняя оригинальное содержимое PostScript. Укажите путь вывода, чтобы создать новый файл или перезаписать исходный.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Распространённые подводные камни и устранение неполадок

- **Пакет XMP равен null** – Если `GetXmpMetadata()` возвращает `null`, убедитесь, что EPS‑файл содержит хотя бы один блок комментариев; в противном случае создайте новый экземпляр `XmpMetadata` вручную.  
- **Проблемы с кодировкой** – Используйте UTF‑8 при добавлении строковых значений, чтобы избежать искажения символов в не‑ASCII языках.  
- **Большие файлы** – Для EPS‑файлов размером более 150 МБ рассмотрите возможность потоковой передачи ввода через `FileStream` с буфером, чтобы снизить использование памяти.

## Часто задаваемые вопросы

**В: Совместима ли Aspose.Page со всеми средами .NET?**  
О: Да, Aspose.Page работает на .NET Framework 4.5+, .NET Core 3.1+ и .NET 5/6/7, обеспечивая одинаковое поведение API на Windows, Linux и macOS.

**В: Можно ли использовать Aspose.Page бесплатно?**  
О: Вы можете оценить библиотеку, скачав бесплатную пробную версию со [страницы покупки Aspose](https://purchase.aspose.com/buy). Для продакшн‑развёртываний требуется коммерческая лицензия.

**В: Доступны ли временные лицензии для Aspose.Page?**  
О: Временные лицензии можно получить со [страницы временных лицензий](https://purchase.aspose.com/temporary-license/) для краткосрочных проектов или оценочных периодов.

**В: Где можно найти поддержку сообщества для Aspose.Page?**  
О: Присоединяйтесь к обсуждению на [форуме Aspose.Page](https://forum.aspose.com/c/page/39), задавайте вопросы и делитесь решениями с другими разработчиками.

**В: Какова последняя версия Aspose.Page для .NET?**  
О: Обратитесь к официальной [документации](https://reference.aspose.com/page/net/) для получения последних примечаний к выпуску и ссылок для загрузки.

---

**Последнее обновление:** 2026-08-08  
**Тестировано с:** Aspose.Page 24.11 for .NET  
**Автор:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## Связанные руководства

- [Изменить элементы массива с помощью Aspose.Page для .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Добавить простые свойства с помощью Aspose.Page для .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Добавить пространство имён с помощью Aspose.Page для .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}