---
date: 2026-01-10
description: .NETでAspose.Pageを使用してXPSをPDFに簡単に変換できます。ライブラリをダウンロードし、ドキュメントを確認し、無料トライアルをご利用ください。
linktitle: Convert XPS to PDF
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET を使用して XPS を PDF に変換
url: /ja/net/document-conversion/convert-xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用した XPS から PDF への変換

## Introduction

このチュートリアルでは、Aspose.Page for .NET ライブラリを使用して **XPS を PDF に変換する方法** を学びます。XPS を PDF に変換することは、PDF リーダーしか持っていないユーザーと XPS ドキュメントを共有したい場合や、XPS コンテンツを大規模な PDF ワークフローに組み込みたい場合に一般的な要件です。各ステップを順に解説し、設定が重要な理由を説明し、JPEG 品質の設定や PDF 画像圧縮の適用など、出力を細かく調整する方法を示します。

## Quick Answers
- **XPS から PDF への変換に最適なライブラリは？** Aspose.Page for .NET
- **本番環境でライセンスは必要ですか？** はい、商用ライセンスが必要です。無料トライアルも利用可能です。
- **画像品質を制御できますか？** もちろんです。`JpegQualityLevel` と `PdfImageCompression` を使用します。
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 .NET 5/6/7。
- **複数の XPS ファイルを 1 つの PDF に変換できますか？** はい、ファイルをループして結果をマージすれば可能です。

## Prerequisites

この変換作業に取り掛かる前に、以下の前提条件が整っていることを確認してください。

- **Aspose.Page for .NET Library** – 開発環境に Aspose.Page for .NET ライブラリがインストールされていることを確認してください。ダウンロードは [Aspose.Page documentation](https://reference.aspose.com/page/net/) から行えます。
- **Development Environment** – Visual Studio などの .NET 開発環境をセットアップしてください。
- **XPS Document** – PDF に変換したい XPS ドキュメントを用意してください。対象ディレクトリに保存されたサンプル XPS ファイルでも構いません。

## Import Namespaces

コードに取り掛かる前に、Aspose.Page for .NET の機能をプロジェクトで利用できるよう、必要な名前空間をインポートしましょう。

```csharp
using Aspose.Page.XPS;
```

## Step‑by‑Step Guide

### Step 1: Initialize Document Directory

ソース XPS ファイルが格納されているフォルダーと、生成された PDF を保存するフォルダーを定義します。

```csharp
string dataDir = "Your Document Directory";
```

`"Your Document Directory"` を、XPS ドキュメントが入っているフォルダーへの絶対パスまたは相対パスに置き換えてください。

### Step 2: Open Streams for PDF Output and XPS Input

2 つのファイルストリームを使用します。1 つは XPS ファイルの読み取り用、もう 1 つは生成された PDF の書き込み用です。

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

> **Pro tip:** パスが正しいこと、そしてアプリケーションが対象フォルダーに対して読み書き権限を持っていることを確認してください。

### Step 3: Load the XPS Document

XPS ストリームから `XpsDocument` インスタンスを作成します。`XpsLoadOptions` オブジェクトで読み込み設定を指定できますが、デフォルトでほとんどのシナリオに対応します。

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### Step 4: Configure PDF Save Options

ここで PDF の出力設定を行います。**PDF 画像圧縮** (`PdfImageCompression.Jpeg`) と **JPEG 品質** (`JpegQualityLevel = 100`) の使用に注目してください。これらの設定はファイルサイズと画質に直接影響します。

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

- **`JpegQualityLevel`** – PDF に埋め込まれる JPEG 画像の品質を制御します（数値が大きいほど高品質でファイルサイズも大きくなります）。
- **`ImageCompression`** – 圧縮アルゴリズムを選択します。JPEG は写真画像に最適です。
- **`TextCompression`** – Flate 圧縮によりテキストの品質を損なうことなく PDF サイズを削減します。
- **`PageNumbers`** – 特定のページだけを **XPS から PDF に保存** できるようにします。

### Step 5: Create a PDF Rendering Device

`PdfDevice` は、先ほど開いたストリームに PDF データを書き込むレンダリングターゲットとして機能します。

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Step 6: Save the Document to PDF

最後に `Save` メソッドを呼び出し、レンダリングデバイスと設定したオプションを渡します。

```csharp
document.Save(device, options);
```

コードの実行が完了すると、`XPStoPDF_out.pdf` が指定したディレクトリに作成され、設定した圧縮と品質オプションが適用された変換ページが格納されます。

## Why Convert XPS to PDF?

- **Universal accessibility** – PDF ビューアは事実上すべてのデバイスにインストールされているのに対し、XPS リーダーはほとんど存在しません。
- **Preserve layout** – PDF は元の XPS と同じビジュアルレイアウト、フォント、グラフィックを正確に保持します。
- **Further processing** – PDF に変換すれば、他の Aspose ライブラリを使って結合、注釈付け、デジタル署名などの追加処理が可能です。

## Common Use Cases

- **Enterprise reporting** – レガシーシステムから生成した XPS レポートを PDF に変換し、配布します。
- **Archiving** – 長期保存のために PDF として文書を保管しつつ、必要に応じて XPS ソースから再生成できます。
- **Web services** – XPS アップロードを受け取り、リアルタイムで PDF ファイルを返す API エンドポイントを提供します。

## Troubleshooting & Tips

- **File not found** – `dataDir` パスを再確認し、XPS ファイル名が正確に一致していることを確認してください。
- **Permission errors** – Visual Studio を管理者として実行するか、出力フォルダーに書き込み権限を付与してください。
- **Large PDFs** – 生成された PDF が大きすぎる場合は、`JpegQualityLevel` を下げるか、`ImageCompression` を `PdfImageCompression.Zip` に変更してください。

## FAQ's

### Q1: Can I convert multiple XPS files to a single PDF using Aspose.Page for .NET?

A1: Yes, you can loop through multiple XPS files and follow the same steps to merge them into a single PDF.

### Q2: Are there other output formats supported by Aspose.Page for .NET?

A2: Yes, Aspose.Page for .NET supports various output formats, including TIFF, JPEG, PNG, and more.

### Q3: How can I customize the appearance of the converted PDF document?

A3: You can tweak the options object parameters, such as image compression and text compression, to achieve the desired appearance.

### Q4: Is there a trial version available for Aspose.Page for .NET?

A4: Yes, you can explore the capabilities of Aspose.Page for .NET by obtaining a free trial from [here](https://releases.aspose.com/).

### Q5: Where can I get community support for Aspose.Page for .NET?

A5: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community discussions and support.

## Frequently Asked Questions (AI‑Friendly)

**Q: How do I set JPEG quality when converting XPS to PDF?**  
A: Use the `JpegQualityLevel` property inside `PdfSaveOptions`. Setting it to 100 gives maximum quality.

**Q: What does “pdf image compression” mean in this context?**  
A: It refers to the `ImageCompression` option, which determines how images are compressed inside the PDF (e.g., JPEG, Zip).

**Q: Can I programmatically generate a PDF without an XPS source?**  
A: Yes, Aspose.Page also supports **c# generate pdf** directly from drawing commands, but that is outside the scope of this tutorial.

**Q: Is there a way to convert XPS to PDF without losing vector graphics?**  
A: The conversion retains vector data; just avoid rasterizing images by keeping `ImageCompression` set to JPEG or Zip as needed.

**Q: Does the library support .NET Core?**  
A: Absolutely – Aspose.Page for .NET works with .NET Core, .NET 5, .NET 6, and later versions.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}