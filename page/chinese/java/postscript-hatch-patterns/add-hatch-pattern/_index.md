---
date: 2026-08-18
description: 学习如何使用 Aspose.Page Java 将 hatch pattern 添加到 Java PostScript 文件。此分步指南展示完整代码和技巧。
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: 在 Java PostScript 中添加 Hatch Pattern
og_description: 学习如何使用 Aspose.Page 在 Java PostScript 中添加 hatch pattern。按照此分步教程快速创建填充
  hatch 的图形。
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: 如何在 Java PostScript 中添加 hatch pattern – Aspose.Page 指南
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: 如何在 Java PostScript 中添加 hatch pattern
url: /zh/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中添加网格填充图案

## 介绍
如果您正在使用 **Aspose.Page Java** 并且想了解 **如何添加网格填充图案** 到您的 PostScript 输出，网格填充图案是一种快速且灵活的解决方案。在本教程中，我们将逐步演示 **如何添加网格** 设计到 PostScript 文档，解释其用途，并提供完整的可直接运行的代码示例。完成后，您只需几行 Java 代码即可创建视觉上吸引人的网格填充形状和文本。

## 快速答案
- **需要哪个库？** Aspose.Page for Java（“aspose page java” SDK）。  
- **我们要添加哪种视觉效果？** 网格填充图案（例如，对角线、交叉线）。  
- **运行示例是否需要许可证？** 免费试用可用于开发；生产环境需要许可证。  
- **代码行数多少？** 大约 70 行，分为清晰的步骤。  
- **可以将相同方法用于 PDF 吗？** 可以——Aspose.Page 支持多种输出格式，包括 PDF。

## 什么是网格填充图案？
网格填充图案是一种基于矢量的填充，由重复的线条或形状组成，产生纹理效果。由于它是数学定义的，图案在放大时不会失真，非常适合高分辨率打印和单色输出。

## 为什么在 Aspose.Page Java 中使用网格填充图案？
Aspose.Page 支持 **10+ 输出格式**（包括 PostScript、PDF、EPS、SVG 和 XPS），并且能够在不将整个文件加载到内存中的情况下，对多达 **500 页** 的文档渲染网格填充。这意味着您可以获得快速的性能、低内存占用以及在所有支持的格式中一致的视觉效果。

## 添加网格填充图案 – 概述
网格填充图案是基于矢量的纹理，可在任何分辨率下清晰渲染，且在单色打印机上表现良好。使用 Aspose.Page Java，您可以将这些图案应用于形状、路径，甚至文本，而无需处理低层的 PostScript 命令。

## 前置条件
在开始之前，请确保您拥有：

- **Java 开发环境** – JDK 8 或更高版本以及您选择的 IDE。  
- **Aspose.Page for Java 库** – 从官方 **Aspose.Page for Java 下载页面** [here](https://releases.aspose.com/page/java/) 下载最新的 JAR。  
- 您也可以在此处浏览其他 Aspose 发布 [here](https://releases.aspose.com/)。  
- **写入权限** 到生成的 PostScript 文件将保存的文件夹。

## 导入包
下面的导入包括用于颜色、笔画和几何形状等图形原语的标准 Java AWT 类，以及提供文档模型、网格样式定义和生成 PostScript 文件所需保存选项的 Aspose.Page 类。  
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 什么是 `Document` 类？
`Document` 类是 Aspose.Page 的顶层对象，表示内存中的单个 PostScript 文件。所有绘图操作均通过此对象执行。

## 如何设置输出流？
要写入输出，创建指向所需文件路径的 `FileOutputStream`；该流负责低层字节写入。`PsSaveOptions` 配置文档的保存方式，包括页面大小和压缩。然后使用指定页面大小、压缩以及其他 PostScript 特定设置的 `PsSaveOptions` 对象实例化 `Document`。  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## 如何保存图形状态并平移原点？
保存图形状态会捕获当前的变换矩阵、裁剪区域和绘图属性，便于稍后恢复。保存后，在图形对象上调用 `translate(x, y)` 将原点平移到绘制网格正方形的便利位置。  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## 如何为每种图案创建可重用的正方形？
`Rectangle2D` 表示由位置和大小定义的矩形形状。通过创建一个匹配单元格尺寸的实例，您可以在每个网格填充正方形中重复使用它，从而减少对象分配并保持绘制循环的高效。  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## 如何为图案正方形轮廓设置笔？
`BasicStroke` 描述矢量形状的轮廓粗细、虚线模式和端点形状。使用 2 点的 `BasicStroke` 为每个网格填充单元提供清晰的边框，确保填充与相邻正方形视觉上分离。  
```java
BasicStroke stroke = new BasicStroke(2);
```

## 如何遍历网格填充图案？
`HatchStyle` 是一个枚举，列出了所有预定义的网格填充图案，如对角线、交叉和点状样式。遍历 `HatchStyle.values()` 可依次应用每种图案，用 `HatchBrush` 填充矩形，然后绘制其轮廓。  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## 绘制后如何恢复图形状态？
在图形对象上调用 `restore()` 可将变换矩阵和绘图设置恢复到之前保存的状态，防止累计的平移或缩放影响后续绘制操作。这确保后续内容从原始坐标系开始，并使用默认属性。  
```java
document.writeGraphicsRestore();
```

## 如何使用网格填充图案填充文本？
`TextFragment` 表示可以独立定位和样式化的文本片段。通过为片段的填充分配带有选定 `HatchStyle` 的 `HatchBrush`，文本字符将使用网格纹理而非纯色进行渲染。  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## 如何使用不同的网格样式描边文本？
`HatchBrush` 也可用于描边。要绘制轮廓，请将片段的笔设置为具有不同 `HatchStyle`（例如 70 % 网格）的 `HatchBrush`，并通过 `setStrokeWidth` 增加笔宽。这样即可在保持填充内部的同时，用自己的网格图案渲染文本边框。  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## 如何关闭并保存文档？
`document.save()` 将内存中的文档写入指定的输出流。完成所有绘图命令后，调用此方法并关闭 `FileOutputStream`，以释放系统资源并确保文件正确刷新到磁盘。  
```java
document.closePage();
document.save();
```

按照这些步骤操作，您将得到一个展示完整网格填充图案集合（包括形状和文本）的 PostScript 文件——全部由 **aspose page java** 提供支持。

## 常见陷阱与技巧
- **文件路径错误** – 确保 `dataDir` 以适当的文件分隔符（`/` 或 `\`）结尾。  
- **不支持的颜色** – 某些旧的 PostScript 解释器可能无法处理特定的颜色空间；为获得最大兼容性，请使用基本的 RGB。  
- **许可证警告** – 在没有有效许可证的情况下运行示例会在输出中嵌入水印。

## 常见问题

**Q: Can I use Aspose.Page Java with other Java frameworks?**  
A: Yes, the library is framework‑agnostic and works with Spring, Jakarta EE, Android (limited), and plain Java SE.  
**Q: 是否有 Aspose.Page Java 的试用版可用？**  
A: 当然。下载免费 30 天试用 [Aspose trial download page](https://releases.aspose.com/)。  
**Q: 如何获取开发用的临时许可证？**  
A: 请求临时许可证 [temporary license request page](https://purchase.aspose.com/temporary-license/)。它会移除评估水印。  
**Q: 在哪里可以找到更多教程和社区支持？**  
A: 访问官方论坛 [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) 获取更多示例和问答。  
**Q: 是否有所有类和方法的完整文档？**  
A: 有，完整的 API 参考可在 [Aspose.Page Java API reference](https://reference.aspose.com/page/java/) 获取。  
**Q: 能否将相同的网格填充图案渲染为 PDF 而不是 PostScript？**  
A: 完全可以。将 `PsSaveOptions` 更改为 `PdfSaveOptions`（或等效对象），其余代码保持不变。  
**Q: 如果生成的文件为空该怎么办？**  
A: 验证输出流指向可写目录，并确保在所有绘图操作后调用 `document.save()`。

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## 相关教程

- [Create Texture Pattern in PostScript – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [How to Add Gradient: Diagonal Gradient in Java PostScript using Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [How to Convert PostScript to PDF Using Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}