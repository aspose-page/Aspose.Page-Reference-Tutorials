---
date: 2026-03-21
description: 学习如何使用 Aspose.Page for .NET 填充文本并向 PS 文档添加文本。提供代码示例的分步指南。
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page 在 PostScript (PS) 文档中填充文本
url: /zh/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 PostScript (PS) 文档中填充文本 使用 Aspose.Page

## 介绍

如果您需要在 PostScript (PS) 文件中 **how to fill text**，Aspose.Page for .NET 可以轻松实现。无论是生成报告、发票还是自定义图形，添加和样式化文本都是核心需求。在本教程中，我们将完整演示整个过程——从环境设置到保存最终的 PS 文档——让您能够在 .NET 应用程序中自信地向 PS 文件添加文本。

## 快速答案
- **What does “fill text” mean?** 它使用实心画刷渲染字符，将字形直接绘制到页面上。  
- **Can I use custom fonts?** 是的——Aspose.Page 通过 `add custom font ps` 功能支持自定义字体。  
- **How do I save the PS document?** 在关闭页面后调用 `document.Save()`；这会将文件写入磁盘（`save ps document`）。  
- **Is “fill and stroke text” supported?** 当然支持；使用 `FillAndStrokeText` 可同时应用填充和描边。  
- **What .NET versions are required?** 任何 .NET Framework 4.5 以上或 .NET Core/5/6 以上的运行时均可。

## 在 PS 文档中，“how to fill text” 是什么？

填充文本是指使用实色（或画刷）绘制字符而不带轮廓。在 PostScript 中，这相当于 `fill` 操作符。Aspose.Page 将其抽象为易于使用的方法，如 `FillText` 和 `FillAndStrokeText`。

## 为什么使用 Aspose.Page 添加 custom font ps？

- **Full font support** – 系统字体和外部 TrueType/OpenType 字体开箱即用。  
- **Precise positioning** – 您可以控制 X/Y 坐标、大小和样式。  
- **Rich styling** – 结合填充、描边和笔来实现诸如 “fill and stroke text” 的效果。  
- **Cross‑platform** – 在 Windows、Linux 和 macOS 上使用相同的 API 工作。

## 先决条件

在开始之前，请确保您拥有：

- **Aspose.Page for .NET** – 从 [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/) 下载库。  
- **Document Directory** – 您机器上的一个文件夹，用于存放源 PS 文件和输出 PS 文件（代码中称为 *Your Document Directory*）。  
- **Fonts Folder** – 包含您计划使用的任何自定义字体的子文件夹。

## 导入命名空间

首先，导入所需的命名空间，以便编译器知道我们将使用的类所在位置：

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 分步指南

### 步骤 1：为 PS 文档创建输出流  

我们打开一个 `FileStream` 来保存生成的 PS 文件，配置 `PsSaveOptions` 指向我们的自定义字体文件夹，并实例化 `PsDocument`。

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

> **专业提示：** 保留 `using` 块以确保流自动关闭，这也会完成 PS 文件的最终写入（`save ps document`）。

### 步骤 2：使用系统字体填充文本  

这里我们演示使用内置的 *Times New Roman* 字体进行基本的 **how to fill text** 操作。

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### 步骤 3：使用自定义字体填充文本  

如果您需要特定的外观，可使用 `ExternalFontCache.FetchDrFont` 从字体文件夹加载自定义字体。这满足了 **add custom font ps** 的需求。

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### 步骤 4：使用系统字体描边（Stroke）文本  

描边会绘制字形的轮廓。将其与填充结合可实现 “fill and stroke” 效果。

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **重要性说明：** `FillAndStrokeText` 调用展示了如何在一步中 **fill and stroke text**，为您提供更丰富的排版控制。

### 步骤 5：使用自定义字体描边文本  

相同的描边技术同样适用于您加载的任何自定义字体。

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### 步骤 6：关闭页面并保存文档  

收尾工作很简单：关闭当前页面并调用 `Save()` 将 PS 文件写入磁盘。

```csharp
document.ClosePage();
document.Save();
}
```

> **结果：** 您将在 *Your Document Directory* 中找到 `AddText_outPS.ps`，其中包含使用系统和自定义字体渲染的填充和描边文本。

## 常见问题及解决方案

| 问题 | 解决方案 |
|-------|----------|
| **Custom font not found** | 确认字体文件（.ttf/.otf）存在于 `AdditionalFontsFolders` 所引用的文件夹中。 |
| **Text appears at wrong position** | 调整传递给 `FillText`/`OutlineText` 的 X/Y 坐标。请记住 PostScript 使用点（1/72 英寸）作为单位。 |
| **Colors look different** | 确保使用了带有正确 `Color` 值的 `SolidBrush` 或 `Pen`。 |
| **Document not saving** | 确认 `using` 块在没有异常的情况下完成，并且应用程序对目标文件夹具有写入权限。 |

## 常见问题解答

**Q: 我可以将 Aspose.Page 与其他 .NET 库一起使用吗？**  
A: 可以，Aspose.Page 能够平滑地与其他 .NET 组件集成，允许您在同一解决方案中组合 PDF、图像或图表库。

**Q: 自定义字体在此过程中是否必需？**  
A: 虽然系统字体也能正常工作，但自定义字体提供了完整的设计自由度，在需要品牌特定排版时非常有用。

**Q: Aspose.Page 适合大规模文档处理吗？**  
A: 绝对适合。该库针对高吞吐场景进行了优化，能够高效处理成千上万的 PS 文件。

**Q: 我可以修改 PS 文档中文本的位置吗？**  
A: 当然可以——只需更改 `FillText` 或 `OutlineText` 调用中的数值 X/Y 即可。

**Q: 我可以在哪里寻求 Aspose.Page 相关问题的帮助？**  
A: 访问 [Aspose.Page Forum](https://forum.aspose.com/c/page/39) 与社区交流并获取专家帮助。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-03-21  
**测试环境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose