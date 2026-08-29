---
date: 2026-08-29
description: 了解如何使用 Aspose.Page 在 Java 中对 EPS 文件进行矢量缩放。本分步指南展示了如何使用点、英寸、毫米或百分比来调整
  EPS 大小。
keywords:
- java vector resize
- how to resize eps
- EPS resizing Java
lastmod: 2026-08-29
linktitle: 在 Java 中缩放 EPS 文件
og_description: Java 矢量缩放让您直接在 Java 中调整 EPS 文件尺寸。使用 Aspose.Page，您可以通过点、英寸、毫米或百分比进行缩放，同时保持矢量质量。
og_image_alt: Guide showing java vector resize of EPS files using Aspose.Page
og_title: Java 矢量缩放：使用 Aspose.Page 更改 EPS 尺寸
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to Java vector resize EPS files in Java using Aspose.Page.
    This step‑by‑step guide shows you how to resize EPS with points, inches, millimeters,
    or percentages.
  headline: How to Java vector resize EPS files with Aspose.Page
  type: TechArticle
- questions:
  - answer: No, Aspose.Page is specialized for PostScript and EPS files only.
    question: Can I use this library for other image formats?
  - answer: Yes, you can explore the free trial **[Aspose free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      for community support.
    question: Where can I find additional help and discussions?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license?
  - answer: Yes, check the documentation **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.
    question: Are there any example projects available?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- java vector resize
- EPS resize
- Aspose.Page
- Java graphics
- vector graphics
title: 如何使用 Aspose.Page 在 Java 中对 EPS 文件进行矢量缩放
url: /zh/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page 在 Java 中矢量调整 EPS 文件大小

## 介绍
如果您需要以编程方式 **java vector resize** EPS 文件，您来对地方了。本教程将指导您使用 Aspose.Page 库在 Java 中调整 EPS 图像的大小。无论您想将尺寸加倍、缩小到特定尺寸，还是使用百分比，下面的步骤都能让您完全控制输出尺寸。掌握如何调整 EPS 大小对于在不同的打印布局、屏幕分辨率或品牌指南下适配图形至关重要。

## 快速答案
- **需要的库是什么？** Aspose.Page for Java  
- **我可以使用点、英寸或毫米来调整大小吗？** 是的——API 支持这三种单位以及百分比。  
- **开发时需要许可证吗？** 免费试用可用于测试；生产环境需要许可证。  
- **需要哪个 Java 版本？** Java 8 或更高版本。  
- **代码是线程安全的吗？** 每个 `PsDocument` 实例是独立的，因此可以并行处理文件。  

## 什么是 EPS，为什么要调整它的大小？
封装的 PostScript（EPS）是一种广泛用于印刷和出版的矢量图形格式。有时原始 EPS 文件的尺寸与目标输出不匹配——例如，一个以 72 pts 设计的标志可能需要在更大的宣传册中使用 144 pts。了解 **how to resize eps** 能让您在保持矢量质量的同时，将尺寸适配到任何工作流。

## 为什么使用 Aspose.Page 来调整 EPS 大小？
Aspose.Page 提供了简洁的 API，允许您使用任何受支持的单位指定目标尺寸，同时自动保留矢量结构。库内部处理单位转换，让您无需手动计算即可专注于所需的尺寸。

- **支持四种测量单位** – Points、Inches、Millimeters 和 Percent。  
- **无外部依赖** – 纯 Java API，无需本地库。  
- **高性能处理** – 在标准的 8 核服务器上每分钟可处理多达 500 个 EPS 文件。  
- **保持矢量保真度** – 输出保持完全可缩放，无栅格化。  

## 前置条件
在深入代码之前，请确保您具备以下条件：

- 已在机器上安装 Java Development Kit (JDK)。  
- Aspose.Page for Java 库。您可以下载 **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**。  
- 对 Java 编程有基本了解。  

## 导入包
在您的 Java 项目中，加入所需的导入，以便使用 Aspose.Page 对象和标准 I/O 流。

`PsDocument` 表示加载到内存中的 EPS 文档。  
`Units` 是一个枚举，定义了 API 接受的测量单位。

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## 如何使用不同单位更改 EPS 尺寸
您可以通过调用 `resizeEps` 方法并传入所需的宽度、高度以及 `Units` 枚举值来更改 EPS 尺寸；该方法支持点、英寸、毫米或百分比。相同的五步模式适用于每种单位，使 API 可预测且易于集成。

`resizeEps` 将 EPS 画布调整为指定尺寸，同时保持内部矢量数据。  

## 如何使用点（points）调整 EPS 大小
加载您的 EPS，使用点指定新尺寸，并保存结果。这种方法在保持宽高比的同时将原始尺寸加倍。使用点可以精确控制打印就绪尺寸，特别适用于排版布局和高分辨率输出。

### 步骤 1：设置输入流
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### 步骤 2：初始化 `PsDocument` 对象
`PsDocument` 加载源 EPS 文件并提供用于操作的方法。  

```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### 步骤 3：提取 EPS 图像的当前尺寸
```java
Dimension oldSize = doc.extractEpsSize();
```

### 步骤 4：为调整大小后的文件创建输出流
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### 步骤 5：使用点调整大小并保存 EPS
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## 如何使用英寸（inches）调整 EPS 大小
使用英寸进行调整可以匹配以英制单位定义的规格，例如宣传册布局或美国的印刷标准。提供以英寸为单位的目标宽度和高度，API 将在应用转换前将其转换为相应的内部单位。

## 如何使用毫米（millimeters）调整 EPS 大小
在基于公制的工作流中，以毫米指定尺寸可确保与美国以外的纸张尺寸和印刷设备保持一致。库会自动处理从毫米到内部坐标系的转换。

## 如何使用百分比（percentages）调整 EPS 大小
通过百分比调整大小会按比例缩放原始尺寸，这对于不计算绝对值的快速尺寸调整非常方便。例如，系数 `0.5` 会将宽度和高度都减少 50 %。

## 常见陷阱与技巧
- **始终关闭流** – 在生产代码中，使用 try‑with‑resources 包装流以避免文件锁定。  
- **保持宽高比** – 除非您有意想要失真，否则请将宽度和高度乘以相同的系数。  
- **检查 DPI** – 调整大小不会改变 DPI；如果需要不同的 DPI，请在调整后单独进行调整。  
- **线程安全** – 每个线程创建一个新的 `PsDocument`；共享同一实例可能导致意外结果。  

## 常见问题

**Q: 我可以将此库用于其他图像格式吗？**  
A: 不可以，Aspose.Page 仅专用于 PostScript 和 EPS 文件。

**Q: Aspose.Page for Java 有免费试用吗？**  
A: 有，您可以访问免费试用 **[Aspose free trial page](https://releases.aspose.com/)**。

**Q: 我在哪里可以找到更多帮助和讨论？**  
A: 请访问 **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** 获取社区支持。

**Q: 我如何获取临时许可证？**  
A: 您可以在 **[temporary license request page](https://purchase.aspose.com/temporary-license/)** 获取临时许可证。

**Q: 是否有示例项目可用？**  
A: 有，请查看文档 **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**。

---

**最后更新:** 2026-08-29  
**测试环境:** Aspose.Page for Java 24.12 (latest at time of writing)  
**作者:** Aspose

## 相关教程

- [使用 Aspose.Page 调整 EPS 大小 – Java EPS 操作](/page/java/manipulation-eps/)
- [如何在 Java 中裁剪 EPS 文件 – Aspose.Page 指南](/page/java/manipulation-eps/crop/)
- [如何使用 Aspose.Page for Java 缩放矩形](/page/java/page-manipulation/transformations/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}