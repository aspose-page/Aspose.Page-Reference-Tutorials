---
title: 使用 Aspose.Page 将文本添加到 PostScript (PS) 文档
linktitle: 将文本添加到 PostScript (PS) 文档
second_title: Aspose.Page .NET API
description: 通过学习使用 Aspose.Page 将文本添加到 PostScript (PS) 文档来增强您的 .NET 开发技能。探索分步示例并释放文档操作的力量。
type: docs
weight: 10
url: /zh/net/text-manipulation/add-text-to-postscript-ps-document/
---
## 介绍

在 .NET 开发的动态世界中，操作和增强 PostScript (PS) 文档是一项常见要求。 Aspose.Page for .NET 提供了一组强大的工具，可以轻松地将文本添加到您的 PS 文档中。本教程将指导您完成整个过程，确保您可以将此功能无缝集成到您的项目中。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

-  Aspose.Page for .NET：确保您已将 Aspose.Page 库集成到您的 .NET 项目中。您可以从[Aspose.Page .NET 文档](https://reference.aspose.com/page/net/).

- 文档目录：设置存储文档的目录。在示例中这将被称为“您的文档目录”。

- 字体文件夹：创建一个文件夹来存储自定义字体，在示例中称为“您的文档目录”。

## 导入命名空间

在开始之前，请确保在您的项目中包含必要的命名空间：

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

现在，让我们将该示例分解为多个步骤。

## 第1步：为PS文档创建输出流

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## 第2步：用系统字体填充文本

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

## 第 3 步：使用自定义字体填充文本

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## 步骤 4：使用系统字体勾勒文本轮廓

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

## 第 5 步：使用自定义字体勾勒文本轮廓

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

## 第 6 步：关闭并保存

```csharp
document.ClosePage();
document.Save();
}
```

## 结论

恭喜！您已成功学习如何使用 Aspose.Page for .NET 将文本添加到 PostScript (PS) 文档。请随意探索更多功能并增强您的文档操作能力。

## 常见问题解答

### Q1：我可以将 Aspose.Page 与其他 .NET 库一起使用吗？

A1：是的，Aspose.Page 与其他 .NET 库无缝集成，为文档操作提供了多功能环境。

### Q2：自定义字体对于此过程至关重要吗？

A2：虽然您可以使用系统字体，但合并自定义字体可以提供更大的灵活性和设计选择。

### Q3：Aspose.Page适合大规模文档处理吗？

A3：当然！ Aspose.Page 旨在高效、可靠地处理大规模文档。

### Q4：PS文档中的文字位置可以修改吗？

A4：当然！调整提供的示例中的坐标以更改添加文本的位置。

### Q5：我可以在哪里寻求 Aspose.Page 相关查询的帮助？

 A5：访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)与社区联系并寻求专家建议。