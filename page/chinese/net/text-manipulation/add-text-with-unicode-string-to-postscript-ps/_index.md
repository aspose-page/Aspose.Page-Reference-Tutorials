---
title: 使用 Aspose.Page 将带有 Unicode 字符串的文本添加到 PostScript (PS)
linktitle: 将带有 Unicode 字符串的文本添加到 PostScript (PS)
second_title: Aspose.Page .NET API
description: 了解如何使用 Aspose.Page for .NET 将 Unicode 文本添加到 PostScript 文件中。轻松增强文档操作。
type: docs
weight: 11
url: /zh/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
---
## 介绍

在文档操作领域，Aspose.Page for .NET 作为一个强大的库脱颖而出，使开发人员能够创建、编辑和转换各种文档格式。其强大的功能之一是能够使用 Unicode 字符串将文本添加到 PostScript (PS) 文件中。在本教程中，我们将探索完成此任务的分步指南，为使用 Aspose.Page 的开发人员提供无缝体验。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

- C# 编程语言的应用知识。
- 安装了 .NET 库的 Aspose.Page。您可以从[.NET 文档的 Aspose.Page](https://reference.aspose.com/page/net/).
- 设置了必要配置的开发环境。

## 导入命名空间

在您的 C# 代码中，导入使用 Aspose.Page for .NET 功能所需的命名空间：

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 第 1 步：设置文档目录和字体文件夹

```csharp
//文档目录的路径。
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## 步骤 2：为 PostScript 文档创建输出流

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    //创建 A4 尺寸的保存选项
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    //...（可以在此处设置其他选项）
    
    //创建新的 1 页 PS 文档
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ...（进一步的步骤将在下面解释）
    
    //保存文档
    document.Save();
}
```

## 步骤 3：添加带有自定义字体的 Unicode 文本

```csharp
string str = "試してみます.";  //统一码文本
int fontSize = 48;

//使用自定义字体填充文本
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## 第四步：关闭当前页面

```csharp
document.ClosePage();
```

## 第 5 步：完成并保存文档

```csharp
document.Save();
```

## 结论

在本教程中，我们演示了使用 Aspose.Page for .NET 将 Unicode 文本添加到 PostScript 文档的过程。利用其强大的功能，开发人员可以增强其文档操作工作流程，确保灵活性和精确性。

## 常见问题解答

### Q1：我可以将 Aspose.Page for .NET 与其他编程语言一起使用吗？

A1：Aspose.Page 主要是为.NET 设计的，但也有其他适用于Java 的版本。

### 问题 2：如何获得 Aspose.Page for .NET 的临时许可证？

 A2：参观[临时牌照](https://purchase.aspose.com/temporary-license/)以获得临时许可证。

### Q3：有 Aspose.Page 讨论的社区论坛吗？

 A3：是的，请访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)以获得社区支持。

### Q4：Aspose.Page for .NET 可以使用哪些格式？

A4：Aspose.Page支持多种格式，包括XPS、PS、EPS、PDF等。

### Q5：我可以自定义添加文本的外观吗？

A5：是的，您可以在Aspose.Page中自定义文本的字体、大小、颜色和其他属性。