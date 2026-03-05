---
date: 2026-03-05
description: 了解如何使用 Aspose.Page for Java 在 EPS 文件的 XMP 元数据中添加 dc:title 数组项。按照本分步指南快速获得结果。
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: 如何使用 Java 在 XMP 元数据中添加 dc:title 数组项
url: /zh/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 XMP 元数据中添加数组项

## 介绍
在本教程中，您将了解 **如何添加 dc:title**（以及其他数组项）到 EPS 文件中的 XMP 元数据，使用 Aspose.Page for Java。更新 XMP 元数据在需要将可搜索信息（如标题、创作者或关键字）直接嵌入图形文件时非常有用。我们将逐步演示每一步，解释每行代码的意义，并展示如何验证更改。

## 快速答疑
- **What does “dc:title” represent?** 它是作为 XMP 数组存储的 Dublin Core 标题属性。  
- **Why modify XMP metadata?** 它能够提升资产管理、可搜索性以及符合标准的要求。  
- **Do I need an existing XMP block?** 不需要——如果缺失，Aspose.Page 会从 PS 注释生成一个。  
- **Which library version is required?** 任意近期的 Aspose.Page for Java 版本（已在最新 2026 版上测试）。  
- **Can I add other array properties?** 可以——使用相同的 `addArrayItem` 方法添加如 `dc:creator` 等属性。

## 前提条件
- 已安装 Aspose.Page for Java 库（将 JAR 添加到项目的 classpath 中）。  
- 基本的 Java 开发经验（推荐使用 JDK 8 及以上）。  
- 包含 XMP 元数据或至少 PS 元数据注释（如 `%%Title`、`%%Creator`）的 EPS 文件。  

## 导入包
首先，导入读取、操作和保存 EPS 文件所需的类：

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 步骤 1：加载 EPS 文档并获取 XMP 元数据
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

这里我们打开 EPS 文件并请求 Aspose.Page 获取其 XMP 块。如果文件缺少 XMP，库会使用现有的 PS 注释自动创建一个，确保您始终拥有可操作的元数据容器。

## 步骤 2：添加新的 **dc:title** 数组项  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

此行演示了 **如何添加 dc:title**。将 `"NewTitle"` 替换为您想嵌入的实际标题。该方法会将值追加到现有的标题数组中，保留之前的所有标题。

## 步骤 3：添加新的 **dc:creator** 数组项  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

同样，您可以丰富 `dc:creator` 属性。可以存储多个创作者；每次调用都会添加一个新条目。

## 步骤 4：准备输出流  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

我们为修改后的 EPS 文件创建一个流。使用不同的文件名（`xmp3_changed.eps`）可以保持原始文件不受影响。

## 步骤 5：保存带有更新 XMP 元数据的文档  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

`save` 调用会将 EPS 数据连同更新后的 XMP 块一起写入。`finally` 块确保即使出现异常也会释放文件句柄。

## 为什么这很重要
嵌入准确的 `dc:title` 和 `dc:creator` 值可以提升：

- **Searchability** 在数字资产管理（DAM）系统中的可搜索性。  
- **Compliance** 符合需要元数据的出版标准。  
- **Collaboration**，团队成员可以在不打开 EPS 的情况下快速识别文件内容。  

## 常见陷阱与技巧
- **Pitfall:** 无意中覆盖已有的数组项。  
  **Tip:** 在添加新项之前，使用 `xmp.getArrayItems("dc:title")` 检查当前值。  
- **Pitfall:** 忘记关闭流，导致文件锁定。  
  **Tip:** 始终像示例中那样使用 try‑with‑resources 或 `finally` 块包装 I/O。  
- **Tip:** 您可以链式调用多个 `addArrayItem`，一次性添加多个标题或创作者。  

## 常见问题

### 我可以将 Aspose.Page for Java 与其他文档格式一起使用吗？
是的，Aspose.Page 支持多种文档格式，包括 EPS、PDF 和 XPS。

### 是否提供 Aspose.Page for Java 的免费试用？
是的，您可以在此处获取免费试用 [here](https://releases.aspose.com/)。

### 在哪里可以找到 Aspose.Page for Java 的文档？
文档可在此处获取 [here](https://reference.aspose.com/page/java/)。

### 如何购买 Aspose.Page for Java？
您可以在此处购买产品 [here](https://purchase.aspose.com/buy)。

### 是否提供 Aspose.Page for Java 的临时许可证？
是的，您可以在此处获取临时许可证 [here](https://purchase.aspose.com/temporary-license/)。

---

**最后更新:** 2026-03-05  
**测试环境:** Aspose.Page for Java (latest 2026 release)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}