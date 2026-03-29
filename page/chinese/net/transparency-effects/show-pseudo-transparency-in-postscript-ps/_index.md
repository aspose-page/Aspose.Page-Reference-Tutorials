---
date: 2026-03-29
description: 学习如何使用 C# 的线性渐变画刷，在 PostScript 中通过 Aspose.Page for .NET 创建伪透明效果。
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: 用于 PS 中伪透明的 C# 线性渐变画刷
url: /zh/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 线性渐变画刷 C# 用于 PostScript (PS) 中的伪透明

## 介绍

如果您需要在 PostScript (PS) 文件中添加细腻的透视效果，**linear gradient brush C#** 是完美的工具。Aspose.Page for .NET 使得绘制具有不透明和半透明渐变填充的矩形变得轻松，为您的文档提供现代分层外观。在本教程中，我们将逐步演示如何使用 C# 中的线性渐变画刷创建伪透明效果。

## 快速答案
- **提供线性渐变画刷的库是什么？** Aspose.Page for .NET
- **哪个图形类创建渐变？** `LinearGradientBrush`
- **我可以对每种颜色的透明度进行控制吗？** 是的，使用 `Color.FromArgb(alpha, …)`
- **生产环境需要许可证吗？** 需要有效的 Aspose.Page 许可证
- **支持的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+

## 什么是 linear gradient brush C#？

`LinearGradientBrush` 是一个 GDI+ 对象，用于在直线沿线的两种颜色之间绘制平滑过渡。当为每种颜色指定 alpha 通道（0‑255）时，您可以创建半透明渐变——这正是我们在 PostScript 中实现伪透明所需的。

## 为什么在伪透明中使用 linear gradient brush C#？

- **细粒度透明度控制：** 调整每种颜色的 alpha 以实现所需的透视程度。  
- **设备无关渲染：** 该画刷在屏幕、PDF、EPS 和 PS 输出上表现一致。  
- **简洁 API：** 几行 C# 代码即可产生专业级视觉效果。

## 前提条件

在深入代码之前，请确保您拥有：

- 已安装 Aspose.Page for .NET。您可以从 [Aspose.Page 文档](https://reference.aspose.com/page/net/) 下载。  
- 一个可写文件夹，用于保存生成的 PostScript 文档。

现在您已经拥有必要的工具，让我们开始构建伪透明矩形。

## 导入命名空间

在开始之前，导入包含我们将使用的类的命名空间：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步骤 1：为 PostScript 文档创建输出流

我们首先创建一个文件流来保存生成的 PS 文件，然后初始化 `PsDocument`。

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步骤 2：创建具有 **不透明** 渐变填充的矩形

这里我们构建一个 `LinearGradientBrush`，其颜色完全不透明（alpha = 255）。此矩形将作为背景层。

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## 步骤 3：创建具有 **半透明** 渐变填充的矩形

现在我们使用 **linear gradient brush C#**，其 alpha 值小于 255（例如 150 和 50）。这使得矩形部分透视，实现伪透明效果。

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## 步骤 4：关闭页面并保存文档

最后我们完成页面并将 PS 文件写入磁盘。

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

按照这四个步骤，您可以无缝混合不透明和半透明矩形，在任何 PostScript 输出中创建逼真的伪透明效果。

## 常见问题及解决方案

| 问题 | 为什么会发生 | 解决方案 |
|------|--------------|----------|
| 颜色显示为完全不透明 | Alpha 值误设为 255 | 使用 `Color.FromArgb(alpha, …)`，其中 `alpha` < 255 |
| 渐变拉伸不正确 | 变换矩阵不正确 | 确认矩阵参数与矩形尺寸匹配 |
| 输出文件为空 | 流未关闭或未调用 `Save()` | 确保在 `using` 块内执行 `document.ClosePage()` 和 `document.Save()` |

## 常见问题

**问：Aspose.Page 是否兼容所有 .NET 版本？**  
**答：** Aspose.Page for .NET 兼容多种 .NET 框架版本，确保灵活性和易于集成。

**问：我可以将伪透明应用于除矩形之外的其他形状吗？**  
**答：** 可以，通过相应调整 `GraphicsPath`，相同原理适用于任何形状。

**问：在哪里可以找到更多示例和文档？**  
**答：** 请访问 [Aspose.Page 文档](https://reference.aspose.com/page/net/) 获取完整示例和详细 API 参考。

**问：Aspose.Page 是否提供免费试用？**  
**答：** 是的，您可以通过 [此链接](https://releases.aspose.com/) 获取 Aspose.Page 的免费试用。

**问：如何获取 Aspose.Page 的临时许可证？**  
**答：** 请访问 [此链接](https://purchase.aspose.com/temporary-license/) 获取 Aspose.Page 的临时许可证。

---

**最后更新：** 2026-03-29  
**测试版本：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}