---
date: 2025-12-21
description: 了解如何使用 Java 通过 Aspose.Page 修改 EPS 文档中的 XMP。使用 Aspose.Page for Java 快速增强元数据。
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page 修改 XMP – 使用 Java 更改 XMP 中的值
url: /zh/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 更改 XMP 值

## 介绍
如果您需要 **aspose.page modify xmp** EPS 文件中的 XMP 数据，您来对地方了。在本教程中，我们将逐步演示如何使用 Aspose.Page for Java 库读取、更新并保存 XMP（可扩展元数据平台）值。完成后，您即可根据项目需求自定义文档元数据——如创建者、标题和修改日期等。

## 快速答案
- **“aspose.page modify xmp” 是做什么的？** 它通过 Aspose.Page Java API 读取和写入 EPS 文件中的 XMP 元数据。  
- **需要哪个库版本？** 任意近期的 Aspose.Page for Java 发行版（API 在各版本间保持稳定）。  
- **运行示例是否需要许可证？** 评估可使用免费试用版；生产环境需商业许可证。  
- **可以一次修改多个 XMP 字段吗？** 可以——在保存文档前对每个字段调用 `put` 即可。  
- **是否需要处理时区？** 设置默认时区（例如 UTC）可确保日期值的一致性。

## 什么是 XMP，为什么要修改它？
XMP（可扩展元数据平台）是一种标准化方式，可将丰富的元数据直接嵌入 EPS、PDF、图像等文件中。更新 XMP 可控制文档的索引、显示和搜索方式——这对品牌、合规和工作流自动化至关重要。

## 为什么使用 Aspose.Page for Java？
- **功能完整的 API** – 无需外部工具，全部在进程内完成。  
- **跨平台** – 兼容任何支持 Java 的操作系统。  
- **无本地依赖** – 纯 Java 实现简化部署。  
- **强大支持** – 能处理已有的 XMP 块，也能在缺失时从 PS 注释创建新块。

## 前置条件
在开始本教程之前，请确保已满足以下前置条件：
1. **Java 开发环境** – JDK（8 或更高）以及您喜欢的 IDE 或构建工具。  
2. **Aspose.Page for Java 库** – 下载并安装 Aspose.Page for Java 库。您可以在 [此处](https://releases.aspose.com/page/java/) 找到所需的包。

## 导入包
在 Java 项目中导入所需的包。这些包对于交互和操作 EPS 文档至关重要。

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

## 步骤 1：获取 XMP 元数据
从 EPS 文档中检索 XMP 元数据。如果 EPS 文件不包含 XMP 元数据，系统将根据 PS 元数据注释（如 %%Creator、%%CreateDate、%%Title）创建一个新块。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## 步骤 2：更改 “ModifyDate” 值
修改 XMP 元数据中的 “ModifyDate” 值，以反映所需的日期。

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## 步骤 3：更改 “Creator” 值
更新 XMP 元数据中的 “Creator” 值，以指定文档的创建者。

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## 步骤 4：更改 “Title” 值
修改 XMP 元数据中的 “Title” 值，为文档设置合适的标题。

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## 步骤 5：使用更改后的 XMP 元数据保存文档
将文档保存为新的 EPS 文件，包含已更新的 XMP 元数据。

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 常见问题及解决方案
- **缺少 XMP 块** – API 会自动根据 PS 注释创建块，但如有需要也可以手动实例化 `XmpMetadata`。  
- **时区不匹配** – 在创建 `Date` 对象前始终调用 `TimeZone.setDefault`，以避免意外的时区偏移。  
- **文件访问错误** – 确认输入输出路径正确，并且应用程序拥有读写权限。

## 常见问答

**问：在修改 XMP 值时如何处理时区问题？**  
答：使用 `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` 可确保时区设置的一致性。

**问：能否在一次操作中更改多个 XMP 值？**  
答：可以，通过对每个需要的键调用 `put` 方法即可同时修改多个 XMP 值。

**问：在哪里可以找到 Aspose.Page for Java 的更多文档？**  
答：请访问[此处](https://reference.aspose.com/page/java/)获取完整文档。

**问：Aspose.Page for Java 是否提供免费试用？**  
答：是的，您可以在[此处](https://releases.aspose.com/)获取免费试用。

**问：如何获取 Aspose.Page for Java 的临时许可证？**  
答：请在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

**问：修改 XMP 会影响 EPS 的可视内容吗？**  
答：不会。XMP 的更改仅涉及元数据，不会改变 EPS 文件的图形元素。

**问：我可以编程方式读取已更新的值以验证更改吗？**  
答：完全可以——在保存并关闭文档前，调用 `xmp.get("dc:creator")`（或相应键）即可获取更新后的值。

## 结论
恭喜！您已成功使用 Aspose.Page for Java 在 EPS 文档中 **aspose.page modify xmp** 值。本教程为您提供了修改元数据的完整方法，帮助您的文档轻松符合特定需求。

---

**最后更新：** 2025-12-21  
**测试环境：** Aspose.Page for Java（最新发布）  
**作者：** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
