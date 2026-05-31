---
date: 2026-01-23
description: 学习如何使用 Aspose.Page for .NET 生成 PostScript 文件并添加圆形椭圆。请按照本分步指南快速绘制椭圆的 C#
  代码。
linktitle: Add Circle Ellipse to PostScript (PS)
second_title: Aspose.Page .NET API
title: 生成 PostScript 文件并添加圆形和椭圆 – Aspose.Page
url: /zh/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 生成 PostScript 文件并添加圆形椭圆 – Aspose.Page

## 介绍

在本教程中，您将了解 **如何生成 PostScript 文件** 并使用 Aspose.Page .NET API 嵌入完美的圆形椭圆。无论您是在构建报表引擎、创建矢量图形，还是需要在 C# 中以编程方式绘制椭圆，本指南都会一步步带您完成——从环境搭建到保存最终的 PS 文档。

## 快速答疑
- **本教程覆盖哪些内容？** 使用 Aspose.Page for .NET 向 PostScript 文件添加两个椭圆（填充和描边）。  
- **目标关键词是什么？** *generate postscript file*。  
- **需要许可证吗？** 开发阶段可使用免费试用版；生产环境需要商业许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **实现大概需要多长时间？** 基本椭圆示例约 10‑15 分钟即可完成。

## 什么是 “generate postscript file”？

生成 PostScript 文件指的是以编程方式创建一个 .ps 文档，使用 PostScript 语言描述页面内容。该格式广泛用于打印、图形设计以及 PDF 转换流水线。

## 为什么要使用 Aspose.Page 添加圆形椭圆？

- **精度** – 基于矢量的绘制确保无损缩放。  
- **跨平台** – 同一 PS 文件可在任何兼容 PostScript 的打印机上渲染。  
- **C# 友好** – API 抽象了底层 PS 命令，让您使用熟悉的 .NET 类型即可 *draw ellipse*。

## 前置条件

在开始之前，请确保您已具备：

1. **Aspose.Page for .NET** – 从 [here](https://releases.aspose.com/page/net/) 下载并安装库。  
2. **.NET 开发环境** – Visual Studio、Rider 或已在机器上安装 .NET CLI。

准备就绪后，开始编写代码吧。

## 导入命名空间

首先，引入所需的命名空间，以便使用 Aspose.Page 类。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步骤指南

### 步骤 1：设置文档目录

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

> **小贴士：** 将 `"Your Document Directory"` 替换为应用程序可写入的绝对或相对路径。

### 步骤 2：为 PostScript 文档创建输出流

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

`FileStream` 会打开（或创建）*AddEllipse_outPS.ps*，生成的 PS 内容将保存到该文件中。

### 步骤 3：创建保存选项并实例化 PS 文档

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

这里我们指定 A4 页面尺寸，并实例化一个单页的 `PsDocument`。

### 步骤 4：为第一个椭圆创建图形路径

```csharp
//Create graphics path from the first ellipse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

`GraphicsPath` 保存了位于 (250, 100)、宽度为 150 pt、高度为 100 pt 的椭圆几何定义。

### 步骤 5：设置画刷并填充椭圆

```csharp
//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Fill the ellipse
document.Fill(path);
```

我们使用鲜艳的橙色填充第一个椭圆。

### 步骤 6：为第二个椭圆创建图形路径

```csharp
//Create graphics path from the second ellipse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

第二个椭圆定义在页面更低的位置（y 坐标 300）。

### 步骤 7：设置描边并绘制椭圆

```csharp
//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Stroke (outline) the ellipse
document.Draw(path);
```

这次我们使用粗细为 3 pt 的红色笔 *draw ellipse*，产生描边轮廓。

### 步骤 8：关闭当前页面并保存文档

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

关闭页面后内容完成，`Save()` 会将 PostScript 输出写入前面创建的流。

## 常见问题与解决方案

| 问题 | 原因 | 解决办法 |
|------|------|----------|
| **文件未创建** | `dataDir` 指向不存在的文件夹。 | 确保目录已存在，或在打开流之前使用 `Directory.CreateDirectory(dataDir);`。 |
| **椭圆出现变形** | 矩形尺寸不正确（宽度 ≠ 高度）。 | 使用相等的宽度和高度以获得完美圆形；相应调整 `RectangleF` 的数值。 |
| **许可证异常** | 在生产环境中未使用有效的 Aspose.Page 许可证。 | 按 Aspose 文档说明应用临时或永久许可证。 |

## 常见问答

**问：我可以在 .NET 中使用 Aspose.Page 处理其他文档格式吗？**  
答：Aspose.Page 主要聚焦于 PostScript，但 Aspose 还提供 PDF、DOCX 等其他格式的库。完整列表请参阅 [Aspose documentation](https://reference.aspose.com/page/net/)。

**问：在哪里可以找到更多支持和社区讨论？**  
答：访问 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 提问、分享示例并获取其他开发者的帮助。

**问：Aspose.Page 是否提供免费试用？**  
答：是的，您可以从 [free trial](https://releases.aspose.com/) 页面下载免费试用版，以评估库的功能后再决定购买。

**问：如何获取用于测试的临时许可证？**  
答：可在 [here](https://purchase.aspose.com/temporary-license/) 申请临时许可证，有效期为 30 天。

**问：在哪里可以购买 Aspose.Page 的正式许可证？**  
答：购买选项列在官方的 [buy page](https://purchase.aspose.com/buy) 上。

## 结论

现在您已经掌握了使用 Aspose.Page for .NET **生成 PostScript 文件** 并 **绘制椭圆** 的方法。按照上述步骤，您可以轻松将矢量图形集成到任何打印或渲染工作流中。尝试不同的颜色、线宽和位置，创建更复杂的插图吧。

---

**最后更新：** 2026-01-23  
**测试环境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}