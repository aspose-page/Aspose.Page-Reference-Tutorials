---
date: 2025-12-30
description: 学习如何使用 Aspose.Page 通过添加矩形在 Java 中创建 XPS 文档。请按照本分步指南，实现无缝的 XPS 文档操作。
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: 在 Java 中创建 XPS 文档 – 使用 Aspose.Page 添加矩形
url: /zh/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 XPS 文档 Java – 添加矩形

## 介绍
在本综合教程中，您将**创建 XPS 文档 Java**文件，并学习如何使用 Aspose.Page 库添加矩形。无论是构建报告、发票还是自定义图形，掌握矩形的创建都能让您对 XPS 布局进行精确控制。我们将逐步演示每一步，解释每行代码背后的原因，并展示如何自定义颜色和描边，以获得专业效果。

## 快速回答
- **推荐使用的库是什么？** Aspose.Page for Java  
- **实现大约需要多长时间？** 基本矩形约 10 分钟  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证  
- **支持哪个 Java 版本？** Java 8 及更高版本  
- **我可以添加多个形状吗？** 可以——对每个形状重复上述步骤

## 前置条件
在开始之前，请确保您具备以下条件：

- 对 Java 编程语言的基本了解。  
- 已安装 Aspose.Page 库。如果未安装，可从 [Aspose.Page Java 文档](https://reference.aspose.com/page/java/) 下载。  
- 可用的 Java 开发环境（IDE、JDK，以及 Maven/Gradle 等构建工具）。

## 导入包
要开始，请在 Java 项目中导入必要的包。确保已将 Aspose.Page 库正确添加到类路径中。以下是一个基本示例：

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

现在，让我们将提供的示例分解为多个步骤，以在 Java XPS 中添加矩形。

## 步骤 1：设置文档目录
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

将 `"Your Document Directory"` 替换为您希望存放 XPS 文件的文件夹路径。

## 步骤 2：创建新的 XPS 文档
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

此行**创建**一个全新的 XPS 文档，您随后可以向其中添加形状、文本或图像。

## 步骤 3：添加 CMYK 实色描边矩形
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

此步骤添加了一个使用 CMYK 实色的描边矩形。您可以更改几何字符串（`"M 20,10 L 220,10 220,100 20,100 Z"`）来修改大小或位置，并在 `createColor` 中调整颜色值以符合您的设计需求。

## 步骤 4：保存生成的 XPS 文档
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

最后，将添加了矩形的修改后 XPS 文档保存到您之前指定的目录中。

## 常见使用场景
- **报告标题** – 使用矩形作为标题的背景块。  
- **发票表格** – 使用彩色边框突出显示单元格或区域。  
- **自定义图形** – 组合多个矩形以创建复杂形状。

## 故障排除提示
- **文件未找到错误：** 确认 `dataDir` 指向已存在的文件夹，并且 ICC 配置文件（`uswebuncoated.icc`）存在。  
- **颜色不正确：** 确保 ICC 配置文件与您使用的色彩空间（CMYK 与 RGB）匹配。  
- **尺寸异常：** 调整几何字符串以匹配正确的坐标。

## 结论
恭喜！您已成功学习如何**创建 XPS 文档 Java**文件并使用 Aspose.Page 添加矩形。此基础使您能够构建更丰富的 XPS 文档、自定义图形，并将形状集成到更大的工作流中。

## 常见问题
### 我可以在单个 XPS 文档中添加多个矩形吗？
是的，您可以通过重复教程中的步骤，添加任意数量的矩形。

### 如何更改矩形的颜色？
在 `createColor` 方法中修改颜色值即可得到所需颜色。

### Aspose.Page 适合处理复杂的 XPS 文档操作吗？
当然！Aspose.Page 提供了一套强大的功能，能够处理各种 XPS 文档任务。

### 我在哪里可以找到更多示例和支持？
访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 获取更多示例，并向社区寻求帮助。

### 我可以在购买前试用 Aspose.Page 吗？
是的，您可以通过 [免费试用](https://releases.aspose.com/) 体验 Aspose.Page 的功能。

## 常见问答

**问：此方法是否适用于 Java 11 或更高版本？**  
答：是的，Aspose.Page 库兼容 Java 8 及更高版本，包括 Java 11、17 以及更高版本。

**问：我可以在矩形区域内嵌入图像吗？**  
答：您可以添加 `XpsImage` 元素，并使用相同的几何坐标将其放置在矩形上方或内部。

**问：如何设置填充颜色而不仅仅是描边？**  
答：调用 `path.setFill(...)`，并使用 `doc.createSolidColorBrush(...)` 创建的实色画刷。

**问：可以旋转矩形吗？**  
答：使用 `path.setTransform(...)` 对路径应用变换矩阵，以实现旋转或缩放。

**问：生产使用需要什么许可证？**  
答：部署时需要商业 Aspose.Page 许可证；免费试用仅限评估和开发使用。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2025-12-30  
**测试环境：** Aspose.Page for Java 24.12（最新）  
**作者：** Aspose  

---