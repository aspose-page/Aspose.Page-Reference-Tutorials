---
title: 使用 Java 更改 XMP 中的数组项
linktitle: 使用 Java 更改 XMP 中的数组项
second_title: Aspose.Page Java API
description: 了解如何使用 Aspose.Page for Java 更改 XMP 中的数组项。使用我们的分步指南轻松修改元数据。立即增强您的 EPS 文档！
type: docs
weight: 15
url: /zh/java/xmp-metadata-manipulation/change-array-items/
---
## 介绍
欢迎来到我们关于使用 Aspose.Page for Java 更改 XMP 中的数组项的综合指南！ Aspose.Page 是一个功能强大的 Java 库，允许您无缝地使用 EPS 文件中的 XMP 元数据。在本教程中，我们将引导您完成修改 XMP 元数据中的数组项的过程，帮助您增强和自定义 EPS 文档。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下先决条件：
- 您的系统上安装了 Java 开发工具包 (JDK)。
-  Java 的 Aspose.Page 库。您可以从以下位置下载：[这里](https://releases.aspose.com/page/java/).
## 导入包
首先，让我们在 Java 项目中导入必要的包。确保您的项目中包含 Aspose.Page 库。
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;

```
## 第 1 步：获取 XMP 元数据
首先，从 EPS 文件中检索 XMP 元数据。如果 EPS 文件尚未包含 XMP 元数据，则会使用 PS 元数据注释中的值（例如 %%Creator、%%CreateDate、%%Title 等）创建一个新文件。
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//初始化输入 EPS 文件流
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
//获取 XMP 元数据。如果 EPS 文件不包含 XMP 元数据，则新文件将填充 PS 元数据注释中的值。
XmpMetadata xmp = document.getXmpMetadata();
```
## 步骤 2：设置“dc:title”数组项
现在，让我们使用新值设置索引 0 处的“dc:title”数组项。
```java
//按索引 0 设置“dc:title”数组项
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```
## 步骤 3：设置“dc:creator”数组项
同样，使用新的创建者值设置索引 0 处的“dc:creator”数组项。
```java
//按索引 0 设置“dc:creator”数组项
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```
## 步骤 4：初始化输出 EPS 文件流
准备将保存修改后的文档的输出 EPS 文件流。
```java
//初始化输出 EPS 文件流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
## 步骤 5：使用更改的 XMP 元数据保存文档
使用更新的 XMP 元数据保存文档。
```java
//保存具有更改的 XMP 元数据的文档
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 结论
恭喜！您已经成功学习了如何使用 Aspose.Page for Java 更改 XMP 中的数组项。本教程提供了分步指导，确保您可以使用自定义元数据轻松增强 EPS 文档。

## 常见问题解答
### 我可以将 Aspose.Page for Java 与其他编程语言一起使用吗？
Aspose.Page 主要是为 Java 设计的，但 Aspose 也为其他语言提供了类似的库。
### 在哪里可以找到 Aspose.Page for Java 的详细文档？
文档可用[这里](https://reference.aspose.com/page/java/).
### Aspose.Page for Java 是否有免费试用版？
是的，您可以获得免费试用[这里](https://releases.aspose.com/).
### 如何获得 Aspose.Page for Java 的临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 在哪里可以购买完整版的 Aspose.Page for Java？
您可以购买完整版[这里](https://purchase.aspose.com/buy).