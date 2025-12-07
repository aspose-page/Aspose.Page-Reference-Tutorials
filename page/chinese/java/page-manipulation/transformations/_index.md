---
date: 2025-12-07
description: 学习如何在 Java 中使用 Aspose.Page 缩放矩形、平移形状并应用仿射变换，以创建 PostScript 文档。
language: zh
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: 如何使用 Aspose.Page 缩放矩形并应用变换
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page 缩放矩形并应用变换

## 介绍
欢迎阅读本指南，全面了解 **Aspose.Page for Java** 的强大功能，完成各种页面变换操作。在本教程中，您将学习 **如何缩放矩形**、平移形状、旋转对象以及 **应用仿射变换** 技术，同时创建 **PostScript 文档**。这些能力让您能够构建图形密集型的 Java 应用，而无需编写底层渲染代码。

## 快速答案
- **如何在 Java 中使用 Aspose.Page 缩放矩形？** 在绘制形状之前调用 `document.scale()` 方法。  
- **能否平移（translate）形状而不影响其他图形？** 可以——先保存图形状态，调用 `document.translate(x, y)`，绘制后再恢复状态。  
- **哪个类用于创建 PostScript 文件？** `PsDocument` 配合 `PsSaveOptions`。  
- **生产环境是否需要许可证？** 商业部署必须使用有效的 Aspose.Page 许可证。  
- **支持哪个 Java 版本？** Aspose.Page 支持 Java 8 及以上版本。

## 前置条件
在开始逐步指南之前，请确保已满足以下前置条件：

- 具备 Java 编程基础。  
- 已安装 Aspose.Page for Java 库。可从 [Aspose.Page for Java 文档](https://reference.aspose.com/page/java/) 下载。  
- 在本机上配置好 Java 集成开发环境（IDE）。

## 导入包
在 Java 项目中导入使用 Aspose.Page 所需的包：

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 什么是 Aspose.Page 中的 “how to scale rectangle”？
缩放矩形会沿 X、Y 轴改变其尺寸，同时保持形状不变。Aspose.Page 提供 `scale(float sx, float sy)` 方法，对当前图形状态应用 **仿射变换**。这正是 **how to scale rectangle** 关键字背后的核心技术。

## 如何使用 Aspose.Page 平移形状
平移会将形状移动到新位置，但不改变其尺寸。这正是 **how to translate shape** 的本质。通过保存图形状态、调用 `translate(dx, dy)`、绘制形状，然后恢复状态，可确保其他对象不受影响。

## 示例 1：无变换
第一个示例绘制一个未应用任何变换的简单矩形，作为后续示例的基准。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## 示例 2：平移
本示例演示 **how to translate shape**，在绘制第二个矩形之前将图形上下文向右平移 250 单位。

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## 示例 3：缩放
本示例回答主要问题 **how to scale rectangle**。我们将矩形的宽度缩小至原来的 50%，高度缩小至 75%。

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## 如何在 Java 中旋转形状（rotate shape java）
旋转是另一种常见的仿射操作。虽然此处省略了旋转代码片段，但模式相同：保存图形状态，调用 `document.rotate(angle)`，绘制形状，然后恢复。这展示了 **rotate shape java** 与 **how to rotate rectangle** 的实际用法。

## 为什么使用 Aspose.Page 进行这些变换？
- **设备无关**：一次编写，可生成 PostScript 或 XPS，无需平台特定代码。  
- **细粒度控制**：直接操作图形状态，可组合平移、缩放、剪切和旋转。  
- **性能**：低开销 API，适合大批量文档的批处理。  

## 常见使用场景
- 生成带有动态条形码和徽标的可打印发票。  
- 创建需要精确缩放和定位的技术图表。  
- 自动化生成多页 PostScript 报告。

## 结论
在本教程中，我们使用 Aspose.Page for Java 探索了 Java 页面操作的各种变换，重点关注 **how to scale rectangle**、**how to translate shape** 以及其他仿射操作。通过这些示例，您可以为 Java 应用添加高级页面操作能力，并 **创建 PostScript 文档**，满足专业出版标准。

## 常见问题
### 我可以使用 Aspose.Page for Java 处理其他文档格式吗？
Aspose.Page 主要聚焦于 PostScript 和 XPS 的页面操作。

### 在哪里可以找到更多 Aspose.Page for Java 的示例和文档？
请访问 [Aspose.Page for Java 文档](https://reference.aspose.com/page/java/) 获取完整信息。

### Aspose.Page for Java 有免费试用吗？
有，您可以在此处获取免费试用 [here](https://releases.aspose.com/)。

### 如何获取 Aspose.Page for Java 的临时许可证？
请在此获取临时许可证 [here](https://purchase.aspose.com/temporary-license/)。

### 在哪里可以获得社区支持或提问关于 Aspose.Page for Java 的问题？
请访问 [Aspose.Page for Java 论坛](https://forum.aspose.com/c/page/39) 与社区交流。

## FAQ

**问：`translate` 与 `scale` 有何区别？**  
答：`translate` 移动坐标系的原点，而 `scale` 按 X 和/或 Y 轴改变绘制对象的大小。

**问：我可以在同一图形状态中组合多种变换吗？**  
答：可以——在绘制前依次调用 `translate`、`scale`、`rotate` 或 `shear`，即可形成组合仿射变换。

**问：绘制形状后如何重置变换？**  
答：使用 `document.writeGraphicsRestore()` 恢复到先前保存的图形状态。

**问：能否围绕矩形中心进行旋转？**  
答：完全可以。先将矩形平移至原点，调用 `rotate(angle)`，再平移回原位置后绘制。

**问：Aspose.Page 是否支持抗锯齿以获得更平滑的图形？**  
答：支持——在 `PsSaveOptions` 中设置相应的渲染选项即可启用抗锯齿。

---

**最后更新：** 2025-12-07  
**测试环境：** Aspose.Page for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}