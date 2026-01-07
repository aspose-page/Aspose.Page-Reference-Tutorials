---
date: 2026-01-07
description: Aspose.Page を使用して .NET で XPS ドキュメントを作成する方法を学びます。このガイドでは、画像で埋められたグリフや外部画像を追加して、ドキュメントのビジュアルを豊かにする方法を示します。
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Aspose.Page を使用した .NET での XPS ドキュメント作成 – 画像で塗りつぶされたグリフと外部画像
url: /ja/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用した .NET の XPS ドキュメント作成 – 画像で埋めたグリフと外部画像

## はじめに

洗練されたプロフェッショナルな見た目の **create XPS document .NET** アプリケーションが必要な場合、Aspose.Page は画像をグリフに直接埋め込み、ドキュメント間でグラフィックリソースを再利用できるツールを提供します。このチュートリアルでは、2つの XPS ファイルを作成し、画像ブラシでグリフを塗りつぶし、そしてそのブラシを2番目のドキュメントで再利用する手順を解説します。最後まで読むと、このアプローチがメモリを節約し、スタイリングを簡素化し、レポートや請求書、その他印刷可能なコンテンツの創造的な可能性を広げる理由が理解できるでしょう。

## クイック回答
- **このチュートリアルでカバーする内容は？** Aspose.Page for .NET を使用して、画像で埋めたグリフを追加し、XPS ドキュメント間で再利用する方法。  
- **対象となる主要キーワードは？** `create xps document .net`.  
- **前提条件は？** .NET 開発環境、Aspose.Page for .NET、そして XPS ファイル用のフォルダー。  
- **実装にかかる時間は？** 作業可能なプロトタイプを作成するのに約 10‑15 分。  
- **他の画像形式を使用できますか？** はい – .NET の `System.Drawing.Image` がサポートする任意の形式です。

## 前提条件

コードに取り掛かる前に、以下が用意されていることを確認してください。

- **Aspose.Page for .NET** – 最新のライブラリを [here](https://releases.aspose.com/page/net/) からダウンロードしてください。  
- **Development Environment** – Visual Studio 2022（または .NET 6+ をサポートする任意の IDE）。  
- **Document Directory** – 入力画像と生成された XPS ファイルを格納するフォルダーを作成します。スニペット内では **Your Document Directory** と呼びます。

## 名前空間のインポート

XPS オブジェクトと描画ユーティリティを操作するために必要な名前空間をインポートします。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ステップバイステップ ガイド

### ステップ 1: 最初の XPS ドキュメントを作成

画像で埋めたグリフを配置するための空の XPS ドキュメントをインスタンス化することから始めます。

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### ステップ 2: 最初のドキュメントにグリフを追加

次に、後で画像ブラシで塗りつぶすグリフ（テキスト文字）を追加します。

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### ステップ 3: 画像ブラシでグリフを塗りつぶす

ここでは、データディレクトリにある TIFF ファイルから `ImageBrush` を作成し、グリフに適用します。ブラシはタイルモードに設定されているため、グリフ領域が画像サイズを超える場合に画像が繰り返されます。

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### ステップ 4: 2 番目の XPS ドキュメントを作成

次に、最初のドキュメントからグリフスタイルと画像ブラシを再利用する 2 番目の XPS ドキュメントを作成します。

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### ステップ 5: 最初のドキュメントのフォントでグリフを追加

2 番目のドキュメントにグリフを追加し、最初のドキュメントから同じフォントオブジェクトを再利用します。これにより、両方のファイルで視覚的一貫性が保たれます。

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### ステップ 6: 最初のドキュメントの塗りから画像ブラシを作成

画像を再度読み込む代わりに、`glyphs1` からブラシをクローンして `glyphs2` に割り当てます。これにより、リソースを効率的に共有できる **create XPS document .NET** ワークフローを実現できることが示されます。

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### ステップ 7: ドキュメントを保存

最後に、両方の XPS ファイルをディスクに保存します。これで任意の XPS ビューアで開き、画像で埋めたグリフ効果を確認できます。

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## XPS ドキュメント .NET を作成する際に画像で埋めたグリフを使用する理由は？

- **ビジュアルインパクト** – プレーンテキストをページ全体をラスタライズせずに、グラフィック豊かな要素に変換します。  
- **リソース再利用** – ブラシやフォントを複数のドキュメント間で共有し、メモリ使用量を削減します。  
- **柔軟性** – 画像ブラシをタイル、ストレッチ、回転させて、カスタムパターンやブランディングを実現します。

## よくある問題とヒント

- **ファイルパスエラー** – `dataDir` が OS に適したパス区切り文字（`\` または `/`）で終わっていることを確認してください。  
- **サポートされていない画像形式** – Aspose.Page は TIFF、PNG、JPEG で最適に動作します。使用前に他の形式は変換してください。  
- **TileMode が適用されない** – `TileMode` を設定する前に `XpsImageBrush` にキャストしているか確認してください。そうしないとプロパティが無視されます。

## よくある質問

### Q1: グリフの塗りつぶしに異なる画像形式を使用できますか？

**A:** はい、Aspose.Page は TIFF、PNG、JPEG、BMP、GIF をサポートしています。`CreateImageBrush` 呼び出し時に正しいファイル拡張子を指定してください。

### Q2: グリフの外観をさらにカスタマイズするには？

**A:** `XpsGlyphs` の `Opacity`、`RenderTransform`、`Stroke` などの追加プロパティを調べて、レンダリングを細かく調整してください。

### Q3: 大量のドキュメントセットを処理するのに Aspose.Page は適していますか？

**A:** もちろんです。このライブラリは高性能シナリオ向けに最適化されており、バッチジョブで数千の XPS ファイルを処理できます。

### Q4: 個々のグリフに異なるスタイルを適用できますか？

**A:** はい。各 `XpsGlyphs` インスタンスは独自の fill、stroke、変換を持つことができ、細かな制御が可能です。

### Q5: 他のドキュメント処理ツールと比較して Aspose.Page を使用する利点は何ですか？

**A:** Aspose.Page は XPS の作成、操作、変換のための完全なライセンスフリー API を提供し、豊富なドキュメントと 24 時間年中無休のサポートが利用できます。

---

**最終更新日：** 2026-01-07  
**テスト環境：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}