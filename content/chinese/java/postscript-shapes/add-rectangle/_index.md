---
title: 自定义 Java PostScript - 使用 Aspose.Page 添加矩形
linktitle: 在 Java PostScript 中添加矩形
second_title: Aspose.Page Java API
description: 探索使用 Aspose.Page for Java 将鲜艳的矩形添加到 Java PostScript 文档的分步指南。轻松增强您的文档定制！
type: docs
weight: 11
url: /zh/java/postscript-shapes/add-rectangle/
---
## 介绍
您是否希望使用充满活力的矩形来增强您的 Java PostScript 文档？别再犹豫了！在本分步指南中，我们将探讨如何使用 Aspose.Page for Java 将矩形添加到 PostScript 文档中。 Aspose.Page 是一个功能强大的库，提供了处理 PostScript 文件的强大功能，使其成为寻求操作和自定义文档的开发人员的理想选择。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
- 对 Java 编程有基本的了解。
- 安装了 Java 库的 Aspose.Page。如果没有，请从以下位置下载[Aspose.Page 用于 Java 文档](https://reference.aspose.com/page/java/).
- 在您的计算机上设置 Java 开发环境。
## 导入包
在您的 Java 项目中，首先导入必要的包：
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## 教程：在 Java PostScript 中添加矩形
## 第1步：设置填充矩形的油漆
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//为 PostScript 文档创建输出流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
//创建 A4 尺寸的保存选项
PsSaveOptions options = new PsSaveOptions();
//打开页面创建新的 PS 文档
PsDocument document = new PsDocument(outPsStream, options, false);
//设置填充矩形的油漆
document.setPaint(Color.ORANGE);        
//填充第一个矩形
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## 第 2 步：设置描边矩形的绘制
```java
//设置描边矩形的油漆
document.setPaint(Color.RED);
//设定行程
document.setStroke(new BasicStroke(3));
//描边（轮廓）第二个矩形
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## 步骤 3：关闭当前页面并保存文档
```java
//关闭当前页面
document.closePage();
//保存文档
document.save();
```
恭喜！您已经使用 Aspose.Page 成功地将充满活力的矩形添加到 Java PostScript 文档中。
## 结论
在本教程中，我们探索了使用 Aspose.Page for Java 通过矩形增强 Java PostScript 文档的过程。这个强大的库为寻求轻松定制和操作文档的开发人员打开了一个充满可能性的世界。
尝试不同的形状和颜色，让您的文档在视觉上更具吸引力！
## 经常问的问题

### 我可以将 Aspose.Page for Java 与其他编程语言一起使用吗？
Aspose.Page 主要支持 Java，但类似的库也可用于其他语言。
### 是否有 Aspose.Page for Java 的试用版？
是的，您可以通过以下方式探索 Aspose.Page for Java 的功能：[免费试用版](https://releases.aspose.com/).
### 我在哪里可以找到更多帮助和讨论？
参观[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)与社区互动并获得帮助。
### 如何获得 Aspose.Page for Java 的临时许可证？
获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 在哪里可以购买 Aspose.Page for Java 的许可版本？
购买授权版本[这里](https://purchase.aspose.com/buy).