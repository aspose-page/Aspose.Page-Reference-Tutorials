---
date: 2026-01-23
description: 了解如何使用 Aspose.Page for .NET 通过添加命名值来编辑 EPS 文件。本分步指南帮助开发者操作 EPS 元数据。
linktitle: Add Named Value
second_title: Aspose.Page .NET API
title: 如何编辑 EPS 文件 – 使用 Aspose.Page 添加命名值
url: /zh/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何编辑 EPS 文件 – 使用 Aspose.Page 添加命名值

## 如何编辑 EPS 文件 – 介绍

## 快速答案
- **Aspose.Page 能做什么？** 它可以读取、修改和写入 EPS 文件，包括 XMP 元数据。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **我需要许可证吗？** 提供免费试用，但生产环境需要商业许可证。  
- **实现需要多长时间？** 对于基本的命名值场景，通常在 前提备以下前提条件：

- C# 编程语言的基础知识。  
- 已安装的集成开发环境（IDE），如 Visual Studio。  
- Aspose.Page for .NET 库。如果尚未安装，可从 [here](https://releases.aspose.com/page/net/) 下载。

## 导入命名空间

首先，让我们在 C# 代码中导入必要的命名空间。这些命名空间对于访问 Aspose.Page 提供的功能至关重要：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 步骤 1：初始化 EPS 文件输入流

第一步是初始化 EPS 文件的输入流。将 `"Your Document Directory"` 替换为文档目录的路径：

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## 步骤 2：获取 XMP 元数据

从 EPS 文件中检索 XMP 元数据。如果 EPS 文件没有 XMP 元数据，将创建一个新的，并用 PS 元数据注释中的值填充：

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## 步骤 3：更改 XMP 元数据值

现在，让我们对 XMP 元数据进行更改。在本例中，我们将向 `"xmpTPg:MaxPageSize"` 结构添加一个命名值：

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## 步骤 4：使用更改后的 XMP 元数据保存 EPS 文件

使用更新后的 XMP 元数据保存 EPS 文件。创建输出流并保存修改后的 EPS 文件：

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## 结论

恭喜！您已成功使用 .NET 中的 Aspose.Page 向 EPS 文件添加了命名值。本演练展示了编辑 **EPS** 元数据是多么简便，使您能够以编程方式丰富文档。

## 常见问题

### Q1：Aspose.Page 是否兼容不同的 EPS 文件版本？

A1：Aspose.Page 支持多种 EPS 文件版本，确保与广泛的文档兼容。

### Q2：我可以在商业项目中使用 Aspose.Page 吗？

A2：可以，Aspose.Page 提供商业许可证，您可以在 [here](https://purchase.aspose.com/buy) 购买。

### Q3：Aspose.Page 有免费试用吗？

A3：有的，您可以通过 [here](https://releases.aspose.com/) 获取免费试用。

### Q4：我如何获取支持或加入 Aspose 社区？

A4：访问 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 获取支持并与社区交流。

### Q5：什么是临时许可证，如何获取？

A5：如果您需要用于测试或评估的临时许可证，可在 [here](https://purchase.aspose.com/temporary-license/) 获取。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-23  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

---