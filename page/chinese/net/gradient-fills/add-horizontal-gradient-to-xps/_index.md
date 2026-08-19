---
date: 2026-02-25
description: 了解如何使用 Aspose.Page for .NET 创建水平填充的 XPS 渐变，轻松提升文档的视觉效果。
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page for .NET 创建 XPS 渐变：水平填充
url: /zh/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 XPS 渐变 – 使用 Aspose.Page for .NET 为 XPS 添加水平渐变

## 介绍

在本教程中，你将 **创建 XPS 渐变** 填充，使其在页面上水平延伸。添加水平渐变可以瞬间让 XPS 文档看起来更精致、更具吸引力，尤其适用于报告、宣传册或任何视觉丰富的输出。我们将使用 Aspose.Page for .NET，完整演示从环境搭建到保存最终 XPS 文件的全过程。

## 快速回答
- **本教程涵盖什么内容？** 使用 Aspose.Page for .NET 为 XPS 文档添加水平渐变。  
- **需要哪个库？** Aspose.Page for .NET（任意近期版本）。  
- **需要许可证吗？** 开发阶段可使用试用版；生产环境需要商业许可证。  
- **实现大概需要多长时间？** 基本渐变约 5–10 分钟即可完成。  
- **可以改变渐变方向吗？** 可以——修改 `LinearGradientBrush` 的起止点即可。

## 如何使用 Aspose.Page for .NET 创建 XPS 渐变

下面提供了逐步指南，解释 **为什么** 每行代码存在，而不仅仅是 **它做了什么**。你可以在 Visual Studio 或其他 .NET 编辑器中跟随操作。

## 前置条件

在开始之前，请确保已满足以下前置条件：

1. Aspose.Page for .NET 库：确保已在开发环境中安装 Aspose.Page for .NET 库。可从 [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/) 下载。  
2. 开发环境：搭建合适的开发环境，包括 Visual Studio 等代码编辑器。

## 导入命名空间

首先在项目中导入必要的命名空间。这些命名空间是使用 Aspose.Page for .NET 的前提：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

现在，让我们把示例代码拆分为多个步骤进行讲解。

## 步骤 1：设置文档目录路径

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## 步骤 2：创建新 XPS 文档

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## 步骤 3：初始化渐变停靠点

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## 步骤 4：创建新路径

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## 步骤 5：保存生成的 XPS 文档

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

至此，你已成功使用 Aspose.Page for .NET 为 XPS 文档添加水平渐变。

## 常见问题及解决方案

| 问题 | 原因 | 解决办法 |
|------|------|----------|
| 渐变显示为纯色 | 渐变停靠点未正确添加 | 确保在设置画笔后执行 `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` |
| 保存的文件为空 | `dataDir` 指向了不存在的文件夹 | 检查文件夹是否存在，或使用绝对路径 |
| `PointF` 编译错误 | 缺少 `System.Drawing` 引用 | 为 .NET Core/5+ 添加 `System.Drawing.Common` 引用 |

## FAQ

### Q1: 在哪里可以找到 Aspose.Page for .NET 文档？

A1: 你可以在 [此处](https://reference.aspose.com/page/net/) 查看文档。

### Q2: 如何下载 Aspose.Page for .NET？

A2: 可从 [Aspose.Page for .NET 下载页面](https://releases.aspose.com/page/net/) 获取库文件。

### Q3: 在哪里可以购买 Aspose.Page for .NET？

A3: 请前往 [购买页面](https://purchase.aspose.com/buy) 进行购买。

### Q4: 是否提供免费试用？

A4: 是的，可在 [此处](https://releases.aspose.com/) 获取免费试用版。

### Q5: 如何获取 Aspose.Page for .NET 的临时许可证？

A5: 可通过 [此链接](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

## 常见问答

**问：我可以在已经包含图像的 XPS 文档中使用此渐变技术吗？**  
答：完全可以。渐变应用于路径层，现有图像不会受到影响。

**问：能否创建垂直渐变？**  
答：可以。只需将 `LinearGradientBrush` 的起止点 Y 坐标设为不同值，而 X 坐标保持不变。

**问：Aspose.Page 是否支持 .NET Core？**  
答：该库完全兼容 .NET Core、.NET 5 及更高版本。

**问：如何在多个页面上复用同一渐变？**  
答：只需创建一次 `XpsLinearGradientBrush`，将其存入变量，然后在每页的路径上引用该变量即可。

## 结论

为 XPS 文档添加渐变不仅提升视觉效果，还能提供更具吸引力的用户体验。借助 Aspose.Page for .NET，你可以 **快速且可靠地创建 XPS 渐变** 填充，为报告、宣传册或电子书赋予专业的光彩。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-02-25  
**测试环境：** Aspose.Page for .NET 24.11  
**作者：** Aspose  

---