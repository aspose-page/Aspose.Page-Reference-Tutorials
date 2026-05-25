---
date: 2026-01-20
description: 学习如何使用 Aspose.Page for .NET 创建 XPS 文档、添加矩形并保存 XPS 文件的分步指南。
linktitle: Add Rectangle to XPS Document
second_title: Aspose.Page .NET API
title: 创建 XPS 文档：使用 Aspose.Page for .NET 添加矩形
url: /zh/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 XPS 文档：使用 Aspose.Page for .NET 添加矩形

## Introduction

在本教程中，您将使用 Aspose.Page for .NET 库 **创建 XPS 文档** 并在其中绘制矩形。添加矩形等形状是需要以编程方式生成发票、报告或自定义图形时的常见需求。按照以下步骤操作，您将在几分钟内拥有可直接使用的 XPS 文件。

## Quick Answers
- **我可以生成什么？** XPS 文档，包含矢量图形和文本。  
- **使用哪个库？** Aspose.Page for .NET（提供免费试用）。  
- **需要多长时间？** 实现并运行大约需要 5‑10 分钟。  
- **我需要许可证吗？** 生产使用需要临时许可证。  
- **我可以将结果保存为 XPS 文件吗？** 是的——`Save` 方法会将 **保存的 XPS 文件** 写入磁盘。

## What is “create XPS document”?

创建 XPS 文档是指以编程方式构建符合 XML Paper Specification（XML 纸张规范）格式的页面描述。生成的文件分辨率无关，适合跨平台的打印和高质量显示。

## Why use Aspose.Page to create XPS document?

- **完整的 .NET 支持** – 兼容 .NET Framework、.NET Core 和 .NET 5/6+。  
- **丰富的绘图 API** – 包含路径几何、画刷、画笔和文本处理。  
- **无外部依赖** – 所有功能均在进程内运行，无需 Office 或 Acrobat。  

## Prerequisites

在开始之前，请确保您具备以下条件：

1. **Aspose.Page for .NET** – 在[此处](https://releases.aspose.com/page/net/)下载。  
2. **可写文件夹**，用于存放生成的 XPS 文件。

## Import Namespaces

在 .NET 项目中，导入所需的命名空间：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Set the Document Directory

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **小贴士：** 使用绝对路径或 `Path.Combine`，以避免不同操作系统上的路径分隔符问题。

## Step 2: Create a New XPS Document

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

此时，您已经 **创建了 XPS 文档** 对象，用于容纳所有绘图元素。

## Step 3: Add a Rectangle (using create path geometry)

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

`CreatePathGeometry` 调用 **创建路径几何**，定义矩形的轮廓。您可以修改类似 SVG 的命令字符串以绘制其他形状。

## Step 4: Save the Document (save XPS file)

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

调用 `Save` 将 **保存的 XPS 文件** 写入您指定的位置。

Congratulations! 您已成功 **创建 XPS 文档**，添加矩形并保存文件。

## Common Issues and Solutions

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| `doc.Save` 时出现 `FileNotFoundException` | `dataDir` 指向不存在的文件夹 | 确保目录存在，或使用 `Directory.CreateDirectory(dataDir)` 创建它。 |
| 矩形不可见 | 缺少描边颜色配置文件或路径几何格式错误 | 检查 ICC 文件路径以及几何字符串 (`M … Z`)。 |
| 大型文档性能下降 | 过多的单独 `AddPath` 调用 | 批量绘制操作或复用画刷/画笔对象。 |

## Frequently Asked Questions

**问：Aspose.Page 与所有 .NET 应用程序兼容吗？**  
答：是的，Aspose.Page 旨在与所有 .NET 应用程序无缝配合。

**问：在哪里可以找到 Aspose.Page for .NET 的文档？**  
答：文档可在[此处](https://reference.aspose.com/page/net/)获取。

**问：在购买前我可以免费试用 Aspose.Page for .NET 吗？**  
答：可以，免费试用请前往[此处](https://releases.aspose.com/)。

**问：如何获取 Aspose.Page for .NET 的临时许可证？**  
答：请访问[此链接](https://purchase.aspose.com/temporary-license/)获取临时许可证。

**问：在哪里可以获取社区支持或提问关于 Aspose.Page for .NET 的问题？**  
答：请前往[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)获取社区支持。

---

**最后更新：** 2026-01-20  
**测试环境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}