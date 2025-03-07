---
title: 在 Java PostScript 中添加填充图案
linktitle: 在 Java PostScript 中添加填充图案
second_title: Aspose.Page Java API
description: 了解如何使用 Aspose.Page 将迷人的填充图案添加到 Java PostScript 文档中。轻松提升您的视觉内容。
weight: 10
url: /zh/java/postscript-hatch-patterns/add-hatch-pattern/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java PostScript 中添加填充图案

## 介绍
在 Java 编程领域，增强视觉元素是开发人员的常见要求。一项有趣的视觉增强功能是向 PostScript 文档添加填充图案。本教程将指导您完成使用 Aspose.Page for Java 添加填充图案的过程。
## 先决条件
在深入学习本教程之前，请确保您已进行以下设置：
- Java 开发环境：确保您已准备好 Java 开发环境。
-  Aspose.Page for Java 库：下载并安装 Aspose.Page for Java 库。就可以找到需要的文件了[这里](https://releases.aspose.com/page/java/).
## 导入包
首先，将所需的包导入到您的 Java 项目中。使用以下代码片段：
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
## 第1步：设置初始参数
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//为 PostScript 文档创建输出流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
//创建 A4 尺寸的保存选项
PsSaveOptions options = new PsSaveOptions();
//打开页面创建新的 PS 文档
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```
## 第 2 步：保存图形状态并转换
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```
## 第 3 步：为每个图案创建正方形
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```
## 步骤 4：为图案方形轮廓设置笔
```java
BasicStroke stroke = new BasicStroke(2);
```
## 第 5 步：迭代填充图案
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    //...（继续使用提供的代码）
}
```
## 第6步：恢复图形状态
```java
document.writeGraphicsRestore();
```
## 第7步：用填充图案填充文本
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```
## 第8步：用剖面线图案勾勒文本轮廓
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```
## 第 9 步：关闭并保存文档
```java
document.closePage();
document.save();
```
按照以下步骤操作，您将使用 Aspose.Page 成功地将填充图案添加到 Java PostScript 文档中。
## 结论
合并阴影图案等视觉元素可以显着增强 Java 应用程序的吸引力。 Aspose.Page for Java 使这一过程变得无缝，让您可以轻松创建视觉上令人惊叹的 PostScript 文档。
## 常见问题解答
### 我可以将 Aspose.Page for Java 与其他 Java 框架一起使用吗？
是的，Aspose.Page for Java 旨在与各种 Java 框架无缝集成。
### Aspose.Page for Java 是否有试用版？
是的，您可以免费试用[这里](https://releases.aspose.com/).
### 如何获得 Aspose.Page for Java 的临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 在哪里可以找到有关 Aspose.Page for Java 的更多教程和支持？
探索[Aspose.Page for Java 论坛](https://forum.aspose.com/c/page/39)获取教程和社区支持。
### 是否有 Aspose.Page for Java 的综合文档资源？
是的，请参阅文档[这里](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
