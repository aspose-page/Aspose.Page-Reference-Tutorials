---
date: 2025-12-02
description: 学习如何在 Java 中轻松使用 Aspose.Page 调整 EPS 文件的大小。本分步指南展示了如何使用点、英寸、毫米或百分比来调整
  EPS 大小。
language: zh
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: 如何使用 Aspose.Page 在 Java 中调整 EPS 文件大小
url: /java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Page 调整 EPS 文件大小

## 介绍
如果您正在寻找一种可靠的 **如何调整 EPS** 文件大小的编程方式，您来对地方了。在本教程中，我们将演示如何使用 Aspose.Page 库在 Java 中调整 EPS 图像的大小。无论您需要将尺寸加倍、缩小到特定尺寸，还是使用百分比进行缩放，下面的步骤都能让您完全控制输出尺寸。

## 快速答案
- **需要哪个库？** Aspose.Page for Java  
- **可以使用点、英寸或毫米进行缩放吗？** 可以——API 支持这三种单位以及百分比。  
- **开发时需要许可证吗？** 免费试用可用于测试；生产环境需要许可证。  
- **需要哪个 Java 版本？** Java 8 或更高。  
- **代码是线程安全的吗？** 每个 `PsDocument` 实例是独立的，您可以并行处理文件。

## 前置条件
在开始编写代码之前，请确保您具备以下条件：

- 已在机器上安装 Java Development Kit (JDK)。  
- Aspose.Page for Java 库。您可以 **[在此下载](https://releases.aspose.com/page/java/)**。  
- 基本的 Java 编程知识。  

## 导入包
在您的 Java 项目中，加入所需的导入，以便使用 Aspose.Page 对象和标准 I/O 流。

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## 使用点单位调整 EPS 大小
下面是一个完整的、逐步的示例，演示如何使用点作为度量单位将 EPS 文件的大小加倍。

### 步骤 1：设置输入流
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### 步骤 2：初始化 `PsDocument` 对象
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

### 步骤 5：使用点单位进行缩放并保存 EPS
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## 使用英寸单位调整 EPS 大小
相同的五步模式同样适用，只需将 `Units.Points` 替换为 `Units.Inches` 并根据需要调整缩放因子。

## 使用毫米单位调整 EPS 大小
同样，遵循相同的步骤，将单位换成 `Units.Millimeters`。在需要基于公制的打印工作流时，这非常方便。

## 使用百分比调整 EPS 大小
对于基于百分比的缩放，保持单位为 `Units.Percent`。将原始宽度和高度乘以所需的百分比（例如 `0.5` 表示缩小 50 %）。

## 常见陷阱与技巧
- **始终关闭流**——在生产代码中，使用 try‑with‑resources 包装流，以避免文件锁定。  
- **保持宽高比**——除非您有意产生失真，否则宽度和高度应使用相同的因子进行乘算。  
- **检查 DPI**——调整大小不会改变 DPI；如果需要不同的 DPI，请在缩放后单独进行调整。

## 结论
现在您已经了解 **如何在 Java 中使用 Aspose.Page 调整 EPS** 文件的大小，无论是使用点、英寸、毫米还是百分比。这种灵活性使您能够将 EPS 操作集成到自动化流水线、桌面工具或服务器端服务中。

## 常见问题

**问：我可以使用该库处理其他图像格式吗？**  
答：不行，Aspose.Page 仅专注于 PostScript 和 EPS 文件。

**问：Aspose.Page for Java 有免费试用吗？**  
答：有，您可以在 **[此处](https://releases.aspose.com/)** 体验免费试用。

**问：在哪里可以找到更多帮助和讨论？**  
答：访问 **[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)** 获取社区支持。

**问：如何获取临时许可证？**  
答：您可以在 **[此处](https://purchase.aspose.com/temporary-license/)** 获取临时许可证。

**问：有没有示例项目可供参考？**  
答：有，查看文档 **[此处](https://reference.aspose.com/page/java/)**。

---

**最后更新：** 2025-12-02  
**测试环境：** Aspose.Page for Java 24.12（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}