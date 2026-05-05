---
date: 2026-05-05
description: 了解如何使用 Aspose.Page for Java 向 PostScript 文档添加纹理平铺图案。本指南展示了如何高效添加纹理并探索创意可能性。
keywords:
- how to add texture
- fill shape with texture
- fill rectangle with texture
linktitle: 在 Java PostScript 中添加纹理平铺模式
second_title: Aspose.Page Java API
title: 如何在 Java PostScript 中添加纹理平铺模式
url: /zh/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中添加纹理平铺模式

## 介绍
在 Java 开发领域，学习 **how to add texture** 到 PostScript 文档是一个常见需求。Aspose.Page for Java 使此任务变得简单，让您专注于设计而不是低层次的 PostScript 语法。在本教程中，我们将逐步演示如何添加纹理平铺模式、填充形状，甚至在 Java PostScript 文档中对文本进行纹理处理。

## 快速答案
- **需要的库是什么？** Aspose.Page for Java  
- **本指南的主要关键词是什么？** *how to add texture*  
- **我需要许可证进行测试吗？** 有免费试用版；生产环境需要许可证。  
- **支持的 Java 版本是什么？** Java 8 或更高。  
- **我可以在多个形状上重复使用纹理画刷吗？** 可以 – 只需创建一次 `TexturePaint`，并将其应用于任何形状。  
- **如何使用纹理填充矩形？** 在将 `TexturePaint` 设置为当前画笔后，使用 `document.fill(shape)`。

## 什么是纹理平铺模式？
纹理平铺模式会在更大的区域中重复一个小图像（瓦片），使您能够 **fill shape with texture** 而无需手动绘制每个瓦片。这种技术非常适合用于 PostScript 中的背景、填充和装饰性文字效果。

## 为什么使用 Aspose.Page for Java？
- **Zero‑dependency rendering** – 无需外部 PostScript 解释器。  
- **Full control over graphics** – 结合矢量形状、文本和位图纹理。  
- **Cross‑platform** – 在任何支持 Java 的操作系统上均可运行。  

## 先决条件
在深入教程之前，请确保您已具备以下先决条件：
- 对 Java 编程语言的基本了解。  
- 熟悉 PostScript 文档结构。  
- 已安装 Aspose.Page for Java 库。您可以在[此处](https://releases.aspose.com/page/java/)下载。

## 导入包
首先为您的 Java 项目导入必要的包：

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 如何在 Java PostScript 中添加纹理平铺模式
以下是逐步指南。每一步都包括简短说明以及您需要复制的完整代码。

### 步骤 1：创建 PostScript 文档
首先创建一个新的 PostScript 文档，指定输出流和保存选项。确保已配置必要的路径。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 步骤 2：设置图形环境
将原点平移到方便的位置，并加载将用作纹理瓦片的位图。

```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```

### 步骤 3：创建纹理画刷
定义一个 `TexturePaint`，使位图在形状区域内重复。如果希望瓦片显示得更大或更小，可调整矩形尺寸。

```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```

### 步骤 4：绘制并填充形状
创建一个矩形，并使用画刷 **fill rectangle with texture**。然后描边该形状，使结果在视觉上更为突出。

```java
// Create rectangle
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// Set this texture brush as current paint
document.setPaint(paint);
// Fill rectangle
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```

### 步骤 5：使用纹理模式添加文本
您也可以将相同的纹理应用于文本字形。这演示了在字符上 **how to fill texture** 的方法，同时仍然可以描边它们。

```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

### 步骤 6：保存并关闭
最后，关闭页面，保存文档，并释放资源。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## 常见问题与技巧
- **Missing texture file** – 验证 `TestTexture.bmp` 的路径是否正确且文件可访问。  
- **Incorrect image dimensions** – 如果纹理出现拉伸，请调整 `imageArea` 以匹配原始图像尺寸。  
- **Performance** – 为多个形状复用同一 `TexturePaint` 实例，以避免不必要的对象创建。  
- **Pro tip:** 使用高分辨率位图作为瓦片，以在缩放时保持纹理清晰。  

## 常见问答

**Q: Aspose.Page for Java 适合初学者吗？**  
A: 当然！Aspose.Page for Java 提供了全面的文档，使所有技能水平的开发者都能轻松使用。

**Q: 我可以将 Aspose.Page for Java 集成到现有的 Java 项目中吗？**  
A: 可以，您只需按照提供的文档[此处](https://reference.aspose.com/page/java/)即可轻松集成 Aspose.Page for Java。

**Q: 我在哪里可以找到支持或讨论 Aspose.Page 相关问题？**  
A: 访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 与社区交流并寻求帮助。

**Q: 是否提供 Aspose.Page for Java 的免费试用？**  
A: 是的，您可以在[此处](https://releases.aspose.com/)尝试免费试用。

**Q: 我如何获取 Aspose.Page for Java 的临时许可证？**  
A: 访问[此链接](https://purchase.aspose.com/temporary-license/)获取临时许可证。

## 结论
恭喜！您已成功学习使用 Aspose.Page for Java 在 Java PostScript 文档中添加 **how to add texture** 平铺模式。欢迎尝试不同的位图瓦片、缩放因子和复合操作，以释放纹理填充的全部创意潜力。

---

**最后更新：** 2026-05-05  
**测试环境：** Aspose.Page for Java 24.12 (latest)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}