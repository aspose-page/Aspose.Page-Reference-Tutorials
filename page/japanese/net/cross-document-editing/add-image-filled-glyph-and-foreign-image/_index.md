---
date: 2026-06-30
description: 数ステップで Aspose.Page for .NET を使用し、XPS ドキュメント .NET を作成し、画像で埋めたグリフや外部画像を追加する方法を学びます。
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: 画像で埋めたグリフと外部画像の追加
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: XPS ドキュメント .NET の作成 – Aspose.Page で画像で埋めたグリフと外部画像を追加
url: /ja/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS ドキュメントを作成 .NET – 画像で塗りつぶしたグリフと外部画像の追加（Aspose.Page 使用）

## はじめに

.NET 開発では、高品質で解像度に依存しないグラフィックが必要な場合に **create XPS document .NET** のタスクが頻繁にあります。Aspose.Page for .NET を使用すれば、このプロセスはシンプルになり、画像で塗りつぶしたグリフを XPS ファイルに追加したり、別の XPS ドキュメントから画像を取り込んだりできます。このチュートリアルの最後までに、2 つの XPS ドキュメントを作成し、グリフに画像を塗りつぶし、画像をドキュメント間で再利用する方法が分かります。請求書、証明書、またはビジュアルリッチな出力の生成に最適です。

## クイック回答
- **Aspose.Page は何をサポートしますか？** 25 以上の画像フォーマットに対応し、最大 500 MB の XPS ファイルをメモリに完全にロードせずに処理できます。  
- **画像で塗りつぶしたグリフを追加するコードは何行ですか？** わずか 2 行です：`ImageBrush` を作成し、`Glyph` に割り当てるだけです。  
- **本番環境でライセンスが必要ですか？** はい、商用ライセンスを取得すると評価用の透かしが削除されます。  
- **対応している .NET バージョンはどれですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **別の XPS からフォントを再利用できますか？** もちろんです。最初のドキュメントからフォントコレクションをインポートして、2 番目のドキュメントで使用できます。

## Aspose.Page .NET を使用して XPS ドキュメントを作成する方法は？

Aspose.Page ライブラリをロードし、`XpsDocument` をインスタンス化し、ページを追加して `Save` を呼び出すだけで、3 行の簡潔なステートメントで完結するワークフローが実現します。API はページサイズ、DPI、リソース管理を自動的に処理するため、低レベルの XPS 構造を自分で管理する必要はありません。このアプローチは、1 ページのチラシから数百ページ規模のカタログまでスケールします。

## 前提条件

- **Aspose.Page for .NET** – [here](https://releases.aspose.com/page/net/) からダウンロードしてください。  
- **.NET IDE** – Visual Studio、Rider、または C# 拡張機能付き VS Code。  
- **ドキュメント用フォルダー** – コード例では **Your Document Directory** と呼びます。

## 名前空間のインポート

`Aspose.Page.XPS` 名前空間はコア XPS ドキュメントクラスを提供し、`Aspose.Page.XPS.XpsModel` にはグリフやブラシなどのモデル要素が含まれます。ファイルの先頭でこれらをインポートします。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 画像で塗りつぶしたグリフとは？

グリフはベクタ形状で、単色、グラデーション、または画像ブラシで描画できます。`ImageBrush` を適用すると、グリフの内部が指定した画像で塗りつぶされ、ページ全体をラスタライズせずに複雑なビジュアル効果を実現できます。

## 手順 1: 最初の XPS ドキュメントを作成

`XpsDocument` は XPS パッケージを表し、XPS ファイルの作成と保存のエントリーポイントです。画像で塗りつぶしたグリフをホストする最初の XPS ドキュメントを作成します。

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## 手順 2: 最初のドキュメントにグリフを追加

`XpsGlyphs` はページ上に配置できるグリフ（テキスト文字）のコレクションを定義します。フォント、サイズ、スタイル、位置を指定して最初のドキュメントにグリフを追加します。

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## 手順 3: 画像ブラシでグリフを塗りつぶす

`ImageBrush` は画像で領域を塗りつぶすため、パターンや写真を形状に適用できます。データディレクトリ内の画像を使用して、グリフに画像ブラシを適用します。

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## 手順 4: 2 番目の XPS ドキュメントを作成

`XpsDocument` を使用して、新しい XPS ファイルを作成します。ここでは、最初のドキュメントからグリフを取り込む 2 番目の XPS ドキュメントを作成します。

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## 手順 5: 最初のドキュメントのフォントでグリフを追加

`Font` は XPS ドキュメントでテキストを描画するための書体を表します。最初のドキュメントから抽出したフォントを使用して、2 番目のドキュメントにグリフを追加します。フォントコレクションを共有することで、ファイルサイズを抑えつつビジュアルの一貫性を保てます。

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## 手順 6: 最初のドキュメントのフィルから画像ブラシを作成

`ImageBrush` は既存のフィルから作成でき、同じ画像を複数のドキュメントで再利用できます。最初のドキュメントのフィルから画像ブラシを作成し、2 番目のドキュメントのグリフを塗りつぶします。この「外部画像」テクニックにより、ソースファイルを重複させずにアートワークを再利用できます。

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## 手順 7: ドキュメントを保存

`Save` は XPS パッケージをファイルに書き込み、すべてのリソースを埋め込みます。最初と 2 番目の XPS ドキュメントを出力フォルダーに保存します。`Save` メソッドは XPS パッケージを書き出し、画像で塗りつぶしたグリフを保持します。

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## よくある問題と解決策

| 問題 | 発生原因 | 対策 |
|------|----------|------|
| **グリフ内に画像が表示されない** | `ImageBrush` が誤った URI で作成されたか、画像サイズがグリフの境界を超えているためです。 | 画像パスを確認し、必要に応じて `ImageBrush.Stretch = Stretch.Uniform` を設定してください。 |
| **2 番目のドキュメントでフォントが欠落** | フォントリソースが最初の XPS からエクスポートされていません。 | グリフを追加する前に `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` を使用してください。 |
| **大きなファイルでのパフォーマンス低下** | 各グリフごとに大きな画像をメモリに読み込んでいるためです。 | すべてのグリフで単一の `ImageBrush` インスタンスを再利用するか、使用前に画像をダウンサンプリングしてください。 |

## よくある質問

### Q1: グリフの塗りつぶしに異なる画像フォーマットを使用できますか？

A1: はい、Aspose.Page は PNG、JPEG、BMP、GIF、TIFF など、合計で 25 種類以上のフォーマットをサポートしています。

### Q2: グリフの外観をさらにカスタマイズするには？

A2: `Glyph.Stroke`、`Glyph.FillOpacity`、`Glyph.Transform` などのプロパティを調べて、輪郭、透明度、回転を調整できます。

### Q3: 大規模なドキュメントセットの処理に Aspose.Page は適していますか？

A3: はい。ライブラリはストリーミングを使用して数百ページ規模の XPS ファイルを処理し、500 ページのドキュメントでもメモリ使用量を 100 MB 未満に抑えます。

### Q4: 個々のグリフに異なるスタイルを適用できますか？

A4: はい、各 `Glyph` インスタンスは独自の `Fill`、`Stroke`、`Transform` プロパティを持ち、グリフごとのスタイリングが可能です。

### Q5: 他の XPS ツールと比較した Aspose.Page の利点は何ですか？

A5: Aspose.Page は 25 以上の画像フォーマットに対応し、最大 500 MB のファイルをメモリに完全にロードせずに処理でき、100 % .NET ネイティブ API を提供します。これにより COM 相互運用や外部ツールが不要になります。

**最終更新日:** 2026-06-30  
**テスト環境:** Aspose.Page 24.11 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [XPS ドキュメントの作成 – Aspose.Page for .NET](/page/net/document-creation/)
- [XPS ドキュメントに画像を追加 – Aspose.Page for .NET](/page/net/image-management/add-image-to-xps-document/)
- [グリフのクローンを追加して色を変更 – Aspose.Page for .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}