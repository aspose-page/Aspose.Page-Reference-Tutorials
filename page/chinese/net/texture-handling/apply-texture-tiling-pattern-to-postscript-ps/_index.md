---
date: 2026-03-26
description: 了解如何使用 Aspose.Page 在 .NET 中创建带有纹理平铺图案的 PostScript 文档。按照我们的分步指南，为您的 PS
  文件添加丰富的纹理。
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: 创建带纹理平铺的 PostScript .NET 文档
url: /zh/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建带纹理平铺的 PostScript .NET 文档

## 如何使用纹理平铺创建 PostScript .NET 文档

在本教程中，您将学习如何 **创建 PostScript 文档 .NET** 并使用 Aspose.Page 库为其添加纹理平铺模式。我们将逐步演示从项目设置到使用纹理画笔填充和描边文本的全过程，让您在几分钟内即可生成视觉效果出色的 PS 文件。

## 快速答案
- **使用的库是什么？** Aspose.Page for .NET  
- **可以使用 .NET Core 吗？** 可以，库支持 .NET Core 和 .NET 5/6  
- **纹理支持哪些图像格式？** 任意 System.Drawing 支持的格式（BMP、PNG、JPEG 等）  
- **实现大概需要多长时间？** 基础示例约 10‑15 分钟  
- **需要许可证吗？** 免费试用可用于测试；生产环境需要许可证  

## 前置条件

- 已在机器上安装 [Visual Studio](https://visualstudio.microsoft.com/)。  
- 具备 C# 编程基础。  
- 下载并安装 [Aspose.Page for .NET library](https://releases.aspose.com/page/net/)。  
- 准备一张用于纹理模式的图像文件（例如 **TestTexture.bmp**）。

## 导入命名空间

在 C# 文件中导入所需的命名空间，以便编译器能够找到我们将使用的类型：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步骤 1：设置文档目录

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

将 **Your Document Directory** 替换为您希望保存生成的 PS 文件的文件夹路径。

## 步骤 2：为 PS 文档创建输出流

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

此代码块打开文件流，配置页面大小（默认 A4），并创建一个全新的 **PsDocument** 实例供后续绘制使用。

## 步骤 3：应用纹理平铺模式

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

这里我们加载位图，将其包装为 **TextureBrush**，可选地在水平方向上拉伸，并告诉 **PsDocument** 在后续绘图操作中使用该画笔。

## 步骤 4：创建矩形路径并填充

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

定义一个简单的矩形，并使用前面设置的纹理画笔进行填充。

## 步骤 5：设置描边并绘制

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

获取当前的画笔（纹理画笔），创建一个红色笔用于描边，然后绘制矩形的边框。

## 步骤 6：使用纹理模式填充并描边文本

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

此步骤演示 **填充并描边文本** 的功能：字符 “ABC” 使用纹理画笔填充后再描边，呈现出醒目的视觉效果。

## 步骤 7：保存并关闭文档

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

关闭页面后完成绘图指令，`Save()` 将 PostScript 文件写入磁盘。

## 常见问题及解决方案

- **纹理出现拉伸错误** – 调整 `Matrix` 的数值以控制 X/Y 方向的缩放。  
- **找不到图像** – 确认 `dataDir` 指向正确的文件夹，并且文件名完全匹配（包括大小写）。  
- **颜色显示异常** – 请记住 PostScript 使用设备无关的颜色空间；确保使用的 `Color` 对象能够正确映射。

## 常见问答

**Q:** 可以使用其他图像格式作为纹理模式吗？  
**A:** 可以，任何 `System.Drawing.Bitmap` 支持的格式（BMP、PNG、JPEG、GIF 等）均可使用。

**Q:** Aspose.Page 是否兼容 .NET Core？  
**A:** 完全兼容。该库可在 .NET Framework、.NET Core 以及 .NET 5/6 上运行。

**Q:** 如何更改纹理矩形的大小？  
**A:** 在创建矩形的步骤中修改 `RectangleF` 的数值，例如 `new RectangleF(0, 0, 300, 150)`。

**Q:** 能在同一文档中应用多个纹理模式吗？  
**A:** 可以。只需使用不同的图像创建新的 `TextureBrush`，并在绘制下一个形状或文本前再次调用 `SetPaint`。

**Q:** 在哪里可以找到更多示例和 API 参考？  
**A:** 访问 [Aspose.Page Forum](https://forum.aspose.com/c/page/39) 获取社区帮助，或查阅官方 [documentation](https://reference.aspose.com/page/net/) 了解详细的 API 用法。

## 结论

现在您已经掌握了 **创建 PostScript 文档 .NET** 并应用纹理平铺模式的完整流程，包括如何 **使用纹理填充并描边文本**。尝试不同的图像、缩放矩阵以及绘图原语，便能为报告、宣传单或任何图形密集的输出生成自定义风格的 PS 文件。

---

**最后更新：** 2026-03-26  
**测试环境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}