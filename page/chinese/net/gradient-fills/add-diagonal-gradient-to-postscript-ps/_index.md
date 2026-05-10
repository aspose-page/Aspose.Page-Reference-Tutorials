---
date: 2026-02-23
description: 了解如何向 PostScript 文件添加渐变、将 PostScript 文件保存为 A4 页面尺寸，以及使用 Aspose.Page for
  .NET 填充矩形渐变。
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: 如何在 PostScript (PS) 中使用 Aspose.Page .NET 添加渐变——对角线渐变
url: /zh/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何添加渐变：使用 Aspose.Page .NET 为 PostScript (PS) 添加对角线渐变

## 介绍

在 PostScript (PS) 文档中添加对角线渐变可以显著提升视觉效果，尤其是在技术报告、宣传册或图形密集型应用中需要 **如何添加渐变** 效果时。本教程将展示如何为 PostScript 文件添加渐变、设置 A4 页面尺寸，并使用 Aspose.Page for .NET 将矩形填充为平滑的颜色过渡。

## 快速答案
- **需要的库是什么？** Aspose.Page for .NET  
- **支持哪些 .NET 版本？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **我可以更改渐变方向吗？** 是 – 如代码所示旋转画笔变换  
- **如何保存结果？** 使用 `PsDocument.Save()` 将 PostScript 文件写入磁盘  
- **生产环境需要许可证吗？** 是的，商业许可证可解锁全部功能  

## 什么是 PostScript 中的对角线渐变？

对角线渐变是一种线性颜色过渡，以一定角度（通常为 45°）跨越形状。在 PostScript 中，通过使用带有自定义变换矩阵的 `LinearGradientBrush` 来实现，该矩阵可以旋转、缩放并平移渐变，以匹配所需的矩形。

## 为什么在渐变填充中使用 Aspose.Page？

Aspose.Page 抽象了底层的 PostScript 命令，让您可以使用熟悉的 .NET 图形对象进行操作。您可以创建复杂的填充、设置页面尺寸，并直接导出为 **save PostScript file**，无需处理原始 PS 语法。

## 前提条件

- **Aspose.Page for .NET 库** – 在[此处](https://releases.aspose.com/page/net/)下载。  
- **文档目录** – 用于写入生成的 `*.ps` 文件的文件夹。

现在我们已经了解了基础，让我们一步一步地演示实现过程。

## 导入命名空间

首先，导入能够访问 EPS 设备、绘图工具和 I/O 类的命名空间。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步骤 1：为 PostScript 文档创建输出流（创建 PostScript 文档）

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## 步骤 2：设置 A4 页面尺寸（保存选项）

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## 步骤 3：创建一个新的一页 PS 文档

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步骤 4：定义矩形参数

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## 步骤 5：创建图形路径

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## 步骤 6：创建线性渐变画刷（填充矩形渐变）

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## 步骤 7：为画刷创建变换矩阵

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## 步骤 8：对画刷应用变换（旋转、缩放、平移）

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## 步骤 9：将变换设置到画刷

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## 步骤 10：设置画笔并填充矩形

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## 步骤 11：关闭当前页面

```csharp
	//Close current page
	document.ClosePage();
```

## 步骤 12：保存文档（保存 PostScript 文件）

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## 如何保存 PostScript 文件

`PsDocument.Save()` 调用会将完整的 PostScript 内容写入您在 **步骤 1** 中打开的流。`using` 块完成后，文件 `DiagonaGradient_outPS.ps` 将出现在您指定的目录中。

## 常见使用场景

- **技术文档** 需要细腻的背景阴影。  
- **营销宣传册** 中对角线渐变增添现代感。  
- **自动化报告生成器** 可即时生成可打印的 PS 文件。

## 故障排除与技巧

- **颜色不正确** – 仔细检查传递给 `LinearGradientBrush` 的 ARGB 值。  
- **渐变不可见** – 确认变换矩阵正确旋转和缩放；`Rotate(-45)` 调用设置了对角线角度。  
- **文件未创建** – 确认 `dataDir` 指向已存在的文件夹且应用具有写入权限。

## 常见问题

**问：Aspose.Page 是否兼容所有 .NET 框架？**  
答：Aspose.Page 支持广泛的 .NET 版本，从 .NET Framework 4.5+ 到 .NET 6+，确保兼容性。

**问：我可以在 Aspose.Page 中自定义渐变颜色吗？**  
答：可以，在构造 `LinearGradientBrush` 时可以指定任意 ARGB 颜色，完全控制起始和结束色调。

**问：Aspose.Page 是否提供试用版？**  
答：是的，您可以通过在[此处](https://releases.aspose.com/)下载试用版来体验 Aspose.Page 的功能。

**问：如何获取 Aspose.Page 的临时许可证？**  
答：可在[此处](https://purchase.aspose.com/temporary-license/)获取 Aspose.Page 的临时许可证，以在评估期间解锁更多功能。

**问：在哪里可以找到 Aspose.Page 的社区支持？**  
答：可在[论坛](https://forum.aspose.com/c/page/39)与 Aspose.Page 社区交流，获取帮助和讨论。

---

**最后更新：** 2026-02-23  
**测试环境：** Aspose.Page for .NET（最新稳定版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}