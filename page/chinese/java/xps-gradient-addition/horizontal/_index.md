---
date: 2026-03-13
description: 学习如何在 Java 中使用 Aspose.Page 为 XPS 文档添加渐变，以及如何自定义渐变停靠点以实现惊艳的水平效果。
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: 如何在 Java XPS 中添加渐变 – 水平渐变
url: /zh/java/xps-gradient-addition/horizontal/
weight: 11
---

 etc. Keep them.

Also ensure we didn't translate any URLs.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java XPS 中添加渐变 – 水平渐变

## 介绍
欢迎阅读本分步指南，了解如何使用 Java **向 XPS 文档添加渐变**。在本教程中，您将学习如何添加水平渐变、它为何对视觉润色至关重要，以及如何 **自定义渐变停靠点** 以实现精确的颜色控制。Aspose.Page for Java 使处理 XPS（XML Paper Specification）文档变得简单，让您专注于设计而非底层文件处理。

## 快速答案
- **需要哪个库？** Aspose.Page for Java  
- **哪个 Java 版本可用？** 任意 Java 8+ 运行时  
- **需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证  
- **可以更改渐变方向吗？** 可以 – 只需修改线性画刷的起始/结束点  
- **可以添加多个渐变吗？** 当然可以 – 对不同的画刷重复路径创建步骤  

## 什么是 XPS 中的水平渐变？
水平渐变是颜色从左到右在形状上平滑过渡的效果。在 XPS 中，它由线性渐变画刷表示，该画刷在定义的 **gradient stops** 之间进行插值。此视觉效果常用于横幅、按钮和背景填充。

## 为什么使用 Aspose.Page for Java？
- **完整的 XPS 支持** – 创建、编辑和渲染，无需第三方工具。  
- **简洁的 API** – 像 `XpsDocument`、`XpsPath` 和 `XpsGradientBrush` 这样的高级对象隐藏了 XML 的复杂性。  
- **性能** – 为大文档和批处理优化。  

## 前置条件
在开始之前，请确保您已拥有：

1. **Java 开发环境** – 从 [java.com](https://www.java.com) 安装最新的 JDK。  
2. **Aspose.Page for Java 库** – 从 [Aspose.Page for Java 文档](https://reference.aspose.com/page/java/) 下载 JAR。  

## 导入包
首先导入必要的类。这些导入为您提供文档创建、渐变处理和基本几何操作的访问权限。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## 步骤 1：初始化 XPS 文档
创建一个新的 `XpsDocument` 实例，并指向您希望保存结果的文件夹。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## 步骤 2：创建水平渐变
定义一个 **gradient stops** 列表，以控制每个过渡点的颜色和位置。下面的示例构建了一个充满活力的彩虹式渐变。

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### 如何自定义渐变停靠点
- **颜色** – 使用 `doc.createColor(alpha, red, green, blue)` 设置任意 ARGB 值。  
- **位置** – 第二个参数（`0` 到 `1` 之间的 `float`）定义停靠点在渐变线上的出现位置。调整这些值可将颜色向左或向右移动。

## 步骤 3：添加带渐变的路径
创建一个矩形路径，必要时应用变换，并使用线性渐变画刷填充。该画刷使用两个点 (`(10,0)` 到 `(228,0)`) 产生水平效果。由于 Y 坐标相同，此画刷充当 **horizontal gradient brush**。

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**技巧提示：** 对多个路径重复使用相同的 `stops` 列表可以提升性能，但在添加新停靠点之前请记得调用 `clear()`。

## 步骤 4：保存文档
将 XPS 文件持久化到磁盘。现在您可以使用任何 XPS 查看器打开它，查看水平渐变的实际效果。

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## 如何应用多个渐变
如果您想在同一 XPS 文档中 **应用多个渐变**，只需对每个新形状重复“创建水平渐变”和“添加带渐变的路径”步骤。使用全新的 `XpsGradientStop` 对象列表（或清除现有列表），并为其分配具有独立起始/结束点的 `LinearGradientBrush`。这种方法可让您在单页中叠加渐变、创建复杂背景或突出显示不同的 UI 元素。

## 为什么这很重要 – 水平渐变画刷的优势
- **视觉深度：** 水平渐变画刷在不使用额外图像的情况下添加细腻的三维感。  
- **文件大小效率：** 渐变以向量定义存储，使 XPS 文件保持轻量。  
- **可伸缩性：** 由于渐变基于向量，在高分辨率显示器上可以清晰缩放。  

## 常见问题与解决方案
| 问题 | 原因 | 解决方案 |
|------|------|--------|
| 渐变显示为纯色 | 未添加渐变停靠点或未设置画刷 | 确保 `path.setFill(...)` 使用 `LinearGradientBrush`，并通过 `getGradientStops().addAll(stops)` 添加停靠点。 |
| 颜色显得暗淡 | Alpha 值（第一个参数）不正确 | 除非需要透明，否则使用 `255` 表示完全不透明的颜色。 |
| 路径尺寸不正确 | 变换矩阵值错误 | 调整矩阵参数（`scaleX, skewY, skewX, scaleY, translateX, translateY`）。 |

## 常见问答

**Q: 我可以在单个 XPS 文档中应用多个渐变吗？**  
A: 可以，您可以添加多个路径，每个路径使用各自的渐变画刷，以创建复杂的分层设计。

**Q: Aspose.Page 与最新的 Java 版本兼容吗？**  
A: Aspose.Page for Java 会定期更新，兼容 Java 8 及更高版本。

**Q: Aspose.Page 还有其他渐变类型吗？**  
A: 除了线性渐变，Aspose.Page 还支持径向渐变，用于圆形颜色过渡。

**Q: 我可以自定义渐变停靠点的颜色和位置吗？**  
A: 当然可以！您可以完全控制每个停靠点的 ARGB 颜色及其相对位置（0‑1 范围）。

**Q: 有没有 Aspose.Page 的社区论坛可以求助？**  
A: 有，您可以访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 与社区交流并获取帮助。

---

**最后更新：** 2026-03-13  
**测试环境：** Aspose.Page for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}