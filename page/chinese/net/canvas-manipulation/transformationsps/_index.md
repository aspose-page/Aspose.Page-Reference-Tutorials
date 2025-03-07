---
title: 使用 Aspose.Page for .NET 转换 PS
linktitle: 变形PS
second_title: Aspose.Page .NET API
description: 通过这份关于 PostScript 转换的综合指南释放 Aspose.Page for .NET 的潜力。轻松创建动态图形。
weight: 12
url: /zh/net/canvas-manipulation/transformationsps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 转换 PS

## 介绍

欢迎来到 Aspose.Page for .NET 的世界，在这里您可以释放 PostScript 文档转换的力量。本教程将指导您完成各种变换，例如平移、缩放、旋转、剪切和复杂变换，使您能够创建视觉上令人惊叹的动态图形。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

-  Aspose.Page for .NET 库：确保您已将 Aspose.Page for .NET 库集成到您的项目中。您可以从[下载链接](https://releases.aspose.com/page/net/).

- 文档目录：为您的文档设置一个目录，并将代码中的占位符替换为实际路径。

## 导入命名空间

在您的 .NET 项目中，导入使用 Aspose.Page 所需的命名空间：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

现在，让我们以分步指南的形式将每个示例分解为多个步骤。


## 无转换

### 第 1 步：创建输出流

```csharp
//文档目录的路径。
string dataDir = "Your Document Directory";

//为 PostScript 文档创建输出流
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    //创建具有默认值的保存选项
    PsSaveOptions options = new PsSaveOptions();

    //创建新的 1 页 PS 文档
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    //从矩形创建图形路径
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    //将绘画设置为上层图形状态
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    //填充处于上层图形状态且不进行任何变换的第一个矩形
    document.Fill(path);

    //关闭当前页面
    document.ClosePage();

    //保存文档
    document.Save();
}
```

此代码创建一个没有转换的 PostScript 文档，用橙色填充矩形。

## 翻译

### 第1步：保存图形状态

```csharp
//保存图形状态以在变换后返回到该状态
document.WriteGraphicsSave();
```

此步骤保存当前的图形状态，以便我们在转换后返回到它。

### 第 2 步：转换图形状态

```csharp
//将当前图形状态向右移动 250
document.Translate(250, 0);
```

通过添加平移组件来平移当前图形状态，然后将当前图形状态下的绘制设置为蓝色。

### 第三步：用平移变换填充矩形

```csharp
//将绘画设置为当前图形状态
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

//填充当前图形状态下的第二个矩形（具有平移变换）
document.Fill(path);
```

此步骤填充当前图形状态下的第二个矩形，其中现在包括平移变换。

### 第四步：恢复图形状态

```csharp
//将图形状态恢复到上一个（上）级别
document.WriteGraphicsRestore();
```

填充矩形后，将图形状态恢复到之前的水平。

继续针对每种变换类型（包括缩放、旋转、剪切和复杂变换）的分步指南。

## 结论

恭喜！您已成功掌握 Aspose.Page for .NET 的变革功能。现在，尝试不同的组合并在 PostScript 文档转换中释放您的创造力。

## 常见问题解答

### Q1：如何对单个对象应用多个变换？

A1：要应用多个转换，请使用`Transform`具有自定义变换矩阵的方法。

### Q2：我可以在保存文档之前预览转换吗？

A2：是的，您可以通过渲染文档并在合适的查看器中预览来可视化转换。

### 问题 3：是否可以对文档中的特定元素应用转换？

A3：是的，您可以隔离文档中特定图形元素的转换。

### Q4：处理复杂的转换时是否有性能方面的考虑？

A4：复杂的转换可能会影响性能，因此请优化代码以提高效率。

### Q5：我如何获得 Aspose.Page 相关查询的支持或寻求帮助？

 A5：访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)以获得社区支持和讨论。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
