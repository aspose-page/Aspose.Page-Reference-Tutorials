---
title: 与 Aspose.Page Java 轻松集成计量许可证
linktitle: 在 Java 中设置计量许可证
second_title: Aspose.Page Java API
description: 探索 Aspose.Page 与 Java 的无缝集成。轻松设置计量许可证并增强您的文档处理能力。
type: docs
weight: 10
url: /zh/java/license-management/set-metered-license/
---
## 介绍
欢迎阅读我们有关使用 Aspose.Page 在 Java 中设置计量许可证的综合指南。如果您希望增强文档处理能力并确保与 Aspose.Page 无缝集成，那么您来对地方了。在本教程中，我们将引导您完成整个过程，将每个步骤分解为易于理解的块。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
- Java 编程的基础知识。
-  Aspose.Page 库已安装。您可以从以下位置下载：[这里](https://releases.aspose.com/page/java/).
- 计量公钥和私钥，您可以通过您的 Aspose 帐户获取。
## 导入包
让我们首先导入 Java 程序所需的包。确保您已将 Aspose.Page 库集成到您的项目中。
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## 第1步：初始化文档和图像格式
第一步是设置文档并定义所需的图像格式。
```java
//设置计量公钥和私钥
com.aspose.page.Metered metered = new com.aspose.page.Metered();
//访问 setMeteredKey 属性并将公钥和私钥作为参数传递
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
//文档目录的路径。
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## 第 2 步：初始化 PostScript 输入流
在此步骤中，我们初始化 PostScript 输入流以进行处理。
```java
//初始化 PostScript 输入流
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## 第3步：检查文档许可证
在继续之前，验证该文档是否获得适当许可至关重要。
```java
//检查文档是否已获得许可
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## 第四步：初始化选项和图像设备
现在，让我们使用默认参数初始化选项和图像设备。
```java
//使用默认参数初始化选项对象。
ImageSaveOptions options = new ImageSaveOptions();
//使用默认参数初始化 ImageDevice 对象。
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## 步骤 5：将 EPS 文件另存为图像
使用定义的选项和设备将 EPS 文件另存为图像。
```java
//将 EPS 文件另存为图像
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## 第 6 步：获取并保存图像字节
检索图像字节并将其保存到文件中。
```java
//获取图像字节。一页一个字节数组。在我们的例子中，我们有一页。
byte[][] imagesBytes = device.getImagesBytes();
//将图像字节保存到文件
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## 结论
恭喜！您已使用 Aspose.Page 在 Java 中成功设置了计量许可证。本教程提供了分步指南，以确保集成过程顺利进行。
## 常见问题解答
### 问：如何获取计量公钥和私钥？
您可以通过您的 Aspose 帐户获取这些密钥。
### 问：Aspose.Page 库是免费的吗？
 Aspose.Page 提供免费试用版和付费版本。访问[这里](https://releases.aspose.com/)免费试用。
### 问：我可以将 Aspose.Page 用于商业项目吗？
是的，Aspose.Page 提供商业许可证。您可以购买它们[这里](https://purchase.aspose.com/buy).
### 问：在哪里可以找到其他文档？
参考文档[这里](https://reference.aspose.com/page/java/).
### 问：如何获得临时许可证？
可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).