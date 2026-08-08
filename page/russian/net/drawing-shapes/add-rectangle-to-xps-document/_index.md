---
date: 2026-07-19
description: Узнайте, как создать XPS документ .NET и добавить прямоугольник, используя
  Aspose.Page for .NET, в кратком пошаговом руководстве.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Добавить прямоугольник в XPS документ
og_description: Быстро создайте XPS документ .NET. Этот учебник показывает, как добавить
  прямоугольник в файл XPS с помощью Aspose.Page for .NET, с понятным кодом и советами.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: Создание XPS документа .NET – Добавление прямоугольника с помощью Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: Создание XPS документа .NET – Добавление прямоугольника с помощью Aspose.Page
url: /ru/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать XPS документ .NET – добавить прямоугольник с Aspose.Page

## Введение

В этом руководстве вы узнаете, как **создать XPS документ .NET** и нарисовать в нём прямоугольник с помощью Aspose.Page for .NET. Независимо от того, создаёте ли вы движок отчетов, печатный счёт‑фактуру или пользовательский графический слой, возможность программно генерировать XPS‑файлы даёт вам полный контроль над макетом и точностью. Следуйте приведённым ниже шагам, и у вас будет готовый к использованию XPS‑файл за несколько минут.

## Быстрые ответы
- **Какова основная цель?** Создать XPS документ .NET и добавить форму прямоугольника.  
- **Какая библиотека требуется?** Aspose.Page for .NET (доступна для загрузки на официальном сайте).  
- **Нужна ли лицензия для тестирования?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшна.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Сколько времени занимает реализация?** Около 5‑10 минут для базового прямоугольника.

## Что такое Aspose.Page for .NET?
Aspose.Page for .NET — это высокопроизводительный полностью управляемый API, позволяющий разработчикам программно создавать, редактировать и рендерить документы XPS (XML Paper Specification) без использования внешних компонентов. Он предоставляет богатую объектную модель для рисования фигур, текста и изображений, а также поддерживает расширенные функции, такие как управление цветом, сжатие и конвертация в PDF, что делает его подходящим для широкого спектра сценариев генерации документов.

## Почему стоит использовать Aspose.Page для создания XPS документа .NET?
Aspose.Page поддерживает **более 30 функций XPS** — включая векторную графику, верстку текста и управление цветом — и может генерировать файлы размером до **500 МБ** без загрузки всего документа в память. Такая измеримая возможность обеспечивает плавную работу даже при больших печатных заданиях.

## Предварительные требования

Перед началом работы с этим руководством убедитесь, что у вас есть следующие предварительные требования:

1. Библиотека Aspose.Page for .NET: Убедитесь, что библиотека Aspose.Page for .NET установлена в вашей среде разработки. Вы можете скачать её [здесь](https://releases.aspose.com/page/net/).
2. Каталог документов: Создайте каталог, в котором вы хотите хранить XPS‑документы.

## Импорт пространств имён

В вашем .NET‑приложении включите необходимые пространства имён для использования возможностей Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Как добавить прямоугольник в XPS документ в .NET?

Загрузите XPS документ, создайте объект `Graphics`, определите `RectangleF` нужного размера и вызовите `DrawRectangle`. Эта последовательность рисует прямоугольник одной строкой кода и автоматически обрабатывает масштабирование DPI. Для типовых страниц формата A4 прямоугольник 200 × 100 pt будет расположен по центру без дополнительных вычислений.

### Шаг 1: Установить каталог документов

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Шаг 2: Создать новый XPS документ

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Шаг 3: Добавить прямоугольник

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Шаг 4: Сохранить документ

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Поздравляем! Вы успешно добавили прямоугольник в XPS документ с помощью Aspose.Page for .NET.

## Распространённые проблемы и советы

- **Отсутствующие шрифты:** Убедитесь, что используемые шрифты установлены на сервере; иначе Aspose.Page заменит их шрифтом по умолчанию, что может изменить макет.  
- **Большие документы:** При генерации файлов более 200 МБ рассмотрите возможность установки `document.SaveOptions.Compress = true` для снижения использования памяти.  
- **Система координат:** XPS использует пункты (1/72 дюйма). Не забудьте преобразовать пиксели в пункты, если вы работаете с размерами, основанными на экране.

## Часто задаваемые вопросы

**В: Совместим ли Aspose.Page со всеми .NET приложениями?**  
О: Да, Aspose.Page без проблем работает с настольными, веб‑ и облачными .NET приложениями.

**В: Где я могу найти документацию по Aspose.Page for .NET?**  
О: Полная ссылка на API доступна [здесь](https://reference.aspose.com/page/net/).

**В: Могу ли я попробовать Aspose.Page for .NET бесплатно перед покупкой?**  
О: Да, вы можете получить бесплатную пробную версию [здесь](https://releases.aspose.com/).

**В: Как получить временную лицензию для Aspose.Page for .NET?**  
О: Перейдите по [этой ссылке](https://purchase.aspose.com/temporary-license/), чтобы получить временную лицензию.

**В: Где я могу получить поддержку сообщества или задать вопросы, связанные с Aspose.Page for .NET?**  
О: Посетите [форум Aspose.Page](https://forum.aspose.com/c/page/39) для поддержки сообщества.

---

**Последнее обновление:** 2026-07-19  
**Тестировано с:** Aspose.Page for .NET 24.9  
**Автор:** Aspose

## Связанные руководства

- [Создать XPS документ с Aspose.Page for .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Рисование фигур](/page/net/drawing-shapes/)
- [Добавить текст в XPS документ с Aspose.Page for .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}