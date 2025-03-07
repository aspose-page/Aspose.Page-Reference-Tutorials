---
title: 在 Java PostScript 中添加椭圆
linktitle: 在 Java PostScript 中添加椭圆
second_title: Aspose.Page Java API
description: 掌握使用 Aspose.Page 在 Java 中创建令人惊叹的 PostScript 文档。学习逐步添加省略号以获得视觉上吸引人的内容。
weight: 10
url: /zh/java/postscript-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java PostScript 中添加椭圆

## 介绍
在 Java 开发的动态世界中，创建具有视觉吸引力的文档是一项常见要求。 Aspose.Page for Java 是一个功能强大的库，使开发人员能够轻松操作 PostScript 文件。在本教程中，我们将探讨如何使用 Aspose.Page for Java 将省略号添加到 PostScript 文档中。跟随我们的脚步，提高您的文档创建技能！
## 先决条件
在深入学习本教程之前，请确保您已设置以下先决条件：
1. Java 开发环境：确保您的计算机上安装了功能齐全的 Java 开发环境。
2.  Aspose.Page for Java Library：下载 Aspose.Page 库并将其包含在您的 Java 项目中。你可以找到图书馆[这里](https://releases.aspose.com/page/java/).
## 导入包
在您的 Java 代码中，导入必要的包以利用 Aspose.Page 功能。这是一个例子：
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## 第 1 步：设置您的文档
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//为 PostScript 文档创建输出流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
//创建 A4 尺寸的保存选项
PsSaveOptions options = new PsSaveOptions();
//打开页面创建新的 PS 文档
PsDocument document = new PsDocument(outPsStream, options, false);
```
## 第2步：用颜色填充椭圆
```java
//设置填充椭圆的油漆
document.setPaint(Color.ORANGE);
//填充第一个椭圆
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```
## 第3步：用描边勾勒出椭圆形的轮廓
```java
//设置描画椭圆的油漆
document.setPaint(Color.RED);
//设定行程
document.setStroke(new BasicStroke(3));
//描边（轮廓）第二个椭圆
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```
## 第 4 步：关闭并保存文档
```java
//关闭当前页面
document.closePage();
//保存文档
document.save();
```
现在您已经使用 Aspose.Page for Java 成功地将省略号添加到您的 PostScript 文档中！尝试不同的坐标和尺寸来定制您的视觉效果。
## 结论
 Aspose.Page for Java 简化了创建和操作 PostScript 文档的过程。本教程为您提供了添加省略号的知识，为更复杂的可视化奠定了坚实的基础。潜入[文档](https://reference.aspose.com/page/java/)了解更多详细信息和功能。
## 常见问题解答
### 问：我可以将 Aspose.Page for Java 与其他 Java 库一起使用吗？
答：是的，Aspose.Page for Java 旨在与其他 Java 库无缝集成。
### 问：如何获得 Aspose.Page for Java 的临时许可证？
答：获得临时许可证[这里](https://purchase.aspose.com/temporary-license/)用于测试目的。
### 问：Aspose.Page 适合商业项目吗？
答：当然！访问[这里](https://purchase.aspose.com/buy)探索商业用途的许可选项。
### 问：我可以在哪里寻求帮助或讨论与 Aspose.Page 相关的查询？
答：加入社区：[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)进行讨论和寻求帮助。
### 问：是否有任何免费资源可以了解有关 Aspose.Page for Java 的更多信息？
答：利用[免费试用](https://releases.aspose.com/)并探索文档中的示例。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
