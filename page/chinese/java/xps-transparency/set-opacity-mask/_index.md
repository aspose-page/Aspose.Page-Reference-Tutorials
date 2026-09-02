---
date: 2026-04-30
description: 学习如何使用 Aspose.Page Java 创建 XPS 文档并添加不透明度遮罩。提供代码示例的逐步指南。
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: 在 Java XPS 中设置不透明度蒙版
second_title: Aspose.Page Java API
title: 使用 Aspose.Page 在 Java 中创建 XPS 文档 – 设置不透明度遮罩
url: /zh/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java XPS 中使用 Aspose.Page Java 设置不透明度遮罩

## 介绍
在本教程中，您将 **create XPS document Java** 文件，并学习如何应用不透明度遮罩，使您的图形呈现出精致的半透明效果。我们将完整演示整个过程——从初始化 XPS 文档、添加画布、绘制矩形，到附加基于图像的不透明度遮罩——使用直观的 Aspose.Page Java API。完成后，您即可以编程方式生成专业的 XPS 文件，并在任何需要的形状上复用该遮罩。

## 快速答案
- **不透明度遮罩的作用是什么？** 它为形状定义不同的透明度级别，使底层内容得以透显。  
- **需要哪个库？** Aspose.Page for Java (aspose page java)。  
- **是否需要许可证？** 临时许可证可用于测试；生产环境需要正式许可证。  
- **代码行数大概多少？** 大约 20 行 Java 代码，加上一些初始化语句。  
- **可以在多个形状上复用遮罩吗？** 可以，您可以将相同的 `ImageBrush` 分配给多个路径。

## XPS 中的不透明度遮罩是什么？
不透明度遮罩是一种位图或矢量，用于控制形状中每个像素的 alpha（透明度）。将其应用于矩形时，矩形的部分区域会变为完全不透明、部分透明或完全透明，从而在不增加额外绘图层的情况下实现复杂的视觉效果。

## 为什么使用 Aspose.Page Java **create XPS document java**？
- **纯 Java API** – 无本地依赖，代码可在 Windows、Linux 或 macOS 上运行。  
- **完整的 XPS 规范兼容** – 遮罩的渲染完全符合 XPS 标准。  
- **面向对象的设计** – 类似 .NET，若您在其他语言中使用过 Aspose，学习成本低。  
- **高性能** – 针对 **large documents** 和批量处理进行优化。

## 常见使用场景
- **水印** – 在页面上应用半透明的徽标。  
- **动态主题** – 在生成的报表中更改 UI 元素的视觉样式。  
- **打印预览** – 在发送到打印机前，展示不同透明度下的设计效果。

## 前置条件
在开始之前，请确保您具备以下条件：
- 对 Java 编程有基本了解。  
- 已安装 Aspose.Page for Java 库。您可以 **[here](https://releases.aspose.com/page/java/)** 下载。  
- 拥有有效的 Aspose.Page 许可证。若没有，可在 **[here](https://purchase.aspose.com/temporary-license/)** 获取临时许可证。  
- 能够编译并运行 Java 应用的开发环境（如 IntelliJ IDEA、Eclipse 或 VS Code）。

## 导入包
首先导入 Aspose.Page 库中所需的类，以确保 API 可在项目中使用。

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## 步骤指南

### 步骤 1：创建新的 XPS 文档
实例化一个全新的 XPS 文档，用于容纳所有图形。

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### 步骤 2：添加画布
画布充当 XPS 页面内的绘图表面。

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### 步骤 3：添加矩形并应用纯色填充
在此我们创建一个矩形路径，并为其设置纯红色填充。该矩形随后将接收不透明度遮罩。

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### 步骤 4：使用 ImageBrush 添加不透明度遮罩
加载 TIFF 图像，定义源矩形和目标矩形，并将画刷设置为平铺模式，以便在需要时重复遮罩。

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### 步骤 5：保存生成的 XPS 文档
最后，将文档持久化到磁盘。输出文件将包含已应用不透明度遮罩的矩形。

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

请严格按照这些步骤，将 **add opacity mask** 功能集成到您的 Java XPS 文档中，使用 Aspose.Page 实现。

## 常见问题与故障排除
- **未找到图像** – 请确认 `dataDir` 指向正确的文件夹，并且 `R08SY_NN.tif` 存在。  
- **遮罩显示为实色** – 请确保源图像确实包含不同的 alpha 值；全不透明的图像不会显示透明效果。  
- **平铺模式未生效** – 目标矩形必须小于源矩形，才能明显看到平铺效果。

## 常见问答

**问：Aspose.Page 是否兼容所有 Java 开发环境？**  
答：是的，Aspose.Page 设计为可无缝工作于各种 Java IDE 和构建工具。

**问：可以在没有许可证的情况下使用 Aspose.Page 吗？**  
答：您可以使用临时许可证进行评估，但生产环境必须使用正式许可证。

**问：试用版有什么限制？**  
答：试用版可能对文件大小或功能有所限制；详情请参阅官方文档。

**问：如何获取 Aspose.Page 的支持？**  
答：访问 **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** 获取社区帮助，或购买许可证以获得高级支持。

**问：Aspose.Page 是否提供退款保证？**  
答：请参阅 **[purchase page](https://purchase.aspose.com/buy)** 了解退款政策。

---

**最后更新：** 2026-04-30  
**测试环境：** Aspose.Page Java 24.11（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}