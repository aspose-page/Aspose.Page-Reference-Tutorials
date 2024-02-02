---
title: 在 Java XPS 中设置不透明蒙版
linktitle: 在 Java XPS 中设置不透明蒙版
second_title: Aspose.Page Java API
description: 探索使用 Aspose.Page 在 Java XPS 中设置不透明蒙版的强大功能。请按照我们的分步指南获得视觉增强的文档体验。
type: docs
weight: 11
url: /zh/java/xps-transparency/set-opacity-mask/
---
## 介绍
欢迎阅读我们有关使用 Aspose.Page 在 Java XPS 中设置不透明蒙版的综合指南。在本教程中，我们将引导您完成使用 Aspose.Page for Java 的强大功能创建 XPS 文档、添加画布以及将不透明蒙版应用于矩形的过程。
## 先决条件
在深入学习本教程之前，请确保您具备以下条件：
- 对 Java 编程有基本的了解。
- 安装了 Java 库的 Aspose.Page。你可以下载它[这里](https://releases.aspose.com/page/java/).
-  Aspose.Page 的有效许可证。如果没有，您可以获取临时许可证[这里](https://purchase.aspose.com/temporary-license/).
- 设置用于运行 Java 应用程序的开发环境。
## 导入包
首先将必要的包导入到您的 Java 项目中。确保您已正确集成 Aspose.Page 库。以下是指导您的片段：
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
现在，让我们将示例代码分解为多个步骤：
## 第 1 步：创建新的 XPS 文档
```java
//创建新的 XPS 文档
XpsDocument doc = new XpsDocument();
```
## 第 2 步：添加画布
```java
//新画布
XpsCanvas canvas = doc.addCanvas();
```
## 第 3 步：添加带有不透明蒙版的矩形
```java
//中间左侧的矩形，不透明度被 ImageBrush 遮盖
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## 第 4 步：使用 ImageBrush 设置不透明蒙版
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## 第 5 步：保存生成的 XPS 文档
```java
//保存生成的 XPS 文档
doc.save(dataDir + "OpacityMask_out.xps"); 
```
仔细按照以下步骤使用 Aspose.Page 将不透明蒙版合并到 Java XPS 文档中。
## 结论
恭喜！您已经成功学习了如何使用 Aspose.Page 在 Java XPS 中设置不透明蒙版。此功能为您的文档增添了一层视觉丰富性，使它们更具吸引力和活力。
## 常见问题解答
### Aspose.Page 是否与所有 Java 开发环境兼容？
是的，Aspose.Page 旨在与各种 Java 开发环境无缝协作。
### 我可以在没有许可证的情况下使用 Aspose.Page 吗？
虽然您可以在没有许可证的情况下使用 Aspose.Page，但建议您获取许可证以获得全部功能和支持。
### 试用版有任何限制吗？
试用版可能有一些功能限制。建议查看文档以了解详细信息。
### 我如何获得 Aspose.Page 的支持？
您可以访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)以获得社区支持或购买许可证以获得高级帮助。
### Aspose.Page 有退款保证吗？
请参阅[购买页面](https://purchase.aspose.com/buy)有关退款政策的信息。