---
date: 2025-12-18
description: 了解如何使用 Aspose.Page for Java 将数组项插入 EPS 文件的 XMP 元数据中，以添加元数据。请按照我们的分步指南操作。
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: 如何添加元数据 – 在 XMP 中添加数组项（Java）
url: /zh/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 XMP 元数据中使用 Java 添加数组项

## 如何添加元数据
欢迎阅读我们的分步指南，了解 **如何向 EPS 文件添加元数据**，使用 Aspose.Page for Java。在本教程中，我们将演示向 XMP 元数据添加数组项的过程——当您需要为文档信息（如标题或创建者）进行丰富时，这是一项常见需求。完成后，您将了解 XMP 的价值、如何以编程方式操作它，以及如何保存更新后的 EPS 文件。

## 快速答案
- **使用的库是什么？** Aspose.Page for Java  
- **目标文件格式是什么？** EPS（Encapsulated PostScript）  
- **可以添加多个标题吗？** 可以，重复使用 `xmp.addArrayItem("dc:title", ...)` 即可  
- **生产环境需要许可证吗？** 需要，有效的 Aspose.Page 许可证是必需的  
- **代码兼容 Java 8+ 吗？** 完全兼容，适用于所有现代 Java 版本  

## 前置条件
在开始教程之前，请确保您具备以下前置条件：
- 已安装 Aspose.Page for Java 库。  
- 具备基本的 Java 编程知识。  
- 拥有包含现有 XMP 元数据或 PS 元数据注释的有效 EPS 文件。  

## 导入包
要开始工作，您需要导入使用 Aspose.Page 所需的包。在 Java 文件的开头加入以下代码行：
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 步骤 1：获取 XMP 元数据
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
在此步骤中，我们从 EPS 文件中检索现有的 XMP 元数据。如果 EPS 文件尚未包含 XMP 元数据，Aspose.Page 将生成一个新对象，并从 PS 元数据注释中填充相应值。

## 步骤 2：添加 “dc:title” 数组项
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
现在，我们向 XMP 元数据中的 **dc:title** 属性添加一个新的数组项。将 `"NewTitle"` 替换为您想要的标题。

## 步骤 3：添加 “dc:creator” 数组项
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
同理，我们向 XMP 元数据中的 **dc:creator** 属性添加一个新的数组项。将 `"NewCreator"` 替换为您想要的创建者信息。

## 步骤 4：初始化输出 EPS 文件流
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
准备输出 EPS 文件流，以便将带有更新后 XMP 元数据的文档保存到该文件中。

## 步骤 5：使用更改后的 XMP 元数据保存文档
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
将文档连同更新后的 XMP 元数据保存到输出 EPS 文件。

## 结论
恭喜！您已成功学习 **如何通过在 XMP 元数据中插入数组项来添加元数据**，使用 Aspose.Page for Java。这款强大的库简化了 EPS 文件的操作，并提供了丰富的文档处理功能。

## 常见问题

### 我可以将 Aspose.Page for Java 与其他文档格式一起使用吗？
可以，Aspose.Page 支持多种文档格式，包括 EPS、PDF 和 XPS。

### Aspose.Page for Java 有免费试用吗？
有，您可以在此处获取免费试用 [here](https://releases.aspose.com/)。

### 哪里可以找到 Aspose.Page for Java 的文档？
文档可在此处查看 [here](https://reference.aspose.com/page/java/)。

### 如何购买 Aspose.Page for Java？
您可以在此处购买产品 [here](https://purchase.aspose.com/buy)。

### Aspose.Page for Java 是否提供临时许可证？
有，您可以在此处获取临时许可证 [here](https://purchase.aspose.com/temporary-license/)。

## 其他常见问题

**问：我可以向同一属性添加多个数组项吗？**  
答：当然可以。对同一属性多次调用 `xmp.addArrayItem` 即可构建值列表。

**问：此方法是否适用于除 Dublin Core 之外的其他 XMP 架构？**  
答：可以，只要正确引用命名空间，您就可以向任何 XMP 属性添加数组项。

**问：我如何验证元数据是否已正确添加？**  
答：在支持 XMP 的查看器（如 Adobe Bridge）中打开生成的 EPS 文件，或使用 `XmpMetadata` 方法以编程方式提取元数据进行检查。

---

**最后更新：** 2025-12-18  
**测试环境：** Aspose.Page for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}