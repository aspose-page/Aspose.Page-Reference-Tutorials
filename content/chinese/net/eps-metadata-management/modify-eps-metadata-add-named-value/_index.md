---
title: 使用 Aspose.Page 添加命名值
linktitle: 添加命名值
second_title: Aspose.Page .NET API
description: 了解如何使用 Aspose.Page 将命名值添加到 .NET 中的 EPS 文件。这个综合教程将逐步指导您完成整个过程。
type: docs
weight: 12
url: /zh/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---
## 介绍

在使用 .NET 进行文档处理的领域中，Aspose.Page 作为处理 EPS 文件的强大工具脱颖而出。 Aspose.Page 使开发人员能够操作 XMP 元数据，从而简化添加命名值等任务。本教程将指导您逐步完成使用 Aspose.Page 将命名值添加到 EPS 文件的过程。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

- C# 编程语言的基础知识。
- 安装了集成开发环境 (IDE)，例如 Visual Studio。
-  .NET 库的 Aspose.Page。如果没有安装，可以从以下地址下载[这里](https://releases.aspose.com/page/net/).

## 导入命名空间

首先，让我们将必要的命名空间导入到您的 C# 代码中。这些命名空间对于访问 Aspose.Page 提供的功能至关重要：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 第1步：初始化EPS文件输入流

初始步骤涉及初始化 EPS 文件的输入流。代替`"Your Document Directory"`与您的文档目录的路径：

```csharp
//开始时间：1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## 第 2 步：获取 XMP 元数据

从 EPS 文件中检索 XMP 元数据。如果 EPS 文件缺少 XMP 元数据，则会创建一个新文件，并填充 PS 元数据注释中的值：

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## 步骤 3：更改 XMP 元数据值

现在，让我们更改 XMP 元数据。在此示例中，我们将向“xmpTPg:MaxPageSize”结构添加一个命名值：

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## 步骤 4：使用更改的 XMP 元数据保存 EPS 文件

使用更新的 XMP 元数据保存 EPS 文件。创建输出流并保存修改后的 EPS 文件：

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## 结论

恭喜！您已成功使用 .NET 中的 Aspose.Page 将命名值添加到 EPS 文件。本教程将引导您完成基本步骤，展示 Aspose.Page 在文档操作中的简单性和有效性。

## 常见问题解答

### Q1: Aspose.Page 是否兼容不同的 EPS 文件版本？

A1：Aspose.Page支持各种EPS文件版本，确保与各种文档的兼容性。

### Q2：我可以将Aspose.Page用于商业项目吗？

 A2：是的，Aspose.Page带有商业许可证，您可以购买它[这里](https://purchase.aspose.com/buy).

### Q3：Aspose.Page 有免费试用版吗？

 A3：是的，您可以免费试用 Aspose.Page[这里](https://releases.aspose.com/).

### 问题 4：我如何获得支持或与 Aspose 社区建立联系？

 A4：访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)获得支持并与社区建立联系。

### 问题 5：什么是临时许可证？如何获得临时许可证？

 A5：如果您需要临时许可证用于测试或评估目的，您可以获取一个[这里](https://purchase.aspose.com/temporary-license/).