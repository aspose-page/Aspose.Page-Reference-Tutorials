---
date: 2025-12-28
description: 学习如何在 Java 中使用 Aspose.Page 向 XPS 文档添加图像。本分步指南将向您展示如何轻松添加图像并提升文档处理能力。
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: 如何向 Java XPS 文档添加图像 – 使用 Aspose.Page 的简易指南
url: /zh/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page 为 Java 向 XPS 文档添加图片

向 XPS 文件添加图片是 Java 开发者在丰富报告、发票或任何可视化文档时的常见需求。在本教程中，你将学习 **如何向 XPS 文档添加图片**，使用功能强大的 Aspose.Page for Java 库。我们将逐步演示每一步，解释每行代码的意义，并提供避免常见陷阱的技巧。

## 快速答案
- **需要哪个库？** Aspose.Page for Java  
- **可以添加多张图片吗？** 可以——对每张图片重复添加步骤  
- **支持的图片格式？** TIFF、JPEG、PNG、GIF（以及 .NET 支持的其他格式）  
- **需要许可证吗？** 免费试用可用于评估；生产环境需要商业许可证  
- **典型实现时间？** 基本图片插入约需 10‑15 分钟

## 介绍
在许多 Java 应用中，向 XPS 文档添加图片是常见需求，涵盖报表生成到文档处理等场景。Aspose.Page for Java 简化了此任务，提供高效的方法将图片无缝集成到 XPS 文件中。本教程将演示如何使用 Aspose.Page for Java 向 XPS 文档添加图片。

## 前置条件
在开始教程之前，请确保已具备以下前置条件：
1. **Aspose.Page for Java 库** – 从[官方网站](https://releases.aspose.com/page/java/)下载并安装 Aspose.Page for Java。  
2. **Java 开发环境** – 确保你的机器上已配置好 Java 开发环境。

现在，进入下一步。

## 导入包
在你的 Java 项目中，导入必要的 Aspose.Page for Java 包，以访问所需的类和方法。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## 步骤 1：设置文档目录
定义存放 XPS 文档和图片文件的目录路径。

```java
String dataDir = "Your Document Directory";
```

## 步骤 2：创建新 XPS 文档
使用以下代码片段初始化一个新的 XPS 文档：

```java
XpsDocument doc = new XpsDocument();
```

## 步骤 3：向 XPS 文档添加图片
要添加图片，需要在 XPS 文档中创建路径，并使用提供的图片文件和坐标设置图像画刷。

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## 步骤 4：保存生成的 XPS 文档
将修改后的 XPS 文档保存到你指定的目录。

```java
doc.save(dataDir + "AddImage_out.xps");
```

重复这些步骤即可添加更多图片，或根据项目需求自定义已有图片。

## 结论
恭喜！你已成功学习 **如何向 XPS 文档添加图片**，使用 Aspose.Page for Java。这项技能对于提升 Java 应用和文档的视觉效果非常有价值。

### 常见问题
### 我可以在同一个 XPS 文档中使用 Aspose.Page for Java 添加多张图片吗？
可以，你可以对每张图片重复本教程中概述的步骤来添加多张图片。

### Aspose.Page for Java 支持哪些图片格式？
Aspose.Page for Java 支持多种图片格式，包括 TIFF、JPEG、PNG 和 GIF。

### 是否有 Aspose.Page for Java 的试用版可供下载？
有，你可以通过[此链接](https://releases.aspose.com/)获取 Aspose.Page for Java 的免费试用版。

### 如何获取 Aspose.Page for Java 的临时许可证？
你可以通过[此链接](https://purchase.aspose.com/temporary-license/)获取临时许可证。

### 在哪里可以找到更多支持或讨论 Aspose.Page for Java 的相关问题？
访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)获取帮助、分享经验并与 Aspose.Page 社区交流。

## 其他提示与常见陷阱
- **路径几何精度** – 确保 SVG 样式的路径字符串与图片尺寸匹配，否则图片可能会被拉伸或裁剪。  
- **图像画刷缩放** – `createImageBrush` 方法接受源矩形和目标矩形；调整这些值可精确控制位置和缩放。  
- **许可证激活** – 如果在没有有效许可证的情况下运行代码，Aspose 会在生成的 XPS 文件上添加水印。

---

**最后更新：** 2025-12-28  
**测试环境：** Aspose.Page for Java 23.12（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}