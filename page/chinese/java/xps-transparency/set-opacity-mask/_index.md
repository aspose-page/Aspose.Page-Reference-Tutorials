---
date: 2026-01-02
description: 学习如何使用 Aspose.Page Java 为 XPS 文档添加不透明度遮罩。一步步指南，创建不透明度遮罩矩形并提升视觉质量。
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: 使用 Aspose.Page Java 在 Java XPS 中设置不透明度掩码
url: /zh/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java XPS 中使用 Aspose.Page Java 设置不透明度蒙版

## 介绍
欢迎阅读我们关于 **aspose page java** 不透明度蒙版的完整指南。在本教程中，您将学习如何创建 XPS 文档、添加画布，并将不透明度蒙版应用于矩形——全部使用强大的 Aspose.Page Java API。完成后，您将能够添加不透明度蒙版矩形，为您的 XPS 文件提供精致的半透明外观。

## 快速答案
- **不透明度蒙版的作用是什么？** 它为形状定义不同的透明度级别，使底层内容得以显现。
- **需要哪个库？** Aspose.Page for Java (aspose page java)。
- **我需要许可证吗？** 临时许可证可用于测试；生产环境需要正式许可证。
- **代码行数大约多少？** 大约 20 行 Java 代码，加上一些初始化语句。
- **我可以在多个形状上复用同一蒙版吗？** 可以，您可以将相同的 ImageBrush 分配给多个路径。

## 什么是 XPS 中的不透明度蒙版？
不透明度蒙版是一种位图或矢量，用于控制形状中每个像素的 alpha（透明度）。将其应用于矩形时，矩形的部分区域会变为完全不透明、部分透明或完全透明，从而产生精细的视觉效果。

## 为什么使用 Aspose.Page Java 来处理不透明度蒙版？
- **在 Java 中提供完整的 .NET 风格 API** – 直观的对象模型。
- **无外部依赖** – 可在纯 Java 环境下运行。
- **高保真渲染** – 蒙版的渲染完全符合 XPS 规范。
- **跨平台** – 可在 Windows、Linux 或 macOS 上运行，无需修改。

## 前置条件
- 对 Java 编程有基本了解。  
- 已安装 Aspose.Page for Java 库。您可以在 **[here](https://releases.aspose.com/page/java/)** 下载。  
- 拥有有效的 Aspose.Page 许可证。如果没有，可在 **[here](https://purchase.aspose.com/temporary-license/)** 获取临时许可证。  
- 能够编译和运行 Java 应用的开发环境（例如 IntelliJ IDEA、Eclipse 或 VS Code）。

## 导入包
首先从 Aspose.Page 库中导入所需的类，以确保项目中可使用该 API。

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
首先，实例化一个新的 XPS 文档，用于容纳所有图形。

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
这里我们创建一个矩形路径并填充纯红色。该矩形随后会应用不透明度蒙版。

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### 步骤 4：使用 ImageBrush 添加不透明度蒙版
我们加载一张 TIFF 图像，定义源矩形和目标矩形，并将画刷设置为平铺模式，以便在需要时重复蒙版。

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### 步骤 5：保存生成的 XPS 文档
最后，将文档保存到磁盘。输出文件将包含已应用不透明度蒙版的矩形。

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

请仔细按照上述步骤，将 **add opacity mask** 功能集成到您的 Java XPS 文档中，使用 Aspose.Page。

## 常见问题与故障排除
- **未找到图像** – 请确认 `dataDir` 指向正确的文件夹，并且 `R08SY_NN.tif` 存在。  
- **蒙版显示为实色** – 确认源图像实际包含不同的 alpha 值；完全不透明的图像不会显示透明效果。  
- **平铺模式未生效** – 目标矩形必须小于源矩形，才能明显看到平铺效果。

## 常见问答

**Q: Aspose.Page 是否兼容所有 Java 开发环境？**  
A: 是的，Aspose.Page 旨在与各种 Java IDE 和构建工具无缝配合。

**Q: 我可以在没有许可证的情况下使用 Aspose.Page 吗？**  
A: 虽然可以使用临时许可证进行评估，但生产使用必须拥有正式许可证。

**Q: 试用版是否有任何限制？**  
A: 试用版可能会对尺寸或功能施加限制；请查阅官方文档获取详细信息。

**Q: 如何获取 Aspose.Page 的支持？**  
A: 请访问 **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** 获取社区帮助，或购买许可证以获得高级支持。

**Q: Aspose.Page 是否提供退款保证？**  
A: 请参阅 **[purchase page](https://purchase.aspose.com/buy)** 了解退款政策。

---

**最后更新：** 2026-01-02  
**测试环境：** Aspose.Page Java 24.11（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}