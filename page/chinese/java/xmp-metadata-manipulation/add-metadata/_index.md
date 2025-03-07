---
title: 使用 Java 在 XMP 中添加元数据
linktitle: 使用 Java 在 XMP 中添加元数据
second_title: Aspose.Page Java API
description: 探索 Aspose.Page for Java 的无缝集成，并了解如何轻松地将 XMP 元数据添加到 EPS 文件中。立即提升您的文档管理水平！
weight: 11
url: /zh/java/xmp-metadata-manipulation/add-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 XMP 中添加元数据

## 介绍
您是否希望通过使用 Java 添加 XMP 信息来增强文档的元数据？别再犹豫了！本分步指南将引导您完成使用 Aspose.Page for Java 库将元数据添加到 EPS 文件的过程。 Aspose.Page 是一个功能强大的工具，可以简化 Java 应用程序中的文档操作任务。
## 先决条件
在我们深入学习本教程之前，请确保您满足以下先决条件：
- Java 编程的基础知识。
- 安装了 Java 库的 Aspose.Page。你可以下载它[这里](https://releases.aspose.com/page/java/).
- 您要修改的 EPS 文件。
## 导入包
首先，将必要的包导入到您的 Java 程序中：
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## 第 1 步：获取 XMP 元数据
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//初始化输入 EPS 文件流
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
//获取 XMP 元数据。如果 EPS 文件不包含 XMP 元数据，则会使用 PS 元数据注释（%%Creator、%%CreateDate、%%Title 等）中的值创建一个新文件
XmpMetadata xmp = document.getXmpMetadata();
```
确保将“您的文档目录”替换为存储文档的实际路径。

## 步骤 2：检索 CreatorTool 值
```java
//获取“CreatorTool”值
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## 步骤 3：检索 CreateDate 值
```java
//获取“创建日期”值
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## 第 4 步：检索标题值
```java
//获取“标题”值
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## 第 5 步：检索格式值
```java
//获取“格式”值
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## 第 6 步：检索创造者价值
```java
//获得“创造者”价值
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## 第 7 步：检索 MetadataDate 值
```java
//获取“元数据日期”值
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## 步骤 8：使用新的 XMP 元数据保存文档
```java
//初始化输出 EPS 文件流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
//使用新的 XMP 元数据保存文档
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
最后，不要忘记关闭输入 EPS 流：
```java
//关闭输入 EPS 流
psStream.close();
```
现在，您已经使用 Aspose.Page for Java 成功将元数据添加到您的 EPS 文件中！
## 结论
在本教程中，我们探索了使用 Aspose.Page for Java 库将 XMP 元数据添加到 EPS 文件的过程。这个强大的工具使您能够无缝地操作文档，从而增强您的整体文档管理体验。
## 常见问题解答
### 问：Aspose.Page for Java 可以免费使用吗？
答：Aspose.Page for Java 是一个商业产品。您可以通过免费试用探索其功能[这里](https://releases.aspose.com/).
### 问：在哪里可以找到 Aspose.Page for Java 的文档？
答：文档已提供[这里](https://reference.aspose.com/page/java/).
### 问：如何获得 Aspose.Page for Java 的临时许可证？
答：您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 问：Aspose.Page for Java 支持哪些文件格式？
答：Aspose.Page for Java 支持多种格式，包括 EPS、PDF 和 XPS。
### 问：我可以购买 Aspose.Page for Java 吗？
答：是的，您可以购买 Aspose.Page for Java[这里](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
