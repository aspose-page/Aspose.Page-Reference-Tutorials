---
date: 2026-03-19
description: 了解如何通过使用 Aspose.Page for .NET 创建自定义打印票据来添加票据。通过细粒度的控制定制您的打印体验。
linktitle: Create Custom Print Ticket
second_title: Aspose.Page .NET API
title: 如何添加票据：使用 Aspose.Page for .NET 创建自定义打印票据
url: /zh/net/print-ticket-management/create-custom-print-ticket/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何添加票据：使用 Aspose.Page for .NET 创建自定义打印票据

## 介绍

如果您需要在 .NET 应用程序中实现 **如何添加票据** 功能，Aspose.Page 能让您直接通过代码生成自定义打印票据。本教程将完整演示整个过程——环境搭建、创建 XPS 文档、附加自定义作业打印票据以及保存结果。完成后，您即可自信地在任何打印工作流中添加票据支持。

## 快速答复
- **“添加票据”是什么意思？** 它指的是嵌入自定义打印票据（XPS 元数据），用于控制打印机设置。  
- **需要哪个库？** Aspose.Page for .NET。  
- **需要许可证吗？** 评估期间可使用临时许可证；生产环境必须使用正式许可证。  
- **可以在 .NET Core 上使用吗？** 可以，Aspose.Page 支持 .NET Framework 和 .NET Core。  
- **实现大概需要多长时间？** 基本票据通常在 15 分钟以内完成。

## 什么是自定义打印票据？
自定义打印票据是一种基于 XML 的打印机首选项描述（如装订、份数、颜色管理等），随 XPS 文档一起传输。它允许开发者以编程方式指定文档的打印方式，省去客户端的手动配置。

## 为什么使用 Aspose.Page 添加票据支持？
- **细粒度控制：** 可在代码中设置装订、份数、介质类型等。  
- **跨平台一致性：** 同一票据可在任何支持 XPS 元数据的打印机上使用。  
- **无缝集成：** 直接在现有 .NET 项目中使用，无需额外服务。

## 前置条件

在开始之前，请确保您具备：

- C# 与 .NET 开发的基本能力。  
- 已安装 Visual Studio（任意近期版本）。  
- 已在项目中添加 Aspose.Page for .NET 库。  

如果尚未添加库，可从 [Aspose.Page for .NET 文档](https://reference.aspose.com/page/net/) 下载。社区帮助请访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39)。

## 导入命名空间

首先引入提供 XPS 与元数据类的命名空间。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

下面我们将逐步拆解实现过程。

## 步骤 1：设置文档目录

定义生成的 XPS 文件保存位置。

```csharp
string dir = "Your Document Directory";
```

## 步骤 2：创建新 XPS 文档

实例化一个新的 XPS 文档，用于保存页面和票据。

```csharp
XpsDocument xDocs = new XpsDocument();
```

## 步骤 3：添加自定义作业打印票据

将自定义作业打印票据附加到文档。这是 **如何添加票据** 功能的核心——在此指定装订、份数、渲染意图、颜色管理以及其他所需设置。

```csharp
xDocs.JobPrintTicket = new JobPrintTicket(
    new PageDevModeSnaphot("SABlAGwAbABvACEAAAA="),
    new DocumentCollate(Collate.CollateOption.Collated),
    // Add other print settings as needed
);
```

> **小贴士：** 将占位符快照字符串替换为与打印机能力匹配的 Base64 编码 DEVMODE 结构。

## 步骤 4：保存文档

将 XPS 文档（含嵌入的票据）持久化到磁盘。

```csharp
xDocs.Save(dir + "output1.xps");
```

当您在支持 XPS 元数据的查看器中打开 *output1.xps* 时，打印机会自动应用票据中定义的设置。

## 常见问题与解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| 票据未生效 | 查看器忽略 XPS 元数据 | 使用支持 XPS 打印票据的打印机驱动或 Microsoft XPS Viewer 等查看器。 |
| Base64 快照无效 | DEVMODE 数据损坏 | 使用 `GetPrinter` API 从打印机驱动重新生成快照。 |
| 权限不足 | 对 `dir` 的写入被拒绝 | 确保应用程序拥有足够的文件系统权限。 |

## 常见问答

**问：Aspose.Page for .NET 能否与其他 .NET 框架一起使用？**  
答：可以，Aspose.Page 支持 .NET Framework、.NET Core、.NET 5/6 及更高版本。

**问：如何获取 Aspose.Page 的临时许可证？**  
答：访问 [此链接](https://purchase.aspose.com/temporary-license/) 获取 Aspose.Page 的临时许可证。

**问：是否有 Aspose.Page 的社区论坛？**  
答：当然，您可以在 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 找到有价值的讨论和支持。

**问：自定义打印票据支持哪些介质类型？**  
答：Aspose.Page 支持多种介质类型，包括普通纸、光面纸以及自定义介质定义。

**问：是否有 Aspose.Page for .NET 的示例项目？**  
答：请查阅 [文档](https://reference.aspose.com/page/net/)，其中提供了示例项目和代码片段，帮助您快速入门。

## 结论

我们已经介绍了使用 Aspose.Page for .NET 为 XPS 文档添加 **如何添加票据** 支持的完整步骤。通过这些步骤，您可以将丰富的打印指令直接嵌入文件，从而在 .NET 应用程序内部完全掌控打印工作流。欢迎尝试更多票据设置，以匹配您的特定打印环境。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-03-19  
**测试环境：** Aspose.Page for .NET（最新稳定版）  
**作者：** Aspose  

---