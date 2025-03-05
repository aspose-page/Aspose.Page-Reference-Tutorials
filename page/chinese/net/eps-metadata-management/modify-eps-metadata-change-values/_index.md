---
title: 使用 Aspose.Page for .NET 更改值
linktitle: 改变值
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page for .NET 掌握 EPS 文件操作。轻松更改 XMP 元数据值。
type: docs
weight: 17
url: /zh/net/eps-metadata-management/modify-eps-metadata-change-values/
---
## 介绍

在文档处理的动态世界中，Aspose.Page for .NET 作为一款强大的工具脱颖而出，为开发人员提供了轻松操作 EPS 文件的能力。在本教程中，我们将深入研究使用 Aspose.Page for .NET 更改 EPS 文件中的值的过程。无论您是经验丰富的开发人员还是好奇的初学者，本分步指南都将为您提供有效修改 EPS 文件中的 XMP 元数据所需的技能。

## 先决条件

在我们深入学习本教程之前，请确保您具备以下先决条件：

### 1..NET 库的 Aspose.Page

确保您的开发环境中安装了 Aspose.Page for .NET 库。如果没有的话可以下载[这里](https://releases.aspose.com/page/net/).

### 2. 文档目录

为您的文档设置一个目录。这将是您的 EPS 文件的存储位置。

现在我们已经解决了先决条件，让我们继续接下来的关键步骤。

## 导入命名空间

在任何 .NET 项目中，导入必要的命名空间以利用 Aspose.Page 的功能至关重要。您可以这样做：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 步骤1：初始化EPS文件输入流

```csharp
//文档目录的路径。
string dataDir = "Your Document Directory";
//初始化EPS文件输入流
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## 步骤 2：从流创建 PsDocument 实例

```csharp
//从流创建 PsDocument 实例
PsDocument document = new PsDocument(psStream);
```

现在我们已经做好准备，让我们继续本教程的核心内容 - 更改 EPS 文件中的 XMP 元数据值。

## 步骤 3：获取 XMP 元数据

```csharp
//获取 XMP 元数据。如果 EPS 文件不包含 XMP 元数据，我们会获取一个新文件，其中填充了 PS 元数据注释中的值（%%Creator、%%CreateDate、%%Title 等）
XmpMetadata xmp = document.GetXmpMetadata();
```

## 步骤 4：修改 XMP 元数据值

现在，让我们更改 XMP 元数据中的一些键值：

### 步骤4.1：更改ModifyDate值

```csharp
//更改修改日期值
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### 步骤4.2：更改创作者价值

```csharp
//改变创造者价值
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### 步骤 4.3：更改标题值

```csharp
//更改标题值
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

完成这些更改后，让我们继续最后一步 - 保存修改后的 EPS 文件。

## 步骤 5：使用更改的 XMP 元数据保存 EPS 文件

### 步骤5.1：创建输出流

```csharp
//创建输出流
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### 步骤5.2：保存EPS文件

```csharp
//保存 EPS 文件
document.Save(outPsStream);
```

最后，关闭输入流：

```csharp
finally
{
    psStream.Close();
}
```

恭喜！您已使用 Aspose.Page for .NET 成功修改了 EPS 文件中的 XMP 元数据值。

## 结论

在本教程中，我们探索了使用 Aspose.Page for .NET 更改 EPS 文件中的值的无缝过程。作为开发人员，您现在可以使用一个强大的工具来进行高效的文档操作。

## 常见问题解答

### Q1：我可以将 Aspose.Page for .NET 与其他文件格式一起使用吗？

A1：Aspose.Page 主要专注于 EPS 文件操作。对于其他格式，请探索 Aspose 的各种产品。

### Q2：有试用版吗？

 A2：是的，您可以免费试用 Aspose.Page for .NET[这里](https://releases.aspose.com/).

### Q3：哪里可以找到详细的文档？

 A3：可以找到全面的文档[这里](https://reference.aspose.com/page/net/).

### Q4：如何获得临时驾照？

 A4：您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).

### Q5：我可以购买 Aspose.Page for .NET 吗？

 A5：当然！访问购买页面[这里](https://purchase.aspose.com/buy)用于许可选项。