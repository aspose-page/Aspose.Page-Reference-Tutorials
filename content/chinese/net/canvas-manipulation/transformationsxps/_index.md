---
title: 使用 Aspose.Page for .NET 进行 XPS 转换
linktitle: XPS 变换
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 轻松转换 XPS 文档。请按照我们的分步指南进行无缝转换。
type: docs
weight: 13
url: /zh/net/canvas-manipulation/transformationsxps/
---
## 介绍

欢迎来到 Aspose.Page for .NET 的世界，这是一个功能强大的库，使您能够轻松地对 XPS 文档执行各种转换。在本教程中，我们将深入研究使用 Aspose.Page for .NET 转换 XPS 文档的过程。无论您是经验丰富的开发人员还是新手，本指南都将引导您完成每个步骤，确保您轻松掌握概念。

## 先决条件

在我们开始之前，请确保您已具备以下条件：

-  Aspose.Page for .NET Library：从以下位置下载并安装该库[Aspose.Page for .NET 文档](https://reference.aspose.com/page/net/).

- 开发环境：设置兼容的开发环境，例如 Visual Studio 或任何其他 .NET 开发工具。

- 您的文档目录：将代码中的占位符替换为文档目录的实际路径。

现在，让我们进入教程吧！

## 导入命名空间

首先，确保导入必要的命名空间，以使 Aspose.Page for .NET 功能在代码中可用。在脚本的开头添加以下命名空间：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 第 1 步：创建新的 XPS 文档

```csharp
//开始时间：1
//文档目录的路径。
string dataDir = "Your Document Directory";

//创建新的 XPS 文档
XpsDocument doc = new XpsDocument();
```

## 第 2 步：创建主画布

```csharp
//创建主画布，所有页面元素通用
XpsCanvas canvas1 = doc.AddCanvas();

//在主画布中进行左侧和顶部偏移
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## 第 3 步：创建矩形路径几何图形

```csharp
//创建矩形路径几何体
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## 第 4 步：添加矩形填充

```csharp
//为矩形创建填充
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## 第 5 步：添加不进行任何变换的新画布

```csharp
//添加新画布而不对主画布进行任何转换
XpsCanvas canvas2 = canvas1.AddCanvas();

//在此画布中创建矩形并填充它
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## 第 6 步：添加带有平移变换的新画布

```csharp
//将具有平移转换的新画布添加到主画布
XpsCanvas canvas3 = canvas1.AddCanvas();

//平移此画布以将新矩形放置在前一个矩形下方
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

//将此画布平移到页面的右侧
canvas3.RenderTransform.Translate(500, 0);

//在此画布中创建矩形并填充它
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## 第7步：添加具有双比例变换的新画布

```csharp
//将具有双比例变换的新画布添加到主画布
XpsCanvas canvas4 = canvas1.AddCanvas();

//平移此画布以将新矩形放置在前一个矩形下方
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

//缩放此画布
canvas4.RenderTransform.Scale(2, 2);

//在此画布中创建矩形并填充它
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## 第 8 步：添加围绕点变换旋转的新画布

```csharp
//将围绕点变换旋转的新画布添加到主画布
XpsCanvas canvas5 = canvas1.AddCanvas();

//平移此画布以将新矩形放置在前一个矩形下方
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

//围绕一点旋转画布 45 度
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

//在此画布中创建矩形并填充它
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## 第 9 步：保存生成的 XPS 文档

```csharp
//保存生成的 XPS 文档
doc.Save(dataDir + "output1.xps");
//结束：1
```

## 结论

恭喜！您已使用 Aspose.Page for .NET 成功转换了 XPS 文档。本指南涵盖了从设置先决条件到执行各种转换的基本步骤。尝试这些技术并释放 Aspose.Page for .NET 在您的项目中的全部潜力。

## 常见问题解答

### Q1：Aspose.Page for .NET 是否兼容所有.NET 开发环境？

A1：是的，Aspose.Page for .NET 旨在与各种 .NET 开发环境（包括 Visual Studio）无缝协作。

### 问题 2：在哪里可以找到 Aspose.Page for .NET 的其他示例和文档？

 A2：访问[Aspose.Page for .NET 文档](https://reference.aspose.com/page/net/)获取全面的文档和示例。

### Q3：我可以在购买前试用 Aspose.Page for .NET 吗？

 A3：是的，您可以访问免费试用版[Aspose.Page 免费试用](https://releases.aspose.com/).

### Q4：如何获得 Aspose.Page for .NET 的临时许可证？

A4：通过访问获得临时许可证[临时牌照](https://purchase.aspose.com/temporary-license/).

### Q5：哪里可以购买 Aspose.Page for .NET？

 A5：购买 .NET 版 Aspose.Page，网址为[Aspose.Page 购买](https://purchase.aspose.com/buy).