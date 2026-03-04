---
date: 2025-12-21
description: Aspose.Page XMP 教程 – 通过 Aspose.Page for Java，学习如何在 EPS 文件中修改 XMP 元数据，提供清晰的分步指南。
linktitle: Change Named Value in XMP using Java
second_title: Aspose.Page Java API
title: Aspose 页面 XMP 教程 – 使用 Java 更改 XMP 中的命名值
url: /zh/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose page xmp 教程 – 使用 Java 更改 XMP 中的命名值

在现代文档工作流中，**Aspose.Page for Java** 使读取、编辑和写入 EPS 文件中的 XMP 元数据变得轻松。此 **aspose page xmp tutorial** 将指导您更改 XMP 包中的命名值，从而保持文档元数据的准确性和可搜索性。无论是更新页面尺寸、作者信息还是自定义标签，下面的步骤都精确展示了在 Java 中的实现方法。

## 快速答案
- **本教程涵盖什么内容？** 使用 Aspose.Page for Java 在 EPS 文件中更改命名的 XMP 值。  
- **需要哪个库版本？** 任意近期的 Aspose.Page for Java 版本（该 API 多年来保持稳定）。  
- **是否需要许可证？** 生产环境需要临时或完整许可证；免费试用可用于测试。  
- **实现需要多长时间？** 对熟悉 Java I/O 的开发者约需 10‑15 分钟。  
- **可以用于其他文件格式吗？** XMP API 也支持 PDF、SVG 以及 Aspose.Page 支持的其他格式。  

## 什么是 XMP 元数据？
XMP（可扩展元数据平台）是一种标准化格式，用于将丰富的元数据（如创建者、标题和自定义属性）直接嵌入文件中。在 EPS 文档中，XMP 与传统的 PostScript 注释共存，使应用程序能够在不更改可视内容的情况下读取和修改元数据。

## 为什么使用 Aspose.Page for Java 编辑 XMP？
- **完全控制** – 访问任何 XMP 属性，包括自定义结构，无需解析原始 XML。  
- **跨格式一致性** – 同一 API 适用于 EPS、PDF 和 SVG，简化代码维护。  
- **无外部依赖** – 纯 Java 库，无需本机代码或额外解析器。  
- **健壮的错误处理** – 内置验证确保生成的 EPS 符合标准。  

## 介绍
Aspose.Page for Java 是一个强大的 Java 库，便于对 EPS 文件进行操作和处理。在这些文件中处理 XMP 元数据时，Aspose.Page 为开发者提供了完整的功能集。本教程将重点介绍如何更改 XMP 中的命名值，为希望提升文档处理能力的开发者提供清晰简明的指南。

## 前提条件
在开始教程之前，请确保已具备以下前提条件：

1. **Java 开发环境** – 确保在机器上已搭建 Java 开发环境。  
2. **Aspose.Page for Java 库** – 下载并将 Aspose.Page for Java 库集成到项目中。您可以在[此处](https://reference.aspose.com/page/java/)找到库及详细文档。  
3. **示例 EPS 文件** – 准备好用于实验的示例 EPS 文件。如果没有，可使用提供的示例文件 **"xmp4.eps"**。  

## 导入包
要开始此过程，请在 Java 代码中导入必要的包。这些包对于与 Aspose.Page for Java 交互至关重要。在 Java 文件的开头加入以下代码行：

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

## 步骤 1：初始化输入 EPS 文件流
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## 步骤 2：初始化 PsDocument
```java
PsDocument document = new PsDocument(psStream);
```

## 步骤 3：获取 XMP 元数据
```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 步骤 4：在 XMP 中设置新值
```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## 步骤 5：初始化输出 EPS 文件流
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## 步骤 6：保存带有更改 XMP 元数据的文档
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 步骤 7：关闭输入 EPS 流
```java
// Close input EPS stream
psStream.close();
```

此分步指南确保使用 Aspose.Page for Java 更改 XMP 中命名值的系统化方法。遵循这些步骤，即可将此功能无缝集成到 Java 应用程序中。

## 常见问题及解决方案
- **FileNotFoundException** – 确认 `dataDir` 指向正确的文件夹且 `xmp4.eps` 存在。  
- **LicenseException** – 若出现许可证错误，请确保在创建 `PsDocument` 前已加载有效的 Aspose.Page 许可证文件。  
- **Metadata Not Updated** – 保存后，在元数据查看器（如 Adobe Bridge）中打开生成的 EPS，确认新值已出现。  

## 结论
总之，Aspose.Page for Java 简化了在 EPS 文件中处理 XMP 元数据的过程。本教程为您提供了高效更改 XMP 中命名值的知识，提升了文档处理能力。

## 常见问答
### 我可以将 Aspose.Page for Java 与其他编程语言一起使用吗？
Aspose.Page 主要支持 Java，但 Aspose 为多种编程语言提供了类似的库。

### 是否提供 Aspose.Page for Java 的免费试用？
是的，您可以在[此处](https://releases.aspose.com/)体验 Aspose.Page for Java 的免费试用。

### 在哪里可以找到关于 Aspose.Page for Java 的更多支持和讨论？
访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 获取社区支持和讨论。

### 如何获取 Aspose.Page for Java 的临时许可证？
您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

### 在哪里购买 Aspose.Page for Java？
购买 Aspose.Page for Java，请访问[购买页面](https://purchase.aspose.com/buy)。

---

**最后更新：** 2025-12-21  
**测试环境：** Aspose.Page for Java（最新版本）  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
