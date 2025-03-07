---
title: 使用 Aspose.Page for .NET 将矩形添加到 XPS 文档
linktitle: 将矩形添加到 XPS 文档
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 增强文档创建。在此分步教程中了解如何向 XPS 文档添加矩形。
weight: 13
url: /zh/net/drawing-shapes/add-rectangle-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 将矩形添加到 XPS 文档

## 介绍

Aspose.Page for .NET 是一个功能强大的库，提供了在 .NET 应用程序中处理 XPS（XML 纸张规范）文档的各种功能。在本教程中，我们将重点介绍使用 Aspose.Page for .NET 将矩形添加到 XPS 文档。按照此分步指南来增强您的文档创建过程。

## 先决条件

在开始学习本教程之前，请确保您具备以下先决条件：

1.  Aspose.Page for .NET 库：确保您的开发环境中安装了 Aspose.Page for .NET 库。你可以下载它[这里](https://releases.aspose.com/page/net/).

2. 文档目录：设置要存储 XPS 文档的目录。

## 导入命名空间

在您的 .NET 应用程序中，包含使用 Aspose.Page 功能所需的命名空间。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 第1步：设置文档目录

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

## 第三步：添加一个矩形

```csharp
//起始时间：5
//左下角的 CMYK（蓝色）纯色描边矩形
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
//结束：5
```

## 步骤 4：保存文档

```csharp
//起始时间：6
//保存生成的 XPS 文档
doc.Save(dataDir + "AddRectangleXPS_out.xps");
//结束：6
```

恭喜！您已使用 Aspose.Page for .NET 成功将矩形添加到 XPS 文档中。

## 结论

Aspose.Page for .NET 简化了文档操作任务，使开发人员能够轻松创建和修改 XPS 文档。本分步指南演示了如何向 XPS 文档添加矩形，为进一步探索奠定了坚实的基础。

## 常见问题解答

### Q1：Aspose.Page 是否与所有.NET 应用程序兼容？

A1：是的，Aspose.Page 旨在与所有 .NET 应用程序无缝协作。

### Q2：在哪里可以找到 Aspose.Page for .NET 的文档？

 A2：文档可用[这里](https://reference.aspose.com/page/net/).

### Q3：我可以在购买前免费试用 Aspose.Page for .NET 吗？

 A3：是的，您可以获得免费试用[这里](https://releases.aspose.com/).

### Q4：如何获得 Aspose.Page for .NET 的临时许可证？

A4：参观[这个链接](https://purchase.aspose.com/temporary-license/)获得临时许可证。

### Q5：我可以在哪里寻求社区支持或提出与 Aspose.Page for .NET 相关的问题？

 A5：访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)以获得社区支持。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
