---
title: 使用 Java 更改 XMP 中的值
linktitle: 使用 Java 更改 XMP 中的值
second_title: Aspose.Page Java API
description: 使用 Aspose.Page for Java 增强 EPS 文档。轻松修改 XMP 元数据以获得定制的专业内容。 #Java开发
type: docs
weight: 17
url: /zh/java/xmp-metadata-manipulation/change-values/
---
## 介绍
在文档处理和操作领域，Aspose.Page for Java 是一款脱颖而出的强大工具。本教程深入探讨使用 Java 和 Aspose.Page 库更改 EPS（封装 PostScript）文档中的 XMP（可扩展元数据平台）值的过程。通过遵循提供的分步指南，您将了解如何轻松修改元数据，确保您的文档适合您的特定要求。
## 先决条件
在开始本教程之前，请确保您具备以下先决条件：
1. Java 开发环境：确保您的计算机上有一个有效的 Java 开发环境。
2.  Aspose.Page for Java 库：下载并安装 Aspose.Page for Java 库。就可以找到需要的包了[这里](https://releases.aspose.com/page/java/).
## 导入包
首先将所需的包导入到您的 Java 项目中。这些包对于与 EPS 文档交互和操作至关重要。
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## 第 1 步：获取 XMP 元数据
从 EPS 文档中检索 XMP 元数据。如果 EPS 文件不包含 XMP 元数据，则会使用 PS 元数据注释（例如 %%Creator、%%CreateDate 和 %%Title）中的值创建一个新文件。
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//初始化输入 EPS 文件流
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
//获取 XMP 元数据。如果 EPS 文件不包含 XMP 元数据，则会使用 PS 元数据注释中的值创建一个新文件
XmpMetadata xmp = document.getXmpMetadata();
```
## 第 2 步：更改“修改日期”值
修改 XMP 元数据中的“ModifyDate”值以反映所需的日期。
```java
//更改“修改日期”值
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## 第 3 步：更改“创建者”值
更新 XMP 元数据中的“Creator”值以指定文档的创建者。
```java
//改变“创造者”价值
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## 第 4 步：更改“标题”值
修改 XMP 元数据中的“标题”值以为文档设置适当的标题。
```java
//更改“标题”值
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## 步骤 5：使用更改的 XMP 元数据保存文档
将包含更新的 XMP 元数据的文档保存到新的 EPS 文件。
```java
//初始化输出 EPS 文件流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//保存具有更改的 XMP 元数据的文档
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 结论
恭喜！您已经成功完成了使用 Aspose.Page for Java 更改 EPS 文档中的 XMP 值的过程。本教程为您提供了修改元数据的知识，确保您的文档无缝地符合您的特定要求。
## 常见问题解答
### 问：修改 XMP 值时如何处理时区注意事项？
利用`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`以确保时区设置的一致性。
### 问：我可以在一次操作中更改多个 XMP 值吗？
是的，通过使用`put`方法为每个所需的值，您可以同时修改多个 XMP 值。
### 问：在哪里可以找到 Aspose.Page for Java 的附加文档？
探索全面的文档[这里](https://reference.aspose.com/page/java/).
### 问：Aspose.Page for Java 是否有免费试用版？
是的，您可以免费试用[这里](https://releases.aspose.com/).
### 问：如何获得 Aspose.Page for Java 的临时许可证？
获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).