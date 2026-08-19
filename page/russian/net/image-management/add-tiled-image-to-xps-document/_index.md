---
date: 2026-03-03
description: Узнайте, как использовать Aspose.Page для .NET для мозаичного размещения
  изображений в XPS‑документах. Это пошаговое руководство показывает, как эффективно
  размещать изображения в виде мозаики и улучшать визуальную привлекательность.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Как использовать Aspose.Page для добавления мозаичного изображения в документ
  XPS
url: /ru/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать Aspose.Page для добавления мозаичного изображения в документ XPS

## Introduction

Если вы задаётесь вопросом **как использовать Aspose**, чтобы придать вашим файлам XPS более богатый визуальный стиль, вы попали в нужное место. В этом руководстве мы пройдём по точным шагам, необходимым для **мозаичного размещения изображения** внутри документа XPS с помощью Aspose.Page для .NET. К концу вы получите переиспользуемый фрагмент кода, который можно вставить в любой .NET‑проект для создания мозаичных графических изображений на лету.

## Quick Answers
- **What library is needed?** Aspose.Page for .NET  
- **Which method creates the tiled brush?** `CreateImageBrush` with `TileMode = XpsTileMode.Tile`  
- **Can I control opacity?** Yes – set `path.Fill.Opacity` (e.g., 0.5f)  
- **Do I need a license for testing?** A temporary license works for evaluation; a full license is required for production.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## What is Aspose.Page and Why Tile Images?

Aspose.Page — мощный API, позволяющий разработчикам генерировать, редактировать и рендерить XPS, PDF и другие форматы, основанные на страницах, без зависимости от Microsoft Office. Мозаичное изображение — повторение битмапа по форме — помогает заполнять большие области узорами, водяными знаками или текстурами фона, сохраняя небольшой размер файла.

## How to Use Aspose.Page to Tile Images in XPS Documents

Ниже вы найдёте полностью готовый к запуску пример. Каждый шаг объясняется простым языком перед соответствующим блоком кода, чтобы вы понимали **почему** каждая строка важна.

### Prerequisites

- **Aspose.Page for .NET** – download and reference the library from the official site [here](https://reference.aspose.com/page/net/).  
- **Development environment** – Visual Studio (any edition) or another .NET IDE you prefer.

### Import Namespaces

Сначала импортируем необходимые пространства имён, чтобы компилятор знал, где находятся классы XPS.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Step 1: Define the Document Directory

Укажите, где будет находиться сгенерированный файл XPS и исходное изображение. Замените заполнитель реальной папкой на вашем компьютере.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Step 2: Create a New XPS Document

Создайте пустой документ XPS, который будет содержать мозаичную графику.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Step 3: Add a Tiled Image

Здесь мы создаём прямоугольный путь, заполняем его `ImageBrush` и устанавливаем режим мозаики для кисти. Свойство `TileMode` указывает движку повторять изображение как по горизонтали, так и по вертикали. При необходимости скорректируйте координаты прямоугольника или исходное изображение под ваш сценарий.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Step 4: Save the Resultant XPS Document

Наконец, сохраняем документ на диск. Полученный файл можно открыть в любом просмотрщике XPS или дальше обрабатывать с помощью Aspose.Page.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Common Issues & Tips

- **Path errors** – Ensure `dataDir` ends with a trailing slash or use `Path.Combine` to avoid missing‑separator problems.  
- **Image size mismatches** – The source image should be large enough for the tiling area; otherwise the pattern may appear stretched.  
- **Opacity not visible** – Some viewers ignore opacity on XPS; test with a viewer that fully supports XPS rendering (e.g., XPS Viewer on Windows).

## Frequently Asked Questions

### Q1: Is Aspose.Page compatible with all .NET development environments?
A: Yes, Aspose.Page works with Visual Studio, Rider, VS Code, and any IDE that supports .NET.

### Q2: Can I adjust the opacity of the tiled image?
A: Absolutely. The example sets `path.Fill.Opacity = 0.5f;`—you can change the float value between 0 (transparent) and 1 (opaque).

### Q3: Are there other tile modes available in Aspose.Page for .NET?
A: Yes. Besides `XpsTileMode.Tile`, you can use `FlipX`, `FlipY`, and `FlipXY` to create mirrored patterns.

### Q4: How do I handle temporary licenses for Aspose.Page?
A: Refer to the [temporary license](https://purchase.aspose.com/temporary-license/) page on the Aspose website for details on obtaining and applying a trial license.

### Q5: Where can I seek help or connect with the Aspose.Page community?
A: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to ask questions, share snippets, and learn from other developers.

### Q6: Can I use this approach to create a watermark effect?
A: Yes. By lowering the opacity and choosing a semi‑transparent image, the tiled brush works perfectly as a repeating watermark.

## Conclusion

Теперь вы знаете **как использовать Aspose** для добавления мозаичного изображения в документ XPS, управления его непрозрачностью и сохранения результата для дальнейшего использования. Эта техника идеальна для фоновых узоров, водяных знаков или любой ситуации, когда повторяющаяся графика добавляет визуальный интерес без увеличения размера файла. Не стесняйтесь экспериментировать с различными формами, изображениями и режимами мозаики, чтобы подобрать оптимальное решение для вашего проекта.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Page for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}