---
title: 在 Java PostScript 中添加水平渐变
linktitle: 在 Java PostScript 中添加水平渐变
second_title: Aspose.Page Java API
description: 了解如何使用 Aspose.Page for Java 在 Java PostScript 中添加水平渐变。轻松创建视觉上令人惊叹的文档。
type: docs
weight: 11
url: /zh/java/postscript-gradient-addition/horizontal/
---
## 介绍
欢迎来到这个关于使用 Aspose.Page for Java 在 Java PostScript 中添加水平渐变的综合教程。 Aspose.Page 是一个功能强大的 Java 库，允许开发人员使用 PostScript 和其他文档格式。在本教程中，我们将通过分步示例指导您完成创建具有水平渐变的 PostScript 文档的过程。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
- 您的计算机上安装了 Java 开发工具包 (JDK)。
- Java 库的 Aspose.Page。您可以从[Aspose.Page Java 文档](https://reference.aspose.com/page/java/).
## 导入包
首先在 Java 项目中导入必要的包。这些包对于使用 Aspose.Page 至关重要。
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## 第 1 步：创建一个矩形
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//为 PostScript 文档创建输出流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
//创建 A4 尺寸的保存选项
PsSaveOptions options = new PsSaveOptions();
//打开页面创建新的 PS 文档
PsDocument document = new PsDocument(outPsStream, options, false);
//创建一个矩形
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## 第2步：创建水平线性渐变绘画
```java
//创建水平线性渐变涂料。变换中的缩放组件必须等于矩形的宽度和高度。
//平移分量是矩形的偏移量。
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
//定漆
document.setPaint(paint);
```
## 第三步：填充矩形
```java
//填充矩形
document.fill(rectangle);
```
## 第四步：用渐变填充文本
```java
//用渐变填充文本
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## 第 5 步：用渐变描边文本
```java
//使用渐变描边文本
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## 结论
恭喜！您已使用 Aspose.Page for Java 在 Java PostScript 中成功添加水平渐变。本教程为您提供了详细的分步指南，帮助您创建具有视觉吸引力的 PostScript 文档。
## 经常问的问题
### 我可以在商业项目中使用 Aspose.Page for Java 吗？
是的，Aspose.Page for Java可以用于商业项目。有关许可详细信息，请访问[Aspose.购买](https://purchase.aspose.com/buy).
### 有免费试用吗？
是的，您可以免费试用 Aspose.Page for Java[这里](https://releases.aspose.com/).
### 在哪里可以找到其他文档和支持？
参观[Aspose.Page Java 文档](https://reference.aspose.com/page/java/)以获得综合资源。如需社区支持，请查看[Aspose.Page 论坛](https://forum.aspose.com/c/page/39).
### 我怎样才能获得临时许可证？
您可以从以下地址获取临时许可证[Aspose.购买](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java 有哪些系统要求？
请参阅[文档](https://reference.aspose.com/page/java/)了解详细的系统要求。