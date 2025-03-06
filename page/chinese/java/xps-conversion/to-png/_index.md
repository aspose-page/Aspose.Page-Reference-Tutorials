---
title: 在 Java 中将 XPS 转换为 PNG
linktitle: 在 Java 中将 XPS 转换为 PNG
second_title: Aspose.Page Java API
description: 使用 Aspose.Page 在 Java 中轻松将 XPS 转换为 PNG。通过这种可靠且对开发人员友好的解决方案简化文档任务。
weight: 13
url: /zh/java/xps-conversion/to-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中将 XPS 转换为 PNG

## 介绍
在软件开发的动态世界中，经常需要将 XPS（XML 纸张规范）文档转换为 PNG（便携式网络图形）图像。为了用 Java 无缝地完成这项任务，Aspose.Page 提供了一个强大的解决方案。在本教程中，我们将逐步介绍使用 Aspose.Page for Java 将 XPS 转换为 PNG 的过程。
## 先决条件
在我们深入学习本教程之前，请确保您已设置以下先决条件：
1. Java 开发工具包 (JDK)：确保您的系统上安装了 JDK。
2.  Aspose.Page for Java：下载并安装 Aspose.Page 库。你可以找到下载链接[这里](https://releases.aspose.com/page/java/).
3. 集成开发环境 (IDE)：选择与 Java 兼容的 IDE，例如 IntelliJ IDEA 或 Eclipse。
## 导入包
在您的 Java 项目中，导入必要的包以利用 Aspose.Page 功能。在 Java 文件的开头添加以下导入语句：
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## 第1步：设置文档目录
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
```
## 第 2 步：加载 XPS 文档
```java
//加载XPS文档
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## 第 3 步：初始化选项
```java
//使用必要的参数初始化选项对象。
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## 第四步：创建渲染设备
```java
//创建PDF格式的渲染设备
ImageDevice device = new ImageDevice();
```
## 第 5 步：保存并迭代
```java
//使用选项和设备将 XPS 文档保存为 PNG
document.save(device, options);
//迭代文档分区（固定文档，用 XPS 术语来说）
for (int i = 0; i < device.getResult().length; i++) {
    //遍历分区页
    for (int j = 0; j < device.getResult()[i].length; j++) {
        //初始化图像输出流
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        //写入图像
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //关闭流
        imageStream.close();
    }
}
```
通过执行以下步骤，您可以使用 Aspose.Page for Java 轻松将 XPS 文档转换为 PNG 图像。
## 结论
总之，Aspose.Page for Java 简化了 XPS 到 PNG 的转换过程，为开发人员提供了可靠且高效的工具。将此库合并到您的 Java 项目中以简化文档操作任务。
## 常见问题解答
### 我可以在商业项目中使用 Aspose.Page for Java 吗？
是的，Aspose.Page 是一个商业产品。您可以找到许可信息[这里](https://purchase.aspose.com/buy).
### 有免费试用吗？
是的，您可以探索免费试用[这里](https://releases.aspose.com/).
### 在哪里可以找到 Aspose.Page for Java 的文档？
提供全面的文档[这里](https://reference.aspose.com/page/java/).
### 如何获得用于测试目的的临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 是否有用于 Aspose.Page 讨论的社区论坛？
是的，访问社区论坛[这里](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
