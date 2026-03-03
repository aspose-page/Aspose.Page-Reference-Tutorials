---
date: 2026-03-03
description: 了解如何使用 Aspose.Page for .NET 在 XPS 文档中平铺图像。本分步指南展示了如何高效平铺图像并提升视觉效果。
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: 如何使用 Aspose.Page 向 XPS 文档添加平铺图像
url: /zh/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page 向 XPS 文档添加平铺图像

## Introduction

如果您想了解 **如何使用 Aspose** 为 XPS 文件增添更丰富的视觉风格，您来对地方了。在本教程中，我们将逐步演示如何使用 Aspose.Page for .NET 在 XPS 文档中 **平铺图像**。完成后，您将拥有一个可在任何 .NET 项目中直接使用的代码片段，以即时创建平铺图像图形。

## Quick Answers
- **需要的库是什么？** Aspose.Page for .NET  
- **哪个方法创建平铺画刷？** `CreateImageBrush` with `TileMode = XpsTileMode.Tile`  
- **我可以控制不透明度吗？** 是 – 设置 `path.Fill.Opacity`（例如 0.5f）  
- **测试是否需要许可证？** 临时许可证可用于评估；生产环境需要正式许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## What is Aspose.Page and Why Tile Images?

Aspose.Page 是一个强大的 API，允许开发者在不依赖 Microsoft Office 的情况下生成、编辑和渲染 XPS、PDF 等基于页面的格式。平铺图像——在形状上重复位图——可帮助您使用图案、水印或背景纹理填充大面积区域，同时保持文件体积较小。

## How to Use Aspose.Page to Tile Images in XPS Documents

下面提供了一个完整、可直接运行的示例。每一步都用通俗的语言进行说明，随后给出相应的代码块，帮助您了解 **为什么** 每行代码是必要的。

### Prerequisites

- **Aspose.Page for .NET** – 从官方站点[here](https://reference.aspose.com/page/net/)下载并引用库。  
- **Development environment** – Visual Studio（任何版本）或您喜欢的其他 .NET IDE。

### Import Namespaces

首先，引入所需的命名空间，以便编译器能够找到 XPS 类。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Step 1: Define the Document Directory

指定生成的 XPS 文件和源图像所在的目录。请将占位符替换为您机器上的实际文件夹路径。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Step 2: Create a New XPS Document

实例化一个空的 XPS 文档，用于容纳平铺图形。

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Step 3: Add a Tiled Image

在这里我们创建一个矩形路径，使用 `ImageBrush` 填充，并将画刷设置为平铺模式。`TileMode` 属性指示引擎在水平和垂直方向上重复图像。根据实际需求调整矩形坐标或源图像。

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Step 4: Save the Resultant XPS Document

最后，将文档写入磁盘。生成的文件可使用任何 XPS 查看器打开，或进一步使用 Aspose.Page 进行处理。

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Common Issues & Tips

- **路径错误** – 确保 `dataDir` 以斜杠结尾，或使用 `Path.Combine` 避免缺少分隔符的问题。  
- **图像尺寸不匹配** – 源图像应足够大以覆盖平铺区域，否则图案可能被拉伸。  
- **不透明度不可见** – 某些查看器会忽略 XPS 的不透明度；请使用完全支持 XPS 渲染的查看器进行测试（例如 Windows 上的 XPS Viewer）。

## Frequently Asked Questions

### Q1: Aspose.Page 是否兼容所有 .NET 开发环境？
A: 是的，Aspose.Page 可在 Visual Studio、Rider、VS Code 以及任何支持 .NET 的 IDE 中使用。

### Q2: 我可以调整平铺图像的不透明度吗？
A: 当然可以。示例中将 `path.Fill.Opacity = 0.5f;` 设置为 0.5——您可以将该浮点值改为 0（透明）到 1（不透明）之间的任意值。

### Q3: Aspose.Page for .NET 还有其他平铺模式吗？
A: 有的。除了 `XpsTileMode.Tile`，您还可以使用 `FlipX`、`FlipY` 和 `FlipXY` 创建镜像图案。

### Q4: 我该如何处理 Aspose.Page 的临时许可证？
A: 请参阅 Aspose 网站上的[temporary license](https://purchase.aspose.com/temporary-license/)页面，了解获取和使用试用许可证的详细信息。

### Q5: 我可以在哪里寻求帮助或加入 Aspose.Page 社区？
A: 访问[Aspose.Page forum](https://forum.aspose.com/c/page/39) ，提问、分享代码片段并向其他开发者学习。

### Q6: 我能用这种方法创建水印效果吗？
A: 可以。通过降低不透明度并选择半透明图像，平铺画刷即可完美实现重复水印。

## Conclusion

您现在已经掌握了 **如何使用 Aspose** 向 XPS 文档添加平铺图像、控制其不透明度并保存结果的完整流程。此技术非常适合用于背景图案、水印或任何需要重复图形而不增加文件大小的场景。欢迎尝试不同的形状、图像和平铺模式，以满足项目的具体需求。

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Page for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}