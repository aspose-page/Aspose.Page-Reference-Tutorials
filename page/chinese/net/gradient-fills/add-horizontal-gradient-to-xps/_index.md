---
title: 使用 Aspose.Page for .NET 将水平渐变添加到 XPS
linktitle: 向 XPS 添加水平渐变
second_title: Aspose.Page .NET API
description: 了解如何使用 Aspose.Page for .NET 将令人惊叹的水平渐变添加到 XPS 文档中。毫不费力地提升视觉吸引力。
type: docs
weight: 13
url: /zh/net/gradient-fills/add-horizontal-gradient-to-xps/
---
## 介绍

在本教程中，我们将探索如何使用 Aspose.Page for .NET 添加水平渐变来增强 XPS 文档。 Aspose.Page for .NET 是一个功能强大的库，可在.NET 应用程序中无缝处理 XPS（XML 纸张规范）文档。添加渐变可以为您的文档带来视觉吸引力，本指南将逐步引导您完成该过程。

## 先决条件

在我们开始之前，请确保您具备以下先决条件：

1.  Aspose.Page for .NET 库：确保您的开发环境中安装了 Aspose.Page for .NET 库。您可以从[Aspose.Page for .NET 文档](https://reference.aspose.com/page/net/).

2. 开发环境：设置合适的开发环境，包括Visual Studio等代码编辑器。

## 导入命名空间

首先将必要的命名空间导入到您的项目中。这些命名空间对于使用 Aspose.Page for .NET 至关重要：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

现在，让我们将提供的示例分解为多个步骤。

## 第1步：设置文档目录路径

```csharp
//起始时间：3
//文档目录的路径。
string dataDir = "Your Document Directory";
//结束：3
```

## 第 2 步：创建新的 XPS 文档

```csharp
//起始时间：4
//创建新的 XPS 文档
XpsDocument doc = new XpsDocument();
//结束：4
```

## 第 3 步：初始化梯度停止点

```csharp
//起始时间：5
//初始化 XpsGradientStop 列表
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
//结束：5
```

## 第 4 步：创建新路径

```csharp
//起始时间：6
//通过以缩写形式定义几何图形来创建新路径
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
//结束：6
```

## 第 5 步：保存生成的 XPS 文档

```csharp
//起始时间：7
//保存生成的 XPS 文档
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
//结束：7
```

现在，您已使用 Aspose.Page for .NET 成功向 XPS 文档添加了水平渐变。

## 结论

使用渐变增强 XPS 文档不仅可以提高其视觉吸引力，还可以提供更具吸引力的用户体验。 Aspose.Page for .NET 简化了这个过程，让您轻松获得专业的结果。

## 常见问题解答

### Q1：在哪里可以找到 Aspose.Page for .NET 文档？

 A1：你可以找到文档[这里](https://reference.aspose.com/page/net/).

### Q2：如何下载 Aspose.Page for .NET？

A2：您可以从以下位置下载该库：[Aspose.Page for .NET 下载页面](https://releases.aspose.com/page/net/).

### Q3：哪里可以购买 Aspose.Page for .NET？

 A3：您可以从以下位置购买 Aspose.Page for .NET[购买页面](https://purchase.aspose.com/buy).

### Q4：有免费试用吗？

 A4：是的，您可以从以下位置获得免费试用[这里](https://releases.aspose.com/).

### Q5：如何获得 Aspose.Page for .NET 的临时许可证？

 A5：您可以从以下地址获得临时许可证：[这个链接](https://purchase.aspose.com/temporary-license/).