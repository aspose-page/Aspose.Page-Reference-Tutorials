---
title: 使用 Aspose.Page for .NET 创建 XPS 文档
linktitle: 创建 XPS 文档
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 探索 XPS 文档创建的世界。按照我们的分步指南轻松生成电子文档。
weight: 10
url: /zh/net/document-creation/create-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 创建 XPS 文档

## 介绍

欢迎阅读我们有关使用 Aspose.Page for .NET 创建 XPS 文档的分步指南。在本教程中，我们将探讨生成 XPS 文件的过程，XPS 文件是一种广泛使用的电子文档格式。无论您是经验丰富的开发人员还是刚刚开始使用 Aspose.Page，本指南都经过量身定制，可通过清晰的示例和详细的说明帮助您无缝创建 XPS 文档。

## 先决条件

在我们深入学习本教程之前，请确保您具备以下先决条件：

1.  Aspose.Page for .NET Library：从以下位置下载并安装 Aspose.Page 库：[下载链接](https://releases.aspose.com/page/net/).

2. 您的文档目录：在系统上选择或创建一个用于保存输出 XPS 文件的目录。

现在，让我们进入教程吧！

## 导入命名空间

为了使用 Aspose.Page for .NET，您需要将必要的命名空间导入到您的项目中。按着这些次序：

### 第1步：添加对Aspose.Page的引用

在您的项目中，添加对 Aspose.Page for .NET 库的引用。您可以在下载的包中找到所需的DLL。

### 第 2 步：导入命名空间

在您的代码文件中包含以下命名空间：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

现在我们已经设置了先决条件并导入了必要的命名空间，让我们将创建 XPS 文档的过程分解为多个步骤。

## 第1步：设置文档目录

```csharp
string dir = "Your Document Directory";
```

确保更换`"Your Document Directory"`与要保存输出 XPS 文件的实际路径。

## 第 2 步：创建 XPS 文档

```csharp
XpsDocument xDocs = new XpsDocument();
```

使用以下命令初始化新的 XPS 文档`XpsDocument`班级。

## 第 3 步：将字形添加到文档中

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

使用`AddGlyphs`向文档添加字形（文本）的方法。根据需要自定义字体、大小、样式和位置。

## 第 4 步：设置字形填充颜色

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

指定添加的字形的填充颜色。在此示例中，我们使用黑色，但您可以选择任何颜色。

## 第 5 步：保存结果

```csharp
xDocs.Save(dir + "output.xps");
```

最后，使用所需的文件名将 XPS 文档保存到指定目录。生成的 XPS 文件将包含“Hello World!”文本。

恭喜！您已使用 Aspose.Page for .NET 成功创建了 XPS 文档。

## 结论

在本教程中，我们演练了使用 Aspose.Page for .NET 创建 XPS 文档的过程。这个功能强大的库提供了一种轻松生成电子文档的无缝方式。尝试不同的字体、样式和内容，根据您的特定需求定制 XPS 文件。

## 常见问题解答

### 问题 1：我可以在 XPS 文档中使用自定义字体吗？

A1：是的，您可以在向 XPS 文档添加字形时指定字体系列和大小。

### Q2：Aspose.Page 与.NET Core 兼容吗？

A2：是的，Aspose.Page 支持.NET Core，允许您在跨平台应用程序中使用它。

### 问题 3：如何将图像添加到 XPS 文档中？

A3：Aspose.Page 提供了将图像添加到 XPS 文档中的方法。请参阅文档了解详细示例。

### 问题 4：我可以创建多页 XPS 文档吗？

A4：当然！您可以使用 Aspose.Page 库将多个页面添加到 XPS 文档中。

### Q5：有试用版吗？

 A5：是的，您可以通过下载Aspose.Page来探索Aspose.Page的功能[免费试用](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
