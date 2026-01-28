---
date: 2026-01-28
description: 了解如何使用 Aspose.Page for .NET 将 EPS 转换为 PNG，并应用计量许可证，实现无缝文档处理。
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page for .NET 将 EPS 转换为 PNG 并应用计量许可证
url: /zh/net/getting-started/apply-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将 EPS 转换为 PNG 并使用 Aspose.Page for .NET 应用计量许可证

## 介绍

通过 **将 EPS 转换为 PNG** 并应用计量许可证，充分发挥 Aspose.Page for .NET 的潜力。本教程将逐步指导您完成每一步——从加载 EPS 文件到将其保存为 PNG 图像——帮助您高效处理文档且不出现评估水印。

## 快速答案
- **本教程涵盖什么内容？** 将 EPS 文件转换为 PNG 图像并使用 Aspose.Page for .NET 应用计量许可证。  
- **我需要许可证吗？** 是的，生产使用需要计量许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **实现大约需要多长时间？** 基本转换大约需要 10–15 分钟。  
- **我可以在 Linux/macOS 上运行吗？** 当然可以——Aspose.Page 是跨平台的。

## 什么是“将 EPS 转换为 PNG”？
将 EPS 转换为 PNG 意味着将基于矢量的封装式 PostScript（EPS）文件光栅化为位图 PNG 图像。当您需要在网页、报告或不支持 EPS 的 UI 组件中显示或嵌入图形时，这非常有用。

## 为什么在 EPS 到图像转换中使用计量许可证？
计量许可证让您仅为实际处理的页面付费，非常适合工作负载量不固定的情况。它还能去除使用免费试用时出现的红色评估横幅，确保为最终用户提供干净的输出。

## 前提条件

在开始操作之前，请确保具备以下前提条件：

- 有效的 Aspose.Page for .NET 许可证：可从 [purchase.aspose.com](https://purchase.aspose.com/buy) 获取。  
- 已安装 Aspose.Page 库：请参阅 [documentation](https://reference.aspose.com/page/net/) 获取安装说明。  
- .NET 开发环境：确保您的机器上已配置可用的 .NET 环境。

## 导入命名空间

在 .NET 项目中，导入必要的命名空间以访问 Aspose.Page 功能：

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## 如何使用计量许可证将 EPS 转换为 PNG？

以下是一步步的指南，涵盖您需要了解的全部内容。

### 步骤 1：设置计量公钥和私钥

初始化 `Aspose.Page.Metered` 类并设置计量公钥和私钥。将 `<type public key here>` 和 `<type private key here>` 替换为您的实际密钥。

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### 步骤 2：加载 EPS 文件并创建文档

指定 EPS 文件的路径并创建流以读取其内容。随后，从流创建 `PsDocument` 类的实例。

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### 步骤 3：将 EPS 转换为 PNG 图像

创建用于将 EPS 文件转换为 PNG 图像的 `ImageDevice`。使用 `ImageSaveOptions` 将 EPS 文件保存为图像。

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### 步骤 4：获取图像字节

获取图像字节，每个字节数组代表一页。本例中只有一页。

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### 步骤 5：将图像字节保存到文件

将图像字节保存到文件，以确保 EPS 成功转换为 PNG。

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### 步骤 6：验证计量许可证

目视检查计量许可证是否成功应用。如果生成的图像不包含红色评估信息，则说明计量许可证已正确应用且没有问题。

现在，您已准备好使用计量许可证充分发挥 Aspose.Page for .NET 的全部功能！

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|-------|-------|-----|
| 仍然出现红色评估横幅 | 许可证未设置或密钥错误 | 再次检查公钥/私钥，并确保在任何文档处理之前调用 `SetMeteredKey` |
| 未创建输出文件 | `dataDir` 路径不正确或文件权限不足 | 确认目录存在且应用具有写入权限 |
| 未保存多页 | 仅写入了第一页 | 遍历 `imagesBytes`，将每个数组写入单独的 PNG 文件 |

## 常见问答

**Q: 我可以在 CI/CD 流水线中使用计量许可证吗？**  
A: 可以，您可以将密钥安全存储（例如放在环境变量中），并在构建过程中调用 `SetMeteredKey`。

**Q: Aspose.Page 在转换为 PNG 时是否支持颜色配置文件保留？**  
A: PNG 输出保留原始颜色信息，但您可以通过 `ImageSaveOptions` 进一步自定义。

**Q: 是否可以将 EPS 转换为其他光栅格式（JPEG、BMP）？**  
A: 完全可以——只需将 `ImageSaveOptions` 更改为所需的格式。

**Q: 支持的最大 EPS 文件大小是多少？**  
A: Aspose.Page 能处理大文件，但内存消耗随图像分辨率增长。对于非常大的文档，建议逐页处理。

**Q: 如何以编程方式获取 EPS 文件的页数？**  
A: 在加载 `PsDocument` 后使用 `document.PagesCount`。

## 常见问答

### Q1: 如何获取 Aspose.Page for .NET 的计量许可证？

A1: 访问 [purchase.aspose.com](https://purchase.aspose.com/buy) 以获取有效许可证。

### Q2: 在哪里可以找到 Aspose.Page for .NET 的文档？

A2: 请参阅 [Aspose.Page .NET](https://reference.aspose.com/page/net/) 获取完整文档。

### Q3: 是否有 Aspose.Page 讨论和支持的论坛？

A3: 有，访问 [forum](https://forum.aspose.com/c/page/39) 与社区交流并寻求帮助。

### Q4: 在购买前我可以试用 Aspose.Page for .NET 吗？

A4: 当然！在 [here](https://releases.aspose.com/) 获取免费试用。

### Q5: 如何获取 Aspose.Page for .NET 的临时许可证？

A5: 访问 [temporary license/](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

---

**最后更新：** 2026-01-28  
**测试版本：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}