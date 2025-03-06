---
title: 使用 Aspose.Page 添加径向渐变椭圆
linktitle: 在 Java XPS 中添加椭圆
second_title: Aspose.Page Java API
description: 探索有关使用 Aspose.Page for Java 在 Java XPS 中添加径向渐变描边椭圆的分步指南。轻松增强您的文档创建。
weight: 10
url: /zh/java/xps-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 添加径向渐变椭圆

## 介绍
欢迎阅读我们有关使用 Aspose.Page for Java 在 Java XPS 中添加椭圆的分步指南。 Aspose.Page 是一个功能强大的 Java 库，允许开发人员轻松处理 XPS 文档。在本教程中，我们将引导您完成创建径向渐变描边椭圆并将其保存为 XPS 文档的过程。
## 先决条件
在我们开始之前，请确保您具备以下先决条件：
- 您的计算机上安装了 Java 开发工具包 (JDK)。
- 下载 Java 库的 Aspose.Page。你可以得到它[这里](https://releases.aspose.com/page/java/).
- 您选择的代码编辑器（Eclipse、IntelliJ 等）用于编写和执行 Java 代码。
## 导入包
确保您已在 Java 项目中导入了使用 Aspose.Page 所需的包。将以下导入语句添加到 Java 文件的顶部：
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
## 第 1 步：设置文档目录
定义保存 XPS 文档的文档目录的路径：
```java
String dataDir = "Your Document Directory";
```
## 第 2 步：创建 XPS 文档
使用以下代码初始化一个新的 XPS 文档：
```java
XpsDocument doc = new XpsDocument();
```
## 第 3 步：定义径向渐变停止点
为径向渐变描边椭圆创建渐变停止点列表：
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## 第 4 步：创建路径几何图形
使用路径几何定义径向渐变描边椭圆：
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## 第5步：添加画布和路径
将新画布添加到文档并附加具有定义的几何图形的路径：
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## 第6步：设置描边和渐变
使用径向渐变画笔配置路径的笔划：
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## 第7步：设置描边粗细
指定路径的描边粗细：
```java
path.setStrokeThickness(12f);
```
## 第 8 步：保存文档
保存生成的 XPS 文档：
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
恭喜！您已使用 Aspose.Page for Java 在 Java XPS 中成功添加了径向渐变描边椭圆。
## 结论
在本教程中，我们探索了创建具有视觉吸引力的径向渐变描边椭圆的 XPS 文档的步骤。 Aspose.Page for Java 简化了 XPS 文档操作，为开发人员提供了强大的工具集。
## 经常问的问题
### 我可以将 Aspose.Page for Java 与其他 Java 库一起使用吗？
是的，Aspose.Page for Java 可以与其他 Java 库无缝集成。
### Aspose.Page适合大规模文档处理吗？
绝对地！ Aspose.Page 旨在高效处理大规模文档。
### 在哪里可以找到有关 Aspose.Page for Java 的更多教程和示例？
参观[Aspose.Page 用于 Java 文档](https://reference.aspose.com/page/java/)获取全面的教程和示例。
### 如何获得 Aspose.Page for Java 的临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 是否有用于 Aspose.Page 讨论的社区论坛？
是的，加入[Aspose.Page 社区论坛](https://forum.aspose.com/c/page/39)与其他开发人员互动并获得帮助。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
