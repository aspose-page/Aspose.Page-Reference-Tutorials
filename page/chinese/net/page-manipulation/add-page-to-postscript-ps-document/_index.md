---
date: 2026-03-03
description: 了解如何使用 Aspose.Page for .NET 设置自定义页面尺寸并向 PostScript 文档添加第二页。
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page 在 PS 文档中设置自定义页面大小
url: /zh/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 向 PostScript (PS) 文档添加页面 使用 Aspose.Page

## 介绍

在 .NET 开发中，能够 **设置自定义页面大小** 并 **添加第二个 PS 页面** 到 PostScript (PS) 文档，使您能够对生成的打印、报告或图形的布局进行精细控制。Aspose.Page for .NET 提供了简洁的面向对象 API，使此任务变得直截了当。在本教程中，您将学习如何创建多页 PS 文件，为每页定义自定义尺寸，并保存结果——只需几行 C# 代码。

## 快速答案
- **我可以设置自定义页面大小吗？** 是的——只需在打开页面时传入宽度和高度。  
- **如何添加第二个 PS 页面？** 再次调用 `document.OpenPage(width, height)`。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **我需要许可证吗？** 临时许可证可用于测试；生产环境需要正式许可证。  
- **在哪里可以下载 Aspose.Page？** 请从下面的官方下载页面获取。

## 前提条件

在开始本教程之前，请确保已具备以下前提条件：

- 具备 .NET 开发的实际经验。  
- 机器上已安装 Visual Studio。  
- Aspose.Page for .NET 库，可在[此处](https://releases.aspose.com/page/net/)下载。  
- 用于测试的首选文档目录。

## 导入命名空间

确保在项目中包含必要的命名空间，以访问 Aspose.Page 提供的功能。在示例中，命名空间已隐式包含，但仍需仔细检查并根据项目结构进行相应调整。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步骤 1：设置项目

在 Visual Studio 中创建一个新的 .NET 项目并进行必要的配置。确保在项目中引用 Aspose.Page 库。

## 设置自定义页面大小并添加第二个 PS 页面

本节演示如何为每页 **设置自定义页面大小**，以及如何在同一文档中 **添加第二个 ps 页面**。

### 步骤 2：初始化文档

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### 步骤 3：添加第一页（默认大小）

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### 步骤 4：使用不同（自定义）尺寸添加第二页

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### 步骤 5：保存文档

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

严格按照这些步骤操作，您即可使用 Aspose.Page for .NET 成功 **设置自定义页面大小** 并向 PostScript 文档添加 **第二个 PS 页面**。

## 为什么这很重要

- **精确布局** – 自定义页面尺寸可匹配打印机规格或创建独特的宣传册格式。  
- **多页** – 添加第二页（或更多）可实现多页报告，无需外部合并工具。  
- **跨平台** – 生成的 PS 文件可在任何兼容 PostScript 的设备上渲染，或随后转换为 PDF。

## 常见陷阱与故障排除

- **路径错误** – 确保 `dataDir` 以路径分隔符结尾，或使用 `Path.Combine`。  
- **许可证问题** – 没有有效许可证时，库可能会添加水印或限制页数。  
- **单位混淆** – 宽度和高度以点为单位（1 point = 1/72 英寸），请相应调整。

## 常见问题

**Q1: Aspose.Page 是否兼容不同的文档格式？**  
A1: Aspose.Page 主要专注于 PostScript 文档的操作。对于其他格式，您可以探索针对特定需求的 Aspose 系列库。

**Q2: 我可以在 Aspose.Page 中自定义页面大小吗？**  
A2: 当然！正如本教程所示，您可以根据需求为每页指定不同的尺寸。

**Q3: 我在哪里可以找到更多示例和文档？**  
A3: 请访问[文档](https://reference.aspose.com/page/net/)，获取全面信息和大量示例。

**Q4: 我如何获取 Aspose.Page 的临时许可证？**  
A4: 前往[此链接](https://purchase.aspose.com/temporary-license/)，获取用于测试的临时许可证。

**Q5: 我在哪里可以寻求社区支持或提问？**  
A5: 加入[Aspose.Page 社区论坛](https://forum.aspose.com/c/page/39)，与其他开发者交流、分享经验并获取帮助。

---

**最后更新：** 2026-03-03  
**已测试版本：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}