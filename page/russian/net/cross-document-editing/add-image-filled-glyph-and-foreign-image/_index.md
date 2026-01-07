---
date: 2026-01-07
description: Узнайте, как создавать XPS‑документы в .NET с помощью Aspose.Page. Это
  руководство показывает, как добавлять глифы, заполненные изображениями, и внешние
  изображения для более насыщенной визуализации документа.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Создание XPS‑документа в .NET с Aspose.Page – глиф, заполненный изображением,
  и внешнее изображение
url: /ru/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание XPS документа .NET с Aspose.Page – Глиф, заполненный изображением, и внешнее изображение

## Введение

Если вам нужно **create XPS document .NET** приложения, которые выглядят отшлифованными и профессиональными, Aspose.Page предоставляет инструменты для встраивания изображений непосредственно в глифы и повторного использования графических ресурсов в разных документах. В этом руководстве мы пройдем процесс создания двух XPS файлов, заполнения глифов кистью изображения и последующего повторного использования этой кисти во втором документе. К концу вы поймёте, почему такой подход экономит память, упрощает стилизацию и открывает творческие возможности для отчетов, счетов‑фактур или любого печатного контента.

## Быстрые ответы

- **What does this tutorial cover?** Добавление глифов, заполненных изображением, и их повторное использование в XPS документах с Aspose.Page для .NET.  
- **Which primary keyword is targeted?** `create xps document .net`.  
- **Prerequisites?** Среда разработки .NET, Aspose.Page для .NET и папка для ваших XPS файлов.  
- **How long does implementation take?** Около 10‑15 минут для работающего прототипа.  
- **Can I use other image formats?** Да — любой формат, поддерживаемый `System.Drawing.Image` в .NET.

## Требования

Прежде чем погрузиться в код, убедитесь, что у вас готово следующее:

- **Aspose.Page for .NET** – download the latest library from [here](https://releases.aspose.com/page/net/).  
- **Development Environment** – Visual Studio 2022 (or any IDE that supports .NET 6+).  
- **Document Directory** – create a folder on your machine that will hold the input images and the generated XPS files; we’ll refer to it as **Your Document Directory** in the snippets.

## Импорт пространств имён

Start by pulling in the namespaces required to work with XPS objects and drawing utilities.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Пошаговое руководство

### Шаг 1: Создать первый XPS документ

We begin by instantiating an empty XPS document that will host the image‑filled glyph.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Шаг 2: Добавить глифы в первый документ

Next, add a glyph (a text character) that we’ll later fill with an image brush.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Шаг 3: Заполнить глифы кистью изображения

Here we create an `ImageBrush` from a TIFF file located in our data directory and apply it to the glyph. The brush is set to tile mode so the image repeats if the glyph area exceeds the image size.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Шаг 4: Создать второй XPS документ

Now we spin up a second XPS document that will reuse the glyph style and image brush from the first one.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Шаг 5: Добавить глифы с шрифтом из первого документа

We add a glyph to the second document, re‑using the exact font object from the first document. This ensures visual consistency across both files.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Шаг 6: Создать кисть изображения из заполнения первого документа

Instead of loading the image again, we clone the brush from `glyphs1` and assign it to `glyphs2`. This demonstrates how you can **create XPS document .NET** workflows that share resources efficiently.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Шаг 7: Сохранить документы

Finally, persist both XPS files to the disk. You can now open them with any XPS viewer to see the image‑filled glyph effect.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Почему использовать глифы, заполненные изображением, при создании XPS документа .NET?

- **Visual Impact** – Преобразовать обычный текст в графически насыщенные элементы без растеризации всей страницы.  
- **Resource Reuse** – Делить кисти и шрифты между несколькими документами, уменьшая потребление памяти.  
- **Flexibility** – Плитка, растягивание или вращение кисти изображения для создания пользовательских узоров или фирменного стиля.

## Распространённые проблемы и советы

- **File Path Errors** – Ensure `dataDir` ends with a path separator (`\` or `/`) appropriate for your OS.  
- **Unsupported Image Formats** – Aspose.Page works best with TIFF, PNG, and JPEG. Convert other formats before use.  
- **TileMode Not Applied** – Verify you cast to `XpsImageBrush` before setting `TileMode`; otherwise the property is ignored.

## Часто задаваемые вопросы

### Q1: Можно ли использовать разные форматы изображений для заполнения глифов?

**A:** Yes, Aspose.Page supports TIFF, PNG, JPEG, BMP, and GIF. Just provide the correct file extension in the `CreateImageBrush` call.

### Q2: Как можно дальше настроить внешний вид глифов?

**A:** Explore additional properties on `XpsGlyphs` such as `Opacity`, `RenderTransform`, and `Stroke` to fine‑tune rendering.

### Q3: Подходит ли Aspose.Page для работы с большими наборами документов?

**A:** Absolutely. The library is optimized for high‑performance scenarios and can process thousands of XPS files in batch jobs.

### Q4: Можно ли применить разные стили к отдельным глифам?

**A:** Yes. Each `XpsGlyphs` instance can have its own fill, stroke, and transformation, giving you granular control.

### Q5: Каковы преимущества использования Aspose.Page по сравнению с другими инструментами обработки документов?

**A:** Aspose.Page offers a complete, license‑free API for XPS creation, manipulation, and conversion, with extensive documentation and 24/7 support.

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}