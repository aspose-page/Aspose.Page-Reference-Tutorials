---
title: 使用 Aspose.Page 将带有 Unicode 字符串的文本添加到 XPS 文档
linktitle: 将带有 Unicode 字符串的文本添加到 XPS 文档中
second_title: Aspose.Page .NET API
description: 通过我们向 XPS 文档添加 Unicode 文本的分步指南，探索 Aspose.Page for .NET 的强大功能。
type: docs
weight: 12
url: /zh/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---
## 介绍

在不断发展的 .NET 开发领域，Aspose.Page 作为处理 XPS 文档的强大工具脱颖而出。在其众多功能中，向 XPS 文档添加带有 Unicode 字符串的文本的能力是一项很有价值的功能。本分步指南将引导您完成整个过程，确保您有效地利用此功能。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

- 对 .NET 开发有基本了解。
- Visual Studio 安装在您的计算机上。
-  .NET 库的 Aspose.Page。您可以从以下位置下载：[这里](https://releases.aspose.com/page/net/).

## 导入命名空间

首先，确保将必要的命名空间导入到您的项目中。这将提供使用 Aspose.Page 所需的类和功能。以下是基本的命名空间：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 第 1 步：设置文档

首先，创建一个新的 XPS 文档，您将在其中添加 Unicode 文本。请按照下面的代码片段操作：

```csharp
//文档目录的路径。
string dataDir = "Your Document Directory";
//创建新的 XPS 文档
XpsDocument doc = new XpsDocument();
```

## 第 2 步：添加 Unicode 文本

现在，让我们将 Unicode 文本添加到 XPS 文档中。此示例使用 Arial 字体，将字体大小设置为 20，并将文本定位在坐标 (400f, 200f) 处。本例中的 Unicode 字符串是“TEN.rof SPX.esopsA”。查看下面的代码片段：

```csharp
//添加文字
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## 第 3 步：保存文档

添加 Unicode 文本后，保存生成的 XPS 文档。这是最后一步：

```csharp
//保存生成的 XPS 文档
doc.Save(dataDir + "AddTextRTL_out.xps");
```

恭喜！您已使用 Aspose.Page for .NET 成功将 Unicode 文本添加到 XPS 文档中。

## 结论

在本教程中，我们探索了使用 Aspose.Page for .NET 将 Unicode 文本添加到 XPS 文档的过程。此功能为在 .NET 环境中创建多样化的动态文档打开了大门。

## 常见问题解答

### Q1：Aspose.Page 与最新的.NET 框架兼容吗？

A1：是的，Aspose.Page 会定期更新，以确保与最新的 .NET 框架兼容。

### Q2：添加文字时可以自定义字体样式和大小吗？

A2：当然！提供的示例代码允许您轻松自定义字体样式、大小和其他属性。

### Q3：在哪里可以找到 Aspose.Page 的附加文档？

 A3：可以参考文档[这里](https://reference.aspose.com/page/net/)获取全面的信息和示例。

### Q4：有没有免费的资源可以开始使用Aspose.Page？

 A4：是的，您可以探索[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)以获得社区支持和讨论。

### Q5：购买前有试用版吗？

 A5：当然！您可以访问免费试用版[这里](https://releases.aspose.com/)在购买之前。