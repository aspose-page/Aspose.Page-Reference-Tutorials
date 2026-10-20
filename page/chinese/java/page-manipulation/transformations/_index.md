---
date: 2026-10-20
description: 了解如何使用 Aspose.Page for Java scale rectangle、translate shape，并 apply affine
  transform 来创建 PostScript 文档。
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Java 页面操作中的 Transformations
og_description: 了解如何使用 Aspose.Page for Java scale rectangle、translate shape，并 apply
  affine transform 高效生成 PostScript 文件。
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: 如何使用 Aspose.Page for Java scale rectangle – step by step guide
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: 如何使用 Aspose.Page for Java scale rectangle
url: /zh/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page for Java 缩放矩形

## 介绍
在本指南中，您将了解如何使用 Aspose.Page for Java **how to scale rectangle** 对象，同时学习如何平移形状位置、旋转图形以及应用仿射变换操作以生成高质量的 PostScript 输出。这些技术使您能够构建复杂的、设备无关的图形，而无需编写底层渲染代码，从而使您的 Java 应用程序更强大且更易维护。

## 快速答案
`scale(sx, sy)` 按给定的水平和垂直因子缩放图形上下文。  

- **如何在 Java 中使用 Aspose.Page 缩放矩形？** 在绘制矩形之前，对图形上下文调用 `scale(sx, sy)` 方法。  
- **我可以移动（平移）形状而不影响其他图形吗？** 可以——在 `writeGraphicsSave()` 和 `writeGraphicsRestore()` 调用之间包装平移操作。  
- **哪个类用于创建 PostScript 文件？** 使用 `PsDocument` 配合 `PsSaveOptions`。  
- **生产环境是否需要许可证？** 商业部署需要有效的 Aspose.Page 许可证。  
- **支持哪个 Java 版本？** Aspose.Page 支持 Java 8 及更高版本。

## 前提条件
在开始之前，请确认您具备以下条件：

- 扎实的核心 Java 语法和面向对象概念。  
- 已安装 Aspose.Page for Java 库。您可以从 [Aspose.Page for Java 文档](https://reference.aspose.com/page/java/) 下载。  
- 已配置好将库的 JAR 文件加入类路径的 Java IDE（IntelliJ IDEA、Eclipse 或 VS Code）。

## 导入包
`PsDocument` 是用于创建 PostScript 文档的主要类，`PsSaveOptions` 用于配置文档的保存方式。  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Aspose.Page 中的 “how to scale rectangle” 是什么？
`scale(float sx, float sy)` 方法对当前图形状态应用仿射缩放变换，按因子 `sx`（水平）和 `sy`（垂直）调整后续绘图的大小。这是 **how to scale rectangle** 关键字背后的核心操作。在绘制之前应用此变换，后续的形状（如矩形）将在保持比例的同时以新的尺寸渲染。

## 如何使用 Aspose.Page 平移形状
`writeGraphicsSave()` 保存当前图形状态，`writeGraphicsRestore()` 恢复该状态，确保变换仅影响目标形状。平移会重新定位坐标系的原点，而不改变对象的尺寸。通过在 `translate(dx, dy)` 前后分别调用 `writeGraphicsSave()` 和 `writeGraphicsRestore()`，可以确保只有目标形状移动，其他图形保持不变，从而对单个元素实现精确控制。

## 示例 1：无变换
第一个示例在没有任何变换的情况下绘制矩形，为后续示例的视觉比较提供基准。  

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## 示例 2：平移
在此示例中，我们在绘制第二个矩形之前将图形上下文向右移动 250 单位，演示 **how to translate shape**。  

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## 示例 3：缩放
这里我们回答主要问题 **how to scale rectangle**。通过调用 `scale(0.5f, 0.75f)`，矩形的宽度缩小至原始的 50%，高度缩小至原始的 75%。  

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## 如何在 Java 中旋转形状（rotate shape java）
`rotate(angle)` 按指定的角度（度）旋转坐标系。加载 `PsDocument`，在图形状态上调用 `rotate(angle)`，绘制形状，然后恢复之前的状态。此模式在单个可复用块中实现了 **rotate shape java** 和 **how to rotate rectangle**，使您能够围绕任意点旋转图形。

## 为什么这很重要 – 实际收益
- **设备无关的输出** – Aspose.Page 能生成在任何打印机或查看器上渲染完全相同的 PostScript 和 XPS 文件，消除平台特定的调整。  
- **细粒度控制** – 结合平移、缩放、剪切和旋转以满足精确的布局规范；API 支持每页超过 20 种变换组合。  
- **面向性能的处理** – 对于典型的 100 页报告，库的内存占用低于 10 MB，使批处理作业快速且可扩展。

## 常见使用场景
- **可打印发票** – 使用缩放和平移精确放置徽标、条形码和表格，以符合企业品牌指南。  
- **技术图纸** – 生成每个组件必须按比例调整大小并定位的示意图。  
- **自动化多页报告** – 创建在各页之间需要一致缩放的 PostScript 报告，例如工程规范。

## 常见问题及解决方案
- **变换未重置** – 始终将 `writeGraphicsSave()` 与 `writeGraphicsRestore()` 配对使用；否则后续绘图会继承不需要的变换。  
- **颜色异常** – 在每次变换后设置绘图颜色，因为恢复后图形状态不保留颜色信息。  
- **文件过大** – 在 `PsSaveOptions` 中启用压缩，并限制嵌入栅格图像的分辨率，以保持典型 50 页文档的最终文件大小在 5 MB 以下。

## 常见问答

### 我可以将 Aspose.Page for Java 用于其他文档格式吗？
Aspose.Page 主要专注于 PostScript 和 XPS 格式的页面操作，但也提供有限的 PDF 导出功能。

### 在哪里可以找到更多 Aspose.Page for Java 的示例和文档？
请访问 [Aspose.Page for Java 文档](https://reference.aspose.com/page/java/) 获取完整的指南、API 参考和示例项目。

### 是否提供 Aspose.Page for Java 的免费试用？
是的，您可以通过 **Aspose 免费试用下载** 页面获取免费试用：[Aspose 免费试用下载](https://releases.aspose.com/)。

### 如何获取 Aspose.Page for Java 的临时许可证？
可通过 **临时许可证请求页面** 获取临时许可证：[temporary license request page](https://purchase.aspose.com/temporary-license/)。

### 在哪里可以获得社区支持或提问关于 Aspose.Page for Java 的问题？
请访问 [Aspose.Page for Java 论坛](https://forum.aspose.com/c/page/39) 参与社区讨论、获取代码片段和故障排除技巧。

## 常见问题

**Q: `translate` 与 `scale` 有何区别？**  
A: `translate` 移动坐标系的原点，而 `scale` 改变绘制对象在 X 和/或 Y 轴上的大小。

**Q: 我可以在单个图形状态中组合多个变换吗？**  
A: 可以——在绘制之前依次调用 `translate`、`scale`、`rotate` 或 `shear`，即可创建组合的仿射变换。

**Q: 绘制形状后如何重置变换？**  
A: 使用 `writeGraphicsRestore()` 恢复到先前保存的图形状态。

**Q: 能否围绕矩形中心旋转它？**  
A: 完全可以。先将矩形平移到原点，应用 `rotate(angle)`，然后在绘制前再平移回原位置。

**Q: Aspose.Page 是否支持抗锯齿以获得更平滑的图形？**  
A: 是的——在 `PsSaveOptions` 中设置相应的渲染选项即可启用抗锯齿。

---

**最后更新：** 2026-10-20  
**测试环境：** Aspose.Page for Java 24.12  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose.Page 在 Java PostScript 中绘制矩形](/page/java/postscript-shapes/add-rectangle/)
- [在 PostScript 中使用 Aspose.Page for Java 创建径向渐变](/page/java/postscript-gradient-addition/)
- [PostScript 页面操作](/page/java/postscript-page-manipulation/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}