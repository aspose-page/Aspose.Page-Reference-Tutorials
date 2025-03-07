---
title: 在 Java PostScript 中添加图像
linktitle: 在 Java PostScript 中添加图像
second_title: Aspose.Page Java API
description: 在本教程中探索 Aspose.Page Java 的无缝集成，向 PostScript 文档添加图像。提升您的文档处理能力。
weight: 10
url: /zh/java/postscript-image-manipulation/add-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java PostScript 中添加图像

## 介绍
在本教程中，我们将探讨如何使用 Aspose.Page for Java 库将图像添加到 Java PostScript 文档中。 Aspose.Page 是一个功能强大的库，提供了处理 PostScript 文件的各种功能，使开发人员能够无缝地操作和增强他们的文档。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下先决条件：
- 您的系统上安装了 Java 开发工具包 (JDK)。
-  Java 库的 Aspose.Page。你可以下载它[这里](https://releases.aspose.com/page/java/).
- 对 Java 编程有基本的了解。
## 导入包
首先，在您的 Java 项目中导入必要的包。使用以下代码片段作为参考：
```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## 第1步：编写图形保存
第一步是将图形保存到文档中。这确保了以后进行的任何转换或修改都可以在需要时回滚。
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//为 PostScript 文档创建输出流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
//创建 A4 尺寸的保存选项
PsSaveOptions options = new PsSaveOptions();
//打开页面创建新的 PS 文档
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```
## 第 2 步：翻译和变换
接下来，翻译文档并从图像文件创建 BufferedImage 对象。使用 AffineTransform 应用一系列变换，例如缩放和旋转。
```java
document.translate(100, 100);
//从图像文件创建 BufferedImage 对象
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
//创建图像变换
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```
## 第 3 步：将图像添加到文档中
现在，将转换后的图像添加到文档中。
```java
document.drawImage(image, transform, null);
```
## 第四步：编写图形恢复
添加图像后，编写图形恢复以完成所做的更改。
```java
document.writeGraphicsRestore();
```
## 第5步：关闭当前页面并保存
关闭当前页面并保存文档。
```java
document.closePage();
document.save();
```
重复这些步骤以添加多个图像或根据您的要求自定义转换。
## 结论
恭喜！您已经成功学习了如何使用 Aspose.Page for Java 将图像添加到 Java PostScript 文档。探索[文档](https://reference.aspose.com/page/java/)以获得更高级的特性和功能。
## 常见问题解答
### 我可以将 Aspose.Page for Java 与其他编程语言一起使用吗？
Aspose.Page 主要支持 Java，但也有适用于其他编程语言的版本。
### Aspose.Page for Java 是否有免费试用版？
是的，您可以免费试用[这里](https://releases.aspose.com/).
### 如何获得 Aspose.Page for Java 的临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 在哪里可以找到与 Aspose.Page for Java 相关的社区支持和讨论？
参观[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)以获得社区支持。
### 是否有任何其他资源可用于购买 Aspose.Page for Java？
你可以购买图书馆[这里](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
