---
date: 2026-01-07
description: 了解如何使用 Aspose.Page for .NET 创建 XPS 文档、添加字形克隆、使用纯色画刷并保存 XPS 文件。
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: 创建 XPS 文档 – 使用 Aspose.Page for .NET 添加字形克隆并更改颜色
url: /zh/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 XPS 文档 – 使用 Aspose.Page for .NET 添加字形克隆并更改颜色

## 介绍

欢迎阅读本分步指南，向您展示 **如何创建 XPS 文档** 文件、克隆字形以及使用 Aspose.Page for .NET 更改其颜色。无论您是在构建动态报表、发票还是自定义图形，掌握这些技术都能让您在 .NET 生态系统内生成视觉丰富的 XPS 输出。

## 快速答案
- **主要目标是什么？** 创建 XPS 文档、添加字形克隆并更改颜色。  
- **使用哪个库？** Aspose.Page for .NET。  
- **需要许可证吗？** 评估期间可使用临时许可证；生产环境需要正式许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **如何保存结果？** 使用 `Save` 方法将 XPS 文件写入磁盘。

## 前置条件

在开始教程之前，请确保您具备以下前置条件：

- 对 C# 编程语言有基本了解。  
- 已安装 Visual Studio 或其他您喜欢的 C# 开发环境。  
- Aspose.Page for .NET 库。您可以在 [此处](https://releases.aspose.com/page/net/) 下载。  
- 熟悉 XPS 文档格式。

## 导入命名空间

要开始，请在 C# 项目中包含必要的命名空间：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 如何创建 XPS 文档并添加字形克隆

### 步骤 1：设置文档目录

首先设置存放文档的目录：

```csharp
string dataDir = "Your Document Directory";
```

### 步骤 2：创建第一个 XPS 文档

现在，创建第一个 XPS 文档：

```csharp
XpsDocument doc1 = new XpsDocument();
```

### 步骤 3：向第一个文档添加字形

使用指定参数向第一个文档添加字形：

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### 步骤 4：使用实心颜色画刷填充字形

使用 **实心颜色画刷**（例如绿色）填充第一个文档中的字形：

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### 步骤 5：创建第二个 XPS 文档

接下来，创建第二个 XPS 文档：

```csharp
XpsDocument doc2 = new XpsDocument();
```

### 步骤 6：如何将字形克隆添加到另一个文档

从第一个文档克隆字形并将其添加到第二个文档：

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### 步骤 7：如何更改克隆字形的颜色

更改第二个文档中克隆字形的颜色，例如改为红色。这演示了 **如何在克隆后更改字形颜色**：

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### 步骤 8：保存 XPS 文件 – 第一个文档

将第一个 XPS 文档保存到前面定义的文件夹：

```csharp
doc1.Save(dataDir + "out1.xps");
```

### 步骤 9：保存 XPS 文件 – 第二个文档

保存第二个 XPS 文档：

```csharp
doc2.Save(dataDir + "out2.xps");
```

恭喜！您已成功 **创建 XPS 文档** 文件、添加字形克隆并使用 Aspose.Page for .NET 更改其颜色。

## 为什么使用字形克隆和颜色更改？

- **可重用性：** 克隆已有字形，可在不重新定义的情况下重复使用复杂的矢量形状。  
- **性能：** 相比从头创建字形，可减少处理时间。  
- **设计灵活性：** 对同一字形应用不同的 `SolidColorBrush` 实例，以实现多样的视觉主题。  
- **跨文档编辑：** 在多个 XPS 文件之间克隆字形，实现报表品牌的一致性。

## 常见问题与故障排除

| 问题 | 解决方案 |
|-------|----------|
| **克隆返回 null** | 确保在克隆之前已将源字形 (`glyphs`) 添加到第一个文档中。 |
| **颜色未改变** | 在第 7 步中，将 `glyphs.Fill` 强制转换为 `XpsSolidColorBrush` 后再设置 `Color` 属性。 |
| **文件未保存** | 检查 `dataDir` 是否指向有效且可写的文件夹，并确认拥有相应的文件系统权限。 |
| **字形尺寸异常** | 调整 `AddGlyphs` 的第二个参数（字体大小）以适当缩放字形。 |

## 常见问答

**Q1：我可以在 .NET 中使用 Aspose.Page 处理其他文档格式吗？**  
A1：Aspose.Page for .NET 专为 XPS 文档设计。如需操作其他格式，可考虑 Aspose 提供的针对相应格式的其他库。

**Q2：Aspose.Page for .NET 有临时许可证吗？**  
A2：有，您可以获取用于测试的临时许可证。详情请访问 [此处](https://purchase.aspose.com/temporary-license/)。

**Q3：如果遇到问题，如何获取支持或帮助？**  
A3：欢迎访问 [Aspose.Page 论坛](https://forum.aspose.com/c/page/39) 与社区交流并获取帮助。

**Q4：免费试用版有哪些限制？**  
A4：免费试用版存在一定限制，建议在使用前查阅文档了解详细信息。

**Q5：在哪里可以找到 Aspose.Page for .NET 的完整文档？**  
A5：请参考文档 [此处](https://reference.aspose.com/page/net/) 获取详细信息和示例。

**Q6：如何更改字形的描边颜色而不是填充颜色？**  
A6：使用 `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);` 设置描边画刷。

**Q7：我可以在同一文档中添加多个字形克隆吗？**  
A7：可以，重复调用 `doc2.Add(glyphs.Clone());` 并根据需要调整位置。

---

**最后更新：** 2026-01-07  
**测试环境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}