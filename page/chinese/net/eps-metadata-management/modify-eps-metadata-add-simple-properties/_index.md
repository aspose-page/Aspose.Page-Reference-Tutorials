---
title: 使用 Aspose.Page for .NET 添加简单属性
linktitle: 添加简单属性
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 增强 EPS 文件。轻松为自定义文档元数据添加简单属性。
weight: 14
url: /zh/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 添加简单属性

## 介绍

在文档操作和增强领域，Aspose.Page for .NET 成为一个强大的工具，为开发人员提供了在 EPS 文件中无缝添加和修改 XMP 元数据的能力。本教程将指导您完成使用 Aspose.Page for .NET 将简单属性添加到 EPS 文件的过程。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

1.  Aspose.Page for .NET：确保您的开发环境中安装了 Aspose.Page for .NET。如果没有的话可以下载[这里](https://releases.aspose.com/page/net/).

2. 文档目录：设置一个目录来存储您的 EPS 文件。更新`dataDir`提供的代码片段中的变量以及文档目录的路径。

## 导入命名空间

首先，导入必要的命名空间以启用与 Aspose.Page for .NET 的通信。在代码文件的开头添加以下行：

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

```csharp
//开始时间：1
//文档目录的路径。
string dataDir = "Your Document Directory";
//初始化EPS文件输入流
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//从流创建 PsDocument 实例
PsDocument document = new PsDocument(psStream);
```

## 第 2 步：获取 XMP 元数据

```csharp
//获取 XMP 元数据。如果 EPS 文件不包含 XMP 元数据，我们会得到一个新文件，其中填充 PS 元数据注释中的值（%%Creator、%%CreateDate、%%Title 等）
XmpMetadata xmp = document.GetXmpMetadata();
```

## 步骤 3：更改 XMP 元数据值

```csharp
//更改 XMP 元数据值
DateTime now = DateTime.UtcNow;

//添加整数属性
xmp.Add("xmp:Intg1", new XmpValue(111));

//添加日期时间属性
xmp.Add("xmp:Date1", new XmpValue(now));

//添加双精度属性
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//添加字符串属性
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## 步骤 4：使用更改的 XMP 元数据保存 EPS 文件

```csharp
//使用更改的 XMP 元数据保存 EPS 文件

//创建输出流
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    //保存 EPS 文件
    document.Save(outPsStream);
}
```

## 第5步：关闭文件流

```csharp
finally
{
    psStream.Close();
}
```

通过执行这些步骤，您可以使用 Aspose.Page for .NET 轻松地将简单的属性合并到 EPS 文件中。

## 结论

总之，Aspose.Page for .NET 对于寻求使用自定义 XMP 元数据增强 EPS 文件的开发人员来说是一项宝贵的资产。通过添加简单的属性，您可以自定义和丰富文档以满足特定要求，从而开启文档操作的无限可能。

## 常见问题解答

### Q1：Aspose.Page for .NET 是否与所有 EPS 文件兼容？

A1：Aspose.Page for .NET 支持多种 EPS 文件。但是，兼容性可能会根据各个文件的复杂性和结构而有所不同。

### 问题 2：我可以使用 Aspose.Page for .NET 修改现有的 XMP 元数据吗？

A2：当然！如本教程所示，您可以轻松更改现有的 XMP 元数据值或添加新值以满足您的需求。

### Q3：我可以添加的属性类型有限制吗？

A3：Aspose.Page for .NET 支持各种属性数据类型，包括整数、日期、双精度数和字符串。您可以灵活地为元数据选择适当的类型。

### Q4：如何获得 Aspose.Page for .NET 的技术支持？

 A4： 如需技术帮助，请访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)或探索[文档](https://reference.aspose.com/page/net/)进行全面指导。

### Q5：Aspose.Page for .NET 有免费试用版吗？

 A5：是的，您可以免费试用[这里](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
