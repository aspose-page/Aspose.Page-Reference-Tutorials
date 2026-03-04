---
date: 2025-12-25
description: 学习如何在 Java 中使用 Aspose.Page 为 XPS 文档添加渐变，以及如何自定义渐变停靠点，以实现惊艳的水平效果。
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: 如何在 Java XPS 中添加渐变 – 水平渐变
url: /zh/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java XPS 中添加水平渐变

## 介绍
欢迎阅读本分步指南，了解 **如何在 XPS 文档中添加渐变**，使用 Java 实现水平渐变，了解其对视觉效果的提升意义，以及如何 **自定义渐变停靠点** 以实现精确的颜色控制。Aspose.Page for Java 让处理 XPS（XML Paper Specification）文档变得简单，您可以专注于设计，而无需关注底层文件处理。

## 快速回答
- **需要哪个库？** Aspose.Page for Java  
- **支持哪个 Java 版本？** 任意 Java 8+ 运行时  
- **需要许可证吗？** 开发阶段可使用免费试用版；生产环境需购买商业许可证  
- **可以改变渐变方向吗？** 可以 – 只需修改线性画刷的起始/结束点  
- **可以添加多个渐变吗？** 完全可以 – 对不同画刷重复路径创建步骤  

## 什么是 XPS 中的水平渐变？
水平渐变是颜色从左到右平滑过渡的效果。在 XPS 中，它由线性渐变画刷表示，画刷在定义的 **gradient stops** 之间进行插值。此视觉效果常用于横幅、按钮和背景填充。

## 为什么使用 Aspose.Page for Java？
- **完整的 XPS 支持** – 无需第三方工具即可创建、编辑和渲染。  
- **简洁的 API** – `XpsDocument`、`XpsPath`、`XpsGradientBrush` 等高级对象隐藏了 XML 的复杂性。  
- **性能优秀** – 针对大文档和批量处理进行优化。  

## 前置条件
在开始之前，请确保您已经具备：

1. **Java 开发环境** – 从 [java.com](https://www.java.com) 安装最新的 JDK。  
2. **Aspose.Page for Java 库** – 从 [Aspose.Page for Java 文档](https://reference.aspose.com/page/java/) 下载 JAR 包。  

## 导入包
首先导入所需的类。这些导入为您提供文档创建、渐变处理以及基本几何操作的访问权限。

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
创建一个全新的 `XpsDocument` 实例，并指定保存结果的文件夹路径。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## 步骤 2：创建水平渐变
定义一组 **gradient stops**，用于控制每个过渡点的颜色和位置。下面的示例构建了一个充满活力的彩虹式渐变。

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
- **位置** – 第二个参数（`0` 到 `1` 之间的 `float`）决定停靠点在渐变线上的出现位置。调整这些数值即可将颜色向左或向右移动。

## 步骤 3：使用渐变添加路径
创建一个矩形路径，必要时应用变换，并使用线性渐变画刷填充。画刷使用两个点（`(10,0)` 到 `(228,0)`）产生水平效果。

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**小技巧：** 对多个路径复用同一个 `stops` 列表可以提升性能，但在添加新停靠点前记得调用 `clear()`。

## 步骤 4：保存文档
将 XPS 文件持久化到磁盘。现在您可以使用任意 XPS 查看器打开，看到水平渐变的实际效果。

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## 常见问题与解决方案
| 问题 | 原因 | 解决办法 |
|------|------|----------|
| 渐变显示为纯色 | 未添加渐变停靠点或未设置画刷 | 确保 `path.setFill(...)` 使用 `LinearGradientBrush`，并通过 `getGradientStops().addAll(stops)` 添加停靠点。 |
| 颜色显得暗淡 | Alpha 值（第一个参数）不正确 | 除非需要透明，否则使用 `255` 以获得完全不透明的颜色。 |
| 路径尺寸不对 | 变换矩阵数值错误 | 调整矩阵参数（`scaleX, skewY, skewX, scaleY, translateX, translateY`）。 |

## 常见问答

**问：我可以在同一个 XPS 文档中使用多个渐变吗？**  
答：可以，您可以为每条路径添加各自的渐变画刷，从而创建复杂的分层设计。

**问：Aspose.Page 是否兼容最新的 Java 版本？**  
答：Aspose.Page for Java 会定期更新，支持 Java 8 及更高版本。

**问：Aspose.Page 还有其他类型的渐变吗？**  
答：除了线性渐变，Aspose.Page 还支持径向渐变，用于圆形颜色过渡。

**问：我可以自定义渐变停靠点的颜色和位置吗？**  
答：当然！您可以完全控制每个停靠点的 ARGB 颜色以及相对位置（0‑1 范围）。

**问：是否有 Aspose.Page 的社区论坛可以求助？**  
答：有，您可以访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 与社区交流并获取帮助。

---

**最后更新：** 2025-12-25  
**测试环境：** Aspose.Page for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}