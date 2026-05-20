---
date: 2026-04-24
description: 学习如何在 Java 中使用径向渐变椭圆创建 XPS 文档。本分步指南展示了如何使用 Aspose.Page 设置笔画粗细并定义路径几何形状。
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: 在 Java XPS 中添加椭圆
second_title: Aspose.Page Java API
title: 在 Java 中创建 XPS 文档 – 添加径向渐变椭圆
url: /zh/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 添加带有 Aspose.Page 的径向渐变椭圆

## 介绍
在本教程中，您将学习如何使用 Aspose.Page for Java 创建带有精美径向渐变描边椭圆的 **create XPS document Java**。Aspose.Page 是一个强大的库，抽象了底层 XPS 细节，让您专注于设计而不是文件格式的复杂性。完成本指南后，您将拥有一个可直接使用的 XPS 文件，可嵌入报告、发票或任何文档生成工作流中。

## 快速答案
- **此代码产生什么？** 一个包含使用多色径向渐变描边的椭圆的单页 XPS 文件。  
- **使用了哪个主要 API？** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, 等)。  
- **运行示例是否需要许可证？** 临时许可证可用于评估；生产环境需要正式许可证。  
- **我们设置的关键属性是什么？** 描边刷（径向渐变）、扩散方式、渐变停止点和描边粗细。  
- **我可以更改椭圆的大小吗？** 可以——修改路径几何字符串或渐变刷坐标。

## 什么是 “create XPS document Java”？
在 Java 中创建 XPS 文档意味着通过代码程序化生成 XML Paper Specification (XPS) 文件——一种类似 PDF 的固定布局文档格式——直接从 Java 代码生成。Aspose.Page 提供了高级对象模型（`XpsDocument`、`XpsCanvas` 等），抽象了 XML 标记，使过程像使用标准 Java 对象一样简单。

## 为什么使用径向渐变椭圆？
径向渐变能够营造出三维感，非常适合在报告中用于视觉突出、徽标或装饰元素。相比纯色描边，渐变在不显著增加文件大小的情况下增加了层次感，且 XPS 格式能够保持矢量质量，支持任意缩放。

## 先决条件
- 在您的机器上已安装 Java Development Kit (JDK)。  
- 已下载 Aspose.Page for Java 库。您可以在[此处](https://releases.aspose.com/page/java/)获取。  
- 您选择的代码编辑器（Eclipse、IntelliJ 等），用于编写和执行 Java 代码。

## 导入包
确保在 Java 项目中导入了使用 Aspose.Page 所需的包。将以下 import 语句添加到 Java 文件的顶部：

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## 步骤 1：设置文档目录
定义保存 XPS 文档的文档目录路径：

```java
String dataDir = "Your Document Directory";
```

## 步骤 2：创建 XPS 文档
使用以下代码初始化一个新的 XPS 文档：

```java
XpsDocument doc = new XpsDocument();
```

## 步骤 3：定义径向渐变停止点
为径向渐变描边椭圆创建渐变停止点列表：

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## 步骤 4：创建路径几何
使用路径几何定义径向渐变描边椭圆：

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## 步骤 5：添加画布和路径
向文档添加新画布，并使用已定义的几何追加路径：

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## 步骤 6：设置描边和渐变
使用径向渐变刷配置路径的描边：

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## 步骤 7：设置描边粗细
指定路径的 **set stroke thickness**：

```java
path.setStrokeThickness(12f);
```

## 步骤 8：保存文档
保存生成的 XPS 文档：

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

恭喜！您已成功在使用 Aspose.Page **create XPS document Java** 时添加了径向渐变描边椭圆。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|----------------|-----|
| **椭圆呈现平面** | 使用 `XpsSpreadMethod.Pad` 而非 `Reflect` | 将扩散方式更改为 `XpsSpreadMethod.Reflect`，如步骤 6 所示。 |
| **没有输出文件** | `dataDir` 指向了不存在的文件夹 | 确保目录存在或使用绝对路径。 |
| **渐变颜色不正确** | 渐变停止点顺序错误 | 验证 `offset` 值（0 → 1）单调递增。 |
| **编译错误** | 类路径上缺少 Aspose.Page JAR 包 | 将 `aspose-page-xx.jar` 添加到项目依赖中。 |

## 常见问题

**Q: 我可以将 Aspose.Page for Java 与其他 Java 库一起使用吗？**  
A: 可以，Aspose.Page for Java 可以无缝集成到其他 Java 库中。

**Q: Aspose.Page 适合大规模文档处理吗？**  
A: 绝对适合！Aspose.Page 旨在高效处理大规模文档处理任务。

**Q: 在哪里可以找到更多 Aspose.Page for Java 的教程和示例？**  
A: 请访问 [Aspose.Page for Java 文档](https://reference.aspose.com/page/java/)获取完整的教程和示例。

**Q: 如何获取 Aspose.Page for Java 的临时许可证？**  
A: 您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

**Q: 是否有 Aspose.Page 讨论的社区论坛？**  
A: 有，加入 [Aspose.Page 社区论坛](https://forum.aspose.com/c/page/39) 与其他开发者交流并获取帮助。

---

**最后更新：** 2026-04-24  
**测试环境：** Aspose.Page for Java 24.11 (latest at time of writing)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}