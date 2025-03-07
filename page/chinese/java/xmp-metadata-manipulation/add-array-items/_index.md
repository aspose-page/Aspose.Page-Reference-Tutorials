---
title: 使用 Java 在 XMP 元数据中添加数组项
linktitle: 使用 Java 在 XMP 元数据中添加数组项
second_title: Aspose.Page Java API
description: 使用 Aspose.Page for Java 增强 EPS 文件。了解如何轻松地将数组项添加到 XMP 元数据。立即按照我们的分步指南进行操作！
weight: 10
url: /zh/java/xmp-metadata-manipulation/add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 XMP 元数据中添加数组项

## 介绍
欢迎阅读我们有关使用 Aspose.Page for Java 在 XMP 元数据中添加数组项的分步指南。 Aspose.Page 是一个功能强大的 Java 库，允许您操作和处理各种文档格式，包括 EPS 文件。在本教程中，我们将重点关注使用 Java 在 XMP 元数据中添加数组项的特定任务。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下先决条件：
- 安装了 Java 库的 Aspose.Page。
- 对 Java 编程有基本的了解。
- 具有现有 XMP 元数据或 PS 元数据注释的有效 EPS 文件。
## 导入包
首先，您需要导入使用 Aspose.Page 所需的包。在 Java 文件的开头包含以下行：
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
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
在此步骤中，我们从 EPS 文件中检索现有的 XMP 元数据。如果 EPS 文件尚不包含 XMP 元数据，Aspose.Page 会生成一个新文件并用 PS 元数据注释中的值填充它。
## 步骤 2：添加“dc:title”数组项
```java
//再添加一项“dc:title”数组项
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
现在，我们将一个新的数组项添加到 XMP 元数据中的“dc:title”属性。将“NewTitle”替换为所需的标题。
## 步骤 3：添加“dc:creator”数组项
```java
//再添加一项“dc:creator”数组项
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
同样，我们将一个新的数组项添加到 XMP 元数据中的“dc:creator”属性中。将“NewCreator”替换为所需的创建者信息。
## 步骤 4：初始化输出 EPS 文件流
```java
//初始化输出 EPS 文件流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
准备输出 EPS 文件流，其中将保存具有更新的 XMP 元数据的修改文档。
## 步骤 5：使用更改的 XMP 元数据保存文档
```java
//保存具有更改的 XMP 元数据的文档
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
将包含更新的 XMP 元数据的文档保存到输出 EPS 文件。
## 结论
恭喜！您已经成功学习了如何使用 Aspose.Page for Java 在 XMP 元数据中添加数组项。这个强大的库简化了 EPS 文件的操作过程，并提供了广泛的文档处理功能。
## 经常问的问题

### 我可以将 Aspose.Page for Java 与其他文档格式一起使用吗？
是的，Aspose.Page 支持各种文档格式，包括 EPS、PDF 和 XPS。
### Aspose.Page for Java 是否有免费试用版？
是的，您可以免费试用[这里](https://releases.aspose.com/).
### 在哪里可以找到 Aspose.Page for Java 的文档？
文档可用[这里](https://reference.aspose.com/page/java/).
### 如何购买 Aspose.Page for Java？
您可以购买该产品[这里](https://purchase.aspose.com/buy).
### Aspose.Page for Java 是否有临时许可证？
是的，您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
