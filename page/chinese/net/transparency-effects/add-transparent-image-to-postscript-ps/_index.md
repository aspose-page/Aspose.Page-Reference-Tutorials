---
date: 2026-03-26
description: 学习如何在 .NET 中创建 PostScript 文档并使用 Aspose.Page 添加透明图像。本分步指南涵盖前置条件、代码和技巧。
linktitle: Add Transparent Image to PostScript (PS)
second_title: Aspose.Page .NET API
title: 使用透明图像在 .NET 中创建 PostScript 文档（Aspose.Page）
url: /zh/net/transparency-effects/add-transparent-image-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建带透明图像的 PostScript 文档 .NET (Aspose.Page)

## 介绍

在本教程中，您将学习 **如何在 .NET 中创建 PostScript 文档** 并使用 Aspose.Page for .NET 嵌入透明 PNG。添加透明图像可以构建更丰富的分层图形——非常适合水印、叠加层或 UI 原型在 PS 文件中的使用。我们将一步步演示，从环境搭建到渲染不透明和透明图像的全过程。

## 快速答案
- **Aspose.Page 是什么？** 它提供了完整的 API，用于在 .NET 中生成、编辑和渲染 PostScript (PS) 与 XPS 文档。  
- **我可以添加透明 PNG 吗？** 可以——使用 `DrawTransparentImage` 来控制不透明度。  
- **支持哪些 .NET 版本？** 所有近期的 .NET Framework、.NET Core 以及 .NET 5/6 版本。  
- **我需要许可证吗？** 免费试用可用于评估；生产环境需要许可证。  
- **实现大约需要多长时间？** 基础示例大约 10‑15 分钟即可完成。

## 先决条件

在开始之前，请确保您拥有：

- **Aspose.Page for .NET** – 从 [download link](https://releases.aspose.com/page/net/) 下载。  
- 用于存放 PS 文档和要嵌入图像的文件夹。  
- 一个透明 PNG（例如 `mask1.png`），将用作透明层。

## 导入命名空间

首先，导入包含我们需要的类的命名空间。这样即可访问 PS 文档模型、图形工具以及基本的 .NET 绘图类型。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 步骤 1：设置文档目录

定义源图像和输出 PS 文件所在的路径。将占位符替换为您机器上的实际路径。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## 步骤 2：为 PostScript 文档创建输出流

我们将生成的 PS 内容写入文件流。该流随后会传递给 `PsDocument` 构造函数。

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTransparentImage_outPS.ps", FileMode.Create))
{
    // Your code for the next steps will go here.
}
```

## 步骤 3：设置保存选项和背景颜色

配置 `PsSaveOptions` 以定义文件的保存方式。设置背景颜色在需要为透明元素提供实色画布时非常有用。

```csharp
PsSaveOptions options = new PsSaveOptions();
options.BackgroundColor = Color.FromArgb(211, 8, 48);
```

## 步骤 4：创建一个新的 1 页 PS 文档

使用上述流和选项创建文档。`false` 标志告诉 Aspose.Page 不要自动关闭流。

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 步骤 5：写入图形保存和位移

在绘制之前，先保存当前的图形状态并平移原点，使图像出现在页面的期望位置。

```csharp
document.WriteGraphicsSave();
document.Translate(20, 100);
```

## 如何向 PostScript 文档添加透明图像

### 步骤 6：添加不透明的 RGB 图像

首先将同一 PNG 作为普通不透明图像添加。此步骤用于展示后续应用透明度时的视觉差异。

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 100, 0), Color.Empty);
}
```

### 步骤 7：添加透明图像

现在使用 `DrawTransparentImage` 渲染带有不透明度值的 PNG。第三个参数 (`255`) 表示完全不透明；数值越低透明度越高。这正是我们 **在 .NET 中设置图像透明度** 的地方。

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawTransparentImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 350, 0), 255);
}
```

> **技巧提示：** 要使图像 50 % 透明，请传入 `128` 而不是 `255`。

## 步骤 8：写入图形恢复并关闭页面

绘制完成后，恢复之前的图形状态并关闭页面，以完成内容的最终化。

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## 步骤 9：保存文档

最后，将 PS 文件持久化到磁盘。

```csharp
document.Save();
```

通过上述步骤，您已经 **创建了一个 .NET PostScript 文档**，其中包含不透明图像和透明图像，展示了如何使用 Aspose.Page **在 C# 中绘制透明图像**。

## 为什么使用 Aspose.Page 实现透明效果？

- **对图形状态、矩阵和不透明度级别的完整控制。**  
- **无外部依赖**——所有操作均在纯 .NET 代码中运行。  
- **跨平台支持**，可在 Windows、Linux 或 macOS 上生成 PS 文件。

## 常见问题与故障排除

| 问题 | 解决方案 |
|-------|----------|
| 即使使用 `DrawTransparentImage`，图像仍显示为完全不透明 | 确保 alpha 值（第三个参数）小于 `255`。 |
| PS 文件显示空白页 | 验证已设置背景颜色且流路径正确。 |
| 异常 “File not found” | 再次检查 `dataDir` 并确认该文件夹中存在 `mask1.png`。 |

## 常见问答

**Q: 我可以使用除 PNG 之外的其他图像格式实现透明吗？**  
A: 可以——Aspose.Page 支持 PNG、GIF 和 TIFF 的透明渲染。

**Q: Aspose.Page 与最新的 .NET 框架兼容吗？**  
A: 完全兼容。库会定期更新以支持 .NET 6、.NET 7 及更高版本。

**Q: 我可以对已有的 PS 文档应用透明度吗？**  
A: 可以。使用 `PsDocument` 打开文档，添加新页或修改已有页，然后使用相同的 `DrawTransparentImage` 方法。

**Q: 与通用图形库相比，Aspose.Page 有哪些优势？**  
A: 它专为 PS/XPS 设计，提供对矢量图形、字体和图像处理的精确控制，无需完整的渲染引擎。

**Q: 透明度级别有没有限制？**  
A: 没有。您可以指定任意 alpha 值，范围从 `0`（完全透明）到 `255`（完全不透明）。

## 结论

我们演示了如何 **创建 .NET PostScript 文档** 并使用 Aspose.Page 嵌入不透明和透明图像。此技术为实现复杂的文档布局、水印以及分层图形打开了大门——所有这些都可以通过 C# 程序化生成。

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}