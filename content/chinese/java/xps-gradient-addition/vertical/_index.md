---
title: 在 Java XPS 中添加垂直渐变
linktitle: 在 Java XPS 中添加垂直渐变
second_title: Aspose.Page Java API
description: 了解如何使用 Aspose.Page 将垂直渐变添加到 Java XPS 文档。毫不费力地增强视觉吸引力。里面有分步指南。
type: docs
weight: 12
url: /zh/java/xps-gradient-addition/vertical/
---
## 介绍
在本教程中，我们将探索如何使用 Aspose.Page for Java 在 Java XPS 中添加垂直渐变。向 XPS 文档添加渐变可以增强内容的视觉吸引力，使其更具吸引力且美观。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下先决条件：
- 一个有效的 Java 开发环境。
-  Java 库的 Aspose.Page。您可以从以下位置下载：[这里](https://releases.aspose.com/page/java/).
- 对 Java 编程有基本的了解。
## 导入包
首先导入 Java 项目所需的包。确保您已在项目依赖项中包含 Aspose.Page for Java 库。
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
//文档目录的路径。
String dataDir = "Your Document Directory";
        
//导入 Java 版 Aspose.Page
```
## 第1步：初始化文档
首先初始化 XPS 文档。这为向文档添加路径和渐变等元素奠定了基础。
```java
//初始化文档
XpsDocument doc = new XpsDocument();
```
## 第2步：创建具有垂直渐变的路径
现在，让我们创建一条具有垂直渐变的路径。这涉及定义路径几何形状并指定渐变停止点。
```java
//创建具有几何形状的路径
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
//定义垂直梯度停止点
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//将垂直渐变应用于路径
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## 第 3 步：保存文档
最后，将添加了垂直渐变的 XPS 文档保存到所需目录。
```java
//保存文档
doc.save(dataDir + "VerticalGradient.xps");
```
恭喜！您已成功使用 Aspose.Page 将垂直渐变添加到 Java XPS 文档中。
## 结论
使用渐变增强 XPS 文档可以显着提高其视觉吸引力。 Aspose.Page for Java 简化了这个过程，让您轻松创建令人惊叹的文档。

### 常见问题解答
### 我可以在商业项目中使用 Aspose.Page for Java 吗？
是的，Aspose.Page for Java 可用于商业用途。您可以购买[这里](https://purchase.aspose.com/buy).
### Aspose.Page for Java 是否有免费试用版？
是的，您可以免费试用[这里](https://releases.aspose.com/).
### 在哪里可以找到 Aspose.Page for Java 的文档？
文档可用[这里](https://reference.aspose.com/page/java/).
### 如何获得 Aspose.Page for Java 的临时许可证？
获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 需要帮助或有疑问吗？
访问 Aspose.Page 社区[论坛](https://forum.aspose.com/c/page/39).