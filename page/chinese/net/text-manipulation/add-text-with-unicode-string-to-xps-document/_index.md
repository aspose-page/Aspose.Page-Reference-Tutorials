---
date: 2026-03-21
description: 了解如何使用 Aspose.Page for .NET 向 XPS 文档添加 Unicode 文本。本指南展示了如何使用 C# 创建 XPS
  文档以及使用 Aspose.Page 添加 Unicode 字符串文本。
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: 如何使用 Aspose.Page 向 XPS 文档添加 Unicode 文本
url: /zh/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page 向 XPS 文档添加 Unicode 文本

## Introduction

如果您需要 **how to add unicode** 字符到 XPS 文件，您来对地方了。在本教程中，我们将逐步演示使用 Aspose.Page for .NET 以 **create XPS document C#** 风格创建 XPS 文档的完整步骤，并展示 **aspose page add text** 功能如何使用 Unicode 字符串。完成后，您将拥有一个能够正确显示从右到左 (RTL) Unicode 文本的完整 XPS 文档。

## Quick Answers
- **本教程涵盖了什么？** 使用 Aspose.Page for .NET 向 XPS 文档添加 Unicode 文本。  
- **使用的语言是什么？** C#（兼容 .NET Framework 和 .NET Core）。  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证。  
- **我可以更改字体或大小吗？** 是的——示例使用 Arial 20 pt，但任何已安装的字体均可使用。  
- **是否包含 RTL 支持？** 将 `BidiLevel = 1` 设置为右到左渲染 Unicode 字符串。

## 在 XPS 中，“how to add unicode” 是什么？

添加 Unicode 文本意味着将来自任何语言——阿拉伯语、希伯来语、中文等——的字符插入到 XPS 文档中。Aspose.Page 的 `XpsGlyphs` 类负责低层的字形定位，而 `BidiLevel` 属性控制 RTL 脚本的文本方向。

## 为什么使用 Aspose.Page 添加文本？

- **完整的 .NET 集成** – 支持 .NET Framework、.NET Core、.NET 5/6+。  
- **无外部依赖** – 纯托管代码，无 COM 互操作。  
- **丰富的排版支持** – 字体、样式、颜色以及双向文本。  
- **高性能** – 快速创建并保存 XPS 文件，适合服务器端生成。

## Prerequisites

- 具备 C# 和 .NET 开发的基础知识。  
- Visual Studio（任意近期版本）。  
- Aspose.Page for .NET 库——从 [here](https://releases.aspose.com/page/net/) 下载。

## Import Namespaces

首先，导入能够访问 XPS 模型和绘图工具的命名空间。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Set up the Document – create XPS document C#

创建一个全新的 XPS 文档，用于容纳 Unicode 文本。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Step 2: Add Unicode Text – aspose page add text

现在我们添加实际的 Unicode 字符串。示例使用 Arial 字体，大小 20，位置位于 (400 f, 200 f)。`BidiLevel` 为 1 告诉渲染器将字符串视为从右到左。

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Step 3: Save the Document

最后，将 XPS 文件持久化到磁盘。

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

恭喜！您已成功使用 Aspose.Page for .NET 向 XPS 文档 **how to add unicode** 文本。

## Common Issues and Solutions

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| 文本出现乱码 | 字体不支持该 Unicode 范围 | 使用包含所需字形的字体（例如 Arial Unicode MS）。 |
| RTL 文本仍然从左到右 | `BidiLevel` 未设置或设置为 0 | 确保对 RTL 脚本设置 `glyphs.BidiLevel = 1;`。 |
| 文件未保存 | `dataDir` 路径无效 | 确认目录存在且应用拥有写入权限。 |

## Frequently Asked Questions

**Q: Aspose.Page 是否兼容最新的 .NET 框架？**  
A: 是的，Aspose.Page 会定期更新以支持 .NET Framework、.NET Core 和 .NET 5/6+。

**Q: 添加文本时我可以自定义字体样式和大小吗？**  
A: 当然！`AddGlyphs` 方法允许您指定任意字体族、大小和 `FontStyle`。

**Q: 我可以在哪里找到 Aspose.Page 的更多文档？**  
A: 您可以参考文档 [here](https://reference.aspose.com/page/net/) 获取完整的 API 细节。

**Q: 有哪些免费资源可以帮助我快速入门 Aspose.Page？**  
A: 有，您可以在 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 社区论坛中查找技巧、示例和同行支持。

**Q: 在购买前是否有试用版可供使用？**  
A: 当然！从 [here](https://releases.aspose.com/) 下载免费试用版以评估该库。

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}