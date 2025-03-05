---
title: 使用 Java 更改 XMP 中的命名值
linktitle: 使用 Java 更改 XMP 中的命名值
second_title: Aspose.Page Java API
description: 探索 Aspose.Page for Java - 通过我们的简化文档处理分步指南，轻松更改 EPS 文件中的 XMP 元数据。
type: docs
weight: 16
url: /zh/java/xmp-metadata-manipulation/change-named-value/
---
在文档操作领域，Aspose.Page for Java 是一款功能强大的工具，使开发人员能够无缝地使用 EPS 文件中的 XMP 元数据。本分步指南将引导您完成使用 Aspose.Page for Java 更改 XMP 中命名值的过程。在我们深入研究细节之前，让我们先做一个介绍。
## 介绍
Aspose.Page for Java 是一个强大的 Java 库，可促进 EPS 文件的操作和处理。在处理这些文件中的 XMP 元数据时，Aspose.Page 为开发人员提供了一套全面的功能。在本教程中，我们将重点关注更改 XMP 中的命名值，为希望增强文档处理能力的开发人员提供清晰简洁的指南。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1. Java 开发环境：确保您的计算机上设置了 Java 开发环境。
2.  Aspose.Page for Java 库：下载 Aspose.Page for Java 库并将其集成到您的项目中。您可以找到该库和详细文档[这里](https://reference.aspose.com/page/java/).
3. 示例 EPS 文件：准备好示例 EPS 文件以供实验。如果您没有，可以使用提供的名为“xmp4.eps”的示例文件。
## 导入包
要开始该过程，请在 Java 代码中导入必要的包。这些包对于与 Aspose.Page for Java 交互至关重要。在 Java 文件的开头包含以下行：
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
现在，让我们将使用 Aspose.Page for Java 更改 XMP 中命名值的过程分解为多个步骤：
## 第 1 步：初始化输入 EPS 文件流
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
        
//初始化输入 EPS 文件流
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```
## 第2步：初始化PsDocument
```java
PsDocument document = new PsDocument(psStream);
```
## 第 3 步：获取 XMP 元数据
```java
//获取 XMP 元数据。如果 EPS 文件不包含 XMP 元数据，我们会得到一个新文件，其中填充 PS 元数据注释中的值（%%Creator、%%CreateDate、%%Title 等）
XmpMetadata xmp = document.getXmpMetadata();
```
## 第 4 步：在 XMP 中设置新值
```java
//为结构“xmpTPg:MaxPageSize”的命名值“stDim:unit”设置新字符串值“Inches”
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```
## 步骤5：初始化输出EPS文件流
```java
//初始化输出 EPS 文件流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```
## 步骤 6：保存具有更改的 XMP 元数据的文档
```java
//保存具有更改的 XMP 元数据的文档
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 第 7 步：关闭输入 EPS 流
```java
//关闭输入 EPS 流
psStream.close();
```
本分步指南确保了使用 Aspose.Page for Java 更改 XMP 中命名值的系统方法。通过执行以下步骤，您可以将此功能无缝集成到您的 Java 应用程序中。
## 结论
总之，Aspose.Page for Java 简化了在 EPS 文件中使用 XMP 元数据的过程。本教程为您提供了有效更改 XMP 中命名值的知识，从而增强您的文档处理能力。
## 经常问的问题
### 我可以将 Aspose.Page for Java 与其他编程语言一起使用吗？
Aspose.Page主要支持Java，但Aspose为各种编程语言提供了类似的库。
### Aspose.Page for Java 是否有免费试用版？
是的，您可以探索 Aspose.Page for Java 的免费试用版[这里](https://releases.aspose.com/).
### 在哪里可以找到有关 Aspose.Page for Java 的其他支持和讨论？
参观[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)以获得社区支持和讨论。
### 如何获得 Aspose.Page for Java 的临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 在哪里可以购买 Java 版 Aspose.Page？
要购买 Java 版 Aspose.Page，请访问[购买页面](https://purchase.aspose.com/buy).