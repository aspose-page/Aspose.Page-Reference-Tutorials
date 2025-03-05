---
title: 使用 Aspose.Page for .NET 将平铺图像添加到 XPS 文档
linktitle: 将平铺图像添加到 XPS 文档
second_title: Aspose.Page .NET API
description: 探索使用 Aspose.Page for .NET 轻松地将平铺图像添加到 XPS 文档中。增强视觉吸引力并创建令人惊叹的文档。
type: docs
weight: 12
url: /zh/net/image-management/add-tiled-image-to-xps-document/
---
## 介绍

您是否希望通过添加具有视觉吸引力的平铺图像来增强您的 XPS 文档？ Aspose.Page for .NET 使开发人员能够无缝地实现这一目标。在本分步指南中，我们将引导您完成使用 Aspose.Page for .NET 将平铺图像添加到 XPS 文档的过程。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

-  Aspose.Page for .NET：确保您已安装 Aspose.Page 库。您可以找到详细的文档并下载库[这里](https://reference.aspose.com/page/net/).
- 开发环境：设置您首选的 .NET 开发环境，例如 Visual Studio。

## 导入命名空间

首先，将必要的命名空间导入到您的项目中。这确保您可以访问使用 Aspose.Page 所需的类和方法。在代码开头添加以下命名空间：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

现在，让我们将该示例分解为多个步骤。

## 第 1 步：定义文档目录

```csharp
//文档目录的路径。
string dataDir = "Your Document Directory";
```

确保将“您的文档目录”替换为您要保存 XPS 文档的实际路径。

## 第 2 步：创建新的 XPS 文档

```csharp
//创建新的 XPS 文档
XpsDocument doc = new XpsDocument();
```

使用以下命令实例化一个新的 XPS 文档`XpsDocument`班级。

## 第 3 步：添加平铺图像

```csharp
//平铺图像
//ImageBrush 填充矩形位于右上方下方
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

此步骤将平铺图像添加到 XPS 文档中。根据您的要求调整坐标和图像文件路径。

## 步骤 4：保存生成的 XPS 文档

```csharp
//保存生成的 XPS 文档
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

将修改后的XPS文档保存到指定目录。

## 结论

恭喜！您已成功学习如何使用 Aspose.Page for .NET 将平铺图像添加到 XPS 文档中。这个简单而强大的功能使您可以轻松增强文档的视觉吸引力。

## 常见问题解答

### Q1：Aspose.Page 是否兼容所有.NET 开发环境？

A1：是的，Aspose.Page 旨在与各种 .NET 开发环境（包括 Visual Studio）无缝协作。

### Q2：我可以调整平铺图像的不透明度吗？

A2：当然，如示例所示，您可以使用以下命令设置填充矩形的不透明度`Opacity`财产。

### Q3：Aspose.Page for .NET 中是否还有其他可用的平铺模式？

 A3：是的，Aspose.Page提供了不同的平铺模式。在本教程中，我们使用了`XpsTileMode.Tile`，但您可以探索文档中的其他选项。

### Q4：如何处理 Aspose.Page 的临时许可证？

 A4：请参阅[临时执照](https://purchase.aspose.com/temporary-license/) Aspose 网站上的页面提供有关获取和实施临时许可证的指导。

### Q5：我可以在哪里寻求帮助或与 Aspose.Page 社区联系？

 A5：访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)与社区互动、提出问题并寻找解决方案。