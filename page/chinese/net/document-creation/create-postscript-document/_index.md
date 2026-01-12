---
date: 2026-01-12
description: 学习如何在 .NET 中使用 Aspose.Page 创建 PostScript 文档。本分步指南展示了如何创建 PostScript 文件、设置
  PostScript 页面尺寸以及自定义边距，以实现无缝集成。
linktitle: Create PostScript Document
second_title: Aspose.Page .NET API
title: 如何使用 Aspose.Page for .NET 创建 PostScript 文档
url: /zh/net/document-creation/create-postscript-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page for .NET 创建 PostScript 文档

## 介绍

欢迎！在本综合教程中，您将学习如何使用 Aspose.Page for .NET 以编程方式 **创建 PostScript** 文档。无论是生成发票、运单标签，还是任何基于矢量的打印输出，本指南将一步步带您完成——从环境搭建到保存最终的 *.ps* 文件。让我们深入了解，只需几行 C# 代码即可轻松生成高质量的 PostScript 文件。

## 快速回答
- **需要的库是什么？** Aspose.Page for .NET  
- **我可以设置页面尺寸吗？** 是的 – 使用 `options.PageSize`（参见 “set PostScript page size”）。  
- **开发时需要许可证吗？** 免费试用可用于测试；生产环境需要许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **实现需要多长时间？** 对于基本文档通常在 10 分钟以内。

## 什么是 .NET 中的 “创建 PostScript”？
Aspose.Page 提供了功能丰富的 API，抽象了底层的 EPS/PostScript 语法，让您专注于页面布局、图形和文本。使用该库可避免手写 PS 代码，并获得对字体、图像和精确度量的支持。

## 为什么使用 Aspose.Page 来创建 PostScript？
- **完全控制** 页面尺寸、边距和绘图原语。  
- **无外部依赖** – 所有操作都在您的 .NET 进程中运行。  
- **跨平台** 支持 Windows、Linux 和 macOS。  
- **强大的字体处理**，包括自定义字体文件夹。

## 前置条件

- Aspose.Page for .NET 库：确保已安装 Aspose.Page for .NET 库。您可以从 [here](https://releases.aspose.com/page/net/) 下载。  
- .NET 环境：确保您的机器上已设置好可用的 .NET 环境。  
- 文本编辑器或 IDE：使用您喜欢的文本编辑器或集成开发环境（IDE）进行编码。

现在一切准备就绪，让我们开始构建文档。

## 导入命名空间

首先，导入提供对核心 Aspose.Page 类访问的命名空间。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.IO;
```

这些命名空间公开了教程中使用的 `PsDocument`、`PsSaveOptions` 和实用类。

## 步骤 1：设置文档目录

```csharp
string dir = "Your Document Directory";
```

将 `"Your Document Directory"` 替换为您希望保存最终 **PostScript** 文件的绝对或相对路径。

## 步骤 2：创建输出流

```csharp
using (Stream outPsStream = new FileStream(dir + "document.ps", FileMode.Create))
```

`FileStream` 打开一个名为 **document.ps** 的可写流。所有后续的绘图命令都将写入此流。

## 步骤 3：创建保存选项

```csharp
PsSaveOptions options = new PsSaveOptions();
```

`PsSaveOptions` 允许您配置文档的渲染和保存方式。

## 步骤 4：设置 PostScript 页面尺寸和边距

```csharp
options.PageSize = PageConstants.GetSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT);
options.Margins = PageConstants.GetMargins(PageConstants.MARGINS_ZERO);
```

这里我们 **设置 PostScript 页面尺寸** 为 A4 纵向并去除所有边距。您可以将 `SIZE_A4` 替换为其他常量（例如 `SIZE_LETTER`），以满足您的布局需求。

## 步骤 5：设置额外的字体文件夹

```csharp
options.AdditionalFontsFolders = new string[] { dir };
```

如果文档使用系统未安装的自定义字体，请将 Aspose.Page 指向包含这些字体文件的文件夹。

## 步骤 6：创建多页文档

```csharp
bool multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

`PsDocument` 实例代表 PostScript 文档。将 `multiPaged` 设置为 `false` 会创建单页文档（如需多页输出可切换为 `true`）。

## 步骤 7：关闭并保存

```csharp
document.ClosePage();
document.Save();
```

调用 `ClosePage()` 完成页面内容的结束，`Save()` 将完整的 PostScript 流写入磁盘。

恭喜！您已经学习了如何使用 Aspose.Page for .NET **创建 PostScript** 文档。

## 常见问题及解决方案

- **文件路径错误** – 确保 `dir` 变量以路径分隔符（`\` 或 `/`）结尾，或使用 `Path.Combine`。  
- **缺少字体** – 如果文本显示为默认字体，请确认 `options.AdditionalFontsFolders` 指向正确的目录。  
- **页面尺寸不正确** – 仔细检查传递给 `PageConstants.GetSize` 的常量；您也可以通过 `new SizeF(width, height)` 提供自定义尺寸。

## 常见问答

### Q1：在哪里可以找到 Aspose.Page for .NET 的文档？
A1：文档可在 [here](https://reference.aspose.com/page/net/) 查看。

### Q2：如何下载 Aspose.Page for .NET？
A2：您可以从 [this link](https://releases.aspose.com/page/net/) 下载。

### Q3：在哪里可以购买 Aspose.Page for .NET 的许可证？
A3：您可以在 [here](https://purchase.aspose.com/buy) 购买许可证。

### Q4：Aspose.Page for .NET 是否提供免费试用？
A4：是的，您可以在 [here](https://releases.aspose.com/) 找到免费试用。

### Q5：如何获取 Aspose.Page for .NET 的临时许可证？
A5：可在 [here](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

### Q6：我可以生成多页 PostScript 文件吗？
A6：当然可以。在构造 `PsDocument` 时将 `bool multiPaged = true`，并在每个额外页面调用 `document.NewPage()`。

### Q7：Aspose.Page 是否支持颜色管理？
A7：是的，如有需要，您可以通过 `PsSaveOptions.ColorProfile` 嵌入 ICC 配置文件。

---

**最后更新：** 2026-01-12  
**测试环境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}