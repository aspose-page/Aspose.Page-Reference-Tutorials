---
date: 2026-02-07
description: 了解如何在 Java 中调整 EPS 文件大小并使用 Aspose.Page 更改 EPS 尺寸。本分步指南将向您展示如何使用点、英寸、毫米或百分比来调整
  EPS 大小。
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: 如何在 Java 中使用 Aspose.Page 调整 EPS 文件大小
url: /zh/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Page 调整 EPS 文件大小

## Introduction
如果您正在寻找一种可靠的方式 **how to resize EPS** 文件的编程方法，您来对地方了。在本教程中，我们将演示如何使用 Aspose.Page 库在 Java 中调整 EPS 图像的大小。无论您需要将尺寸加倍、缩小到特定尺寸，还是使用百分比，下面的步骤都能让您完全控制输出尺寸。了解 **how to resize eps** 在需要为不同的打印布局或屏幕分辨率调整图形时至关重要。

## Quick Answers
- **需要哪个库？** Aspose.Page for Java  
- **我可以使用点、英寸或毫米进行调整吗？** 是的 – API 支持这三种单位以及百分比。  
- **开发时需要许可证吗？** 免费试用可用于测试；生产环境需要许可证。  
- **需要哪个 Java 版本？** Java 8 或更高。  
- **代码是线程安全的吗？** 每个 `PsDocument` 实例是独立的，因此可以并行处理文件。  

## What is EPS and Why Resize It?
Encapsulated PostScript (EPS) 是一种在出版和印刷中常用的矢量图形格式。有时原始 EPS 文件的尺寸与目标输出不匹配，例如，一个在 72 pts 设计的标志可能需要在更大的宣传册中使用 144 pts。了解 **how to resize eps** 可以让您在保持矢量质量的同时，将尺寸适配到任何工作流。

## Why Use Aspose.Page for Resizing EPS?
- **对单位的完整控制** – 点、英寸、毫米或百分比。  
- **无外部依赖** – 纯 Java API，无本地库。  
- **高性能** – 适用于服务器上的批处理。  
- **保持矢量保真度** – 输出保持可缩放，无需光栅化。

## Prerequisites
在深入代码之前，请确保您具备以下条件：

- 已在机器上安装 Java Development Kit (JDK)。  
- Aspose.Page for Java 库。您可以在 **[此处](https://releases.aspose.com/page/java/)** 下载。  
- 对 Java 编程有基本了解。  

## Import Packages
在您的 Java 项目中，加入所需的导入，以便使用 Aspose.Page 对象和标准 I/O 流。

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## How to Change EPS Dimensions with Different Units
该库通过选择相应的 `Units` 枚举，让您 **change eps dimensions**。下面我们将演示针对点、英寸、毫米和百分比的相同五步模式。唯一变化的只是传递给 `resizeEps` 的单位。

## How to Resize EPS Using Points
下面是一个完整的逐步示例，使用点作为测量单位将 EPS 文件的大小加倍。

### Step 1: Set up the input stream
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Step 2: Initialize the `PsDocument` object
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Step 3: Extract the current size of the EPS image
```java
Dimension oldSize = doc.extractEpsSize();
```

### Step 4: Create an output stream for the resized file
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Step 5: Resize and save the EPS using points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## How to Resize EPS Using Inches
相同的五步模式适用，只需将 `Units.Points` 替换为 `Units.Inches`，并将缩放因子调整为所需的英寸值。

## How to Resize EPS Using Millimeters
同样，遵循相同的步骤，将单位换成 `Units.Millimeters`。当您在打印工作流中需要基于公制的尺寸时，这非常方便。

## How to Resize EPS Using Percentages
对于基于百分比的缩放，保持单位为 `Units.Percent`。将原始宽度和高度乘以所需的百分比（例如，`0.5` 表示缩小 50 %）。

## Common Pitfalls & Tips
- **始终关闭流** – 在生产代码中，使用 try‑with‑resources 包装流以避免文件锁定。  
- **保持宽高比** – 除非您有意要失真，否则应将宽度和高度乘以相同的因子。  
- **检查 DPI** – 调整大小不会改变 DPI；如果需要不同的 DPI，请在调整后单独进行设置。  
- **线程安全** – 为每个线程创建新的 `PsDocument`；共享同一实例可能导致意外结果。  

## Frequently Asked Questions

**问：我可以将此库用于其他图像格式吗？**  
答：不行，Aspose.Page 仅专注于 PostScript 和 EPS 文件。

**问：Aspose.Page for Java 是否提供免费试用？**  
答：是的，您可以在 **[此处](https://releases.aspose.com/)** 了解免费试用。

**问：我可以在哪里找到更多帮助和讨论？**  
答：访问 **[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)** 获取社区支持。

**问：如何获取临时许可证？**  
答：您可以在 **[此处](https://purchase.aspose.com/temporary-license/)** 获取临时许可证。

**问：是否有示例项目可用？**  
答：有，您可以在 **[此处](https://reference.aspose.com/page/java/)** 查看文档。

---

**最后更新：** 2026-02-07  
**测试环境：** Aspose.Page for Java 24.12（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}