---
date: 2026-04-03
description: 学习如何在 .NET 中使用 Aspose.Page 添加透明矩形并应用网格视觉画刷，以创建惊艳的 XPS 文档。
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: 应用网格视觉画刷
second_title: Aspose.Page .NET API
title: 使用 Grid Visual Brush 添加透明矩形（.NET）
url: /zh/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 添加透明矩形并使用网格视觉刷 (.NET)

## 介绍

如果您希望 **添加透明矩形** 到 XPS 文档，同时应用时尚的网格视觉刷，那么您来对地方了。在本教程中，我们将使用 Aspose.Page for .NET 逐步演示所需的完整步骤，让您能够创建视觉丰富、脱颖而出的文档。完成后，您将拥有一个完整、可运行的示例，展示这两种技术的单一、易于遵循的工作流。

## 快速答案
- **透明矩形有什么作用？** 它添加一个半不透明的覆盖层，使背景内容能够透过显示。  
- **哪个 API 创建刷子？** `XpsDocument.CreateVisualBrush` 构建网格视觉刷。  
- **我需要许可证吗？** 免费试用可用于测试；生产环境需要商业许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **实现大概需要多长时间？** 基本示例约需 10‑15 分钟。

## 什么是 XPS 中的透明矩形？
透明矩形是一种填充颜色的 alpha 分量小于 1.0 的形状，允许底层图形部分可见。这非常适合在不完全遮挡背景的情况下突出显示区域。

## 为什么使用网格视觉刷？
网格视觉刷可以在更大的区域内平铺小的矢量图形，形成网格、交叉线或自定义纹理等图案。将其与透明矩形结合，可实现轻量且分辨率无关的分层视觉效果。

## 前置条件

在开始编写代码之前，请确保您已具备：

- **Aspose.Page for .NET** – 您可以在 [here](https://releases.aspose.com/page/net/) 下载。  
- 一个 .NET 开发环境（Visual Studio、VS Code 或您喜欢的任何 IDE）。  
- 一个用于保存生成的 XPS 文件的文件夹。

## 导入命名空间

在您的 C# 文件中，导入所需的命名空间：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

现在让我们将解决方案拆分为清晰的编号步骤。

## 步骤 1：初始化 XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

我们首先创建一个 `XpsDocument` 实例，它将承载后续的所有绘图操作。

## 步骤 2：创建品红网格几何体

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

此几何体定义了视觉刷将填充的网格轮廓。

## 步骤 3：设计品红网格 VisualBrush

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

这里我们绘制一个小的品红色瓦片，以便在网格上重复平铺。

## 步骤 4：将 VisualBrush 应用于网格

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

`CreateVisualBrush` 调用将品红色瓦片与网格几何体关联，并启用平铺功能。

## 步骤 5：将网格添加到画布

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

我们将平铺的网格放置在画布上，并应用平移变换，使其出现在所需位置。

## 步骤 6：添加透明矩形

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

在此步骤中我们 **添加透明矩形**（红色形状，`Opacity = 0.7f`）。调整不透明度值即可控制矩形的透视程度。

## 步骤 7：保存文档

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

XPS 文件将写入您之前指定的文件夹。

## 常见用例

- **报告高亮：** 在图表或表格上覆盖半透明矩形以强调重点。  
- **水印效果：** 将平铺网格与透明覆盖层结合，实现细腻的品牌标识。  
- **交互式 PDF/XPS：** 将图案用作表单字段的背景，同时保持 UI 可读。

## 故障排除提示

- **不透明度未显示？** 确保您的查看器支持 XPS 透明度；某些旧版查看器可能会忽略 `Opacity` 属性。  
- **瓦片尺寸不正确？** 核实源矩形 (`new RectangleF(0f, 0f, 10f, 10f)`) 是否与矢量瓦片的尺寸匹配。  
- **文件未保存？** 再次检查 `dataDir` 是否指向一个存在且可写的目录。

## 常见问题

**Q: 我可以在 Web 和桌面应用程序中都使用 Aspose.Page for .NET 吗？**  
A: 可以，库在所有 .NET 应用类型中均可使用。

**Q: 在购买前是否有试用版可供使用？**  
A: 当然，您可以在 [here](https://releases.aspose.com/) 获取免费试用。

**Q: 我可以在哪里找到更多支持或社区讨论？**  
A: 访问 [Aspose.Page Forum](https://forum.aspose.com/c/page/39) 获取社区和 Aspose 工程师的帮助。

**Q: 如何获取临时许可证进行评估？**  
A: 您可以在 [here](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**Q: Aspose.Page for .NET 还有哪些其他文档可供参考？**  
A: 请在 [here](https://reference.aspose.com/page/net/) 浏览完整文档。

---

**最后更新：** 2026-04-03  
**已测试版本：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}