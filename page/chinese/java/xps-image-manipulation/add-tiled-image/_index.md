---
date: 2025-12-28
description: 学习如何使用 Aspose.Page 在 Java 中创建 XPS 文档，并轻松添加平铺图像的分步指南。
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: 如何在 Java 中使用平铺图像创建 XPS 文档
url: /zh/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中创建 XPS 文档并添加平铺图像

## 介绍
在现代 Java 开发中，能够**创建 XPS 文档**文件是一项有价值的技能，尤其是当您需要使用平铺图像等图形来丰富文档时。Aspose.Page for Java 使此过程变得简单，让您可以专注于视觉设计，而不是低层文件处理。在本教程中，您将学习如何创建 XPS 文档、**添加平铺图像**并保存结果，全部配有清晰的逐步代码示例。

## 快速回答
- **Aspose.Page 的作用是什么？** 它提供了一个高级 API，用于在 Java 中生成和操作 XPS 文档。  
- **我可以平铺图像吗？** 可以——使用 `XpsImageBrush` 并将 `XpsTileMode.Tile` 作为平铺模式。  
- **我需要许可证吗？** 生产环境使用需要临时或商业许可证。  
- **支持哪个 Java 版本？** 任意 JDK 8 及以上版本均兼容。  
- **实现需要多长时间？** 对于基本的平铺图像场景，大约需要 10–15 分钟。

## 什么是“创建 XPS 文档”？
XPS（XML Paper Specification）文件是一种类似 PDF 的固定布局文档格式。以编程方式创建 XPS 文档可以让您直接从 Java 代码生成可打印、与设备无关的文件。

## 为什么要添加平铺图像？
平铺图像会在定义的区域内重复该图形，非常适合作为背景、水印或图案填充。使用 Aspose.Page 的 `XpsTileMode.Tile`，只需几行代码即可实现。

## 前置条件
在开始之前，请确保您已具备以下条件：

1. **Java Development Kit (JDK)** – 已安装 JDK 8 或更高版本。  
2. **Aspose.Page for Java** – 从[网站](https://releases.aspose.com/page/java/)下载。  
3. **可写目录** – 用于保存生成的 XPS 文件。

## 导入包
在您的 Java 项目中，导入必要的类：

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## 步骤指南

### 步骤 1：设置项目
将 Aspose.Page JAR 文件添加到项目的类路径，并验证导入语句能够成功编译。

### 步骤 2：创建 XPS 文档
实例化一个新的 `XpsDocument` 对象。这是容纳所有页面、路径和资源的核心容器。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### 步骤 3：定义平铺图像路径
将您想要平铺的图像（例如 `R08LN_NN.jpg`）放置在 `dataDir` 所指向的目录中。该图像将用作画刷模式。

### 步骤 4：添加平铺图像
创建一个矩形路径，并使用 `XpsImageBrush` 填充。通过将平铺模式设置为 `Tile`，图像将在矩形内重复。

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
将 XPS 文件持久化到磁盘。输出文件将包含您刚才定义的平铺图像。

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

每当您需要在同一 XPS 文档的其他页面或形状中**添加平铺图像**时，都可以重复上述步骤。

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| 图像未显示 | 验证文件路径 (`dataDir + "R08LN_NN.jpg"`) 是否正确且图像可访问。 |
| 平铺图案被拉伸 | 调整源和目标 `Rectangle2D` 的数值以控制平铺大小。 |
| 不透明度无效 | 确保在设置平铺模式后再设置画刷的不透明度。 |

## 常见问答

### Aspose.Page 是否兼容所有 Java 版本？
Aspose.Page 设计用于兼容多种 Java 版本。请通过查看文档[此处](https://reference.aspose.com/page/java/)确认兼容性。

### 我可以在商业项目中使用 Aspose.Page 吗？
是的，Aspose.Page 提供商业许可证。可在[此处](https://purchase.aspose.com/buy)购买。

### 是否提供免费试用？
是的，可在[此处](https://releases.aspose.com/)获取免费试用。

### 在哪里可以找到社区支持和讨论？
可在[论坛](https://forum.aspose.com/c/page/39)与 Aspose.Page 社区交流。

### 如何获取 Aspose.Page 的临时许可证？
可在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

---

**最后更新：** 2025-12-28  
**测试环境：** Aspose.Page for Java 24.12（最新）  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
