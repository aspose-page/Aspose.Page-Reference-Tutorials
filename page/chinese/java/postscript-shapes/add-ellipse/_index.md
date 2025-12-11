---
date: 2025-12-11
description: 学习如何使用 Aspose.Page 在 Java 中创建 PostScript 椭圆。此分步指南向您展示如何使用 Java 为椭圆填充颜色并绘制椭圆。
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: 如何在 Java 中使用 Aspose.Page 创建 PostScript 椭圆
url: /zh/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Page 创建 PostScript 椭圆

## 介绍
以编程方式创建 **PostScript ellipse** 能让您对报告、发票或任何可打印文档中的矢量图形进行细粒度控制。在本教程中，您将学习如何使用 Aspose.Page for Java 库 **创建 PostScript ellipse** 形状、为椭圆填充颜色以及绘制椭圆轮廓。完成后，您即可将自定义图形直接嵌入到 PostScript 输出中。

## 快速回答
- **在 Java 中绘制 PostScript 图形的最佳库是什么？** Aspose.Page for Java.  
- **我可以用纯色填充椭圆吗？** 可以——在 `fill` 之前使用 `document.setPaint(Color.YOUR_COLOR)`。  
- **如何仅绘制椭圆的轮廓？** 设置 paint 和 stroke，然后调用 `document.draw(...)`。  
- **生产环境是否需要许可证？** 需要商业许可证；可获取临时许可证用于测试。  
- **支持哪些 Java 版本？** 任何 Java 8 以上的运行时均可与当前的 Aspose.Page 版本配合使用。

## 什么是 PostScript 椭圆？
PostScript 椭圆是一种由边界矩形定义的矢量形状。不同于光栅图像，它可以在不失真的情况下缩放，非常适合高分辨率打印和 PDF 转换。

## 为什么使用 Aspose.Page 创建 PostScript 椭圆？
- **完整控制** 绘图基元（线条、曲线、椭圆）。  
- **跨平台** – 可在 Windows、Linux 和 macOS 上运行。  
- **无外部依赖** – 纯 Java API，无本机代码。  
- **易于集成** 与现有的 Java 应用程序和构建工具。

## 前置条件
在开始之前，请确保您具备以下条件：

1. 功能完整的 Java 开发环境（JDK 8 或更高）。  
2. 已在项目中添加 Aspose.Page for Java 库。您可以在 **[此处](https://releases.aspose.com/page/java/)** 下载。

## 导入包
在 Java 源文件中，导入绘制和保存 PostScript 内容所需的类。

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 步骤指南

### 步骤 1：设置 PostScript 文档
创建输出流，配置页面大小，并实例化 `PsDocument`。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 步骤 2：用颜色填充椭圆
将 paint 设置为所需的填充颜色，并使用 `Ellipse2D` 实例调用 `fill`。

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### 步骤 3：使用描边绘制椭圆轮廓
将 paint 切换为描边颜色，定义用于线宽的 `BasicStroke`，并绘制椭圆轮廓。

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### 步骤 4：关闭并保存文档
完成页面并将 PostScript 文件写入磁盘。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

现在您已经拥有一个包含两个椭圆的 PostScript 文件——一个填充橙色，另一个以红色描边。欢迎尝试不同的坐标、尺寸和颜色，以满足您的设计需求。

## 常见问题及故障排除
- **文件路径不正确** – 确保 `dataDir` 以适合您操作系统的分隔符（`/` 或 `\\`）结尾。  
- **缺少许可证** – 没有有效许可证时，库会以评估模式运行，可能会添加水印。  
- **颜色未生效** – 请记得在每次 `fill` 或 `draw` 调用 *之前* 设置 `document.setPaint(...)`；paint 设置不会在不同操作之间自动保持。

## 常见问答

**问：我可以将 Aspose.Page for Java 与其他 Java 库一起使用吗？**  
**答：可以，Aspose.Page for Java 旨在与其他 Java 库无缝集成。**

**问：如何获取 Aspose.Page for Java 的临时许可证？**  
**答：可在 **[此处](https://purchase.aspose.com/temporary-license/)** 获取用于测试的临时许可证。**

**问：Aspose.Page 适用于商业项目吗？**  
**答：当然！请访问 **[此处](https://purchase.aspose.com/buy)** 了解商业使用的授权选项。**

**问：我可以在哪里寻求帮助或讨论 Aspose.Page 相关问题？**  
**答：加入 **[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)** 社区进行讨论和获取帮助。**

**问：有没有免费资源可以进一步了解 Aspose.Page for Java？**  
**答：可使用 **[免费试用](https://releases.aspose.com/)** 并在文档中查看示例。  

## 结论
Aspose.Page for Java 使得 **创建 PostScript ellipse** 图形变得简单，无论您需要简单的填充形状还是复杂的描边轮廓。通过上述步骤，您可以快速向任何可打印文档添加专业级矢量图形。欲进一步探索——如组合多个形状、应用渐变或转换为 PDF——请参阅官方 **[文档](https://reference.aspose.com/page/java/)**。

---

**最后更新：** 2025-12-11  
**测试环境：** Aspose.Page for Java 24.11  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
