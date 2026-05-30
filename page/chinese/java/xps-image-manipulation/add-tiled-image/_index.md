---
date: 2026-05-30
description: 了解如何在 Java 中使用 Aspose.Page 创建 XPS 文档，并通过本分步指南轻松添加平铺图像。快速创建 XPS 文件的方法。
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: 在 Java XPS 中添加平铺图像
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: 如何在 Java 中使用平铺图像创建 XPS 文档
url: /zh/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用平铺图像创建 XPS 文档

## 介绍
以编程方式创建 XPS 文档是需要可打印、设备无关输出的 Java 开发者的核心技能。**如何创建 XPS** 文件的高效方法由 Aspose.Page for Java 提供，它抽象了低层的 XML Paper Specification 细节，让您专注于视觉设计。在本指南中，您将准确了解如何创建 XPS 文档、将平铺图像作为背景或图案添加，并保存结果——全部使用简洁、可投入生产的代码。

## 快速答案
- **Aspose.Page 的作用是什么？** 它提供了一个高级 API，用于在 Java 中生成和操作 XPS 文档。  
- **我可以平铺图像吗？** 是的——使用 `XpsImageBrush` 与 `XpsTileMode.Tile`。  
- **我需要许可证吗？** 在生产环境中需要临时或商业许可证。  
- **支持哪个 Java 版本？** 任何 JDK 8+ 都兼容。  
- **实现需要多长时间？** 对于基本的平铺图像场景，大约需要 10–15 分钟。  

## 什么是“创建 XPS 文档”？
`XpsDocument` 是 Aspose.Page 的顶层对象，表示内存中的单个 XPS 文件。它封装了页面、资源和元数据，使您能够以编程方式构建文档。创建 XPS 文档意味着实例化此类，添加可视元素，最后调用 `save` 将固定布局文件写入磁盘。这种方法消除了手动 XML 处理，并确保符合 XML Paper Specification。

## 为什么要添加平铺图像？
平铺会在定义的区域内重复图形，非常适合作为背景、水印或图案填充。使用 `XpsTileMode.Tile`，图像会自动重复，无需手动复制，从而节省开发时间并确保在任何设备上渲染一致。平铺图像还能保持文件大小较小，因为相同的位图资源被重复使用，而不是多次嵌入。

## 先决条件
在深入之前，请确保您拥有：

1. **Java Development Kit (JDK)** – 已安装 JDK 8 或更高版本。  
2. **Aspose.Page for Java** – 从[网站](https://releases.aspose.com/page/java/)下载。  
3. **可写目录** – 用于保存生成的 XPS 文件的目录。  

## 导入包
在您的 Java 项目中，导入必要的类：

`XpsDocument` 是表示 XPS 文件的主要对象。  
`XpsImageBrush` 使用图像源绘制形状。  
`XpsTileMode` 指定图像的平铺方式。  
`Rectangle2D` 描述用于定位的矩形区域。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## 分步指南

### 步骤 1：设置项目
将 Aspose.Page JAR 文件添加到项目的类路径，并验证导入语句能够成功编译且无错误。

### 步骤 2：创建 XPS 文档
`XpsDocument` 是保存页面、路径和资源的核心容器。使用所需的页面尺寸实例化它，然后即可开始添加图形元素。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### 步骤 3：定义平铺图像路径
将要平铺的图像（例如 `R08LN_NN.jpg`）放置在 `dataDir` 所指的目录中。该图像将用作画刷图案。

### 步骤 4：添加平铺图像
创建一个矩形路径，并使用 `XpsImageBrush` 填充。通过将平铺模式设置为 `Tile`，图像将在矩形内重复。调整源矩形和目标矩形以控制平铺大小和位置。

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### 步骤 5：保存文档
将 XPS 文件持久化到磁盘。输出文件将包含您刚定义的平铺图像，并可使用任何 XPS 查看器打开。

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

每当需要在同一 XPS 文档的其他页面或形状中**添加平铺图像**时，重复这些步骤。

## 常见问题与解决方案
| 问题 | 解决方案 |
|-------|----------|
| 图像未显示 | 确认文件路径 (`dataDir + \"R08LN_NN.jpg\"`) 正确且图像可访问。 |
| 平铺图案出现拉伸 | 调整源和目标 `Rectangle2D` 的值以控制平铺大小。 |
| 不透明度无效 | 确保在平铺模式配置**之后**设置画刷的不透明度。 |

## 常见问答

**Q:** Aspose.Page 与所有 Java 版本兼容吗？  
**A:** Aspose.Page 支持 Java 8 到 Java 21；您可以在[此处](https://reference.aspose.com/page/java/)找到完整的兼容性矩阵。

**Q:** 我可以在商业项目中使用 Aspose.Page 吗？  
**A:** 是的，生产使用需要商业许可证。购买选项列在[此处](https://purchase.aspose.com/buy)。

**Q:** 是否提供免费试用？  
**A:** 可以从 Aspose 发布页面[此处](https://releases.aspose.com/)下载功能完整的免费试用版。

**Q:** 我可以在哪里获得社区支持？  
**A:** 加入 Aspose.Page 社区论坛[forum](https://forum.aspose.com/c/page/39)提问并分享示例。

**Q:** 如何获取用于评估的临时许可证？  
**A:** 可通过 Aspose 门户[此处](https://purchase.aspose.com/temporary-license/)请求临时许可证。

## 结论
您现在拥有使用 Aspose.Page for Java 创建带平铺图像的 XPS 文档的完整、可投入生产的工作流。通过利用 `XpsImageBrush` 和 `XpsTileMode.Tile`，您可以生成丰富且可重复的图形，而不会增加文件大小。尝试不同的平铺尺寸、不透明度级别和形状，以构建复杂的文档布局。下一步，探索添加矢量形状或文本覆盖层，以进一步增强您的 XPS 文件。

---

**最后更新:** 2026-05-30  
**测试环境:** Aspose.Page for Java 24.12 (latest)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [如何向 Java XPS 文档添加图像 – Aspose.Page 简单指南](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - 向 XPS 添加页面教程](/page/java/xps-page-manipulation/add-page/)
- [使用 Aspose.Page Java 将 XPS 转换为 PDF](/page/java/file-merging/xps-to-pdf/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}