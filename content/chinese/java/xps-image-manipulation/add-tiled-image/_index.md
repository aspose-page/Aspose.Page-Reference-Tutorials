---
title: 在 Java XPS 中添加平铺图像
linktitle: 在 Java XPS 中添加平铺图像
second_title: Aspose.Page Java API
description: 使用 Aspose.Page 探索无缝 Java XPS 文档操作。使用此分步指南学习轻松添加平铺图像。
type: docs
weight: 11
url: /zh/java/xps-image-manipulation/add-tiled-image/
---
## 介绍
在 Java 开发的动态世界中，对高效文档操作和创建的需求不断增长。 Aspose.Page for Java 成为一个强大的工具，为开发人员提供无缝处理 XPS 文档的能力。本教程重点关注一项特定任务 - 将平铺图像添加到 Java XPS 文档。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1. Java 开发工具包 (JDK)：确保您的系统上安装了 JDK。
2.  Aspose.Page for Java：从以下位置下载并安装 Aspose.Page for Java：[网站](https://releases.aspose.com/page/java/).
3. 您的文档目录：选择或创建要保存 XPS 文档的目录。
## 导入包
在您的 Java 项目中，导入必要的包以利用 Aspose.Page 功能：
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
现在，让我们将向 Java XPS 文档添加平铺图像的过程分解为清晰、可管理的步骤。
## 第 1 步：设置您的项目
首先设置您的 Java 项目，确保正确集成 Aspose.Page for Java。
## 第 2 步：创建 XPS 文档
使用以下代码初始化一个新的 XPS 文档：
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//创建新的 XPS 文档
XpsDocument doc = new XpsDocument();
```
## 第 3 步：定义平铺图像路径
指定要添加到 XPS 文档的平铺图像的路径。
## 第 4 步：添加平铺图像
使用下面的代码片段将平铺图像添加到 XPS 文档中：
```java
//平铺图像
//ImageBrush 填充矩形位于右上方下方
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## 第 5 步：保存文档
最后，使用以下代码保存生成的 XPS 文档：
```java
//保存生成的 XPS 文档
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
重复这些步骤，即可使用 Aspose.Page 轻松地将平铺图像合并到 Java XPS 文档中。
## 结论
Aspose.Page for Java 简化了 XPS 文档的处理过程，为开发人员提供了高效的文档操作解决方案。通过遵循此分步指南，您可以轻松地将平铺图像添加到 Java XPS 文档中。

## 常见问题解答
### Aspose.Page 与所有 Java 版本兼容吗？
 Aspose.Page 设计用于各种 Java 版本。通过检查文档确保兼容性[这里](https://reference.aspose.com/page/java/).
### 我可以将 Aspose.Page 用于商业项目吗？
是的，Aspose.Page 提供商业许可证。购买它们[这里](https://purchase.aspose.com/buy).
### 有免费试用吗？
是的，通过免费试用探索 Aspose.Page 功能[这里](https://releases.aspose.com/).
### 我在哪里可以找到社区支持和讨论？
与 Aspose.Page 社区互动[论坛](https://forum.aspose.com/c/page/39).
### 如何获得 Aspose.Page 的临时许可证？
获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).