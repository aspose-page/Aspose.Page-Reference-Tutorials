---
date: 2026-03-21
description: 学习如何使用 Aspose.Page for .NET 在 C# 中创建包含 Unicode 文本的 PostScript 文档——一种快速提升文档处理的方式。
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: 使用 C# 创建带 Unicode 文本的 PostScript 文档 – Aspose.Page
url: /zh/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 向 PostScript (PS) 添加 Unicode 字符串文本

## 介绍

如果您需要 **create a PostScript document C#** 并嵌入 Unicode 字符，Aspose.Page for .NET 让此过程变得简单。在本教程中，我们将通过一个完整的动手示例，展示如何向 PS 文件添加日文文本（或任何 Unicode 字符串），选择自定义字体并保存结果。完成后，您将拥有一个可在任何 C# 项目中使用的可复用代码片段。

## 快速答案
- **本教程涵盖什么内容？** 使用 Aspose.Page 在 C# 中向 PostScript 文件添加 Unicode 文本。
- **需要哪个库？** Aspose.Page for .NET（最新版本）。
- **需要特殊字体吗？** 任何支持所需 Unicode 范围的 TrueType/OpenType 字体，例如 *Arial Unicode MS*。
- **代码行数是多少？** 大约 30 行，分为清晰的步骤。
- **需要许可证吗？** 临时许可证可用于评估；生产环境需要正式许可证。

## 什么是 “create postscript document c#”？

在 C# 中创建 PostScript 文档是指以编程方式生成符合 PostScript 语言规范的 .ps 文件。Aspose.Page 抽象了底层细节，让您专注于文本、图形和字体等内容。

## 为什么使用 Aspose.Page 处理 Unicode 文本？

- **完整的 Unicode 支持** – 渲染任何语言的字符，无需手动编码。
- **设备无关** – 相同代码可用于 PS、EPS 和 PDF 输出。
- **无外部依赖** – 库内部处理字体加载和字形映射。

## 前提条件

- 对 C# 和 .NET 开发有基本了解。
- 已安装 Aspose.Page for .NET 库。您可以从 [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) 下载。
- 包含您计划使用的字体的文件夹（例如 *Arial Unicode MS*）。

## 导入命名空间

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步骤 1：设置文档目录和字体文件夹

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## 步骤 2：为 PostScript 文档创建输出流

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## 步骤 3：使用自定义字体添加 Unicode 文本

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## 步骤 4：关闭当前页面

```csharp
document.ClosePage();
```

## 步骤 5：完成并保存文档

```csharp
document.Save();
```

## 常见问题及解决方案

- **未找到字体** – 确保 `AdditionalFontsFolders` 路径指向包含 .ttf/.otf 文件的文件夹，并且字体名称完全匹配。
- **乱码字符** – 验证源字符串在 C# 源文件中已编码为 UTF‑8（如有需要使用 `#pragma warning disable 1591`）。
- **文件未创建** – 检查 `dataDir` 的写入权限以及流是否已正确释放（`using` 块会处理此问题）。

## 常见问答

**Q: 我可以在其他编程语言中使用 Aspose.Page for .NET 吗？**  
A: Aspose.Page 主要面向 .NET，但也提供 Java 等等价实现。

**Q: 如何获取 Aspose.Page for .NET 的临时许可证？**  
A: 请访问 [Temporary License](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**Q: 是否有 Aspose.Page 讨论的社区论坛？**  
A: 有，访问 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 获取社区支持。

**Q: Aspose.Page for .NET 支持哪些格式？**  
A: Aspose.Page 支持多种格式，包括 XPS、PS、EPS、PDF 等。

**Q: 我可以自定义添加文本的外观吗？**  
A: 可以，您可以在 Aspose.Page 中自定义文本的字体、大小、颜色及其他属性。

## 结论

在本教程中，我们演示了如何 **create a PostScript document C#** 并使用 Aspose.Page 嵌入 Unicode 文本。按照上述步骤，您可以快速将多语言文本渲染集成到任何 .NET 应用程序中，全面掌控文档生成和布局。

---

**最后更新：** 2026-03-21  
**测试版本：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}