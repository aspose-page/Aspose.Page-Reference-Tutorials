---
date: 2026-02-18
description: 学习如何使用 Aspose.Page 在 Java PostScript 中绘制矩形形状。本分步指南展示了如何设置画笔、设置矩形颜色（Java），以及创建生动的图形，同时解释如何高效绘制矩形。
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: 如何使用 Aspose.Page 在 Java PostScript 中绘制矩形
url: /zh/java/postscript-shapes/add-rectangle/
weight: 11
---

 not actual code but placeholders. Should keep them unchanged.

We need to translate headings, paragraphs, list items, etc.

Also note "For Chinese, ensure proper RTL formatting if needed" - Chinese is LTR, ignore.

Proceed to translate.

Let's produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中使用 Aspose.Page 绘制矩形

## 介绍
如果你需要在 Java PostScript 文件中 **绘制矩形**，这里就是正确的地方。在本教程中，我们将演示如何使用 Aspose.Page for Java 添加彩色矩形、控制填充和描边，并将结果保存为 PostScript 文档。你将看到 **如何设置 paint**、如何定义矩形的几何形状，以及为什么这种方法非常适合以编程方式生成可打印的图形。阅读完本指南后，你还会了解 **draw rectangle java** 技术的更广泛背景，以及它们在 **java awt rectangle drawing** 工作流中的作用。

## 快速回答
- **需要哪个库？** Aspose.Page for Java  
- **可以更改矩形颜色吗？** 可以 – 使用 `setPaint` 并传入任意 `java.awt.Color`  
- **开发阶段需要许可证吗？** 免费试用可用于测试；生产环境需要许可证  
- **示例使用的页面尺寸是什么？** A4（默认 `PsSaveOptions`）  
- **代码兼容 Java 8+ 吗？** 完全兼容 – 使用的是标准 AWT 类  

## 什么是 PostScript 中的 “How to Draw Rectangle”？
在 PostScript 文档中绘制矩形意味着定义一个矩形区域，并对其进行填充、描边或两者兼有。使用 Aspose.Page，你可以通过熟悉的 **java awt rectangle drawing** 类来完成，这使得代码易于阅读和维护。

## 为什么选择 Aspose.Page 绘制矩形图形？
- **跨平台**：生成的标准 PostScript 可在任何打印机上使用。  
- **细粒度控制**：可以独立设置填充颜色、描边颜色和线宽。  
- **无外部依赖**：仅使用内置的 AWT 几何类，无需额外的图形库。  

## 前置条件
在开始教程之前，请确保已满足以下前置条件：
- 具备基本的 Java 编程知识。  
- 已安装 Aspose.Page for Java 库。若未安装，请从 [Aspose.Page for Java 文档](https://reference.aspose.com/page/java/) 下载。  
- 在你的机器上配置好 Java 开发环境。

## 导入包
在 Java 项目中，首先导入所需的包。这些导入让你能够使用 AWT 的 `Color`、`BasicStroke`、`Rectangle2D` 类，以及 Aspose.Page 的核心文档处理类。

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步骤指南：在 Java PostScript 中绘制矩形

### 步骤 1：设置矩形填充的 Paint  
**如何设置 paint** – 我们为第一个矩形选择橙色填充。这演示了 **set rectangle color java** 的能力。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### 步骤 2：设置矩形描边的 Paint  
**Set rectangle color java** – 现在将 paint 改为红色并定义描边宽度。此示例展示了如何使用自定义线粗细 **draw rectangle java**。

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### 步骤 3：关闭当前页面并保存文档  
绘制完成后，关闭页面并持久化文件。关闭页面可确保所有绘图指令被刷新到 PostScript 流中。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## 矩形绘制的常见使用场景
- **发票或收据生成** – 矩形用作边框或突出显示区域。  
- **标签制作** – 绘制彩色框以分隔商品信息。  
- **简易图表** – 使用填充矩形作为条形图元素。  
- **自定义可打印表单** – 将矩形与文字结合构建表单字段。

## 常见问题与技巧
- **文件路径错误** – 确保 `dataDir` 以文件分隔符（`/` 或 `\\`）结尾。  
- **许可证异常** – 试用版会添加水印；生产环境请获取正式许可证。  
- **颜色可见性** – 某些打印机对特定 RGB 值的解释可能不同；建议先用黑色矩形测试。  
- **内存使用** – 对于大型文档，考虑在每页后刷新流（`document.closePage()`）。

## 常见问答

**问：** *我可以在其他编程语言中使用 Aspose.Page for Java 吗？*  
**答：** Aspose.Page 主要支持 Java，但其他语言也有类似的库可供选择。

**问：** *Aspose.Page for Java 有试用版吗？*  
**答：** 有，您可以通过 [免费试用版](https://releases.aspose.com/) 体验 Aspose.Page for Java 的功能。

**问：** *在哪里可以找到更多帮助和讨论？*  
**答：** 访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 与社区交流并获取支持。

**问：** *如何获取 Aspose.Page for Java 的临时许可证？*  
**答：** 请前往 [此处](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**问：** *在哪里可以购买 Aspose.Page for Java 的正式许可证？*  
**答：** 请在 [此处](https://purchase.aspose.com/buy) 进行购买。

**补充问答**

**问：** *我可以动态更改矩形大小吗？*  
**答：** 可以 – 在调用 `fill` 或 `draw` 之前，只需修改 `Rectangle2D.Float(x, y, width, height)` 参数。

**问：** *可以在矩形内部添加文字吗？*  
**答：** 完全可以。绘制矩形后，使用 `document.drawString(...)` 并指定所需的字体和位置即可。

**问：** *Aspose.Page 支持绘制其他形状，如圆形或多边形吗？*  
**答：** 支持，API 提供了 `drawEllipse`、`drawPolygon` 等方法，可绘制多种矢量图形。

## 结论
本指南演示了在 Java PostScript 文档中 **绘制矩形** 的方法，涵盖了 **如何设置 paint**，并展示了如何使用 Aspose.Page **设置矩形颜色 java**。现在，你已经具备了创建丰富可打印图形的坚实基础，无论是用于发票、标签还是自定义表单。欢迎尝试不同的颜色、线型以及其他 AWT 形状，以丰富你的输出效果。

---

**最后更新：** 2026-02-18  
**测试环境：** Aspose.Page for Java 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}