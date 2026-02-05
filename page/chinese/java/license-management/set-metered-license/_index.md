---
date: 2026-02-05
description: 学习如何在配置计量授权的情况下使用 Aspose.Page for Java 将 EPS 保存为 PNG。一步一步的指南，附完整代码示例。
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: 使用 Aspose.Page Java 将 EPS 保存为 PNG（计量许可证）
url: /zh/java/license-management/set-metered-license/
weight: 10
---

 note "Last Updated:" etc.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page Java（计量许可证）将 EPS 保存为 PNG

## 介绍
如果您需要在 Java 应用程序中 **save EPS as PNG**，并且想要一种免除许可证管理麻烦的方式，那么您来对地方了。本教程将手把手教您为 Aspose.Page 配置计量许可证、加载 PostScript（EPS）文件并将其转换为 PNG 图像——所有步骤都简明易懂，您可以立即跟随操作。完成后，您还将了解如何高效 **render EPS to PNG**，以及在生产环境中可用的 **write PNG file Java** 代码。

## 快速答复
- **“save EPS as PNG” 是什么意思？** 它将矢量 EPS 文件转换为光栅 PNG 图像。  
- **为什么使用计量许可证？** 只需为实际处理的页面付费，适合工作负载波动的场景。  
- **需要网络连接吗？** 不需要，计量密钥在本地验证。  
- **需要哪个 Java 版本？** Java 8 或更高。  
- **设置大约需要多长时间？** 基本实现约 10 分钟即可完成。  

## 什么是“将 EPS 保存为 PNG”？
将 EPS 保存为 PNG 将可伸缩的封装式 PostScript 文档转换为一种被广泛支持的位图格式。PNG 保留透明度并提供无损压缩，非常适合网页图形、缩略图和打印预览。

## 为什么使用 Aspose.Page 将 EPS 渲染为 PNG？
- **Pure Java API** – 无需本地依赖，可在任何支持 JVM 的环境中运行。  
- **高保真渲染** – 矢量图形被准确光栅化，保持线条质量。  
- **计量许可** – 只为实际转换的内容付费，成本可预测。  
- **多种输出选项** – 除 PNG 外，还可生成 JPEG、TIFF 等，满足不同项目需求。

## 先决条件
在开始之前，请确保您具备：

- 基本的 Java 编程知识。  
- 已安装 Aspose.Page 库 – 从 [here](https://releases.aspose.com/page/java/) 下载。  
- 计量公钥和私钥，可通过您的 Aspose 账户获取。

## 导入包
首先，导入我们需要的类。请保持导入块与示例完全一致，以确保代码能够编译。

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

### 步骤 1：初始化文档和图像格式
在此我们设置计量密钥并定义输出格式（PNG），这是 **save EPS as PNG** 操作的基础。

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
打开要转换的 EPS 文件。该流将文档传递给 Aspose.Page。

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### 步骤 3：检查文档许可证
在处理之前务必确认计量许可证已正确应用。

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### 步骤 4：初始化选项和图像设备
创建控制转换设置的 options 对象，以及接收渲染后图像的设备。

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### 步骤 5：将 EPS 文件保存为图像
这就是核心的 **save EPS as PNG** 调用。文档使用我们配置的 options 渲染到图像设备中。

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
| 问题 | 为什么会出现 | 解决办法 |
|-------|----------------|-----|
| **License not recognized** | 密钥不正确或顺序错误。 | 仔细检查公钥/私钥字符串，并确保在任何文档处理之前调用 `setMeteredKey`。 |
| **Output file is empty** | `device.getImagesBytes()` 返回 `null`。 | 确认 EPS 文件有效，且 `ImageSaveOptions` 未设置为零尺寸画布。 |
| **OutOfMemoryError on large EPS** | 渲染大型矢量文件会消耗大量内存。 | 按页处理或增大 JVM 堆内存 (`-Xmx2g`)。 |

## 常见问题

**Q: 如何获取计量公钥和私钥？**  
A: 可通过您的 Aspose 账户获取这些密钥。

**Q: Aspose.Page 库是免费的吗？**  
A: Aspose.Page 提供免费试用版和付费版。访问 [here](https://releases.aspose.com/) 获取免费试用。

**Q: 我可以在商业项目中使用 Aspose.Page 吗？**  
A: 可以，Aspose.Page 提供商业许可证。您可在 [here](https://purchase.aspose.com/buy) 购买。

**Q: 哪里可以找到更多文档？**  
A: 请参阅文档 [here](https://reference.aspose.com/page/java/)。

**Q: 如何获取临时许可证？**  
A: 临时许可证可在 [here](https://purchase.aspose.com/temporary-license/) 获取。

**Q: 如果需要转换多页 EPS 文件怎么办？**  
A: 使用 `device.getImagesBytes()` 循环遍历每一页，并将每个字节数组写入单独的 PNG 文件。

**Q: 能否更改 PNG 的质量或色深？**  
A: 可以，在调用 `document.save(...)` 前配置 `ImageSaveOptions`（例如 `options.setCompressionLevel(...)`）。

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Page 24.12 for Java  
**Author:** Aspose  

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Page 24.12 for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}