---
date: 2026-02-18
description: 学习如何使用 Aspose.Page 在 Java 中设置绘图颜色并创建 PostScript 椭圆。本指南展示了如何在 Java 中填充椭圆、绘制椭圆轮廓以及设置笔画粗细。
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: 在 Java 中设置绘图颜色以绘制 PostScript 椭圆
url: /zh/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中设置绘制 PostScript 椭圆的颜色

## 介绍
如果您在绘制矢量图形时需要 **set paint color**，Aspose.Page for Java 库可以让您完全控制每一次描边和填充。在本教程中，您将学习如何 **set paint color**、**fill ellipse Java** 和 **draw ellipse outline**，通过简单的逐步方法。完成后，您就可以在发票、报告或任何可打印文档中添加高质量的 PostScript 椭圆。

## 快速回答
- **在 Java 中绘制 PostScript 图形的最佳库是什么？** Aspose.Page for Java.  
- **我可以用纯色填充椭圆吗？** 可以——在 `fill` 之前使用 `document.setPaint(Color.YOUR_COLOR)`。  
- **如何仅绘制椭圆的轮廓？** 设置 paint 和 stroke，然后调用 `document.draw(...)`。  
- **生产环境是否需要许可证？** 需要商业许可证；可获取临时许可证用于测试。  
- **支持哪个 Java 版本？** 任何 Java 8 以上的运行时都可与当前的 Aspose.Page 版本配合使用。

## 什么是 PostScript 椭圆？
PostScript 椭圆是一种由边界矩形定义的矢量形状。与光栅图像不同，它可以在不失真的情况下缩放，非常适合高分辨率打印和 PDF 转换。

## 为什么使用 Aspose.Page 创建 PostScript 椭圆？
- **完整控制** 绘图基元（线条、曲线、椭圆）。  
- **跨平台**——在 Windows、Linux 和 macOS 上均可运行。  
- **无外部依赖**——纯 Java API，无本机代码。  
- **易于集成** 与现有的 Java 应用程序和构建工具。

## 先决条件
在开始之前，请确保您拥有：

1. 可用的 Java 开发环境（JDK 8 或更高）。  
2. 已在项目中添加 Aspose.Page for Java 库。您可以在 **[here](https://releases.aspose.com/page/java/)** 下载。

## 导入包
在您的 Java 源文件中，导入绘制和保存 PostScript 内容所需的类。

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 如何为椭圆设置绘图颜色
在进行任何填充或描边操作之前，首先需要设置绘图颜色。`setPaint` 方法决定了下一条绘图指令将使用的颜色。

### 步骤 1：设置 PostScript 文档
创建输出流，配置页面大小，并实例化 `PsDocument`。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 步骤 2：如何填充椭圆 – 使用 set paint color
要 **fill ellipse**，必须先使用所需的填充颜色调用 `setPaint`，然后使用 `Ellipse2D` 实例调用 `fill`。

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### 步骤 3：绘制椭圆轮廓并设置笔触粗细
填充后，您可以将 paint 更改为其他颜色，定义 `BasicStroke` 来控制线宽，并绘制椭圆轮廓。

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### 步骤 4：关闭并保存文档
完成页面并将 PostScript 文件写入磁盘。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

现在您已经拥有一个包含两个椭圆的 PostScript 文件——一个填充橙色，另一个用红色描边。欢迎尝试不同的坐标、尺寸和颜色，以满足您的设计需求。

## 常见问题与故障排除
- **文件路径错误**——确保 `dataDir` 以适合您操作系统的分隔符（`/` 或 `\\`）结尾。  
- **缺少许可证**——没有有效许可证时，库会以评估模式运行，并可能添加水印。  
- **颜色未生效**——请记得在每次 `fill` 或 `draw` 调用 *之前* 设置 `document.setPaint(...)`；paint 设置不会自动在不同操作之间保持。

## 常见问答

**Q: 我可以将 Aspose.Page for Java 与其他 Java 库一起使用吗？**  
A: 可以，Aspose.Page for Java 旨在与其他 Java 库无缝集成。

**Q: 我如何获取 Aspose.Page for Java 的临时许可证？**  
A: 可在 **[here](https://purchase.aspose.com/temporary-license/)** 获取用于测试的临时许可证。

**Q: Aspose.Page 适用于商业项目吗？**  
A: 绝对适用！请访问 **[here](https://purchase.aspose.com/buy)** 了解商业使用的授权选项。

**Q: 我可以在哪里寻求帮助或讨论 Aspose.Page 相关问题？**  
A: 加入 **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** 社区进行讨论和获取帮助。

**Q: 有哪些免费资源可以进一步了解 Aspose.Page for Java 吗？**  
A: 使用 **[free trial](https://releases.aspose.com/)** 并在文档中查看示例。

## 结论
Aspose.Page for Java 使 **set paint color**、**fill ellipse** 和 **draw ellipse outline** 变得简单——无论您需要的是简单的填充形状还是复杂的描边图形。通过上述步骤，您可以快速为任何可打印文档添加专业级矢量图形。想进一步探索——例如组合多个形状、应用渐变或转换为 PDF——请参考官方 **[documentation](https://reference.aspose.com/page/java/)**。

---

**最后更新：** 2026-02-18  
**测试环境：** Aspose.Page for Java 24.11  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}