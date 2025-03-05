---
title: 使用 Aspose.Page for .NET 更改命名值
linktitle: 更改命名值
second_title: Aspose.Page .NET API
description: 了解如何使用 Aspose.Page for .NET 更改 EPS 文件中的命名值。轻松自定义 XMP 元数据以进行定制文档处理。
type: docs
weight: 16
url: /zh/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---
## 介绍

在文档处理领域，Aspose.Page for .NET 作为操作 EPS 文件的强大工具脱颖而出。它提供的关键功能之一是能够更改 XMP 元数据中的命名值。本教程将指导您完成使用 Aspose.Page for .NET 更改命名值的过程，使您能够根据您的特定需求自定义 EPS 文件。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

-  Aspose.Page for .NET：确保您已安装 Aspose.Page for .NET 库。如果没有的话可以下载[这里](https://releases.aspose.com/page/net/).

- 文档目录：为 EPS 文件指定一个目录，您可以在其中执行命名值更改。

## 导入命名空间

在您的.NET项目中，您需要导入必要的命名空间来访问Aspose.Page提供的功能。将以下命名空间添加到您的代码中：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

现在，我们将代码分解为多个步骤以便全面理解：

## 第1步：初始化EPS文件输入流

```csharp
//开始时间：1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
//结束：1
```

在此步骤中，我们为要修改的 EPS 文件设置输入流。确保将“您的文档目录”替换为文档目录的实际路径。

## 第 2 步：获取 XMP 元数据

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

从 EPS 文件中检索现有的 XMP 元数据。如果 EPS 文件不包含 XMP 元数据，则会使用 PS 元数据注释中的值生成一个新文件。

## 步骤 3：更改 XMP 元数据值

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

在这里，我们演示如何更改“xmpTPg:MaxPageSize”结构中的两个命名值。您可以根据您的具体要求进行自定义。

## 步骤 4：使用更改的 XMP 元数据保存 EPS 文件

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

将修改后的 EPS 文件保存到输出流。该文件现在将反映对 XMP 元数据所做的更改。

## 结论

通过本教程，您了解了如何利用 Aspose.Page for .NET 更改 EPS 文件中 XMP 元数据内的命名值。此功能为自定义和定制文档以满足特定要求开辟了无限可能。

## 常见问题解答

### Q1：我可以将 Aspose.Page for .NET 与其他文档格式一起使用吗？

A1：是的，Aspose.Page支持各种文档格式，包括EPS、XPS和PDF。

### Q2：Aspose.Page for .NET 有试用版吗？

 A2：是的，您可以免费试用[这里](https://releases.aspose.com/).

### Q3：在哪里可以找到有关 Aspose.Page for .NET 的更多文档？

 A3：参考文档[这里](https://reference.aspose.com/page/net/).

### Q4：如何获得 Aspose.Page for .NET 的临时许可证？

 A4：您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).

### 问题 5：Aspose.Page for .NET 用户可以使用哪些支持选项？

 A5：访问社区论坛[这里](https://forum.aspose.com/c/page/39)以寻求支持和讨论。