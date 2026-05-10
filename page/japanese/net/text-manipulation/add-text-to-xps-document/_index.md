---
date: 2026-03-21
description: .NETでXPSドキュメントを作成し、Aspose.Page for .NETを使用してテキストを追加する方法を学びましょう。.NET開発者向けのステップバイステップガイドです。
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: .NETでXPSドキュメントを作成し、Aspose.Pageでテキストを追加する
url: /ja/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS ドキュメント .NET を作成し、Aspose.Page でテキストを追加する

In modern .NET development, the ability to **create XPS document .NET** files programmatically is a valuable skill, especially when you need to generate printable reports, invoices, or custom graphics. This tutorial walks you through using Aspose.Page to **aspose.page add text** to an XPS document, giving you full control over layout and styling—all from within your .NET application.

## Quick Answers
- **このチュートリアルでカバーする内容は何ですか？** Aspose.Page for .NET を使用して新規作成した XPS ドキュメントにテキストを追加する。  
- **所要時間はどれくらいですか？** 基本的な実装で約 5〜10 分です。  
- **前提条件は何ですか？** .NET 開発環境と Aspose.Page ライブラリ。  
- **ライセンスは必要ですか？** はい、製品版で使用するには有効な Aspose.Page ライセンスが必要です。  
- **.NET Core / .NET 6+ で実行できますか？** もちろんです – Aspose.Page は最新の .NET バージョンすべてをサポートしています。

## What is create xps document .net?

.NET で XPS ドキュメントを作成することは、デバイスやプリンター間でコンテンツの外観を正確に保持する固定レイアウトのファイルを生成することを意味します。XPS (XML Paper Specification) は Microsoft のオープン標準のページ記述形式で、PDF に似ていますが完全に XML ベースです。

## Why use Aspose.Page to add text?

Aspose.Page は低レベルの XPS マークアップを抽象化した高レベルのオブジェクト指向 API を提供します。生の XML を扱うことなくテキスト、グラフィック、シェイプを追加でき、開発プロセスが高速かつエラーが少なくなります。

## Prerequisites

- Aspose.Page for .NET: Ensure that you have the Aspose.Page library installed. You can download it from the [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- Development Environment: Set up your .NET development environment. If you haven't done this yet, follow the installation instructions provided in the [documentation](https://reference.aspose.com/page/net/).
- Document Directory: Create a directory where you'll store your documents. Replace "Your Document Directory" in the provided code snippet with the actual path.

Now that we’ve covered the basics, let’s dive into the code.

## Import Namespaces

Firstly, import the necessary namespaces to kick‑start the project:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Create XPS document .NET

Create a fresh XPS document that will serve as the canvas for our text.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## Step 2: Create a brush for text

Define a solid‑color brush that determines the color of the text. Here we use black.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## Step 3: Add glyphs (aspose.page add text)

Glyphs are the low‑level representation of characters in an XPS document. This call adds the text “Hello World!” at the specified coordinates.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## Step 4: Save the resultant XPS document

Persist the document to disk so you can view or print it later.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

By following these steps, you’ve successfully **create XPS document .NET** and added custom text using Aspose.Page.

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| **File not found** when saving | `dataDir` が存在しないフォルダーを指しています | ディレクトリが存在することを確認するか、保存前に `Directory.CreateDirectory(dataDir)` を使用してください。 |
| **Text not visible** | ブラシの色が背景と同じです | `Color.Black` を別のコントラストのある色に変更してください。 |
| **Unsupported font** | フォントがマシンにインストールされていません | 確実に存在するフォントを使用するか、Aspose.Page のフォント埋め込み機能を利用してフォントを埋め込んでください。 |

## Frequently Asked Questions

### Q1: Can I customize the font and size of the added text?

A1: Yes, you have full control over the font and size. Adjust the parameters in the `AddGlyphs` method accordingly.

### Q2: Is Aspose.Page compatible with .NET Core?

A2: Absolutely! Aspose.Page supports .NET Core, ensuring compatibility with the latest .NET technologies.

### Q3: Are there any licensing requirements for using Aspose.Page?

A3: Yes, you need a valid license. Explore licensing options [here](https://purchase.aspose.com/buy).

### Q4: How can I get support or seek help?

A4: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to connect with the community and get assistance.

### Q5: Is there a free trial available?

A5: Certainly! You can get a free trial [here](https://releases.aspose.com/).

**Additional Q&A**

**Q: Can I add multiple text blocks on the same page?**  
A: Yes, simply call `doc.AddGlyphs` multiple times with different coordinates.

**Q: Does Aspose.Page allow text rotation?**  
A: You can apply a transformation matrix to the `XpsGlyphs` object to rotate or skew the text.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**最終更新日:** 2026-03-21  
**テスト環境:** Aspose.Page 24.11 for .NET  
**作者:** Aspose  

---