---
date: 2026-02-28
description: 了解如何使用 Aspose.Page for .NET 将图像添加到 PostScript 文档。本指南还涵盖如何在需要时将位图插入 PS
  并从 PS 中提取图像。
linktitle: Add Image to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: 如何使用 Aspose.Page 向 PostScript (PS) 文档添加图像
url: /zh/net/image-management/add-image-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page 向 PostScript (PS) 文档添加图像

## 如何向 PostScript (PS) 文档添加图像

在本教程中，您将学习 **如何向 PostScript (PS) 文档添加图像**，使用功能强大的 Aspose.Page for .NET 库。无论是准备可打印的传单、技术图纸，还是自定义报告，将图形直接嵌入 PS 文件都能显著提升视觉质量。我们将逐步演示每一步，解释每行代码的意义，并提供可在后续项目中复用的技巧。

## 快速答疑
- **需要哪个库？** Aspose.Page for .NET（最新版本）
- **可以在 ps 中插入位图吗？** 可以 – 使用 `DrawImage` 并传入 `Bitmap` 对象
- **实现大概需要多长时间？** 基本图像插入通常在 10 分钟以内
- **需要许可证吗？** 试用版可用于评估；生产环境需购买商业许可证
- **以后可以从 ps 中提取图像吗？** 完全可以 – Aspose.Page 也提供提取 API

## 前置条件

在编写代码之前，请确保已满足以下前置条件：

- Aspose.Page for .NET 库：从 [here](https://releases.aspose.com/page/net/) 下载并安装 Aspose.Page for .NET 库。
- 文档目录：在系统上创建一个目录，用于存放文档和图像文件。

## 导入命名空间

首先在项目中导入必要的命名空间。这些命名空间使您能够在 .NET 应用程序中使用 Aspose.Page 功能：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步骤 1：设置文档目录

确保为文档准备了专用目录。将下面代码片段中的 `"Your Document Directory"` 替换为实际的文档目录路径。

```csharp
string dataDir = "Your Document Directory";
```

## 步骤 2：为 PS 文档创建输出流

为 PostScript 文档设置输出流。该流将用于保存修改后的文档。

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddImage_outPS.ps", FileMode.Create))
```

## 步骤 3：创建保存选项

为 PS 文档创建保存选项，指定所需的设置，例如页面尺寸。

```csharp
PsSaveOptions options = new PsSaveOptions();
```

## 步骤 4：创建 PS 文档

初始化一个包含 1 页的 PS 文档，并准备进行图形操作。

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
document.WriteGraphicsSave();
document.Translate(100, 100);
```

## 步骤 5：在 PS 文档中插入位图

从图像文件加载 `Bitmap` 对象并应用变换。这是 **如何向文档添加图像** 的核心——我们将在 PS 画布上绘制位图。

```csharp
using (Bitmap image = new Bitmap(dataDir + "TestImage Format24bppRgb.jpg"))
{
    System.Drawing.Drawing2D.Matrix transform = new System.Drawing.Drawing2D.Matrix();
    transform.Translate(35, 300);
    transform.Scale(3, 3);
    transform.Rotate(-45);
    
    document.DrawImage(image, transform, Color.Empty);
}
```

> **专业提示：** 调整 `Translate`、`Scale` 和 `Rotate` 参数，以将图像精确定位并设定所需大小。

## 步骤 6：完成图形操作

结束图形操作并关闭当前页面。

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## 步骤 7：保存文档

保存已修改的 PS 文档。

```csharp
document.Save();
```

## 如何从 PS 文档中提取图像

如果以后需要获取图形，Aspose.Page 提供了如 `PsDocument.ExtractImages` 的提取方法。虽然本教程侧重于插入，但同一库同样可以 **从 ps 中提取图像**，用于复用或分析。

## 常见问题及解决方案

| 问题 | 产生原因 | 解决办法 |
|------|----------|----------|
| 图像出现失真 | 缩放矩阵不正确 | 检查 `Scale` 参数；使用统一缩放（如 `Scale(1,1)`）以保持原始尺寸 |
| 输出文件为空 | 流未刷新 | 确保在 `using` 块内调用 `document.Save()` |
| 不支持的图像格式 | Bitmap 无法加载该文件 | 将图像转换为受支持的格式，如 JPEG、PNG、BMP 或 GIF |

## 结论

恭喜！您已成功学习 **如何向 PostScript 文档添加图像**，并使用 Aspose.Page for .NET 完成操作。现在，您已经掌握了插入图形的基础，并了解了 **从 ps 中提取图像** 与 **在 ps 中插入位图** 的方法。欢迎尝试多图像、不同变换，甚至自定义绘图指令，以创建丰富的可打印内容。

## 常见问答

### Q1: 能否使用 Aspose.Page 在单个 PS 文档中添加多张图像？

A1: 可以。只需在文档中重复图像添加的步骤即可。

### Q2: Aspose.Page for .NET 支持哪些图像格式？

A2: Aspose.Page for .NET 支持多种图像格式，包括 JPEG、PNG、BMP 和 GIF。

### Q3: 添加的图像是否有大小限制？

A3: 大小限制取决于 PS 文档的规格以及系统资源。Aspose.Page 能处理各种尺寸的图像。

### Q4: 能否对图像应用额外的效果，如滤镜或叠加？

A4: 可以。Aspose.Page 允许在将图像加入文档前，对其进行各种变换和效果处理。

### Q5: 如何从 PS 文档中提取图像？

A5: Aspose.Page for .NET 提供了从 PS 文档中提取图像的方法。详细信息请参阅官方文档。

---

**最后更新：** 2026-02-28  
**测试环境：** Aspose.Page for .NET（最新发布）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}