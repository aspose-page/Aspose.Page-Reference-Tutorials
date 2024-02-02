---
title: 使用 Aspose.Page for .NET 将矩形添加到 PostScript (PS)
linktitle: 将矩形添加到 PostScript (PS)
second_title: Aspose.Page .NET API
description: 使用 Aspose.Page 增强 .NET 中的文档创建。了解逐步向 PostScript (PS) 文件添加矩形。
type: docs
weight: 12
url: /zh/net/drawing-shapes/add-rectangle-to-postscript-ps/
---
## 介绍

如果您希望增强 .NET 中的文档创建能力，Aspose.Page 提供了处理 PostScript 文档的强大解决方案。在本教程中，我们将指导您完成使用 Aspose.Page for .NET 将矩形添加到 PostScript 文档的过程。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

-  Aspose.Page for .NET 库：从以下位置下载并安装 Aspose.Page for .NET 库：[这里](https://releases.aspose.com/page/net/).

- 开发环境：确保您的计算机上设置了 .NET 开发环境。

## 导入命名空间

在开始编码之前，请确保导入必要的命名空间以访问所需的类和方法：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

现在，让我们将示例分解为多个步骤：

## 第 1 步：设置您的文档目录

```csharp
//开始时间：1
//文档目录的路径。
string dataDir = "Your Document Directory";
```

在此步骤中，将“您的文档目录”替换为您要保存 PostScript 文档的路径。

## 步骤 2：为 PostScript 文档创建输出流

```csharp
//为 PostScript 文档创建输出流
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

在这里，我们为 PostScript 文档创建一个输出流并指定文件名（“AddRectangle_outPS.ps”）。根据您的喜好调整文件名和位置。

## 步骤 3：设置保存选项并创建 PS 文档

```csharp
//创建 A4 尺寸的保存选项
PsSaveOptions options = new PsSaveOptions();

//创建新的 1 页 PS 文档
PsDocument document = new PsDocument(outPsStream, options, false);
```

设置保存选项，指定所需的页面尺寸（本例中为 A4）。然后，创建一个新的单页 PostScript 文档。

## 第四步：添加矩形并填充

```csharp
//从第一个矩形创建图形路径
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//定漆
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//填充矩形
document.Fill(path);
```

在这里，我们创建一个表示第一个矩形的图形路径，设置绘画颜色（在本例中为橙色），并填充矩形。

## 第5步：添加另一个矩形和描边

```csharp
//从第二个矩形创建图形路径
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//设定行程
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//描边（轮廓）矩形
document.Draw(path);
```

与上一步类似，我们为第二个矩形创建图形路径，设置描边颜色（红色，厚度为3），并勾勒出矩形的轮廓。

## 步骤 6：关闭页面并保存文档

```csharp
//关闭当前页面
document.ClosePage();

//保存文档
document.Save();
```

最后，关闭当前页面并保存整个文档。

## 结论

恭喜！您已使用 Aspose.Page for .NET 成功将矩形添加到 PostScript 文档中。本教程涵盖了从设置开发环境到保存最终文档的基本步骤。

## 常见问题解答

### Q1：我可以自定义矩形的颜色吗？

A1: 是的，您可以通过调整参数中的参数来自定义颜色`SolidBrush`和`Pen`类。

### Q2：Aspose.Page 是否兼容其他文档格式？

A2：是的，Aspose.Page支持各种文档格式，包括XPS和PostScript。

### Q3：如何在文档中添加文本？

 A3：您可以使用`TextFragment`Aspose.Page 中的类将文本添加到文档中。

### Q4：在哪里可以找到更多示例和文档？

 A4：浏览文档[这里](https://reference.aspose.com/page/net/)并参观[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)以获得社区支持。

### Q5：我可以在购买前试用Aspose.Page吗？

 A5：是的，您可以获得免费试用版[这里](https://releases.aspose.com/)，并且为了延长使用，请考虑[临时执照](https://purchase.aspose.com/temporary-license/).
