---
date: 2025-12-11
description: 学习如何使用 Aspose.Page 在 Java PostScript 中绘制矩形形状。本分步指南展示了如何设置绘图、设置矩形颜色（Java），以及创建生动的图形。
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: 如何使用 Aspose.Page 在 Java PostScript 中绘制矩形
url: /zh/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page 在 Java PostScript 中绘制矩形

## Introduction
如果您需要在 Java PostScript 文件中绘制矩形形状，您来对地方了。在本教程中，我们将演示如何使用 Aspose.Page for Java 添加彩色矩形，控制填充和描边，并将结果保存为 PostScript 文档。您将看到如何 **设置 paint**，如何定义矩形的几何形状，以及为什么这种方法适合以编程方式生成可打印的图形。

## Quick Answers
- **需要的库是什么？** Aspose.Page for Java  
- **我可以更改矩形颜色吗？** 是 – 使用 `setPaint` 并传入任意 `java.awt.Color`  
- **开发时需要许可证吗？** 免费试用可用于测试；生产环境需要许可证  
- **示例使用的页面尺寸是什么？** A4（默认 `PsSaveOptions`）  
- **代码是否兼容 Java 8+？** 完全兼容 – 使用标准 AWT 类  

## Prerequisites
在开始教程之前，请确保您具备以下前提条件：
- 基本的 Java 编程理解。  
- 已安装 Aspose.Page for Java 库。若未安装，可从 [Aspose.Page for Java 文档](https://reference.aspose.com/page/java/) 下载。  
- 在您的机器上已搭建好 Java 开发环境。

## Import Packages
在您的 Java 项目中，首先导入必要的包：

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## How to Draw Rectangle in Java PostScript
以下是完整的工作流程，分为清晰的步骤。每一步都包含简短说明以及原始代码块（保持不变）。

### Step 1: Set Paint for Filling Rectangle  
**如何设置 paint** – 我们为第一个矩形选择橙色填充颜色。

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

### Step 2: Set Paint for Stroking Rectangle  
**设置矩形颜色 java** – 现在我们将 paint 改为红色并定义描边宽度。

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Step 3: Close Current Page and Save Document  
绘制完成后，我们关闭页面并保存文件。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Why Use Aspose.Page for Rectangle Graphics?
- **跨平台**：生成的标准 PostScript 可在任何打印机上使用。  
- **细粒度控制**：可以独立设置填充颜色、描边颜色和线宽。  
- **无外部依赖**：仅使用内置的 AWT 几何类。  

## Common Issues & Tips
- **文件路径错误** – 确保 `dataDir` 以文件分隔符（`/` 或 `\\`）结尾。  
- **许可证异常** – 试用版会添加水印；生产使用请获取正式许可证。  
- **颜色可见性** – 某些打印机可能对特定 RGB 值解释不同；建议先使用简单的黑色矩形进行测试。  

## Conclusion
在本指南中，我们演示了 **如何在 Java PostScript 文档中绘制矩形**，介绍了 **如何设置 paint**，并展示了使用 Aspose.Page **设置矩形颜色 java** 的方法。欢迎尝试不同的形状、颜色和线型，以创建用于报表、发票或自定义打印的丰富可打印图形。

## Frequently Asked Questions

### 我可以在其他编程语言中使用 Aspose.Page for Java 吗？
Aspose.Page 主要支持 Java，但其他语言也有类似的库可供选择。

### 是否有 Aspose.Page for Java 的试用版可用？
有，您可以通过 [免费试用版](https://releases.aspose.com/) 体验 Aspose.Page for Java 的功能。

### 我在哪里可以找到更多帮助和讨论？
访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 与社区交流并获取帮助。

### 如何获取 Aspose.Page for Java 的临时许可证？
请在此处获取临时许可证 [here](https://purchase.aspose.com/temporary-license/)。

### 我在哪里可以购买 Aspose.Page for Java 的正式许可证？
请在此处购买正式许可证 [here](https://purchase.aspose.com/buy)。

**Additional Q&A**

**Q:** *我可以动态更改矩形的大小吗？*  
**A:** 可以 – 在调用 `fill` 或 `draw` 之前，只需修改 `Rectangle2D.Float(x, y, width, height)` 参数即可。

**Q:** *可以在矩形内部添加文字吗？*  
**A:** 完全可以。绘制矩形后，使用 `document.drawString(...)` 并指定所需的字体和位置即可。

**Q:** *Aspose.Page 是否支持除矩形外的其他形状，如圆形或多边形？*  
**A:** 支持，API 提供了 `drawEllipse`、`drawPolygon` 等方法，可绘制多种矢量图形。

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}