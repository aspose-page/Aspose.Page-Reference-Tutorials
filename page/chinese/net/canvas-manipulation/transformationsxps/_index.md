---
date: 2026-01-05
description: 了解如何使用 Aspose.Page for .NET 轻松转换 XPS 文档。遵循我们的分步指南，实现无缝转换。
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: 如何使用 Aspose.Page for .NET 转换 XPS
url: /zh/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page for .NET 转换 XPS

## 介绍

欢迎来到 Aspose.Page for .NET 的世界，这是一款强大的库，可让您轻松对 XPS 文档执行各种转换。**在本教程中，您将了解如何使用 Aspose.Page for .NET 转换 XPS 文档**，无论您是经验丰富的开发者还是刚入门。我们将逐步演示每一步，解释每次转换背后的原理，并提供可在实际项目中应用的实用技巧。

## 快速答案
- **可以实现什么？** 以编程方式创建、平移、缩放和旋转 XPS 画布元素。  
- **需要哪个库？** Aspose.Page for .NET（最新版本）。  
- **需要许可证吗？** 开发阶段可使用免费试用版；生产环境需要商业许可证。  
- **支持的平台？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **实现需要多长时间？** 基本转换大约需要 10‑15 分钟。

## 什么是 “how to transform xps”？
短语 *how to transform xps* 指的是以编程方式修改 XPS（XML Paper Specification）文档内部元素的布局、大小和方向。使用 Aspose.Page，您可以对画布应用基于矩阵的转换，从而在不手动编辑 XPS XML 的情况下，实现对定位、缩放和旋转的细粒度控制。

## 为什么使用 Aspose.Page 进行 XPS 转换？
- **完整的 .NET 集成** – 与 Visual Studio、Rider 等 IDE 无缝配合。  
- **无外部依赖** – API 为您处理所有底层 XPS 细节。  
- **丰富的转换支持** – 平移、缩放、旋转，并可在一次调用中组合多种转换。  
- **性能优化** – 适用于即时生成报表、发票或任何可打印图形。

## 前置条件

在开始之前，请确保您已具备：

- **Aspose.Page for .NET 库** – 从官方文档下载并安装：[Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/)。  
- **开发环境** – Visual Studio、Visual Studio Code 或其他 .NET 兼容的 IDE。  
- **文档目录** – 您机器上的一个文件夹，用于读取/写入 XPS 文件。请在代码中将占位符替换为实际路径。

准备就绪后，让我们进入代码实现。

## 导入命名空间

首先，导入提供 Aspose.Page 类的命名空间：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 如何转换 XPS – 步骤指南

### 步骤 1：创建新 XPS 文档

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*说明*：我们首先定义存放源文件和输出文件的文件夹，然后实例化一个空的 `XpsDocument`。该对象将作为后续所有转换的画布。

### 步骤 2：创建主画布

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*为何重要*：主画布充当所有其他画布的容器。通过添加少量偏移，确保内容不会在页面边缘被裁剪。

### 步骤 3：创建矩形路径几何体

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*提示*：路径字符串遵循标准 XPS 路径语法（`M` 表示移动，`L` 表示直线，`Z` 表示闭合）。调整坐标即可改变矩形大小。

### 步骤 4：为矩形添加填充

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*专业技巧*：使用 `CreateColor` 并提供 RGB 值，以匹配您的品牌配色。

### 步骤 5：添加一个不带转换的新画布

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

这里我们仅在页面上放置一个矩形，不做额外转换——可作为基准元素使用。

### 步骤 6：添加一个带平移转换的新画布

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*发生了什么？* 第一个矩阵将矩形向下移动 200 单位。随后 `Translate` 调用再向右平移 500 单位，演示了如何链式使用多个平移。

### 步骤 7：添加一个带双倍缩放转换的新画布

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*为何缩放？* 缩放 2 倍会使矩形的宽高翻倍，您无需重新定义几何体即可创建更大的图形。

### 步骤 8：添加一个围绕点旋转的画布

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*关键点*：`RotateAround` 使画布围绕自定义点（此处为 (100, 50)）旋转，让您精确控制旋转锚点。

### 步骤 9：保存生成的 XPS 文档

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

所有转换完成后，文档将保存为 `output1.xps`。使用任意 XPS 查看器打开，即可看到堆叠的矩形及其对应的平移、缩放和旋转效果。

## 常见问题与排查

| 症状 | 可能原因 | 解决办法 |
|------|----------|----------|
| 输出文件为空 | `dataDir` 指向不存在的文件夹 | 确认目录已创建或使用绝对路径 |
| 矩形位置不符合预期 | 矩阵数值错误 | 检查 `Translate`、`Scale`、`RotateAround` 调用的顺序 |
| 颜色显示错误 | RGB 值超出 0‑255 范围 | 为每个通道使用有效的字节值 |

## 常见问答

**问：Aspose.Page for .NET 是否兼容所有 .NET 开发环境？**  
答：是的，它可在 Visual Studio、Visual Studio Code、Rider 以及任何支持 .NET 的 IDE 中无缝使用。

**问：在哪里可以找到更多示例和详细的 API 文档？**  
答：访问官方文档：[Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/)。

**问：我可以在购买许可证前试用 Aspose.Page 吗？**  
答：当然。免费试用可在此获取：[Aspose.Page Free Trial](https://releases.aspose.com/)。

**问：如何获取临时许可证用于测试？**  
答：可通过临时许可证页面申请：[Temporary License](https://purchase.aspose.com/temporary-license/)。

**问：在哪里购买正式许可证？**  
答：直接在 Aspose 商店购买：[Aspose.Page Buy](https://purchase.aspose.com/buy)。

---

**最后更新：** 2026-01-05  
**测试环境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}