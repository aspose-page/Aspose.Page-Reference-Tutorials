---
date: 2025-12-03
description: 了解如何在配置计量许可证的情况下使用 Aspose.Page for Java 将 EPS 保存为 PNG。一步一步的指南，附完整代码示例。
language: zh
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: 使用 Aspose.Page Java 将 EPS 保存为 PNG（计量许可）
url: /java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page Java（计量许可证）将 EPS 保存为 PNG

## Introduction
如果您需要在 Java 应用程序中 **将 EPS 保存为 PNG**，并且想要一种免除许可证管理麻烦的方式，您来对地方了。本教程将指导您为 Aspose.Page 配置计量许可证，加载 PostScript（EPS）文件，并将其转换为 PNG 图像——所有步骤都简明易懂，您可以立即跟随操作。

## Quick Answers
- **What does “save EPS as PNG” mean?** **“将 EPS 保存为 PNG” 是什么意思？** 它将矢量 EPS 文件转换为栅格 PNG 图像。  
- **Why use a metered license?** **为什么使用计量许可证？** 它让您只为处理的页面付费，非常适合工作负载波动的情况。  
- **Do I need an internet connection?** **需要互联网连接吗？** 不需要，计量密钥在本地验证。  
- **Which Java version is required?** **需要哪个 Java 版本？** Java 8 或更高。  
- **How long does the setup take?** **设置大约需要多长时间？** 基本实现约 10 分钟。

## What is “save EPS as PNG”?
将 EPS 保存为 PNG 是指将可伸缩的 Encapsulated PostScript 文档转换为广泛支持的位图格式。PNG 保留透明度并提供无损压缩，非常适合网页图形、缩略图和打印预览。

## Why use Aspose.Page for this task?
- **Pure Java API** – 无本地依赖。  
- **High fidelity** – 矢量图形渲染准确。  
- **Metered licensing** – 您只为实际转换的内容付费。  
- **Support for multiple output formats** – 支持多种输出格式 – PNG、JPEG、TIFF 等。

## Prerequisites
在开始之前，请确保您具备：

- 基本的 Java 编程知识。  
- 已安装 Aspose.Page 库 – 从 [here](https://releases.aspose.com/page/java/) 下载。  
- 计量公钥和私钥，可通过您的 Aspose 账户获取。

## Import Packages
首先，导入我们需要的类。请保持导入块与示例完全一致，以确保代码能够编译。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Step 1: Initialize Document and Image Format
在这里我们设置计量密钥并定义输出格式（PNG）。这是 **将 EPS 保存为 PNG** 操作的基础。

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

## Step 2: Initialize PostScript Input Stream
打开您想要转换的 EPS 文件。该流将文档输入到 Aspose.Page。

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Step 3: Check Document License
在处理之前，请始终验证计量许可证是否已正确应用。

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Step 4: Initialize Options and Image Device
创建控制转换设置的 options 对象以及接收渲染图像的设备。

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Step 5: Save EPS File as Image
这就是核心的 **将 EPS 保存为 PNG** 调用。文档使用我们配置的选项渲染到图像设备中。

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Step 6: Get and Save Image Bytes
从设备中提取 PNG 字节并将其写入磁盘文件。

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Common Issues and Solutions
| 问题 | 产生原因 | 解决方案 |
|-------|----------------|-----|
| **License not recognized** | 密钥不正确或顺序错误。 | 仔细检查公钥/私钥字符串，并确保在任何文档处理之前调用 `setMeteredKey`。 |
| **Output file is empty** | `device.getImagesBytes()` 返回 `null`。 | 验证 EPS 文件有效且 `ImageSaveOptions` 未设置为零尺寸画布。 |
| **OutOfMemoryError on large EPS** | 渲染大型矢量文件会消耗大量内存。 | 一次处理一页，或增加 JVM 堆内存（`-Xmx2g`）。 |

## Frequently Asked Questions

**Q: How do I obtain metered public and private keys?**  
A: You can obtain these keys through your Aspose account.

**Q: Is the Aspose.Page library free?**  
A: Aspose.Page offers both free trial and paid versions. Visit [here](https://releases.aspose.com/) for a free trial.

**Q: Can I use Aspose.Page for commercial projects?**  
A: Yes, Aspose.Page offers commercial licenses. You can purchase them [here](https://purchase.aspose.com/buy).

**Q: Where can I find additional documentation?**  
A: Refer to the documentation [here](https://reference.aspose.com/page/java/).

**Q: How can I get temporary licenses?**  
A: Temporary licenses can be obtained [here](https://purchase.aspose.com/temporary-license/).

---

**最后更新:** 2025-12-03  
**测试环境:** Aspose.Page 24.12 for Java  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
