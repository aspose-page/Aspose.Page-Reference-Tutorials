---
date: 2026-02-15
description: 学习如何使用 Aspose.Page Java 为 Java PostScript 文件添加交叉线图案。本分步指南展示完整代码和技巧。
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 如何在 Java PostScript 中使用 Aspose.Page 添加填充图案
url: /zh/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中添加填充图案

## 介绍
如果您正在使用 **Aspose.Page Java** 并且想了解 **如何向 PostScript 输出添加填充图案**，填充图案是一种快速且灵活的解决方案。在本教程中，我们将逐步演示 **如何向 PostScript 文档添加填充** 设计，解释其用途，并提供完整、可直接运行的代码示例。完成后，您只需几行 Java 代码即可创建视觉上吸引人的填充图案形状和文字。

## 快速回答
- **需要哪个库？** Aspose.Page for Java（即 “aspose page java” SDK）。  
- **我们要添加哪种视觉效果？** 填充图案（例如对角线、交叉线）。  
- **运行示例是否需要许可证？** 开发阶段可使用免费试用版；生产环境需要许可证。  
- **代码行数大概多少？** 大约 70 行，分为清晰的步骤。  
- **可以将相同方法用于 PDF 吗？** 可以——Aspose.Page 支持多种输出格式，包括 PDF。

## 添加填充图案 – 概览
填充图案是基于向量的纹理，可在任何分辨率下保持清晰，并且在单色打印机上表现良好。使用 Aspose.Page Java，您可以将这些图案应用于形状、路径，甚至文字，而无需处理底层的 PostScript 命令。

## 前置条件
在开始之前，请确保您拥有：

- **Java 开发环境** – JDK 8 或更高版本，以及您喜欢的 IDE。  
- **Aspose.Page for Java 库** – 从官方站点[此处](https://releases.aspose.com/page/java/)下载最新 JAR。  
- **写入权限** – 对将保存生成的 PostScript 文件的文件夹拥有写入权限。

## 导入包
首先，将所需的类引入项目。这些导入让您能够使用绘图原语、颜色处理以及 Aspose.Page API。

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

## 步骤 1：设置初始参数
创建输出流，配置页面尺寸（A4），并定义在绘制每个填充方块时会重复使用的布局变量。

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

## 步骤 2：保存图形状态并平移
保存图形状态可以让我们在后续返回原始坐标系，而 `translate` 则将原点移动到一个方便的起始位置。

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## 步骤 3：为每种图案创建方块
定义一个可复用的矩形，作为每个填充单元格的表示。

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## 步骤 4：为图案方块轮廓设置画笔
使用 2 点的 `BasicStroke` 为每个方块提供清晰的轮廓。

```java
BasicStroke stroke = new BasicStroke(2);
```

## 步骤 5：遍历填充图案
遍历 `HatchStyle` 枚举中的每个值，用相应的纹理填充每个方块，然后绘制其轮廓。这是 **添加填充图案** 功能的核心。

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## 步骤 6：恢复图形状态
在完成方块网格的绘制后，返回原始坐标系。

```java
document.writeGraphicsRestore();
```

## 步骤 7：使用填充图案绘制文字
此示例演示如何使用填充纹理为文字上色。示例将单词 “ABC” 填充为对角交叉图案。

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## 步骤 8：使用填充图案描边文字
现在对同一文字进行描边，这次使用 70 % 的填充样式和更粗的笔触。

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## 步骤 9：关闭并保存文档
完成页面后，将文件写入磁盘并释放资源。

```java
document.closePage();
document.save();
```

按照这些步骤操作，您将得到一个展示完整填充图案集合的 PostScript 文件，图案同时应用于形状和文字——全部由 **aspose page java** 提供支持。

## 为什么在 Aspose.Page Java 中使用填充图案？
- **视觉区分度** – 即使在仅支持单色输出的打印机上，填充图案仍能清晰呈现。  
- **性能** – 纹理实时生成，避免了大尺寸图像文件。  
- **跨格式支持** – 相同代码可轻松切换至 PDF、EPS 或 SVG，只需极少改动。

## 常见陷阱与技巧
- **文件路径错误** – 确保 `dataDir` 以正确的文件分隔符（`/` 或 `\`）结尾。  
- **不受支持的颜色** – 某些旧版 PostScript 解释器可能不兼容特定颜色空间；为获得最大兼容性，请使用基本的 RGB。  
- **许可证警告** – 未使用有效许可证运行示例会在输出中嵌入水印。

## 结论
使用填充图案可以显著提升技术图纸、地图或任何由 Java 生成的图形的可读性和美观度。借助 **Aspose.Page Java**，您可以使用简洁的 API 抽象底层 PostScript 命令，专注于设计而非文件格式细节。现在您已经掌握 **如何在 PostScript 文档中添加填充图案**——尝试不同的 `HatchStyle` 值，创建符合需求的外观。

## 常见问题

**问：可以将 Aspose.Page Java 与其他 Java 框架一起使用吗？**  
答：可以，库与框架无关，可在 Spring、Jakarta EE、Android（受限）以及普通 Java SE 中使用。

**问：Aspose.Page Java 是否提供试用版？**  
答：当然。免费 30 天试用版可在[此处](https://releases.aspose.com/)下载。

**问：如何获取开发用的临时许可证？**  
答：在[此处](https://purchase.aspose.com/temporary-license/)申请临时许可证，可去除评估水印。

**问：在哪里可以找到更多教程和社区支持？**  
答：访问官方论坛 [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)获取更多示例和问答。

**问：是否有完整的类和方法文档？**  
答：有，完整的 API 参考可在[此处](https://reference.aspose.com/page/java/)查看。

**问：能否将相同的填充图案渲染为 PDF 而不是 PostScript？**  
答：完全可以。将 `PsSaveOptions` 替换为 `PdfSaveOptions`（或等效选项），其余代码保持不变。

**问：如果生成的文件为空该怎么办？**  
答：检查输出流指向的目录是否可写，并确保在所有绘图操作完成后调用 `document.save()`。

---

**最后更新：** 2026-02-15  
**测试环境：** Aspose.Page for Java 24.12（撰写时最新）  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}