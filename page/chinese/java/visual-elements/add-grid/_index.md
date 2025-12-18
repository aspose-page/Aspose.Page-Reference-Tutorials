---
date: 2025-12-18
description: 学习如何在 Java XPS 文档中使用 Aspose.Page 添加网格和透明矩形。一步一步的指南，帮助高效保存 XPS 文档。
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: 如何在 Java 中使用 Visual Brush 添加网格
url: /zh/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Visual Brush 添加网格

## Introduction
如果您想在 Java 生成的 XPS 文档中 **添加网格** 元素，您来对地方了。在本教程中，我们将逐步演示如何使用 Visual Brush 添加网格，叠加透明矩形，最后使用 Aspose.Page Java API **保存 XPS 文档**。完成后，您将拥有一个可在报告、发票或任何文档密集型应用中重复使用的精美视觉效果。

## Quick Answers
- **Visual Brush 的作用是什么？** 它在定义的区域内绘制可重复使用的视觉内容，非常适合网格等重复图案。  
- **我可以更改网格颜色吗？** 可以——修改画刷的纯色设置。  
- **如何在网格上方添加透明矩形？** 对填充了纯色的路径调用 `setOpacity`。  
- **哪个方法保存文件？** `doc.save(...)` 将 XPS 文件写入磁盘。  
- **我需要许可证吗？** 生产使用时需要临时或正式许可证。

## What is a Visual Brush Grid?
什么是 Visual Brush 网格？  
Visual Brush 允许您定义一个小的视觉（网格图案），然后在更大的区域内平铺。相比逐条绘制每条线，这种方式更节省内存，并且能够实现像素级的完美重复。

## Why use Aspose.Page for this task?
- **Cross‑platform** – Works on any OS that supports Java.  
- **High‑fidelity rendering** – Precise control over colors, opacity, and tiling.  
- **No external dependencies** – Everything is handled through the Aspose.Page library.

## Prerequisites
在开始之前，请确保您具备以下条件：

- 基本的 Java 编程知识。  
- 已安装 Aspose.Page 库 – 您可以从 [Aspose.Page for Java 文档](https://reference.aspose.com/page/java/) 下载。  
- 已在开发机器上安装 JDK 8 或更高版本。

## Import Packages
首先，导入所需的类，以便编译器知道我们将使用的类型所在位置：

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Step‑by‑Step Guide

### Step 1: Set Up Your Project
创建一个新的 `XpsDocument` 实例，并指定要保存输出文件的文件夹。

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Step 2: Create a Magenta Grid Visual Brush
我们定义一个小的品红色形状，用于在网格区域平铺。

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Step 3: Define Geometry for the Grid Brush
设置将接收平铺视觉的矩形区域。

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Step 4: Create a New Canvas for the Document
向文档添加画布，并将其定位到网格出现的位置。

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Step 5: Add the Grid to the Canvas
将 Visual Brush 应用于几何形状，以实现平铺。

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Step 6: Add a Transparent Red Rectangle (Secondary Feature)
这里我们演示如何在网格上方 **添加透明矩形** 以突出显示。

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Step 7: Save the Resulting XPS Document
最后，将文档写入磁盘——这就是 **保存 XPS 文档** 的步骤。

```java
doc.save(dataDir + "AddGrid_out.xps");
```

按照这些步骤操作，您将得到一个专业外观的网格并带有透明覆盖层，全部由程序生成。

## Common Issues & Tips
- **平铺尺寸不正确：** 确保用于画刷的 `Rectangle2D` 与预期的重复尺寸匹配，否则图案可能会拉伸。  
- **不透明度未生效：** 记得在需要透明的路径上调用 `setOpacity`；它不会影响画刷本身。  
- **文件未保存：** 检查 `dataDir` 是否指向已存在的文件夹，并确保您的应用拥有写入权限。

## Frequently Asked Questions

**问：Aspose.Page 适合专业文档生成吗？**  
答：是的，Aspose.Page 是一个强大的库，专为在 Java 中生成高质量的 XPS 和 PDF 而设计。

**问：我可以使用 Visual Brush 自定义网格颜色吗？**  
答：当然可以！在画刷的 `setFill` 调用中更改 `createColor` 参数即可使用任意 RGBA 值。

**问：在哪里可以找到 Aspose.Page 的其他支持？**  
答：访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 获取社区帮助和官方解答。

**问：Aspose.Page 有免费试用吗？**  
答：有，您可以访问 [免费试用](https://releases.aspose.com/) 在购买前体验所有功能。

**问：如何获取用于测试的临时许可证？**  
答：获取一份适用于开发和评估的 [临时许可证](https://purchase.aspose.com/temporary-license/)。

---

**最后更新：** 2025-12-18  
**测试环境：** Aspose.Page for Java 23.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}