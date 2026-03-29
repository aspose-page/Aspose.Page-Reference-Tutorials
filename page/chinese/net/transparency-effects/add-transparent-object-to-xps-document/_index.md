---
date: 2026-03-29
description: 学习如何在 XPS 文档中添加透明对象，然后使用 Aspose.Page for .NET 将 XPS 导出为 PDF。一步一步的指南，提供实用技巧。
linktitle: Add Transparent Object to XPS Document
second_title: Aspose.Page .NET API
title: 将 XPS 导出为 PDF – 使用 Aspose.Page 添加透明对象
url: /zh/net/transparency-effects/add-transparent-object-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 导出 XPS 为 PDF – 使用 Aspose.Page 添加透明对象

## 介绍

在本教程中，您将学习如何向 XPS 文档添加透明对象，然后使用 Aspose.Page for .NET **导出 XPS 为 PDF**。透明度可以让您的文档更具现代感，并帮助突出重要信息。我们将逐步演示每一步，解释代码背后的原理，并展示如何通过将 XPS 文件转换为 PDF 来完成工作流，以便轻松共享。

## 快速答疑
- **“导出 XPS 为 PDF”是什么意思？** 将 XPS 文件转换为 PDF 文件，同时保留布局、颜色和透明度。  
- **为什么先添加透明度？** 透明对象可以创建层叠图形，使最终 PDF 看起来更出色。  
- **我需要许可证吗？** 是的，生产环境中必须拥有有效的 Aspose.Page 许可证。  
- **这可以在 .NET Core 上运行吗？** 当然可以 – Aspose.Page 支持 .NET Core、.NET 5/6 以及完整的 .NET Framework。  
- **在哪里可以找到更多示例？** 请查看下面链接的 Aspose.Page 文档和社区论坛。

## 先决条件

在开始教程之前，请确保您已具备以下条件：

- Aspose.Page for .NET：确保已安装 Aspose.Page .NET 库。您可以从 [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/) 下载。

## 导入命名空间

要开始使用，请在项目中包含必要的命名空间：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

现在，让我们继续逐步指南。

## 步骤 1：创建新的 XPS 文档

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

此代码使用 Aspose.Page for .NET 初始化一个新的 XPS 文档。

## 步骤 2：演示透明度

```csharp
// Just to demonstrate transparency
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

这些代码行创建了两个灰色路径，作为后续添加透明形状的背景。

## 步骤 3：使用闭合矩形几何创建路径

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

这里我们创建一个蓝色矩形。由于稍后会更改其不透明度，矩形在最终 PDF 中将呈现半透明效果。

## 步骤 4：操作路径和颜色

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

我们克隆第一个矩形，将其添加到页面，并将填充颜色切换为绿色。这演示了复用现有几何体的简便性。

## 步骤 5：克隆并变换路径

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

克隆后的路径向下移动 300 单位并填充为红色，形成堆叠层效果。

## 步骤 6：重复并修改路径

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

我们复用 `path2` 的几何数据，将其向右移动，并再次应用蓝色填充。

## 步骤 7：管理不透明度

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

将 `Opacity` 属性设置为 0.8，使该矩形的透明度为 80 %，展示了如何为每个元素微调透明度。

## 步骤 8：保存 XPS 文档

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

XPS 文件已保存，所有透明对象均已应用。  

**导出为 PDF：** 要 **导出 XPS 为 PDF**，只需再次调用 `doc.Save` 并使用 `.pdf` 扩展名，例如 `doc.Save(dataDir + "TransparentDocument.pdf");`。生成的 PDF 将保留相同的视觉保真度，包括不透明度设置。

## 为什么在添加透明度后导出 XPS 为 PDF？

- **通用兼容性：** PDF 在各平台上得到广泛支持，而 XPS 更为小众。  
- **保留视觉效果：** Aspose.Page 在转换过程中保持透明度、渐变和矩阵变换。  
- **便于共享：** PDF 可在浏览器、移动设备以及众多第三方阅读器中打开，无需额外插件。

## 常见使用场景

- **营销手册**：层叠图形营造高端感。  
- **技术图表**：在不杂乱布局的情况下突出显示关键部分。  
- **报告生成**：可在报告上叠加部分透明的水印或徽标。

## 技巧与注意事项

- **专业提示：** 始终将 `Opacity` 值设定在 0 到 1 之间。超出范围的值会被截断，可能导致意外结果。  
- **性能提示：** 复用几何体 (`path2.Data`) 可在需要大量相似形状时降低内存占用。  
- **陷阱：** 直接在添加透明度后保存为 PDF 可即刻生效，但若后续使用其他工具编辑 PDF，某些旧版阅读器可能无法正确渲染不透明度。

## 结论

使用 Aspose.Page for .NET 向 XPS 文档添加透明对象，为提升视觉表现提供了灵活的方式。当您的 XPS 文件达到理想效果后，只需一行代码即可 **导出 XPS 为 PDF**，并在广泛分发时保留所有透明效果。

## 常见问题

### Q1：我可以对 XPS 文档中的任何对象应用透明度吗？

A1：是的，透明度可以应用于 XPS 文档中的路径、形状和图像等多种对象。

### Q2：如何调整特定元素的不透明度？

A2：可以设置 Fill 或 Stroke 的 `Opacity` 属性，以调节特定元素的透明度。

### Q3：Aspose.Page 与 .NET Core 兼容吗？

A3：是的，Aspose.Page 支持 .NET Core，能够实现跨平台开发。

### Q4：我可以使用 Aspose.Page 将 XPS 文档导出为其他格式吗？

A4：Aspose.Page 提供将 XPS 文档导出为多种格式的功能，包括 PDF 和图像。

### Q5：在哪里可以找到更多支持和社区讨论？

A5：有关更多支持和社区讨论，请访问 [Aspose.Page Forum](https://forum.aspose.com/c/page/39)。

### Q6：PDF 转换会保留我的透明度设置吗？

A6：当然。使用 Aspose.Page 导出 XPS 为 PDF 时，所有不透明度和混合设置都会被保留。

### Q7：我可以批量处理多个 XPS 文件并导出为 PDF 吗？

A7：可以，您可以遍历 XPS 文件集合，对每个文件调用 `doc.Save(...".pdf")`，实现批量转换。

---

**最后更新：** 2026-03-29  
**已测试版本：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}