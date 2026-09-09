---
date: 2026-09-09
description: 了解如何在 Java PostScript 中创建渐变，并使用 Aspose.Page 将渐变添加到形状。请按照本一步一步的指南，查看代码和技巧。
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: 使用 Aspose.Page 的 Java PostScript 径向渐变
og_description: 了解如何在 Java PostScript 中创建渐变，并使用 Aspose.Page 将渐变添加到形状。请按照本一步一步的指南，查看代码和技巧。
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: 如何在 Java PostScript 中使用径向填充创建渐变
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: 如何在 Java PostScript 中使用径向填充创建渐变
url: /zh/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中使用径向填充创建渐变

## 介绍
在本教程中，您将学习如何使用 Java 和 Aspose.Page 在 PostScript 文档中**创建渐变**图形。我们将逐步演示——从项目设置到渲染一个填充平滑径向渐变的圆形——让您能够**即时为形状添加渐变**，提升 Java 应用程序的视觉质量。

## 快速答案
- **本教程创建了什么？** 一个包含径向渐变填充圆形的 PostScript 文件（`.ps`）。  
- **需要哪个库？** Aspose.Page for Java（最新版本）。  
- **实现需要多长时间？** 大约 10‑15 分钟即可得到可运行的示例。  
- **是否需要许可证？** 生产环境需要临时或正式许可证；开发阶段可使用免费试用版。  
- **代码能否复用于 PDF 或 SVG？** 可以——Aspose.Page 支持多种输出格式，只需少量修改。

## 如何在 PostScript 中使用渐变填充形状
您可以通过创建 `PsDocument`、定义 `RadialGradientPaint`、将其应用到目标形状并最终保存文档的方式，在 PostScript 中使用径向渐变填充形状。此简洁工作流让您无需栅格图像即可生成专业级矢量图形，同一段代码也可复用于 PDF 或 SVG 输出。该过程直观且在所有受支持的格式中表现一致。

## 什么是径向渐变？
径向渐变从中心点向外过渡颜色，形成平滑的圆形混合。它非常适合用于高光、按钮背景或任何需要自然“发光”效果的视觉元素。通过调整颜色停点和半径，您可以在纯矢量形式中模拟光照、深度和材质属性。

## 为什么使用 Aspose.Page 实现径向渐变？
Aspose.Page 让您通过单一的 Java API 生成与设备无关的矢量图形。它支持超过 50 种输入和输出格式——包括 PostScript、PDF 和 SVG——同时保持颜色准确性和高分辨率输出的抗锯齿。该库还提供易于使用的渐变类，使复杂的视觉效果实现变得简单。

## 前置条件
在开始之前，请确保您具备：

- 对 Java 编程有基本了解。  
- 已在机器上安装 JDK 8 或更高版本。  
- Aspose.Page for Java 库（可从 [Aspose.Page Java 文档](https://reference.aspose.com/page/java/) 下载）。  

## 导入包
首先，导入我们需要的类。这些包括标准的 AWT 图形类型以及 Aspose.Page API。

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步骤 1：设置文档目录
定义生成的 PostScript 文件将保存的文件夹。将占位符替换为系统中的实际路径。

```java
String dataDir = "Your Document Directory";
```

## 步骤 2：创建输出流
`FileOutputStream` 将原始字节写入文件，允许保存二进制数据。打开指向 `.ps` 文件的流后，Aspose.Page 可直接将生成的 PostScript 数据流式写入磁盘。

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## 步骤 3：创建保存选项
`PsSaveOptions` 配置 PostScript 文件的保存方式，包括页面尺寸和压缩方式。您可以自定义这些设置，但默认值已足够本示例使用。

```java
PsSaveOptions options = new PsSaveOptions();
```

## 步骤 4：创建 ps 文档
`PsDocument` 表示内存中的 PostScript 文档，并提供添加页面和图形的方法。

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步骤 5：创建圆形
`Ellipse2D.Float` 描述椭圆形状；当宽度 = 高度时即为完美圆形。该对象将作为我们渐变填充的画布。

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## 如何使用渐变绘制圆形
要使用径向渐变绘制圆形，您需要将 `RadialGradientPaint` 加载到图形上下文中，然后填充先前定义的椭圆。此单一步骤即可实现从中心向外的平滑颜色过渡，产生视觉上令人愉悦的效果。

## 步骤 6：定义渐变颜色
准备两个数组：一个用于渐变中的颜色，另一个用于对应的分数位置（0 = 中心，1 = 边缘）。

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## 步骤 7：创建仿射变换
`AffineTransform` 是一个矩阵，可对图形对象进行平移、旋转、缩放或剪切。这里它用于缩放并平移渐变，使其恰好适配圆形内部。

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## 步骤 8：创建径向渐变画笔
`RadialGradientPaint` 根据中心点、半径和颜色停点创建径向颜色渐变。

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## 步骤 9：设置画笔并填充圆形
将渐变画笔应用到文档并填充先前定义的圆形。这是我们**径向渐变示例**的核心，演示了如何**使用渐变填充形状**。

```java
document.setPaint(paint);
document.fill(circle);
```

## 步骤 10：关闭页面并保存文档
完成页面，写入磁盘并关闭流。您的 PostScript 文件现在可以使用任何 PS 查看器打开。

```java
document.closePage();
document.save();
```

恭喜！您已成功使用 Aspose.Page 在 Java PostScript 中创建了径向渐变示例。现在您拥有了一个可复用的**使用渐变填充形状**模式，可适配其他形状和 Aspose.Page 支持的输出格式。

## 常见问题与解决方案
| 问题 | 解决方案 |
|---------|----------|
| **FileNotFoundException** 在打开输出流时出现 | 确认 `dataDir` 指向的文件夹存在且您拥有写入权限。 |
| 渐变显示平坦或缺失 | 确保 `fractions` 数组长度与 `colors` 数组相匹配，并检查 `AffineTransform` 的缩放是否正确。 |
| 颜色出现倒置 | 调换 `colors` 数组中的颜色顺序或调整 `focus` 点坐标。 |

## 常见问答

**问：在哪里可以找到 Aspose.Page for Java 的文档？**  
答：完整的 API 参考位于 [Aspose.Page Java API 文档](https://reference.aspose.com/page/java/)。

**问：如何下载 Aspose.Page for Java？**  
答：从 [releases 页面](https://releases.aspose.com/page/java/) 获取最新的 JAR 包。

**问：是否提供免费试用？**  
答：是的——可从 [Aspose 免费试用下载页面](https://releases.aspose.com/) 下载试用版。

**问：我可以获取临时许可证用于测试吗？**  
答：当然，可以在 [临时许可证页面](https://purchase.aspose.com/temporary-license/) 申请。

**问：在哪里可以获得社区支持？**  
答：加入 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 进行讨论。

## 结论
本指南展示了如何使用 Aspose.Page for Java 为 PostScript 文档构建完整的**径向渐变示例**。通过遵循上述步骤，您现在拥有了一个可复用的**使用渐变填充形状**模式，可轻松迁移至 PDF、SVG 或 Aspose.Page 支持的任何其他格式。尝试不同的颜色、半径和形状，丰富您的 Java 图形项目。

---

**最后更新：** 2026-09-09  
**测试环境：** Aspose.Page for Java 24.11（撰写时最新）  
**作者：** Aspose

## 相关教程

- [在 Java 中创建 PostScript 渐变 – 添加垂直渐变](/page/java/postscript-gradient-addition/vertical/)
- [在 PostScript 中使用 Aspose.Page for Java 创建纹理图案](/page/java/postscript-texture-patterns/)
- [Aspose.Page 透明度教程 – 在 Java PostScript 中添加透明度](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}