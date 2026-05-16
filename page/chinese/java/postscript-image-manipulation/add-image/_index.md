---
date: 2026-02-15
description: 学习如何使用 Aspose.Page for Java 创建 PostScript Java 文档并生成带有图像平移和旋转的 PostScript
  文档文件。
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: 创建 PostScript Java – 在 Java PostScript 中添加图像
url: /zh/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 PostScript Java – 在 Java PostScript 中添加图像

## 介绍
在本教程中，您将学习如何使用 Aspose.Page for Java 库 **create postscript java** 文档并嵌入图像。我们将逐步演示，从初始化新的 PostScript 文件到应用 **translate and rotate image** 转换。完成后，您将能够以编程方式生成 PostScript 文件，并以像素级精度控制图像放置——这非常适合自动化报告、打印工作流或任何需要从 Java **generate postscript document** 输出的场景。

## 快速答案
- **需要什么库？** Aspose.Page for Java  
- **我可以添加多张图像吗？** 是的 – 重复变换和绘制步骤  
- **开发需要许可证吗？** 免费试用可用于测试；生产环境需要许可证  
- **支持哪个 Java 版本？** Java 8 及更高版本  
- **支持图像旋转吗？** 当然 – 使用 `AffineTransform.rotate()`  

## 什么是 create postscript java？
**create postscript java** 操作会生成一个 PostScript 页面描述文件，其中包含文本、矢量图形和光栅图像。使用 Aspose.Page，您可以直接从 Java 代码构建这些文件，从而在布局、缩放和旋转方面拥有完整的编程控制，而无需单独的 PostScript 解释器。

## 为什么使用 Aspose.Page 进行图像处理？
- **High‑level API:** 抽象低层 PostScript 命令为简易的 Java 方法。  
- **Cross‑platform:** 可在任何支持 Java 的操作系统上运行。  
- **Full graphics‑state control:** 可随意保存、恢复、平移、缩放和旋转图形状态。  
- **No external dependencies:** 在内部处理图像加载、格式转换和嵌入，无需外部依赖。  

## 前提条件
在深入代码之前，请确保您已具备：

- 已在系统上安装 Java Development Kit (JDK)。  
- Aspose.Page for Java 库。您可以在 [here](https://releases.aspose.com/page/java/) 下载。  
- 对 Java 编程有基本了解。  

## 导入包
要开始，请在 Java 项目中导入必要的包。使用以下代码片段作为参考：

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步骤 1：写入图形保存
第一步是在文档中写入图形保存。这可确保随后进行的任何转换或修改在需要时能够回滚。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## 步骤 2：平移和变换（translate and rotate image）
接下来，平移文档并从图像文件创建 `BufferedImage` 对象。使用 `AffineTransform` 应用一系列转换，如缩放和旋转。这就是执行 **translate and rotate image** 操作的地方。

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## 步骤 3：将图像添加到文档
现在，将已变换的图像添加到文档中。

```java
document.drawImage(image, transform, null);
```

## 步骤 4：写入图形恢复
添加图像后，写入图形恢复以完成所做的更改。

```java
document.writeGraphicsRestore();
```

## 步骤 5：关闭当前页面并保存
关闭当前页面并保存文档。

```java
document.closePage();
document.save();
```

您可以重复这些步骤以添加多张图像，或根据需求自定义转换。

## 常见问题及解决方案
- **FileNotFoundException:** 确保 `dataDir` 路径以文件分隔符（`/` 或 `\\`）结尾，并且图像文件名完全匹配。  
- **ImageIO.read returns null:** 验证图像格式是否受支持（例如 JPEG、PNG）。  
- **Incorrect rotation angle:** `AffineTransform.rotate` 需要弧度。必要时将角度转换为弧度（`Math.toRadians(degrees)`）。  

## 常见问答

**Q: 我可以将 Aspose.Page for Java 与其他编程语言一起使用吗？**  
A: Aspose.Page 主要支持 Java，但也提供其他编程语言的版本。

**Q: Aspose.Page for Java 有免费试用吗？**  
A: 有，您可以在 [here](https://releases.aspose.com/) 获取免费试用。

**Q: 我如何获取 Aspose.Page for Java 的临时许可证？**  
A: 您可以在 [here](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**Q: 我在哪里可以找到 Aspose.Page for Java 的社区支持和讨论？**  
A: 请访问 [Aspose.Page Forum](https://forum.aspose.com/c/page/39) 获取社区支持。

**Q: 有哪些购买 Aspose.Page for Java 的额外资源？**  
A: 您可以在 [here](https://purchase.aspose.com/buy) 购买该库。

## 结论
恭喜！您已成功学习如何使用 Aspose.Page for Java **create postscript java** 文档并嵌入图像。请浏览 [documentation](https://reference.aspose.com/page/java/) 以了解更多高级功能，如矢量图形、文本渲染和自定义页面尺寸。

---

**最后更新:** 2026-02-15  
**测试使用:** Aspose.Page for Java 23.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}