---
title: 使用 Aspose.Page 在 Java 中调整 EPS 文件大小
linktitle: 在Java中调整EPS文件的大小
second_title: Aspose.Page Java API
description: 了解如何使用 Aspose.Page for Java 轻松调整 Java 中的 EPS 文件大小。请按照我们的综合指南获取分步说明。
type: docs
weight: 11
url: /zh/java/manipulation-eps/resize/
---
## 介绍
欢迎来到我们关于使用强大的 Aspose.Page 库在 Java 中调整 EPS 文件大小的分步指南。如果您曾经需要以编程方式调整 EPS 图像的尺寸，那么您来对地方了。在本教程中，我们将探索各种调整大小选项，包括点、英寸、毫米和百分比，为您提供满足特定要求所需的灵活性。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下条件：
- 您的计算机上安装了 Java 开发工具包 (JDK)。
-  Java 库的 Aspose.Page。你可以下载它[这里](https://releases.aspose.com/page/java/).
- 对 Java 编程有基本的了解。
## 导入包
在您的 Java 项目中，确保您具有使用 Aspose.Page 功能所需的导入。这是一个例子：
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
现在，让我们将教程分解为每个调整大小选项的多个步骤：
## 使用点调整 EPS 大小
### 第 1 步：设置输入流
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### 步骤2：初始化PsDocument对象
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### 步骤3：提取EPS图像的当前尺寸
```java
Dimension oldSize = doc.extractEpsSize();
```
### 第 4 步：创建输出流
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### 第 5 步：调整大小并以磅为单位保存
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## 使用英寸调整 EPS 大小
按照与示例 1 类似的步骤，将“点”替换为“英寸”并相应地调整新尺寸。
## 使用毫米调整 EPS 大小
按照与示例 1 类似的步骤，将“点”替换为“毫米”并相应地调整新尺寸。
## 使用百分比调整 EPS 大小
按照与示例 1 类似的步骤，将“点”替换为“百分比”并相应地调整新大小。
## 结论
恭喜！您已经成功学习了如何使用 Aspose.Page 在 Java 中调整 EPS 文件的大小。本指南为您提供了多种选项，确保您可以定制调整大小过程以满足您的特定需求。

## 常见问题解答
### 我可以将此库用于其他图像格式吗？
不，Aspose.Page 是专门为处理 PostScript 和 EPS 文件而设计的。
### Aspose.Page for Java 是否有免费试用版？
是的，您可以探索免费试用版[这里](https://releases.aspose.com/).
### 我在哪里可以找到更多帮助和讨论？
参观[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)以获得社区支持。
### 我怎样才能获得临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 有可用的示例项目吗？
是的，检查文档[这里](https://reference.aspose.com/page/java/).