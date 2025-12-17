---
date: 2025-12-17
description: 学习如何在 Java PostScript 中使用 Aspose.Page 添加 Unicode 文本——一步步轻松添加 Unicode
  字符串的指南。
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: How to Add Unicode Text in Java PostScript with Aspose.Page
url: /zh/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中使用 Aspose.Page 添加 Unicode 文本

## 介绍
如果您想了解 **如何向** 基于 Java 的 PostScript（或 XPS）工作流 **添加 Unicode** 字符，您来对地方了。在本教程中，我们将逐步演示使用 Aspose.Page for Java 库嵌入 Unicode 字符串的确切步骤。完成本指南后，您将能够将任何语言特定的文本——阿拉伯语、中文、表情符号，随您喜欢——直接插入到 PostScript 输出中。

## 快速答案
- **需要的库是什么？** Aspose.Page for Java  
- **我可以添加从右到左的脚本吗？** 是的，按代码中所示设置 Bidi 级别  
- **开发需要许可证吗？** 免费试用可用于测试；生产环境需要商业许可证  
- **哪个 IDE 最合适？** 任意 Java IDE（IntelliJ IDEA、Eclipse、NetBeans）  
- **代码是否跨平台？** 绝对可以——可在 Windows、macOS 或 Linux 上运行  

## 在 PostScript 中“如何添加 Unicode”是什么意思？
在 PostScript 的上下文中，“如何添加 Unicode”意味着插入超出基本 ASCII 范围的代码点字符。Aspose.Page 抽象了底层编码细节，让您专注于文本内容及其视觉布局。

## 为什么使用 Aspose.Page 来处理 Unicode 文本？
- **完整的 Unicode 支持** – 处理复杂脚本、连字以及从右到左的语言。  
- **无外部依赖** – 无需手动管理字体文件；API 可使用系统字体。  
- **简洁的 API** – 几个方法调用即可渲染多语言文本。  

## 前置条件
在开始之前，请确保以下项目已准备好：

1. **Java 开发工具包 (JDK)** – 任意近期版本（8 或更高）。  
2. **Aspose.Page for Java** – 从[下载链接](https://releases.aspose.com/page/java/)下载并安装库。  
3. **您选择的 IDE** – IntelliJ IDEA、Eclipse 或其他您偏好的 Java IDE。  

## 导入包
将所需的 Aspose.Page 类添加到您的 Java 源文件中：

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## 步骤 1：设置项目
创建一个新的 Java 项目，将 Aspose.Page JAR 添加到项目的构建路径，并创建一个文件夹用于保存生成的 XPS 文件。该文件夹稍后将在代码中引用为 `dataDir`。

## 步骤 2：初始化 XPS 文档
实例化一个空的 XPS 文档，用于容纳内容：

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## 步骤 3：添加 Unicode 文本
现在我们实际添加 Unicode 字符串。下面的示例写入反转的短语 “AVAJ rof SPX.esopsA”，该短语仅包含 ASCII 字符，但您可以将其替换为任何 Unicode 文本（例如阿拉伯语 “مرحبا” 或中文 “你好”）。

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **专业提示：** 为了正确渲染从右到左的语言，设置 `glyphs.setBidiLevel(1);`。对于从左到右的脚本可以省略此行。

## 步骤 4：保存文档
将 XPS 文件持久化到磁盘：

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

运行程序后，使用任意 XPS 查看器打开生成的 `AddEncodingText_out.xps`，即可看到在指定坐标渲染的 Unicode 文本。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| 文本显示为方块 | 未找到字体或字体不支持这些字符 | 使用包含所需字形的字体（例如 “Arial Unicode MS”） |
| 从右到左的文本显示为从左到右 | 未设置 Bidi 级别 | 调用 `glyphs.setBidiLevel(1);` |
| 文件未保存 | `dataDir` 路径无效或缺少写权限 | 确保目录存在且应用程序拥有写入权限 |

## 常见问答

### 我可以将 Aspose.Page for Java 与其他编程语言一起使用吗？
Aspose.Page 主要面向 Java 设计，但 Aspose 为多种编程语言提供了库。

### 是否提供免费试用？
是的，您可以在[此处](https://releases.aspose.com/)获取 Aspose.Page 的免费试用。

### 在哪里可以找到关于 Aspose.Page 的支持和讨论？
访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 获取支持和讨论。

### 如何获取 Aspose.Page 的临时许可证？
您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

### Aspose.Page 支持哪些字体样式？
Aspose.Page 支持 Regular、Bold、Italic 和 BoldItalic 等字体样式。

## 结论
您已经掌握了 **如何向** Java PostScript（XPS）文档中使用 Aspose.Page 添加 Unicode 文本。这一功能打开了多语言报表、国际化发票以及任何需要非 ASCII 字符的场景的大门。欢迎探索更多功能，如文本旋转、裁剪路径或嵌入自定义字体——详细信息请参阅官方[文档](https://reference.aspose.com/page/java/)。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2025-12-17  
**测试环境：** Aspose.Page for Java 23.12（撰写时的最新版本）  
**作者：** Aspose