---
date: 2025-12-09
description: 学习如何使用 Aspose.Page 在 Java 中创建 PostScript 文档，并平移和旋转图像，实现无缝的图像操作。
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: 在 Java 中创建 PostScript 文档 – 在 Java PostScript 中添加图像
url: /zh/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 PostScript 文档（Java） – 在 Java PostScript 中添加图像

## 介绍
在本教程中，您将学习如何 **创建 PostScript 文档（Java）** 并使用 Aspose.Page for Java 库嵌入图像。我们将逐步演示从设置文档到应用 **平移和旋转图像** 操作的每一步。完成后，您将能够以编程方式生成丰富的 PostScript 文件，并根据实际布局需求自定义图像位置。

## 快速答疑
- **需要哪个库？** Aspose.Page for Java  
- **可以添加多张图像吗？** 可以 – 重复变换和绘制步骤即可  
- **开发阶段需要许可证吗？** 免费试用可用于测试；生产环境需要许可证  
- **支持哪个 Java 版本？** Java 8 及以上  
- **支持图像旋转吗？** 完全支持 – 使用 `AffineTransform.rotate()`  

## 什么是用 Java 创建 PostScript 文档？
PostScript 文档是一种页面描述语言文件，用于描述文本、图形和图像。使用 Aspose.Page，您可以在 Java 中以编程方式生成这些文件，全面掌控布局、图形状态和图像处理，而无需 PostScript 解释器。

## 为什么使用 Aspose.Page 进行图像处理？
- **高级 API：** 简化复杂的 PostScript 命令。  
- **跨平台：** 在任何支持 Java 的操作系统上均可运行。  
- **完整的图形状态控制：** 轻松保存、恢复、平移、缩放和旋转图形。  
- **无外部依赖：** 内部处理图像加载和转换。

## 前置条件
在开始编写代码之前，请确保您拥有：

- 已在系统上安装 **Java Development Kit (JDK)**。  
- Aspose.Page for Java 库。您可以在 [此处](https://releases.aspose.com/page/java/) 下载。  
- 对 Java 编程有基本了解。  

## 导入包
要开始使用，请在 Java 项目中导入必要的包。以下代码片段可作参考：

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
第一步是向文档写入图形保存指令。这可确保后续的任何变换或修改在需要时能够回滚。

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

## 步骤 2：平移和变换（平移并旋转图像）
接下来，对文档进行平移，并从图像文件创建 `BufferedImage` 对象。使用 `AffineTransform` 进行一系列变换，如缩放和旋转。这一步实现了 **平移并旋转图像** 的操作。

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
在添加图像后，写入图形恢复指令以完成对更改的最终确认。

```java
document.writeGraphicsRestore();
```

## 步骤 5：关闭当前页面并保存
关闭当前页面并保存文档。

```java
document.closePage();
document.save();
```

您可以重复上述步骤以添加多张图像，或根据需求自定义变换参数。

## 常见问题及解决方案
- **FileNotFoundException：** 确保 `dataDir` 路径以文件分隔符（`/` 或 `\\`）结尾，并且图像文件名完全匹配。  
- **ImageIO.read 返回 null：** 验证图像格式是否受支持（如 JPEG、PNG）。  
- **旋转角度不正确：** `AffineTransform.rotate` 需要弧度。必要时使用 `Math.toRadians(degrees)` 将度数转换为弧度。  

## 常见问答

**Q: 我可以在其他编程语言中使用 Aspose.Page for Java 吗？**  
A: Aspose.Page 主要支持 Java，但也提供其他语言的版本。

**Q: Aspose.Page for Java 有免费试用吗？**  
A: 有，您可以在 [此处](https://releases.aspose.com/) 获取免费试用。

**Q: 如何获取 Aspose.Page for Java 的临时许可证？**  
A: 您可以在 [此处](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

**Q: 哪里可以找到 Aspose.Page for Java 的社区支持和讨论？**  
A: 请访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 获取社区支持。

**Q: 有哪些渠道可以购买 Aspose.Page for Java？**  
A: 您可以在 [此处](https://purchase.aspose.com/buy) 购买该库。

## 结论
恭喜！您已成功学习如何 **创建 PostScript 文档（Java）** 并使用 Aspose.Page for Java 嵌入图像。请进一步查阅 [文档](https://reference.aspose.com/page/java/) 以了解更高级的功能，如矢量图形、文本渲染和自定义页面尺寸。

---

**最后更新：** 2025-12-09  
**测试环境：** Aspose.Page for Java 23.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}