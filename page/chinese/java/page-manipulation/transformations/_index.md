---
date: 2026-02-07
description: 学习如何使用 Aspose.Page for Java 缩放矩形，如何平移形状，以及应用仿射变换来创建 PostScript 文档。
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: 如何使用 Aspose.Page for Java 缩放矩形
url: /zh/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page for Java 缩放矩形

## 介绍
欢迎阅读本综合指南，利用 **Aspose.Page for Java** 的强大功能执行各种页面转换。在本教程中，您将学习 **how to scale rectangle**、平移形状、旋转对象以及在创建 **PostScript document** 时 **apply affine transform** 技术。这些能力让您能够构建丰富、图形密集的 Java 应用程序，而无需处理底层渲染代码。

## 快速答案
- **如何在 Java 中使用 Aspose.Page 缩放矩形？** 在绘制形状之前使用 `document.scale()` 方法。  
- **我可以移动（平移）形状而不影响其他图形吗？** 是的——保存图形状态，调用 `document.translate(x, y)`，绘制，然后恢复状态。  
- **哪个类用于创建 PostScript 文件？** `PsDocument` 与 `PsSaveOptions` 一起使用。  
- **生产环境使用是否需要许可证？** 商业部署需要有效的 Aspose.Page 许可证。  
- **支持哪个 Java 版本？** Aspose.Page 支持 Java 8 及更高版本。

## 前置条件
在深入逐步指南之前，请确保您已具备以下前置条件：

- 具备 Java 编程的基础知识。  
- 已安装 Aspose.Page for Java 库。您可以从 [Aspose.Page for Java 文档](https://reference.aspose.com/page/java/) 下载。  
- 在您的机器上已设置 Java 集成开发环境（IDE）。

## 导入包
在您的 Java 项目中，导入使用 Aspose.Page for Java 所需的包：

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Aspose.Page 中的 “how to scale rectangle” 是什么？
缩放矩形会沿 X 轴和 Y 轴改变其尺寸，同时保持形状不变。Aspose.Page 提供 `scale(float sx, float sy)` 方法，该方法对当前图形状态应用 **affine transform**。这就是 **how to scale rectangle** 关键字背后的核心技术。

## 使用 Aspose.Page 平移形状的方法
平移将形状移动到新位置而不改变其尺寸。这正是 **how to translate shape** 的本质。通过保存图形状态，应用 `translate(dx, dy)`，绘制，然后恢复状态，您可以保持其他对象不受影响。

## 示例 1：无转换
第一个示例绘制了一个未应用任何转换的简单矩形。这作为后续示例比较的基准。

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
这里我们通过在绘制第二个矩形之前将图形上下文向右移动 250 单位，演示 **how to translate shape**。

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
此示例回答了主要问题 **how to scale rectangle**。我们将矩形的宽度缩小至原始的 50%，高度缩小至 75%。

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
旋转是另一种常见的仿射操作。出于简洁考虑，旋转的代码片段被省略，但模式完全相同：保存图形状态，调用 `document.rotate(angle)`，绘制形状，然后恢复。这展示了实际中的 **rotate shape java** 和 **how to rotate rectangle**。

## 为什么这很重要 – 实际收益
- **设备无关的输出** – 编写一次即可生成 PostScript 或 XPS，无需平台特定的调整。  
- **细粒度控制** – 结合平移、缩放、剪切和旋转，以满足精确的布局需求。  
- **面向性能** – 低开销的 API，非常适合批量处理大规模文档。  

## 常见使用场景
- 生成可打印的发票 – 例如，一个 **printable invoice java** 解决方案，可精确放置徽标和条形码。  
- 创建需要精确缩放和定位的技术图表。  
- 自动生成 PostScript 格式的多页报告。  

## 常见问题及解决方案
- **转换未重置** – 始终将 `document.writeGraphicsSave()` 与 `document.writeGraphicsRestore()` 配对使用，以避免不必要的残留效果。  
- **意外的颜色** – 确保在每次转换后设置绘图颜色；恢复后图形状态不会保留先前的颜色设置。  
- **文件大小过大** – 使用 `PsSaveOptions` 启用压缩或在嵌入光栅图形时降低图像分辨率。  

## 常见问答
### 我可以将 Aspose.Page for Java 用于其他文档格式吗？
Aspose.Page 主要专注于对 PostScript 和 XPS 格式的页面操作。

### 在哪里可以找到更多 Aspose.Page for Java 的示例和文档？
请访问 [Aspose.Page for Java 文档](https://reference.aspose.com/page/java/) 获取全面信息。

### 是否提供 Aspose.Page for Java 的免费试用？
是的，您可以在 [此处](https://releases.aspose.com/) 获取免费试用。

### 如何获取 Aspose.Page for Java 的临时许可证？
请在 [此处](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

### 在哪里可以寻求社区支持或提问关于 Aspose.Page for Java 的问题？
请访问 [Aspose.Page for Java 论坛](https://forum.aspose.com/c/page/39) 进行社区讨论。

## 常见问题

**Q: `translate` 与 `scale` 有何区别？**  
A: `translate` 移动坐标系的原点，而 `scale` 沿 X 和/或 Y 轴改变绘制对象的大小。

**Q: 我可以在单个图形状态中组合多个转换吗？**  
A: 可以——在绘制之前依次调用 `translate`、`scale`、`rotate` 或 `shear`，即可创建组合的仿射变换。

**Q: 绘制形状后如何重置转换？**  
A: 使用 `document.writeGraphicsRestore()` 恢复到先前保存的图形状态。

**Q: 能否围绕矩形中心旋转它？**  
A: 完全可以。先将矩形平移到原点，应用 `rotate(angle)`，然后在绘制前再平移回去。

**Q: Aspose.Page 是否支持抗锯齿以获得更平滑的图形？**  
A: 是的——在 `PsSaveOptions` 中设置相应的渲染选项即可启用抗锯齿。

---

**最后更新：** 2026-02-07  
**测试环境：** Aspose.Page for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}