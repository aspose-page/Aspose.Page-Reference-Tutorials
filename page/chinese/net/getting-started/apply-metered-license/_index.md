---
title: 使用 Aspose.Page for .NET 应用计量许可证
linktitle: 申请计量许可证
second_title: Aspose.Page .NET API
description: 通过此有关应用计量许可证的分步指南，探索 Aspose.Page for .NET 的无缝集成。轻松优化文档处理。
weight: 10
url: /zh/net/getting-started/apply-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page for .NET 应用计量许可证

## 介绍

通过应用计量许可证来释放 Aspose.Page for .NET 的全部潜力。本教程将指导您完成设置和应用计量许可证的过程，确保顺利和优化地使用这个强大的 .NET 库。

## 先决条件

在深入了解这些步骤之前，请确保满足以下先决条件：

- 适用于 .NET 许可证的有效 Aspose.Page：您可以从以下位置获取它：[购买.aspose.com](https://purchase.aspose.com/buy).
-  Aspose.Page库安装：参考[文档](https://reference.aspose.com/page/net/)获取安装说明。
- .NET 开发环境：确保您的计算机上设置了有效的 .NET 环境。

## 导入命名空间

在您的 .NET 项目中，导入必要的命名空间以访问 Aspose.Page 功能：

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

## 第 1 步：设置计量公钥和私钥

初始化`Aspose.Page.Metered`类并设置计量的公钥和私钥。代替`<type public key here>`和`<type private key here>`用你的实际钥匙。

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## 步骤 2：加载 EPS 文件并创建文档

指定 EPS 文件的路径并创建一个流来读取其内容。然后，创建一个实例`PsDocument`来自流的类。

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## 步骤 3：将 EPS 转换为 PNG 图像

创建一个`ImageDevice`用于将 EPS 文件转换为 PNG 图像。使用以下命令将 EPS 文件另存为图像`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## 第 4 步：检索图像字节

获取图像字节，其中每个字节数组代表一页。在本例中，我们有一页。

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## 第 5 步：将图像字节保存到文件

将图像字节保存到文件中，确保从 EPS 成功转换为 PNG。

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## 第 6 步：验证计量许可证

目视检查计量许可证是否已成功应用。如果生成的图像不包含红色评估消息，则表示已应用计量许可证，没有任何问题。

现在您已准备好通过计量许可证来利用 Aspose.Page for .NET 的全部功能！

## 结论

本分步指南为您提供了使用 Aspose.Page for .NET 无缝应用计量许可证的知识。增强您的文档处理能力并探索这个强大的库提供的大量功能。

## 常见问题解答

### 问题 1：如何获得 Aspose.Page for .NET 的计量许可证？

 A1：参观[购买.aspose.com](https://purchase.aspose.com/buy)获得有效的许可证。

### Q2：在哪里可以找到 Aspose.Page for .NET 的文档？

 A2：参考[Aspose.Page .NET](https://reference.aspose.com/page/net/)以获得全面的文档。

### Q3：有 Aspose.Page 讨论和支持的论坛吗？

 A3：是的，请访问[论坛](https://forum.aspose.com/c/page/39)与社区互动并寻求帮助。

### Q4：我可以在购买前试用 Aspose.Page for .NET 吗？

 A4：当然！访问免费试用版[这里](https://releases.aspose.com/).

### Q5：如何获得 Aspose.Page for .NET 的临时许可证？

A5：参观[临时牌照/](https://purchase.aspose.com/temporary-license/)获得临时许可证。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
