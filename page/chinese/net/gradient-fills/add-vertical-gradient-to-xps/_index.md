---
title: 使用 Aspose.Page for .NET 将垂直渐变添加到 XPS
linktitle: 向 XPS 添加垂直渐变
second_title: Aspose.Page .NET API
description: 了解如何使用 Aspose.Page for .NET 通过垂直渐变增强 XPS 文档。请按照我们的分步指南进行无缝集成。
weight: 15
url: /zh/net/gradient-fills/add-vertical-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 将垂直渐变添加到 XPS

## 介绍

欢迎阅读本分步教程，了解如何使用 Aspose.Page for .NET 将垂直渐变添加到 XPS 文档。 Aspose.Page 是一个功能强大的 API，允许您在 .NET 应用程序中使用 XPS（XML 纸张规范）文件。在本教程中，我们将指导您完成创建新 XPS 文档、向路径添加垂直渐变以及保存结果的过程。

## 先决条件

在我们深入学习本教程之前，请确保您具备以下先决条件：

-  Aspose.Page for .NET 库：确保您的开发环境中安装了 Aspose.Page for .NET 库。你可以下载它[这里](https://releases.aspose.com/page/net/).

- 开发环境：使用您首选的 IDE（例如 Visual Studio）设置 .NET 开发环境。

现在，让我们开始使用 Aspose.Page for .NET 向 XPS 文档添加垂直渐变。

## 导入命名空间

在您的 .NET 应用程序中，包含访问 Aspose.Page 类和方法所需的命名空间。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## 第 1 步：设置您的文档目录

开始之前，设置要保存生成的 XPS 文档的文档目录的路径。

```csharp
//起始时间：3
string dataDir = "Your Document Directory";
//结束：3
```

## 第 2 步：创建新的 XPS 文档

使用以下代码初始化一个新的 XPS 文档：

```csharp
//起始时间：4
XpsDocument doc = new XpsDocument();
//结束：4
```

## 第 3 步：定义渐变停止点

创建渐变停止点列表，指定每个停止点的颜色和位置。在此示例中，我们定义了具有五个停止点的垂直渐变。

```csharp
//起始时间：5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
//结束：5
```

## 第四步：创建渐变路径

通过指定其几何形状来定义路径并向其应用线性渐变画笔。

```csharp
//起始时间：6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
//结束：6
```

## 第 5 步：保存生成的 XPS 文档

将修改后的 XPS 文档保存到指定目录。

```csharp
//起始时间：7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
//结束：7
```

恭喜！您已使用 Aspose.Page for .NET 成功向 XPS 文档添加垂直渐变。

## 结论

在本教程中，我们探讨了如何利用 Aspose.Page for .NET 通过垂直渐变增强 XPS 文档。 Aspose.Page 简化了复杂的任务，为开发人员提供了在 .NET 应用程序中操作 XPS 文件的无缝方式。

## 常见问题解答

### Q1：Aspose.Page 与 Visual Studio 2019 兼容吗？

A1：是的，Aspose.Page 与 Visual Studio 2019 兼容。确保您安装了正确版本的库。

### Q2：我可以将Aspose.Page用于商业项目吗？

 A2：是的，Aspose.Page可以用于商业项目。访问[这里](https://purchase.aspose.com/buy)探索许可选项。

### Q3：有免费试用吗？

A3：是的，您可以免费试用Aspose.Page[这里](https://releases.aspose.com/).

### Q4：哪里可以找到Aspose.Page文档？

 A4：文档可用[这里](https://reference.aspose.com/page/net/).

### Q5：我如何获得支持或提出问题？

 A5：访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)以获得社区支持。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
