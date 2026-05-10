---
date: 2026-03-05
description: 学习如何在 Java 中使用 Aspose.Page 的 Visual Brush 添加网格。按照一步步指南，轻松提升文档的视觉效果。
linktitle: Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: 如何在 Java 中使用 Visual Brush 添加网格
url: /zh/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Visual Brush 添加网格

## 介绍
如果您想在 Java 生成的文档中**添加网格**元素，Aspose.Page 的 Visual Brush 功能让这变得异常简单。在本教程中，我们将逐步演示每一步，解释为何 Visual Brush 非常适合网格图案，并向您展示一个完整、可运行的示例。

## 快速答案
- **什么是 Visual Brush？** 可重复平铺或拉伸以填充区域的可复用视觉元素。  
- **为什么使用网格？** 网格有助于构建布局、创建背景图案或在 XPS 文档中突出显示特定区域。  
- **先决条件？** Java JDK、Aspose.Page for Java，以及对 Java 图形的基本了解。  
- **实现需要多长时间？** 库配置好后约 10‑15 分钟即可完成。  
- **可以自定义颜色吗？** 可以——您可以在代码中直接控制填充颜色、不透明度和瓦片大小。

## 为什么使用 Visual Brush 添加网格？
Visual Brush 允许您一次定义一个小的视觉元素（即“瓦片”），然后在任意形状上重复它。这种方式内存效率高，代码也更简洁，尤其是在需要对多个画布应用相同图案时。

## 先决条件
在深入代码之前，请确保您具备以下条件：
- 对 Java 编程有基本了解。  
- 已安装 Aspose.Page 库。您可以从 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) 下载。  
- 机器上已安装 Java Development Kit (JDK)。

## 导入包
确保在 Java 项目中导入了必要的包：
```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

### 步骤 1：设置项目
首先，创建一个 `XpsDocument` 实例，并指向保存输出的文件夹。
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### 步骤 2：创建品红网格 Visual Brush
我们构建一个小的品红色瓦片以供重复。路径几何体定义了瓦片的形状。
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### 步骤 3：为品红网格 Visual Brush 定义几何体
在这里描述将接受平铺刷子的区域。
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### 步骤 4：创建新画布
向文档添加一个全新的画布，并应用平移变换，使网格出现在期望的位置。
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### 步骤 5：将网格添加到画布
现在将 Visual Brush 绑定到几何体并设置平铺模式。
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### 步骤 6：添加红色半透明矩形
为了演示层叠效果，我们在网格上覆盖一个半透明的红色矩形。
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### 步骤 7：保存生成的 XPS 文档
最后，将 XPS 文件写入磁盘。
```java
doc.save(dataDir + "AddGrid_out.xps");
```

按照这些步骤操作，您就能在使用 Aspose.Page 的 Java 应用程序中成功添加视觉上令人满意的网格。

## 常见用例
- **报告背景：** 为财务或工程报告添加细微的网格图案，以提升可读性。  
- **设计模板：** 创建可复用的页面模板，使相同的网格在多页之间重复。  
- **突出显示区域：** 使用彩色网格覆盖特定文档区域，以吸引注意力。

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| **网格出现拉伸** | 确认 `TileMode` 已设置为 `XpsTileMode.Tile`，且源矩形和目标矩形尺寸相同。 |
| **颜色偏差** | 创建实色刷时使用正确的 RGBA 值（`createColor(alpha, red, green, blue)`）。 |
| **文档未保存** | 检查 `dataDir` 是否指向已存在且可写入的文件夹，并确认拥有相应的文件系统权限。 |

## 结论
恭喜！您已经学习了如何使用 Aspose.Page 的 Visual Brush 在 Java 中**添加网格**元素。这种技术让您对图案渲染拥有细粒度的控制，同时保持代码简洁、易于维护。

## 常见问题
### Aspose.Page 适合专业文档生成吗？
是的，Aspose.Page 是一个为 Java 设计的强大库，专用于专业文档生成。

### 能否使用 Visual Brush 自定义网格颜色？
当然可以！Visual Brush 允许您使用各种颜色进行绘制，提供了高度的自定义灵活性。

### 在哪里可以获得 Aspose.Page 的额外支持？
请访问 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 获取社区支持和讨论。

### Aspose.Page 有免费试用吗？
有，您可以访问 [free trial](https://releases.aspose.com/) 体验 Aspose.Page 的功能。

### 如何获取 Aspose.Page 的临时许可证？
可获取 [temporary license](https://purchase.aspose.com/temporary-license/) 用于测试目的。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-03-05  
**测试环境：** Aspose.Page for Java（最新发布）  
**作者：** Aspose  

---