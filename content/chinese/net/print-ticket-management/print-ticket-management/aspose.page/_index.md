---
title: 使用 Aspose.Page for .NET 编辑现有的打印票证
linktitle: 编辑现有的打印票证
second_title: Aspose.Page .NET API
description: 了解使用 Aspose.Page for .NET 在 XPS 文档中编辑打印票据。开发人员的分步指南。轻松增强文档打印控制。
type: docs
weight: 11
url: /zh/net/print-ticket-management/print-ticket-management/aspose.page/
---
## 介绍

欢迎阅读这份关于使用 Aspose.Page for .NET 编辑现有打印票证的综合指南！ Aspose.Page 是一个功能强大的库，允许开发人员轻松处理 XPS 文档。在本教程中，我们将通过实际示例引导您完成编辑打印票证的过程，分解每个步骤以获得无缝的学习体验。

## 先决条件

在我们深入学习本教程之前，请确保您具备以下先决条件：

- C# 编程基础知识。
- Visual Studio 安装在您的计算机上。
- 下载 Aspose.Page for .NET 库并在您的项目中引用。

如果您尚未安装 Aspose.Page for .NET，可以下载它[这里](https://releases.aspose.com/page/net/).

## 导入命名空间

首先，将必要的命名空间导入到您的 C# 项目中。这确保您可以访问 Aspose.Page 功能。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

现在，让我们将您提供的示例代码分解为多个步骤。

## 第1步：设置文档目录

```csharp
//文档目录的路径。
string dir = "Your Document Directory";
```

在这里，替换`"Your Document Directory"`与 XPS 文档所在的实际路径。

## 第 2 步：打开带有打印票据的 XPS 文档

```csharp
//起始时间：3
XpsDocument xDocs = new XpsDocument(dir + "input3.xps");
JobPrintTicket pt = xDocs.JobPrintTicket;
//结束：3
```

此步骤涉及打开 XPS 文档并获取其 JobPrintTicket。

## 步骤 3：从作业打印单中删除参数

```csharp
//起始时间：4
pt.Remove(
	"ns0000:PageDevmodeSnapshot",
	"ns0000:JobInterleaving",
	"ns0000:JobImageType");
//结束：4
```

使用以下命令从 JobPrintTicket 中删除不需要的参数`Remove`方法。

## 步骤 4：向作业打印单添加参数

```csharp
//起始时间：5
pt.Add(
	new JobCopiesAllDocuments(2),
	new PageMediaSize(PageMediaSize.PageMediaSizeOption.ISOA4));
//结束：5
```

使用以下命令将所需参数添加到 JobPrintTicket`Add`方法。

## 步骤 5：保存带有更改的作业打印票的文档

```csharp
//起始时间：6
xDocs.Save(dir + "output3.xps");
//结束：6
```

使用更新的 JobPrintTicket 保存修改后的 XPS 文档。

重复这些步骤，即可使用 Aspose.Page for .NET 轻松编辑打印票据！

## 结论

恭喜！您已成功学习如何使用 Aspose.Page for .NET 编辑现有的打印票证。这个功能强大的库提供了处理 XPS 文档的灵活性和简便性，使其成为开发人员的宝贵工具。

## 经常问的问题

### Q1：我可以将 Aspose.Page for .NET 与其他文档格式一起使用吗？

A1：是的，Aspose.Page for .NET 主要关注 XPS 文档，但 Aspose 为不同格式提供了各种库。查看他们的文档以获取更多详细信息。

### Q2：Aspose.Page for .NET 与 .NET Core 兼容吗？

A2：是的，Aspose.Page for .NET 与 .NET Core 兼容，为您的开发环境提供灵活性。

### Q3：我如何获得与 Aspose.Page 相关的支持或提出问题？

 A3：访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)获得社区支持并与其他开发人员联系。

### 问题 4：Aspose.Page for .NET 是否有免费试用版？

 A4：是的，您可以获得免费试用[这里](https://releases.aspose.com/).

### Q5：如何获得 Aspose.Page for .NET 的临时许可证？

A5：参观[这个链接](https://purchase.aspose.com/temporary-license/)获得临时许可证。