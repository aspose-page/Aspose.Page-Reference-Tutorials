---
title: 使用 Aspose.Page 添加数组项
linktitle: 添加数组项
second_title: Aspose.Page .NET API
description: 探索如何使用 Aspose.Page for .NET 在 EPS 文件中添加数组项。请按照我们的分步指南进行无缝文档操作。
type: docs
weight: 11
url: /zh/net/eps-metadata-management/modify-eps-metadata-add-array-items/
---
## 介绍

在 .NET 文档操作和处理领域，Aspose.Page 是一个脱颖而出的强大工具。在其众多功能中，处理 EPS 文件中的数组项是一项常见要求。在本教程中，我们将探索在 .NET 环境中使用 Aspose.Page 添加数组项的分步过程。无论您是经验丰富的开发人员还是新手，本指南都将清晰准确地引导您完成整个过程。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

- 对 .NET 编程有基本的了解。
-  Aspose.Page for .NET 已安装。如果没有，您可以从以下位置下载[这里](https://releases.aspose.com/page/net/).
- 代码编辑器，例如 Visual Studio，与示例一起使用。

## 导入命名空间

在您的 .NET 项目中，请确保导入必要的命名空间以利用 Aspose.Page 功能。在代码开头添加以下行：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

这些命名空间提供对 EPS 文件操作所需的基本类和方法的访问。

## 步骤1：初始化EPS文件输入流

```csharp
//起始时间：3
//文档目录的路径。
string dataDir = "Your Document Directory";
//初始化EPS文件输入流
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//从流创建 PsDocument 实例
PsDocument document = new PsDocument(psStream);            
//结束：3
```

在这里，我们为 EPS 文件设置初始输入流并创建`PsDocument`实例。

## 第 2 步：获取 XMP 元数据

```csharp
//起始时间：4
//获取 XMP 元数据。如果 EPS 文件不包含 XMP 元数据，我们会得到一个新文件，其中填充了 PS 元数据注释中的值（%%Creator、%%CreateDate、%%Title 等）
XmpMetadata xmp = document.GetXmpMetadata();
//结束：4
```

从 EPS 文件中检索 XMP 元数据。如果 EPS 文件缺少 XMP 元数据，则会使用 PS 元数据注释中的值创建一个新文件。

## 步骤 3：更改 XMP 元数据值

```csharp
//起始时间：5
//更改 XMP 元数据值

//再添加一个标题。默认情况下它将添加到数组的末尾。
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

//再添加一位创作者。它将通过索引 (0) 添加到数组中。
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
//结束：5
```

通过向数组添加新标题和创建者来修改 XMP 元数据。

## 步骤 4：使用更改后的 XMP 元数据保存 EPS 文件

```csharp
//起始时间：6
//使用更改的 XMP 元数据保存 EPS 文件

//创建输出流
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    //保存 EPS 文件
    document.Save(outPsStream);
}
//结束：6
```

最后，使用更新的 XMP 元数据保存 EPS 文件。对数组项所做的更改将反映在输出文件中。

## 结论

在 .NET 中使用 Aspose.Page 添加数组项是一个简单的过程，如本教程所示。通过正确的先决条件和分步指南，开发人员可以无缝操作 EPS 文件，确保其文档满足特定的元数据要求。

## 常见问题解答

### Q1：Aspose.Page 是否兼容所有.NET 环境？

A1：是的，Aspose.Page 旨在与所有 .NET 环境无缝协作，提供跨平台的一致功能。

### Q2：我可以免费使用Aspose.Page吗？

 A2：Aspose.Page提供免费试用版，允许用户探索其功能。要继续使用，必须从以下位置购买许可证[这里](https://purchase.aspose.com/buy).

### Q3：Aspose.Page 是否有临时许可证？

 A3：是的，临时许可证可以从[这里](https://purchase.aspose.com/temporary-license/)以满足短期项目的需要。

### Q4：在哪里可以找到 Aspose.Page 的社区支持？

A4：如需社区讨论和支持，请访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39).

### Q5：Aspose.Page for .NET 的最新版本是什么？

 A5：要访问最新版本的 Aspose.Page for .NET，请参阅[文档](https://reference.aspose.com/page/net/).