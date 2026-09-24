---
date: 2026-09-24
description: 了解如何使用 Aspose.Page 在 Java 中将 EPS 转换为 PNG，配置 metered license，并高效编写 PNG
  文件的 Java 代码。
keywords:
- aspose page convert eps
- write png file java
- metered license java
- eps to png conversion
lastmod: 2026-09-24
linktitle: 在 Java 中设置 Metered License
og_description: Aspose.Page 在 Java 中使用 metered license 将 EPS 转换为 PNG。本指南逐步展示如何配置许可、渲染
  EPS，以及编写 PNG 文件的 Java 代码。
og_image_alt: Guide showing Aspose.Page Java converting EPS to PNG with metered license
og_title: Aspose.Page 将 EPS 转换为 PNG（Java，metered license）
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  headline: Aspose.Page convert EPS to PNG in Java (metered license)
  type: TechArticle
- description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  name: Aspose.Page convert EPS to PNG in Java (metered license)
  steps:
  - name: initialize document and image format
    text: First, set the metered keys and define the output format (PNG). This establishes
      the foundation for the conversion. The `MeteredLicense` class stores your public
      and private keys, while `ImageSaveOptions` tells Aspose.Page to produce PNG
      output.
  - name: initialize PostScript input stream
    text: Open the EPS file you want to convert. The stream feeds the document into
      Aspose.Page. The `FileInputStream` reads the EPS file from disk, allowing the
      `Document` constructor to parse the PostScript data.
  - name: check document license
    text: Always verify that the metered license was applied correctly before processing.
      The `isLicensed()` method returns `true` only when the supplied keys are valid,
      preventing accidental usage of an unlicensed library.
  - name: initialize options and image device
    text: Create the options object that controls conversion settings and the device
      that will receive the rendered image. `ImageDevice` captures the rasterized
      output in memory, while `ImageSaveOptions` lets you tweak DPI, compression level,
      and color depth.
  - name: save EPS file as image
    text: This is the core **save EPS as PNG** call. The document is rendered into
      the image device using the options we configured. The `document.save(device,
      options)` method performs the rasterization in a single step.
  - name: get and save image bytes
    text: Extract the PNG bytes from the device and write them to a file on disk.
      This step demonstrates how to **write PNG file Java** safely. `Files.write(Paths.get("output.png"),
      device.getImagesBytes()[0])` persists the image without additional libraries.
  type: HowTo
- questions:
  - answer: Log into your Aspose account, navigate to the **Metered License** section,
      and copy the generated public and private keys.
    question: How do I obtain metered public and private keys?
  - answer: Aspose.Page offers a free trial with full functionality; production use
      requires a paid license. Download the trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is the Aspose.Page library free?
  - answer: Yes, a commercial license permits deployment in production environments.
      Purchase a license [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: The full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: Temporary licenses are provided through the Aspose portal [Aspose temporary
      license page](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image conversion
- metered licensing
title: Aspose.Page 将 EPS 转换为 PNG（Java，metered license）
url: /zh/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page 将 EPS 转换为 PNG（Java，计量许可证）

## 介绍
如果您需要在 Java 应用程序中 **将 EPS 保存为 PNG**，并且希望许可证管理简便，那么您来对地方了。本教程将指导您为 Aspose.Page 配置 **计量许可证**，加载 EPS（Encapsulated PostScript）文件，并将其转换为 PNG 图像。完成后，您将了解如何 **高效地将 EPS 渲染为 PNG**，以及如何编写可靠的 **Java 写 PNG 文件** 代码，以在生产环境中稳定运行。

## 快速答案
- **“save EPS as PNG” 是什么意思？** 它将矢量 EPS 文件转换为光栅 PNG 图像，保留透明度并实现无损压缩。  
- **为什么使用计量许可证？** 您只需为处理的页面付费，这对于工作负载变化的情况非常理想。  
- **我需要互联网连接吗？** 不需要，计量密钥在 JVM 本地进行验证。  
- **需要哪个 Java 版本？** 完全支持 Java 8 或更高版本。  
- **设置需要多长时间？** 基本实现大约需要 10 分钟。

## 什么是 “save EPS to PNG”？
将 EPS 保存为 PNG 将矢量 Encapsulated PostScript 文档转换为光栅 PNG 图像，保留透明度并提供无损压缩。当您需要可用于网页的图形、缩略图或可打印预览时，这种转换非常有用，因为它们可以在任何浏览器中显示，而无需 PostScript 解释器。

## 为什么使用 Aspose.Page 将 EPS 渲染为 PNG？
Aspose.Page 提供纯 Java API，能够高保真地将 EPS 文件光栅化，支持超过 50 种输出格式，并提供计量许可证，使您只为实际转换的内容付费。该库可以在不将整个文件加载到内存的情况下处理数百页的文档，在任何支持 JVM 的平台上实现快速、准确的渲染。

## 前提条件
- 基本的 Java 开发经验。  
- 从 [Aspose.Page Java download page](https://releases.aspose.com/page/java/) 下载的 Aspose.Page 库。  
- 来自您的 Aspose 账户的计量公钥和私钥。  

## 导入包
`import` 语句将所需的类引入作用域。请保持此代码块与示例完全一致，以确保代码能够编译。

`java.io` 类处理文件流，而 Aspose.Page 类负责许可证管理、文档加载和图像渲染。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## 如何使用 Aspose.Page Java 将 EPS 保存为 PNG
下面是结合许可证、加载、渲染以及写入最终 PNG 文件的逐步指南。

### 直接答案
加载 EPS 文件，应用计量许可证，配置 `ImageSaveOptions` 为 PNG，渲染文档到 `ImageDevice`，最后将生成的字节数组写入磁盘。此流程仅需几行 Java 代码即可完成 **save EPS as PNG** 工作流。

### 步骤 1：初始化文档和图像格式
首先，设置计量密钥并定义输出格式（PNG）。这为转换奠定基础。

`MeteredLicense` 类保存您的公钥和私钥，而 `ImageSaveOptions` 告诉 Aspose.Page 生成 PNG 输出。

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

### 步骤 2：初始化 PostScript 输入流
打开您想要转换的 EPS 文件。该流将文档输入到 Aspose.Page。

`FileInputStream` 从磁盘读取 EPS 文件，使 `Document` 构造函数能够解析 PostScript 数据。

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### 步骤 3：检查文档许可证
在处理之前，请始终验证计量许可证是否已正确应用。

`isLicensed()` 方法仅在提供的密钥有效时返回 `true`，从而防止意外使用未授权的库。

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### 步骤 4：初始化选项和图像设备
创建控制转换设置的选项对象以及接收渲染图像的设备。

`ImageDevice` 在内存中捕获光栅化输出，而 `ImageSaveOptions` 允许您调整 DPI、压缩级别和颜色深度。

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### 步骤 5：将 EPS 文件保存为图像
这就是核心的 **save EPS as PNG** 调用。文档使用我们配置的选项渲染到图像设备中。

`document.save(device, options)` 方法一次性完成光栅化。

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### 步骤 6：获取并保存图像字节
从设备中提取 PNG 字节并写入磁盘文件。此步骤演示了如何安全地 **write PNG file Java**。

`Files.write(Paths.get("output.png"), device.getImagesBytes()[0])` 在不使用额外库的情况下持久化图像。

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

## 常见问题及解决方案
| 问题 | 产生原因 | 解决方案 |
|-------|----------------|-----|
| **License not recognized** | 密钥不正确，或在文档处理后才调用 `setMeteredKey`。 | 仔细检查公钥/私钥字符串，并确保 `setMeteredKey` 在任何 Aspose.Page 调用之前运行。 |
| **Output file is empty** | `device.getImagesBytes()` 返回 `null`，因为 EPS 文件无法解析。 | 确认 EPS 文件有效，并且 `ImageSaveOptions` 指定了非零的画布大小。 |
| **OutOfMemoryError on large EPS** | 渲染大型矢量文件会消耗大量堆内存。 | 一次处理一页，或增加 JVM 堆内存（`-Xmx2g`）。 |

## 常见问题

**Q: 如何获取计量公钥和私钥？**  
A: 登录您的 Aspose 账户，进入 **Metered License** 部分，复制生成的公钥和私钥。

**Q: Aspose.Page 库免费吗？**  
A: Aspose.Page 提供功能完整的免费试用版；生产使用需要付费许可证。下载试用版请访问 [Aspose trial download page](https://releases.aspose.com/)。

**Q: 我可以在商业项目中使用 Aspose.Page 吗？**  
A: 可以，商业许可证允许在生产环境中部署。购买许可证请访问 [Aspose purchase page](https://purchase.aspose.com/buy)。

**Q: 我在哪里可以找到更多文档？**  
A: 完整的 API 参考可在 [Aspose.Page Java API reference](https://reference.aspose.com/page/java/) 查看。

**Q: 我如何获取用于评估的临时许可证？**  
A: 临时许可证可通过 Aspose 门户获取，详见 [Aspose temporary license page](https://purchase.aspose.com/temporary-license/)。

**Q: 如果需要转换多页 EPS 文件怎么办？**  
A: 使用 `device.getImagesBytes()` 循环遍历每一页，并将每个字节数组写入单独的 PNG 文件。

**Q: 我可以更改 PNG 的质量或颜色深度吗？**  
A: 可以，在调用 `document.save(...)` 之前配置 `ImageSaveOptions`（例如 `options.setCompressionLevel(9)`）。

---

**Last Updated:** 2026-09-24  
**Tested with:** Aspose.Page 24.12 for Java (latest)  
**Author:** Aspose

## 相关教程

- [如何为 Aspose.Page Java API 设置许可证 – 许可证管理](/page/java/license-management/)
- [使用 Aspose.Page Java API 将 PS 转换为 PNG](/page/java/postscript-conversion/to-image/)
- [使用 Aspose.Page 调整 EPS 大小 – Java EPS 操作](/page/java/manipulation-eps/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}