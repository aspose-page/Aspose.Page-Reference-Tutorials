---
date: 2026-06-30
description: Узнайте, как создать XPS document .NET и добавить image‑filled glyphs
  или foreign images с помощью Aspose.Page for .NET за несколько простых шагов.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Добавить Image Filled Glyph & Foreign Image
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Создать XPS Document .NET – Add Image Filled Glyph & Foreign Image с Aspose.Page
url: /ru/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать XPS документ .NET – Добавить глиф, заполненный изображением, и внешнее изображение с Aspose.Page

## Введение

В разработке на .NET задачи **создание XPS документа .NET** часто встречаются, когда требуется графика высокого качества, независимая от разрешения. Aspose.Page для .NET упрощает этот процесс и позволяет обогащать XPS‑файлы глифами, заполненными изображениями, или импортировать изображения из другого XPS‑документа. К концу этого руководства вы узнаете, как создать два XPS‑документа, заполнить глифы изображениями и повторно использовать эти изображения в разных документах — идеально для генерации счетов, сертификатов или любого визуально‑насыщенного вывода.

## Быстрые ответы

- **Что поддерживает Aspose.Page?** Более 25 форматов изображений и возможность обрабатывать XPS‑файлы размером до 500 МБ без полной загрузки в память.  
- **Сколько строк кода требуется для добавления глифа, заполненного изображением?** Всего две строки: создать `ImageBrush` и назначить его `Glyph`.  
- **Нужна ли лицензия для продакшн?** Да, коммерческая лицензия удаляет водяные знаки оценки.  
- **Какие версии .NET совместимы?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Можно ли повторно использовать шрифты из другого XPS?** Абсолютно — вы можете импортировать коллекцию шрифтов из первого документа во второй.

## Как создать XPS документ с помощью Aspose.Page .NET?

Загрузите библиотеку Aspose.Page, создайте экземпляр `XpsDocument`, добавьте страницу и вызовите `Save` — это полный рабочий процесс в трех лаконичных инструкциях. API автоматически обрабатывает размер страницы, DPI и управление ресурсами, поэтому вам не нужно самостоятельно управлять низкоуровневыми структурами XPS. Такой подход масштабируется от одностраничного листовки до многосотстраничных каталогов.

## Требования

Before you start, ensure you have:

- **Aspose.Page for .NET** – download it from [here](https://releases.aspose.com/page/net/).  
- **IDE для .NET** – Visual Studio, Rider или VS Code с расширением C#.  
- **Папка для ваших документов** – в примерах кода мы будем ссылаться на неё как **Your Document Directory**.

## Импорт пространств имён

The `Aspose.Page.XPS` namespace provides core XPS document classes, while `Aspose.Page.XPS.XpsModel` contains model elements such as glyphs and brushes. Import them at the top of your file:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Что такое глиф, заполненный изображением?

Глиф — это векторная форма, которую можно отрисовать сплошным цветом, градиентом или кистью изображения. При применении `ImageBrush` внутренняя часть глифа заполняется указанным изображением, позволяя создавать сложные визуальные эффекты без растрирования всей страницы.

## Шаг 1: Создать первый XPS документ

`XpsDocument` представляет пакет XPS и является точкой входа для создания и сохранения XPS‑файлов. Начните с создания первого XPS‑документа, который будет содержать глифы, заполненные изображениями.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Шаг 2: Добавить глифы в первый документ

`XpsGlyphs` определяет коллекцию глифов (символов текста), которые можно разместить на странице. Добавьте глифы в первый документ, указав шрифт, размер, стиль и позицию.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Шаг 3: Заполнить глифы кистью изображения

`ImageBrush` закрашивает область изображением, позволяя использовать узоры или картинки для заполнения форм. Заполните глифы кистью изображения, используя файл из вашего каталога данных.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Шаг 4: Создать второй XPS документ

`XpsDocument` используется для создания нового XPS‑файла, который может содержать страницы, ресурсы и контент. Теперь создайте второй XPS‑документ, который будет включать глифы из первого документа.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Шаг 5: Добавить глифы с шрифтом из первого документа

`Font` представляет типографическое семейство, используемое для отображения текста в XPS‑документе. Добавьте глифы во второй документ, используя шрифт, извлечённый из первого документа. Совместное использование коллекции шрифтов позволяет уменьшить размер файла и обеспечить визуальную согласованность.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Шаг 6: Создать кисть изображения из заполнения первого документа

`ImageBrush` можно создать из существующего заполнения, чтобы повторно использовать одно и то же изображение в разных документах. Создайте кисть изображения из заполнения первого документа и используйте её для заполнения глифов во втором документе. Эта техника «внешнего изображения» позволяет повторно использовать графику без дублирования исходного файла.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Шаг 7: Сохранить документы

`Save` записывает пакет XPS в файл, внедряя все ресурсы. Сохраните оба XPS‑документа (первый и второй) в выходную папку. Метод `Save` записывает пакет XPS, внедряя все ресурсы и сохраняет глифы, заполненные изображениями.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Распространённые проблемы и решения

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| **Изображение не отображается внутри глифа** | Кисть `ImageBrush` была создана с неверным URI или размер изображения превышает границы глифа. | Проверьте путь к изображению и при необходимости установите `ImageBrush.Stretch = Stretch.Uniform`. |
| **Шрифты отсутствуют во втором документе** | Ресурсы шрифтов не были экспортированы из первого XPS. | Вызовите `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` перед добавлением глифов. |
| **Снижение производительности при больших файлах** | Загрузка больших изображений в память для каждого глифа. | Повторно используйте один экземпляр `ImageBrush` для всех глифов или уменьшите разрешение изображения перед использованием. |

## Часто задаваемые вопросы

### Q1: Могу ли я использовать разные форматы изображений для заполнения глифов?

A1: Да, Aspose.Page поддерживает PNG, JPEG, BMP, GIF, TIFF и другие — более 25 форматов в общей сложности.

### Q2: Как я могу дополнительно настроить внешний вид глифов?

A2: Изучите свойства, такие как `Glyph.Stroke`, `Glyph.FillOpacity` и `Glyph.Transform`, чтобы настроить контуры, прозрачность и вращение.

### Q3: Подходит ли Aspose.Page для работы с большими наборами документов?

A3: Абсолютно. Библиотека обрабатывает многосотстраничные XPS‑файлы с помощью потоковой передачи, удерживая использование памяти ниже 100 МБ даже для документов из 500 страниц.

### Q4: Могу ли я применять разные стили к отдельным глифам?

A4: Да, каждый экземпляр `Glyph` имеет собственные свойства `Fill`, `Stroke` и `Transform`, позволяющие задавать стили для каждого глифа отдельно.

### Q5: Каковы преимущества использования Aspose.Page по сравнению с другими XPS‑инструментами?

A5: Aspose.Page поддерживает более 25 форматов изображений, обрабатывает файлы размером до 500 МБ без полной загрузки в память и предоставляет 100 % .NET‑нативный API — устраняя необходимость в COM‑interop или внешних инструментах.

---

**Последнее обновление:** 2026-06-30  
**Тестировано с:** Aspose.Page 24.11 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Создать XPS документ – Aspose.Page для .NET](/page/net/document-creation/)
- [Добавить изображение в XPS документ с Aspose.Page для .NET](/page/net/image-management/add-image-to-xps-document/)
- [Добавить клон глифа и изменить цвет с Aspose.Page для .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}