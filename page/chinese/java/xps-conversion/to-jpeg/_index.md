---
date: 2025-12-23
description: 学习如何在 Java 中将 XPS 转换为 JPEG，并了解如何使用 Aspose.Page 高效地转换 XPS 文件。一本提供逐步说明的全面指南，帮助实现无缝集成。
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: 如何在 Java 中将 XPS 转换为 JPEG
url: /zh/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中将 XPS 转换为 JPEG

## 介绍
在本教程中，**您将学习如何使用强大的 Aspose.Page for Java 库将 XPS 转换为 JPEG**。当您需要在 Web 或桌面应用程序中显示、预览或进一步处理文档页面时，将 XPS 文件转换为图像格式是常见需求。我们将逐步演示每一步，解释每行代码的意义，并提供实用技巧，让您能够自信地将转换逻辑集成到自己的项目中。

## 快速答案
- **哪个库负责转换？** Aspose.Page for Java  
- **我可以选择特定页面吗？** 可以 – 在 `JpegSaveOptions` 中使用 `setPageNumbers`  
- **我可以控制哪些图像质量参数？** 平滑模式、分辨率和 JPEG 质量设置  
- **生产环境需要许可证吗？** 是的，需要商业许可证（提供免费试用）  
- **代码兼容 Java 8 吗？** 完全兼容 – API 支持 Java 8 及更高版本  

## XPS 是什么以及为何将其转换为 JPEG？
XPS（XML Paper Specification）是一种固定布局文档格式，类似于 PDF。将 XPS 转换为 JPEG 在需要缩略图、电子邮件附件或与仅接受图像文件的系统集成时非常有用。JPEG 在视觉质量和文件大小之间提供了良好的平衡，适合基于 Web 的预览。

## 前置条件
在深入代码之前，请确保具备以下条件：

- **Java 开发环境** – 已安装并配置 JDK 8 或更高版本。  
- **Aspose.Page for Java** – 从官方站点[此处](https://releases.aspose.com/page/java/)下载最新库。  
- **示例 XPS 文档** – 您想转换为 JPEG 图像的 XPS 文件。  

## 导入包
在 Java 源文件中导入必要的类：

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## 步骤 1：初始化路径并加载 XPS 文档
设置包含源 XPS 文件的目录，并创建 `XpsDocument` 实例：

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **专业提示：** 使用 `java.nio.file` 中的 `Paths.get()` 进行跨平台路径处理。

## 步骤 2：配置 JPEG 保存选项
定义 JPEG 图像的渲染方式——分辨率、平滑以及要导出的页面：

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` 生成适合打印的高分辨率输出。  
- `setPageNumbers` 让您仅选择所需页面，节省时间和内存。  

## 步骤 3：创建渲染设备
`ImageDevice` 捕获渲染后的页面为字节数组：

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## 步骤 4：将 XPS 文档渲染为 JPEG
调用 `save` 方法，传入设备和已配置的选项：

```java
document.save(device, options);
```

此时 `device` 持有一个二维数组，其中每个元素代表一个 JPEG 编码的页面。

## 步骤 5：遍历结果并写入文件
循环遍历渲染的页面，并将每个字节数组写入单独的 JPEG 文件：

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

每个文件将命名为 `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg`，便于识别源文档和页码。

## 常见问题与故障排除
| 症状 | 可能原因 | 解决方案 |
|------|----------|----------|
| **空白 JPEG 文件** | 输出流未正确刷新或关闭 | 确保在内部循环中调用 `imageStream.close()`（如示例所示）。 |
| **大 XPS 文件导致内存不足错误** | 一次渲染所有页面会消耗过多内存 | 将页面分批处理或增加 JVM 堆内存 (`-Xmx`)。 |
| **缺失页面** | `setPageNumbers` 未包含所需页面 | 确认页面编号数组与实际 XPS 页面索引（从 1 开始）匹配。 |

## 常见问答

### 问：Aspose.Page 适用于商业项目吗？
答：是的，Aspose.Page 是商业产品，提供多种授权选项。详情请查看[此处](https://purchase.aspose.com/buy)。

### 问：我可以在购买前试用 Aspose.Page 吗？
答：可以，您可以在[此处](https://releases.aspose.com/)获取免费试用。

### 问：在哪里可以找到 Aspose.Page 文档？
答：文档可在[此处](https://reference.aspose.com/page/java/)获取。

### 问：如何获取 Aspose.Page 支持？
答：请访问[Aspose.Page 论坛](https://forum.aspose.com/c/page/39)获取社区支持。

### 问：测试时需要临时许可证吗？
答：是的，您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

## 结论
您已经掌握了使用 Aspose.Page for Java **将 XPS 转换为 JPEG** 的方法。通过本分步指南，您可以将此转换流程集成到任何 Java 应用程序中——无论是桌面工具、Web 服务还是批处理实用程序。欢迎尝试不同的分辨率、页面选择和图像格式，以满足项目需求。

---

**最后更新：** 2025-12-23  
**测试环境：** Aspose.Page 24.11 for Java（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}