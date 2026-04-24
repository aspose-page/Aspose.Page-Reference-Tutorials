---
date: 2026-04-24
description: 学习如何在 Java XPS 中使用 Aspose.Page 设置矩形颜色并添加矩形。本指南涵盖 Java 添加矩形以及更改矩形描边。
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: 在 Java XPS 中添加矩形
second_title: Aspose.Page Java API
title: 在 Java XPS 中设置矩形颜色并添加矩形
url: /zh/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java XPS 中设置矩形颜色并添加矩形

## 介绍
在本指南中，您将学习如何使用 Aspose.Page 库在 Java XPS 中 **设置矩形颜色** 和 **添加矩形**。无论是为报告绘制简单形状，还是创建复杂的矢量图形，掌握矩形样式都能让您对 XPS 文档进行精确控制。

## 快速答案
- **需要的库是什么？** Aspose.Page for Java  
- **我可以更改矩形描边吗？** 是的，使用 `setStroke` 和 `setStrokeThickness`  
- **是否支持 CMYK 颜色配置文件？** 当然——如示例所示，您可以加载 ICC 配置文件  
- **生产环境需要许可证吗？** 是的，非评估使用需要商业许可证  
- **实现需要多长时间？** 对于基本矩形，通常在 10 分钟以内

## 什么是 **set rectangle color**？
设置矩形的颜色意味着定义形状在最终 XPS 文档中渲染时的填充或描边颜色。使用 Aspose.Page，您可以使用 RGB、CMYK，甚至自定义 ICC 颜色配置文件来实现精确的颜色匹配。

## 为什么使用 Aspose.Page 来 **add rectangle java** 和 **change rectangle stroke**？
- **功能完整的 API** – 支持纯色和渐变。  
- **跨平台** – 在任何 Java 运行时上工作，无需本地依赖。  
- **丰富的几何支持** – 创建复杂路径、应用变换，并轻松管理描边粗细。  

## 先决条件
在深入代码之前，请确保您具备：

- 具备 Java 编程的基础知识。  
- 已安装 Aspose.Page 库。如未安装，请从 [Aspose.Page Java 文档](https://reference.aspose.com/page/java/) 下载。  
- 可用的 Java 开发环境（IDE、JDK 等）。  

## 导入包
要开始，请在 Java 项目中导入必要的包。确保 Aspose.Page 库已正确添加到类路径中。以下是一个基本示例：
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

现在，让我们将示例拆解为多个步骤，以在 Java XPS 中 **添加矩形** 并 **设置其颜色**。

## 第一步：设置文档目录
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
将 `"Your Document Directory"` 替换为您希望读取/写入 XPS 文件的绝对路径。

## 第二步：创建新的 XPS 文档
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
此行初始化一个新的 XPS 文档，用于保存我们的形状。

## 第三步：添加 CMYK 实色描边矩形
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
此步骤添加一个 **描边矩形**，使用 CMYK 实色。`setStroke` 方法定义矩形的轮廓颜色，`setStrokeThickness` 控制线宽——非常适合 **更改矩形描边**。

### 小贴士：
如果您更喜欢 RGB 颜色，请将 `createColor` 调用替换为 `doc.createColor(0, 0, 255)`，即可得到纯蓝填充。

## 第四步：保存生成的 XPS 文档
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
最后，将 XPS 文档持久化到磁盘。文件 `AddRectangle_out.xps` 现在包含了您定义颜色和描边的矩形。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|-------|----------|
| **矩形不可见** | 路径几何不正确或描边厚度设置为 0 | 验证路径字符串 (`"M 20,10 L 220,10 220,100 20,100 Z"`) 并确保 `setStrokeThickness` 大于 0。 |
| **颜色错误** | 使用了与目标色彩空间不匹配的 ICC 配置文件 | 使用 `doc.createColor(r, g, b)` 创建 RGB 颜色，或再次检查 ICC 文件路径。 |
| **文件未保存** | `dataDir` 指向不存在的文件夹或没有写入权限 | 提前创建该文件夹或选择可写入的位置。 |

## 常见问题

**Q:** *我可以在单个 XPS 文档中添加多个矩形吗？*  
A: 是的。只需为每个需要的矩形重复几何创建和样式设置步骤。

**Q:** *我如何更改矩形的填充颜色而不是描边？*  
A: 使用 `path.setFill(...)` 并提供实色画刷，类似于使用 `setStroke` 的方式。

**Q:** *Aspose.Page 适用于复杂的 XPS 文档操作吗？*  
A: 当然。该库支持渐变、变换和嵌入字体等高级功能。

**Q:** *我在哪里可以找到更多示例和社区支持？*  
A: 浏览 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 获取更多代码示例和同行帮助。

**Q:** *我可以在购买前试用 Aspose.Page 吗？*  
A: 可以，您可以探索 [免费试用](https://releases.aspose.com/) 来评估 API 的功能。

---

**最后更新：** 2026-04-24  
**测试环境：** Aspose.Page for Java 24.12  
**作者：** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}