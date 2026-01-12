---
date: 2026-01-12
description: 了解如何使用 Aspose.Page for .NET 保存 PostScript 文件并创建 PostScript 文档，以及对动态图形应用多种变换。
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page Transformations (.NET) 保存 PostScript 文件
url: /zh/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 转换 (.NET) 保存 PostScript 文件

## 介绍

在本教程中，您将了解如何在使用 Aspose.Page for .NET 时 **保存 PostScript 文件**。我们将演示创建 PostScript 文档、应用平移、缩放、旋转和剪切等多种变换，最后保存结果。完成后，您将能够以编程方式创建动态图形，并准确掌握在图形状态中放置每个变换的位置。

## 快速回答
- **我可以创建什么？** 一个具备完整功能的带有变换图形的 PostScript 文档。  
- **需要哪个库？** Aspose.Page for .NET（可从官方网站下载）。  
- **如何保存文件？** 在配置图形状态后使用 `PsDocument.Save()`。  
- **我可以应用多个变换吗？** 可以——使用 `Transform` 或顺序调用来组合它们。  
- **需要许可证吗？** 免费试用可用于开发，生产环境需要商业许可证。

## 什么是“保存 PostScript 文件”操作？

保存 PostScript 文件意味着将您在内存中构建的绘图指令持久化为磁盘上的 `.ps` 文件。该文件随后可以被任何 PostScript 解释器、打印机或查看器渲染。

## 为什么使用 Aspose.Page for .NET 创建 PostScript 文档？

Aspose.Page 提供了高级、设备无关的 API，抽象了底层的 PostScript 语法。您将获得：

- 强类型的 C# 对象，用于路径、画刷和变换。  
- 自动处理图形状态栈（保存/恢复）。  
- 完全支持复杂的变换矩阵，无需手动计算。  

## 前提条件

在开始之前，请确保您已：

- 将 **Aspose.Page for .NET** 库集成到项目中。可从 [download link](https://releases.aspose.com/page/net/) 获取。  
- 拥有可写入的文件夹，用于存放生成的 `.ps` 文件。请将代码中的占位路径替换为实际目录。

## 导入命名空间

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

现在让我们逐步探索每个变换。

## 无变换

### 步骤 1：创建输出流

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

此代码片段创建了一个仅包含橙色矩形的 **PostScript 文档**，并在未应用任何变换的情况下 **保存 PostScript 文件**。

## 平移

### 步骤 1：保存图形状态

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

保存图形状态可让您在移动对象后恢复原始状态。

### 步骤 2：平移图形状态

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

此平移操作会将此后绘制的所有内容向右移动 250 个单位。

### 步骤 3：使用平移变换填充矩形

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

现在，一个蓝色矩形出现在橙色矩形右侧 250 点的位置。

### 步骤 4：恢复图形状态

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

恢复后坐标系返回原始位置，后续绘制不受平移影响。

## 缩放

> *您可以遵循相同的模式——保存状态、应用 `Scale`、绘制，然后恢复。*  
> **专业提示：** 使用非均匀缩放 (`Scale(sx, sy)`) 可仅在单一方向上拉伸对象。

## 旋转

> *使用 `Rotate(angle)` 绕原点或自定义枢轴点进行旋转。*  
> **专业提示：** 在旋转前先 `Translate`，可实现围绕特定点的旋转。

## 剪切

> *剪切变换 (`Shear(shx, shy)`) 会倾斜形状，适用于斜体效果。*  

## 复杂变换

> *对于高级场景，构建自定义 `Matrix` 并将其传递给 `Transform(matrix)`。*  
> 这就是在单一步骤中 **应用多个变换** 的方式。

## 结论

您已经学习了如何 **保存 PostScript 文件**、**创建 PostScript 文档**，以及使用 Aspose.Page for .NET **应用多种变换**。尝试不同的变换顺序、组合它们，观察图形的演变。

## 常见问题

**Q: 如何对单个对象应用多个变换？**  
A: 使用 `Transform` 方法并传入自定义 `Matrix`，在所需顺序中组合平移、缩放、旋转或剪切。

**Q: 能在保存文档前预览变换效果吗？**  
A: 可以——将 `PsDocument` 渲染为图像，或使用 PostScript 查看器在调用 `Save()` 前检查输出。

**Q: 能对文档中的特定元素单独应用变换吗？**  
A: 完全可以。在绘制该元素前保存图形状态，应用所需变换，绘制后恢复状态。

**Q: 处理复杂变换时有哪些性能考虑？**  
A: 复杂矩阵会增加 CPU 负担。尽量保持变换简洁，并在绘制大量相似对象时复用已保存的状态。

**Q: 如何获取 Aspose.Page 相关的支持或帮助？**  
A: 访问 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 获取社区帮助，或直接联系 Aspose 支持。

---

**Last Updated:** 2026-01-12  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}