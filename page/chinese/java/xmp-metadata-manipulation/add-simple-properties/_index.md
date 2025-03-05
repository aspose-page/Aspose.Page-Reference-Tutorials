---
title: 使用 Java 在 XMP 中添加简单属性
linktitle: 使用 Java 在 XMP 中添加简单属性
second_title: Aspose.Page Java API
description: 通过我们向 EPS 文件中的 XMP 元数据添加属性的指南来释放 Aspose.Page for Java 的潜力。轻松提升文档处理能力！
type: docs
weight: 14
url: /zh/java/xmp-metadata-manipulation/add-simple-properties/
---
## 介绍
在不断发展的文档处理领域，有效管理元数据至关重要。 Aspose.Page for Java 使开发人员能够无缝操作可扩展元数据平台 (XMP) 数据。在本教程中，我们将探索使用 Java 向 XMP 添加简单属性的过程，为您提供全面的分步指南。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
- Java 编程的基础知识。
- 安装了 Java 库的 Aspose.Page。你可以下载它[这里](https://releases.aspose.com/page/java/).
- 包含元数据的示例 EPS 文件。如果您没有，请随意使用提供的“xmp3.eps”文件。
## 导入包
确保导入必要的包来启动您的项目：
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
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//初始化输入 EPS 文件流
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
//获取 XMP 元数据。如果 EPS 文件不包含 XMP 元数据，我们会得到一个新文件，其中填充 PS 元数据注释中的值（%%Creator、%%CreateDate、%%Title 等）
XmpMetadata xmp = document.getXmpMetadata();
```
## 第2步：添加日期属性
```java
//添加日期属性“xmp:Date1”值
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## 第 3 步：添加整数属性
```java
//添加整数属性“xmp:Intg1”值
xmp.put("xmp:Intg1", new XmpValue(111));
```
## 第4步：添加双重属性
```java
//添加双属性“xmp:Double1”值
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## 第5步：添加字符串属性
```java
//添加字符串属性“xmp:String1”值
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## 第 6 步：保存文档
```java
//初始化输出 EPS 文件流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//保存具有更改的 XMP 元数据的文档
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 第 7 步：关闭流
```java
//关闭输入 EPS 流
psStream.close();
```
## 结论
Aspose.Page for Java 简化了在 EPS 文件中操作 XMP 元数据的过程。通过遵循此分步指南，您可以轻松添加简单的属性来增强文档的元数据。
## 经常问的问题
### 我可以将 Aspose.Page for Java 与其他编程语言一起使用吗？
Aspose.Page 主要支持 Java，但也有适用于其他语言（例如 .NET）的版本。
### Aspose.Page for Java 可以免费试用吗？
是的，您可以通过免费试用来探索 Aspose.Page 的功能[这里](https://releases.aspose.com/).
### 在哪里可以找到 Aspose.Page for Java 的详细文档？
文档可用[这里](https://reference.aspose.com/page/java/).
### 如何获得 Aspose.Page for Java 的临时许可证？
可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 在哪里可以购买 Java 版 Aspose.Page？
您可以购买该产品[这里](https://purchase.aspose.com/buy).