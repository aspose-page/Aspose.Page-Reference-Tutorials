---
date: 2025-12-13
description: 了解如何在 Java 中的 asp 页面添加文本、设置字体样式以及使用 Aspose.Page 添加 Unicode 文本。请按照我们的分步指南操作。
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: ASP 页面添加文本 – Java PostScript 中的 Unicode
url: /zh/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – Java PostScript 中的 Unicode

## 介绍
如果您需要在 Java PostScript 工作流中 **asp page add text** 并保留 Unicode 字符，您来对地方了。在本教程中，我们将演示如何添加 Unicode 文本、设置字体样式以及使用 **Aspose.Page for Java** 保存结果。完成后，您将了解如何在 Java 中设置字体样式以及高效地添加 Unicode 文本。

## 快速答案
- **哪个库可以在 Java PostScript 中添加 Unicode 文本？** Aspose.Page for Java。  
- **主要的添加文本方法是什么？** 使用 `doc.addGlyphs(...)` 并传入 `XpsGlyphs` 对象。  
- **是否需要特殊字体来支持 Unicode？** 只要使用支持相应代码点的 TrueType/OpenType 字体（例如 Arial）即可。  
- **可以更改字体样式吗？** 可以，使用 `XpsFontStyle`（Regular、Bold、Italic 等）。  
- **生产环境是否需要许可证？** 需要，非试用使用必须提供有效的 Aspose.Page 许可证。

## 什么是 asp page add text？
`asp page add text` 指的是使用 Aspose.Page API 将文本字符串插入到 PostScript 或 XPS 文档的过程。该 API 将底层的 PostScript 命令抽象为高级对象，如 `XpsGlyphs`，让您可以更方便地操作。

## 为什么使用 Aspose.Page 来 set font style java 并添加 Unicode 文本？
- **完整的 Unicode 支持** – 能处理从右到左的脚本和复杂字形。  
- **简洁的 API** – 一行代码即可添加文本并应用样式。  
- **跨平台** – 适用于任何兼容 Java 的环境。  
- **无外部依赖** – 不需要额外的渲染引擎。

## 前置条件
在开始教程之前，请确保已满足以下前置条件：

1. **Java Development Kit (JDK)** – 确认机器上已安装 Java。  
2. **Aspose.Page for Java** – 从 [download link](https://releases.aspose.com/page/java/) 下载并安装 Aspose.Page 库。  
3. **集成开发环境 (IDE)** – 选择您喜欢的 Java IDE，例如 IntelliJ IDEA 或 Eclipse。

## 导入包
在 Java 项目中，导入 Aspose.Page 所需的包。将以下代码行加入您的代码中：

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## 步骤 1：设置项目
在 IDE 中创建一个新的 Java 项目并搭建项目结构。确保在项目依赖中加入 Aspose.Page 库。

## 步骤 2：初始化 XPS 文档
在项目中初始化一个新的 XPS 文档：

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## 步骤 3：添加 Unicode 文本
现在，使用 Aspose.Page 库向 XPS 文档添加 Unicode 文本。使用以下代码片段：

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

此代码段将在坐标 (400, 200) 处向 XPS 文档添加 Unicode 文本 **"AVAJ rof SPX.esopsA"**，并使用指定的字体和样式。`setBidiLevel(1)` 调用会启用从右到左的渲染，以正确显示 Unicode。

## 步骤 4：保存文档
使用以下代码保存生成的 XPS 文档：

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## 结论
恭喜！您已成功在 Java PostScript 场景中使用 Aspose.Page 完成 **asp page add text** 并设置字体样式。此方法为 Unicode 渲染和样式提供了细粒度的控制，适用于国际化报表、发票和图形等场景。

如需了解更多功能和细节，请访问 [documentation](https://reference.aspose.com/page/java/)。

## 常见问题

**Q:** 我可以在其他编程语言中使用 Aspose.Page for Java 吗？  
**A:** Aspose.Page 主要面向 Java，但 Aspose 还提供了面向多种编程语言的库。

**Q:** 是否提供免费试用？  
**A:** 是的，您可以在此处获取 Aspose.Page 的免费试用 [here](https://releases.aspose.com/)。

**Q:** 哪里可以找到 Aspose.Page 的支持和讨论？  
**A:** 请访问 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 获取支持和交流。

**Q:** 如何获取 Aspose.Page 的临时许可证？  
**A:** 您可以在此处获取临时许可证 [here](https://purchase.aspose.com/temporary-license/)。

**Q:** Aspose.Page 支持哪些字体样式？  
**A:** Aspose.Page 支持 Regular、Bold、Italic 和 BoldItalic 等字体样式。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2025-12-13  
**测试环境：** Aspose.Page for Java（最新）  
**作者：** Aspose  

---