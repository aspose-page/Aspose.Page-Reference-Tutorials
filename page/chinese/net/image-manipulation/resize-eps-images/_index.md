---
title: 使用 Aspose.Page for .NET 调整 EPS 图像大小
linktitle: 调整 EPS 图像的大小
second_title: Aspose.Page .NET API
description: 探索使用 Aspose.Page 在 .NET 中调整 EPS 图像大小的无缝过程。轻松实现点、英寸、毫米和百分比的精度。
weight: 11
url: /zh/net/image-manipulation/resize-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 调整 EPS 图像大小

## 介绍

您是否希望使用 Aspose.Page for .NET 无缝调整 EPS 图像的大小？本教程是您轻松操作各种单位（例如点、英寸、毫米和百分比）的 EPS 图像尺寸的综合指南。 Aspose.Page for .NET 提供了一组强大的工具，在本教程中，我们将逐步引导您完成该过程。

## 先决条件

在深入研究调整大小魔法之前，请确保满足以下先决条件：

-  Aspose.Page for .NET 库：确保您已安装 Aspose.Page for .NET 库。您可以从以下位置下载：[这里](https://releases.aspose.com/page/net/).

- 文档目录：创建一个目录，用于存储输入 EPS 文件和输出调整大小的文件。

现在您已完成所有设置，让我们继续导入必要的命名空间并深入研究分步指南。

## 导入命名空间

在您的 .NET 项目中，首先导入必要的命名空间以使用 Aspose.Page。在文件的开头添加以下代码：

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## 第 1 步：以磅为单位调整大小

让我们首先以磅为单位调整 EPS 图像的大小。点是印刷行业的标准计量单位。

```csharp
public static void ResizeInPoints()
{
    //您的文档目录
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## 第 2 步：以英寸为单位调整大小

现在，让我们以英寸为单位调整 EPS 图像的大小，英寸是图形设计中使用的常用单位。

```csharp
public static void ResizeInInches()
{
    //您的文档目录
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## 第 3 步：以毫米为单位调整大小

现在，让我们以毫米为单位调整 EPS 图像的大小，这是设计和打印中另一个广泛使用的单位。

```csharp
public static void ResizeInMillimeters()
{
    //您的文档目录
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## 第 4 步：以百分比调整大小

最后，让我们使用百分比调整 EPS 图像的大小，从而提供一种灵活的方法来调整图像大小。

```csharp
public static void ResizeInPercents()
{
    //您的文档目录
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

请随意将这些方法集成到您的项目中，您将轻松调整 EPS 图像的大小。尝试不同的单位以获得所需的尺寸。

## 结论

恭喜！您已经掌握了使用 Aspose.Page for .NET 调整 EPS 图像大小的技巧。这个强大的库为操作矢量图形开辟了一个充满可能性的世界。无论您是为印刷媒体还是数字媒体进行设计，Aspose.Page 都能帮助您实现精确且定制的结果。

## 常见问题解答

### Q1：我可以同时调整多个 EPS 图像的大小吗？

A1：是的，您可以循环遍历 EPS 文件的集合，并相应地应用调整大小方法。

### Q2：Aspose.Page 是否兼容其他图像格式？

A2：Aspose.Page 主要关注 PostScript 和 EPS 格式。对于其他图像格式，请考虑使用 Aspose.Imaging。

### Q3：商业项目有什么许可注意事项吗？

 A3：是的，请确保您拥有有效的许可证。访问[这里](https://purchase.aspose.com/buy)了解许可详细信息。

### Q4：我可以在购买前试用Aspose.Page吗？

 A4：当然！您可以获得免费试用[这里](https://releases.aspose.com/).

### Q5：我可以在哪里寻求更多帮助或讨论问题？

 A5：访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)与社区联系并获得帮助。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
