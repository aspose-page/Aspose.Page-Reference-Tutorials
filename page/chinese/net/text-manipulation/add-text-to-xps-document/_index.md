---
date: 2026-03-21
description: 学习如何使用 Aspose.Page for .NET 创建 XPS 文档并添加文本。面向 .NET 开发者的逐步指南。
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page 在 .NET 中创建 XPS 文档并添加文本
url: /zh/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 在 .NET 中创建 XPS 文档并添加文本

在现代 .NET 开发中，能够以编程方式 **创建 XPS 文档 .NET** 文件是一项有价值的技能，尤其是当你需要生成可打印的报告、发票或自定义图形时。本教程将手把手教你使用 Aspose.Page **aspose.page add text** 向 XPS 文档添加文本，让你在 .NET 应用程序中完全掌控布局和样式。

## 快速回答
- **本教程涵盖什么内容？** 使用 Aspose.Page for .NET 向新建的 XPS 文档添加文本。  
- **需要多长时间？** 基本实现约需 5‑10 分钟。  
- **前置条件是什么？** .NET 开发环境和 Aspose.Page 库。  
- **需要许可证吗？** 是的，生产环境必须使用有效的 Aspose.Page 许可证。  
- **能在 .NET Core / .NET 6+ 上运行吗？** 完全可以——Aspose.Page 支持所有近期的 .NET 版本。

## 什么是 create xps document .net？

在 .NET 中创建 XPS 文档指生成一种固定布局文件，能够在不同设备和打印机上保持内容的精确外观。XPS（XML Paper Specification）是微软的开放页面描述标准，类似 PDF，但完全基于 XML。

## 为什么使用 Aspose.Page 添加文本？

Aspose.Page 提供了高级、面向对象的 API，抽象了底层的 XPS 标记。你可以在不直接操作原始 XML 的情况下添加文本、图形和形状，从而让开发过程更快、更不易出错。

## 前置条件

- Aspose.Page for .NET：确保已安装 Aspose.Page 库。可从 [Aspose.Page for .NET 文档](https://reference.aspose.com/page/net/) 下载。  
- 开发环境：搭建好 .NET 开发环境。如果尚未完成，请参照 [文档](https://reference.aspose.com/page/net/) 中的安装说明。  
- 文档目录：创建一个用于存放文档的目录。将示例代码中的 “Your Document Directory” 替换为实际路径。

了解完基础后，让我们进入代码实现。

## 导入命名空间

首先，导入项目所需的命名空间：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 步骤 1：创建 XPS 文档 .NET

创建一个全新的 XPS 文档，作为文本的画布。

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## 步骤 2：为文本创建画笔

定义一个实色画笔来决定文本颜色，这里使用黑色。

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## 步骤 3：添加字形（aspose.page add text）

字形是 XPS 文档中字符的底层表示。此调用将在指定坐标处添加文本 “Hello World!”。

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## 步骤 4：保存生成的 XPS 文档

将文档持久化到磁盘，以便后续查看或打印。

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

通过以上步骤，你已经成功 **create XPS document .NET** 并使用 Aspose.Page 添加了自定义文本。

## 常见问题及解决方案

| 问题 | 原因 | 解决办法 |
|------|------|----------|
| **保存时文件未找到** | `dataDir` 指向不存在的文件夹 | 确认目录已创建，或在保存前使用 `Directory.CreateDirectory(dataDir)`。 |
| **文本不可见** | 画笔颜色与背景相同 | 将 `Color.Black` 改为其他对比度更高的颜色。 |
| **不支持的字体** | 机器上未安装该字体 | 使用保证已安装的字体，或通过 Aspose.Page 的字体嵌入功能嵌入字体。 |

## 常见问答

### Q1：我可以自定义添加文本的字体和大小吗？

A1：可以，完全由你控制。只需在 `AddGlyphs` 方法中相应地设置参数即可。

### Q2：Aspose.Page 与 .NET Core 兼容吗？

A2：完全兼容！Aspose.Page 支持 .NET Core，确保与最新的 .NET 技术栈兼容。

### Q3：使用 Aspose.Page 是否有许可证要求？

A3：是的，需要有效的许可证。请在 [此处](https://purchase.aspose.com/buy) 查看授权选项。

### Q4：我该如何获取支持或求助？

A4：访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 与社区交流并获取帮助。

### Q5：是否提供免费试用？

A5：当然！你可以在 [此处](https://releases.aspose.com/) 获取免费试用。

**其他问答**

**问：我可以在同一页上添加多个文本块吗？**  
答：可以，只需对不同坐标多次调用 `doc.AddGlyphs` 即可。

**问：Aspose.Page 支持文本旋转吗？**  
答：可以对 `XpsGlyphs` 对象应用变换矩阵，实现旋转或倾斜效果。

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**最后更新：** 2026-03-21  
**测试环境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

---