---
date: 2026-02-25
description: 了解如何使用 Aspose.Page for .NET 创建 XPS 文档并应用线性渐变。按照我们的分步指南保存 XPS 文件。
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page 创建具有垂直渐变的 XPS 文档
url: /zh/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 为 XPS 添加垂直渐变

## 介绍

在本教程中，您将 **创建 XPS 文档**，其中包含平滑的垂直渐变。添加渐变是让 XPS 文件看起来更专业的常用方法——非常适合报告、宣传册或任何可打印的图形。我们将逐步演示，从项目设置到保存最终的 XPS 文件，让您能够快速为任意路径应用线性渐变。

## 快速答案
- **本教程涵盖什么内容？** 在 XPS 文档中的路径上添加垂直线性渐变。  
- **需要哪个库？** Aspose.Page for .NET。  
- **需要许可证吗？** 开发阶段可使用免费试用版；生产环境需要商业许可证。  
- **实现大概需要多长时间？** 基本示例约 10‑15 分钟。  
- **可以将结果保存为 XPS 文件吗？** 可以，`Save` 方法会将文件写入磁盘。

## 什么是 XPS 中的垂直渐变？

垂直渐变是指颜色从形状的顶部向底部过渡的效果。在 XPS 中，这通过 **线性渐变画刷** 实现，需定义起始点和结束点，并提供一组渐变停靠点，以控制特定位置的颜色。

## 为什么使用 Aspose.Page 来创建带渐变的 XPS 文档？

- **完整的 .NET 集成** – 支持 .NET Framework、.NET Core 以及 .NET 5/6+。  
- **无外部依赖** – 所有渲染工作均由库内部完成。  
- **高保真度** – 渐变按照定义精确渲染，符合 XPS 规范。  
- **易于维护** – 对路径、画刷和颜色提供清晰的对象模型。

## 前置条件

- Aspose.Page for .NET 库：确保已在开发环境中安装 Aspose.Page for .NET 库。您可以在[此处](https://releases.aspose.com/page/net/)下载。  
- 开发环境：使用您喜欢的 IDE（如 Visual Studio）搭建 .NET 开发环境。

准备就绪后，让我们进入代码实现。

## 导入命名空间

在 .NET 应用程序中，加入必要的命名空间以访问 Aspose.Page 类和方法。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## 步骤 1：设置文档目录

定义生成的 XPS 文件将保存的文件夹路径。

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## 步骤 2：创建新 XPS 文档

实例化一个全新的 XPS 文档，随后我们将在其中填充带渐变的路径。

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## 步骤 3：定义渐变停靠点

渐变停靠点决定颜色以及它们在渐变线上的位置。这里我们创建五个停靠点，以实现平滑的垂直过渡。

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## 步骤 4：创建带渐变的路径

我们绘制一个矩形路径，并应用 **线性渐变画刷**，该画刷从点 (10, 110) 垂直延伸到点 (10, 200)。画刷使用前面定义的渐变停靠点。

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## 步骤 5：保存生成的 XPS 文档

最后，将 XPS 文档写入磁盘。此 **保存 XPS 文件** 步骤会在您指定的文件夹中生成 `AddVerticalGradient_outXPS.xps`。

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**小贴士：** 通过在 Windows XPS Viewer 或任意第三方查看器中打开 XPS 文件，验证渐变是否如预期显示。

## 常见问题与排查

| 症状 | 可能原因 | 解决办法 |
|---------|--------------|-----|
| 渐变显示为纯色 | 渐变停靠点未添加到画刷 | 确保执行 `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);`。 |
| 保存时文件未找到 | `dataDir` 指向了不存在的文件夹 | 先创建目录或使用绝对路径。 |
| 颜色显示不一致 | 颜色值使用 ARGB 顺序；请检查通道顺序 | 正确使用 `CreateColor(alpha, red, green, blue)`。 |

## 常见问答

**问：Aspose.Page 与 Visual Studio 2019 兼容吗？**  
答：兼容。请确保已安装对应版本的库。

**问：可以在商业项目中使用 Aspose.Page 吗？**  
答：可以。请访问[此处](https://purchase.aspose.com/buy)了解授权选项。

**问：是否提供免费试用？**  
答：提供，您可以在[此处](https://releases.aspose.com/)获取免费试用版。

**问：在哪里可以找到 Aspose.Page 的文档？**  
答：文档位于[此处](https://reference.aspose.com/page/net/)。  

**问：如何获取支持或提问？**  
答：请访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)获取社区支持。

## 结论

现在，您已经掌握了使用 Aspose.Page for .NET **创建 XPS 文档**、**应用线性渐变**以及**保存 XPS 文件**的完整流程。这种方法让您能够全面控制 XPS 输出的视觉样式，使可打印文档更具吸引力。

---  

**最后更新：** 2026-02-25  
**测试环境：** Aspose.Page for .NET 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}