---
date: 2026-03-19
description: 学习如何使用 Aspose.Page for .NET **删除 XPS 页面** 文档和 **按索引删除页面**——完整的逐步指南，包含前置条件、代码示例和常见问题解答。
linktitle: Remove Page from XPS Document
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page for .NET 从 XPS 文档中删除页面
url: /zh/net/page-manipulation/remove-page-from-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 从 XPS 文档中删除页面 使用 Aspose.Page for .NET

## Introduction

如果您需要以编程方式**删除 XPS 页面**文件，Aspose.Page for .NET 为您提供一种干净、可靠的方式来实现。在本教程中，我们将逐步演示删除 XPS 文档中特定页面的确切步骤，解释此操作的重要性，并展示如何将更新后的文件保存回磁盘。

## Quick Answers
- **“remove page xps” 是什么意思？** 它指的是从 XPS（XML Paper Specification）文档中删除单个页面。  
- **哪个方法用于删除页面？** 使用 `RemovePageAt(index)`，其中 index 为从零开始的索引。  
- **我可以在任意位置删除页面吗？** 可以——您可以根据需要**在索引** 0、1、2 等处**删除页面**。  
- **使用 Aspose.Page 是否需要许可证？** 测试时需要临时许可证；生产环境需要正式许可证。  
- **代码是否兼容 .NET 6？** 完全兼容——Aspose.Page 支持 .NET Framework、.NET Core 以及 .NET 5/6。

## What is “remove page xps”?
从 XPS 文档中删除页面意味着在保留文档其余内容、布局和元数据的同时，去除其中的一页。此操作在需要裁剪 PDF、生成自定义报告或遵守文档大小限制时非常有用。

## Why use Aspose.Page for .NET?
- **无外部依赖** – 纯 .NET 库。  
- **高保真** – 保持矢量图形和布局精度。  
- **跨平台** – 在 Windows、Linux 和 macOS 上运行。  
- **简洁 API** – 单个方法调用（`RemovePageAt`）即可完成繁重工作。

## Prerequisites

在深入代码之前，请确保您已具备以下条件：

- **Aspose.Page for .NET** – 从 [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) 下载。  
- 一个 **.NET 开发环境**（Visual Studio、VS Code 或您喜欢的任何 IDE）。  
- 一个 **示例 XPS 文档**（例如 `Sample.xps`），放置在项目可以引用的文件夹中。

## Import Namespaces

在 C# 文件顶部添加所需的命名空间，以便编译器能够找到 XPS 类。

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

> **小贴士：** 使用 `Path.Combine` 进行跨平台路径构建。

## Step 2: Create a New XPS Document

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument(dataDir + "Sample.xps");
// ExEnd:4
```

此行代码将现有的 XPS 文件（`Sample.xps`）加载到 `XpsDocument` 对象中，准备进行操作。

## Step 3: Delete Page at Index

```csharp
// ExStart:5
// Remove the first page (at index 1).
doc.RemovePageAt(1);
// ExEnd:5
```

`RemovePageAt` 方法**删除指定索引处的页面**。请记住索引从 0 开始，因此 `1` 删除第二页。根据需要调整索引以定位要删除的页面。

## Step 4: Save the Resultant XPS Document

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "Sample_out.xps");
// ExEnd:6
```

删除后，文档会保存为 `Sample_out.xps`。您现在可以打开此文件，确认不需要的页面已被移除。

## Common Issues and Solutions

| 问题 | 原因 | 解决方案 |
|-------|-------|-----|
| **索引超出范围** | 尝试删除不存在的页面。 | 在调用 `RemovePageAt` 前使用 `doc.Pages.Count` 验证页面数量。 |
| **文件被锁定** | XPS 文件正被其他程序打开。 | 关闭所有查看器或确保文件未被占用后再运行代码。 |
| **未应用许可证** | 在生产环境中未使用有效许可证使用库。 | 使用 `License license = new License(); license.SetLicense("Aspose.Page.lic");` 应用临时或永久许可证。 |

## Frequently Asked Questions

**Q1：我可以一次删除多个页面吗，使用 Aspose.Page for .NET？**  
A1：可以，只需重复调用 `RemovePageAt`，或遍历索引列表进行循环（记得从最高索引向最低索引删除，以保持剩余索引的有效性）。

**Q2：Aspose.Page 是否兼容最新的 .NET 框架？**  
A2：Aspose.Page 会定期更新，以支持最新的 .NET 版本，包括 .NET 6 和 .NET 7。

**Q3：我可以在商业应用中使用 Aspose.Page 吗？**  
A3：当然可以。有关许可证详情，请访问 [Aspose.Purchase](https://purchase.aspose.com/buy) 页面。

**Q4：我在哪里可以找到关于 Aspose.Page 的更多支持和讨论？**  
A4：加入 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 社区，获取技巧、示例和故障排除帮助。

**Q5：测试 Aspose.Page 是否需要临时许可证？**  
A5：是的，您可以获取 [临时许可证](https://purchase.aspose.com/temporary-license/)，在购买前评估该库。

**Q6：删除页面后如何保留文档元数据？**  
A6：`RemovePageAt` 方法会自动保留原始元数据。如果需要修改，可使用 `doc.DocumentProperties` 集合。

## Conclusion

您现在已经学习了如何使用 Aspose.Page for .NET **删除 XPS 页面** 文档以及 **按索引删除页面**。这种简洁的方法让您能够将页面删除逻辑直接集成到 .NET 应用程序中，全面控制 XPS 文档内容。

---

**最后更新：** 2026-03-19  
**测试环境：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}