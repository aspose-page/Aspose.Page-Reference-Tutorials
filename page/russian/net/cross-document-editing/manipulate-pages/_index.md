---
date: 2026-07-24
description: Узнайте, как объединять XPS‑документы с Aspose.Page for .NET. Этот пошаговый
  гид показывает техники манипуляции страницами для эффективных результатов.
keywords:
- merge xps documents
- how to merge xps
- asp page .net tutorial
lastmod: 2026-07-24
linktitle: Манипулировать страницами
og_description: Эффективно объединяйте XPS‑документы с помощью Aspose.Page for .NET.
  Это руководство проведёт вас через объединение, вставку и удаление страниц с понятными
  примерами кода.
og_image_alt: Guide showing how to merge XPS documents using Aspose.Page in a .NET
  application
og_title: Объединение XPS‑документов с Aspose.Page for .NET – Быстрая манипуляция
  страницами
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Learn how to merge XPS documents with Aspose.Page for .NET. This step‑by‑step
    guide shows page manipulation techniques for efficient results.
  headline: Merge XPS Documents with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to merge XPS documents with Aspose.Page for .NET. This step‑by‑step
    guide shows page manipulation techniques for efficient results.
  name: Merge XPS Documents with Aspose.Page for .NET
  steps:
  - name: '**InsertPage(1, doc2.Page, false)** – places the first page of `doc2` at
      position 1 in `doc4`.'
    text: '**InsertPage(1, doc2.Page, false)** – places the first page of `doc2` at
      position 1 in `doc4`.'
  - name: '**AddPage(doc3.Page, false)** – appends the first page of `doc3` to the
      end of `doc4`.'
    text: '**AddPage(doc3.Page, false)** – appends the first page of `doc3` to the
      end of `doc4`.'
  - name: '**RemovePageAt(2)** – removes the page now at index 2 (useful for eliminating
      unwanted pages).'
    text: '**RemovePageAt(2)** – removes the page now at index 2 (useful for eliminating
      unwanted pages).'
  - name: '**InsertPage(2, doc1.SelectActivePage(3), false)** – inserts the third
      page of `doc1` into position 2, completing the merge.'
    text: '**InsertPage(2, doc1.SelectActivePage(3), false)** – inserts the third
      page of `doc1` into position 2, completing the merge.'
  type: HowTo
- questions:
  - answer: Absolutely. Create additional `XpsDocument` instances and use `InsertPage`
      or `AddPage` repeatedly to build a larger merged document.
    question: Can I merge more than three XPS files?
  - answer: Yes. Aspose.Page copies the page content byte‑for‑byte, so text, images,
      and vector graphics remain unchanged.
    question: Does the merge preserve original formatting and graphics?
  - answer: Use `AddPage(sourcePage, false)` which appends the page to the document’s
      end.
    question: How do I insert a page at the end without specifying an index?
  - answer: The API is fully headless; you can run the same code in ASP.NET, Azure
      Functions, or any server‑side .NET environment.
    question: Is it possible to merge XPS documents on a server without a UI?
  - answer: Aspose.Page currently does not support encrypted XPS files; you must decrypt
      them before merging.
    question: What if my XPS files are password‑protected?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- merge xps
- Aspose.Page
- .NET XPS manipulation
- document merging
- C# XPS processing
title: Объединение XPS‑документов с Aspose.Page for .NET
url: /ru/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Объединение XPS-документов с помощью Aspose.Page для .NET

## Введение

В этом руководстве вы узнаете, как **merge XPS documents** и управлять их страницами с помощью библиотеки Aspose.Page в среде .NET. Независимо от того, нужно ли вам объединить несколько отчетов в один XPS‑файл, переупорядочить страницы для получения отшлифованного результата или удалить нежелательные разделы, это руководство проведет вас через весь процесс с понятными, разговорными объяснениями и готовыми к запуску фрагментами кода.

## Быстрые ответы
- **What can I do with Aspose.Page?** Объединять XPS документы, вставлять, добавлять или удалять страницы и сохранять результат.  
- **Do I need a license for testing?** Временная лицензия доступна для оценки.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Is Visual Studio required?** Нет, любой IDE, поддерживающий C#, подходит, но рекомендуется Visual Studio.  
- **How long does the merge take?** Обычно несколько секунд для XPS файлов стандартного размера.

## Что такое объединение XPS-документов?

Объединение XPS документов означает взятие страниц из двух или более существующих XPS‑файлов и их комбинирование в один XPS‑документ. Такой подход позволяет создавать консолидированные отчёты, собирать много‑главные руководства или готовить пакеты для печати без конвертации в другой формат, экономя время и место.

## Почему использовать Aspose.Page для .NET?

Aspose.Page предлагает **pure .NET API**, который работает напрямую с XPS‑файлами — без необходимости во внешних инструментах или сторонних компонентах. Он предоставляет детальный контроль над порядком страниц, точками вставки и сохранением содержимого, делая процесс объединения надёжным и быстрым. Библиотека поддерживает **30+ XPS manipulation methods** и может обрабатывать документы до **500 pages** без загрузки всего файла в память, обеспечивая производительность корпоративного уровня.

## Требования

- **Aspose.Page for .NET** – загрузите из [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).  
- **Development Environment** – Visual Studio, Rider или любой IDE, поддерживающий C#.  
- **Input XPS Files** – три примерных файла (`input1.xps`, `input2.xps`, `input3.xps`), размещённые в известной папке.

## Импорт пространств имён

Эти пространства имён предоставляют доступ к основным классам XPS‑документов, моделям страниц и базовым утилитам рисования.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Шаг 1: Установите каталог документов

Замените **Your Document Directory** полным путём к папке, где хранятся ваши XPS‑файлы, например, `C:\\Docs\\XpsFiles\\`.

```csharp
string dataDir = "Your Document Directory";
```

## Шаг 2: Создайте экземпляры XPS‑документов

Класс `XpsDocument` представляет отдельный XPS‑файл и предоставляет методы для чтения, редактирования и сохранения его страниц.

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2` и `doc3` представляют исходные документы, которые вы хотите объединить.  
- `doc4` — пустой XPS‑документ, который будет содержать результат объединения.

## Шаг 3: Вставка, добавление и удаление страниц

Метод `InsertPage` вставляет исходную страницу в указанную позицию целевого XPS‑документа.  
Метод `AddPage` добавляет исходную страницу в конец целевого документа.  
Метод `RemovePageAt` удаляет страницу по заданному нулевому индексу.  
Метод `SelectActivePage` получает конкретную страницу из исходного документа для дальнейших операций.

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

Вот что делает каждая строка:

1. **InsertPage(1, doc2.Page, false)** – помещает первую страницу `doc2` на позицию 1 в `doc4`.  
2. **AddPage(doc3.Page, false)** – добавляет первую страницу `doc3` в конец `doc4`.  
3. **RemovePageAt(2)** – удаляет страницу, находящуюся сейчас под индексом 2 (полезно для удаления нежелательных страниц).  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – вставляет третью страницу `doc1` в позицию 2, завершая объединение.

Эти операции демонстрируют, как можно **merge XPS documents**, переупорядочивая или удаляя страницы по необходимости.

## Шаг 4: Сохраните объединённый документ

Метод `Save` записывает структуру XPS из памяти в физический файл.

```csharp
doc4.Save(dataDir + "out.xps");
```

Итоговый объединённый XPS‑файл (`out.xps`) записывается в тот же каталог. Теперь вы можете открыть его в любом XPS‑просмотрщике или дальше обрабатывать с помощью Aspose.Page.

## Распространённые проблемы и решения
- **File not found** – дважды проверьте путь `dataDir` и убедитесь, что входные файлы существуют.  
- **Invalid page index** – индексы страниц начинаются с 1; попытка вставить несуществующую страницу вызывает исключение.  
- **License errors** – используйте временную или полную лицензию перед развертыванием в продакшн.

## Часто задаваемые вопросы

**Q: Can I merge more than three XPS files?**  
A: Конечно. Создайте дополнительные экземпляры `XpsDocument` и используйте `InsertPage` или `AddPage` многократно, чтобы собрать более крупный объединённый документ.

**Q: Does the merge preserve original formatting and graphics?**  
A: Да. Aspose.Page копирует содержимое страницы байт‑за‑байтом, поэтому текст, изображения и векторная графика остаются неизменными.

**Q: How do I insert a page at the end without specifying an index?**  
A: Используйте `AddPage(sourcePage, false)`, который добавляет страницу в конец документа.

**Q: Is it possible to merge XPS documents on a server without a UI?**  
A: API полностью безголовый; вы можете запускать тот же код в ASP.NET, Azure Functions или любой серверной .NET‑среде.

**Q: What if my XPS files are password‑protected?**  
A: Aspose.Page в текущей версии не поддерживает зашифрованные XPS‑файлы; их необходимо расшифровать перед объединением.

---

**Последнее обновление:** 2026-07-24  
**Тестировано с:** Aspose.Page for .NET 24.10  
**Автор:** Aspose

## Связанные руководства

- [Создать XPS документ – Aspose.Page for .NET](/page/net/document-creation/create-xps-document/)
- [Добавить страницу в XPS документ с помощью Aspose.Page for .NET](/page/net/page-manipulation/add-page-to-xps-document/)
- [Объединить XPS документы в PDF с помощью Aspose.Page for .NET](/page/net/document-merging/merge-xps-documents-into-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}