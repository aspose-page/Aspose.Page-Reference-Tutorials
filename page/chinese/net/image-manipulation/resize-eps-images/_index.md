---
date: 2026-03-03
description: 学习如何在 .NET 中使用 Aspose.Page 调整 EPS 图像的大小——一步步指南，教您使用点、英寸、毫米或百分比来调整 EPS
  大小。
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: 如何使用 Aspose.Page for .NET 调整 EPS 图像大小
url: /zh/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Page for .NET 调整 EPS 图像大小

## 介绍

您是否在寻找 **如何调整 EPS** 图像大小的无缝方案？本教程将为您提供在点、英寸、毫米和百分比等多种单位下轻松操作 EPS 图像尺寸的完整指南。Aspose.Page for .NET 提供了一套强大的工具，在本教程中，我们将一步步带您完成整个过程。

## 快速答案
- **哪个库负责 EPS 调整大小？** Aspose.Page for .NET  
- **支持哪些单位？** 点（Points）、英寸（Inches）、毫米（Millimeters）和百分比（Percents）  
- **生产环境需要许可证吗？** 是的 – 需要商业许可证  
- **可以一次性调整多个文件吗？** 当然可以 – 只需遍历文件即可  
- **支持 .NET Core 吗？** 支持，API 可在 .NET Framework 和 .NET Core 上运行  

## 什么是 EPS 调整大小？
封装的 PostScript（EPS）是一种基于矢量的图形格式，常用于印刷和设计工作流。调整 EPS 文件的大小会改变其边界框，而不会对图形进行光栅化，从而在任何比例下都能保持清晰度。

## 为什么要调整 EPS 图像大小？
- **保持印刷质量：** 矢量缩放可保持边缘锐利。  
- **符合布局需求：** 调整尺寸以匹配页面或画布大小。  
- **自动化批处理任务：** 以编程方式在几秒钟内调整数十个文件的大小。  

## 前置条件

在开始调整大小的魔法之前，请确保已满足以下前置条件：

- Aspose.Page for .NET 库：确保已安装 Aspose.Page for .NET 库。您可以从 [here](https://releases.aspose.com/page/net/) 下载。  

- 文档目录：创建一个目录，用于存放输入的 EPS 文件和输出的调整后文件。  

准备好以上内容后，接下来导入必要的命名空间并进入逐步指南。

## 导入命名空间

在 .NET 项目中，首先导入使用 Aspose.Page 所需的命名空间。在文件开头添加以下代码：

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

## 如何使用点（Points）调整 EPS 大小

点是印刷行业的标准计量单位。下面的示例将原始宽度和高度均放大两倍。

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
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

## 如何使用英寸（Inches）调整 EPS 大小

英寸是平面设计师在准备印刷资产时常用的单位。

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
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

## 如何使用毫米（Millimeters）调整 EPS 大小

毫米在使用公制系统的地区非常常见。

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
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

## 如何使用百分比（Percentages）调整 EPS 大小

基于百分比的调整让您可以相对于原始尺寸进行缩放。

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
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

将这些方法集成到您的项目中，即可轻松完成 EPS 图像的大小调整。尝试不同的单位，以获得所需的尺寸。

## 常见问题及解决方案
- **文件未找到：** 请确认 `dataDir` 指向正确的文件夹，并且 `input.eps` 已存在。  
- **尺寸异常：** 请记住 `Units.Percents` 需要传入类似 150 这样的数值，表示原始大小的 150%。  
- **许可证异常：** 如果出现许可证错误，请在创建 `PsDocument` 之前加载有效的 Aspose.Page 许可证文件。  

## 结论

恭喜您！您已经掌握了 **如何使用 Aspose.Page for .NET 调整 EPS** 图像大小的技巧。这个强大的库为矢量图形的操作打开了无限可能。无论是为印刷还是数字媒体设计，Aspose.Page 都能帮助您实现精确且可定制的结果。

## FAQ's

### Q1: 能否一次性调整多个 EPS 图像？

A1: 可以，您可以遍历 EPS 文件集合，依次调用相应的调整大小方法。

### Q2: Aspose.Page 是否兼容其他图像格式？

A2: Aspose.Page 主要聚焦于 PostScript 和 EPS 格式。对于其他图像格式，建议使用 Aspose.Imaging。

### Q3: 商业项目的许可证有哪些注意事项？

A3: 是的，请确保拥有有效的许可证。访问 [here](https://purchase.aspose.com/buy) 获取许可证详情。

### Q4: 可以在购买前试用 Aspose.Page 吗？

A4: 当然！您可以在 [here](https://releases.aspose.com/) 获取免费试用。

### Q5: 哪里可以获取更多帮助或讨论问题？

A5: 访问 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 与社区交流并获取支持。

## 常见问答

**Q: 这段代码在 .NET Core 6 上能运行吗？**  
A: 能。该 API 兼容 .NET Framework 4.5+、.NET Core 3.1+、.NET 5+ 和 .NET 6+。

**Q: 如何保留原始的颜色配置文件？**  
A: `ResizeEps` 方法不会更改颜色数据，只会修改边界框。

**Q: 能否在不将整个文件加载到内存的情况下调整 EPS 大小？**  
A: 如示例所示使用流可以保持低内存占用，文档会在飞行中处理。

**Q: 可以链式调用多个调整大小操作吗？**  
A: 完全可以。对同一个 `PsDocument` 实例依次调用 `ResizeEps` 即可。

**Q: EPS 中嵌入的图像会怎样？**  
A: 它们会随矢量内容按比例缩放，保持质量。

---

**最后更新：** 2026-03-03  
**测试环境：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}