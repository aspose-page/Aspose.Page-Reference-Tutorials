---
title: Aspose.Page .NET を使用して画像埋め込みグリフと外部画像を追加する
linktitle: 画像を埋め込んだグリフと外部画像を追加
second_title: Aspose.Page .NET API
description: Aspose.Page を使用して、.NET でのドキュメント処理の能力を解放します。画像を埋め込んだグリフを簡単に追加できます。ビジュアルを強化し、ワークフローを合理化します。
weight: 11
url: /ja/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page .NET を使用して画像埋め込みグリフと外部画像を追加する

## 導入

.NET 開発の世界では、Aspose.Page はドキュメント処理タスクを処理するための強力なツールキットとして際立っています。このチュートリアルでは、Aspose.Page for .NET を使用して、画像で埋められたグリフを追加し、外部画像を組み込むプロセスについて説明します。このガイドを読み終えるまでに、ドキュメント処理能力を強化する方法をしっかりと理解できるようになります。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Page for .NET: Aspose.Page ライブラリがインストールされていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/page/net/).

- 開発環境: Visual Studio またはその他の優先 IDE を使用して、動作する .NET 開発環境をセットアップします。

- ドキュメント ディレクトリ: ドキュメントを保存するディレクトリを作成します。これは、コード例では「ドキュメント ディレクトリ」と呼ばれます。

## 名前空間のインポート

.NET アプリケーションで、Aspose.Page が提供するクラスとメソッドにアクセスするために必要な名前空間をインポートすることから始めます。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ステップ 1: 最初の XPS ドキュメントを作成する

まず、Aspose.Page を使用して最初の XPS ドキュメントを作成します。このドキュメントは、画像で埋められたグリフを追加するための基礎として機能します。

```csharp
//例開始:1
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";

//最初の XPS ドキュメントを作成する
XpsDocument doc1 = new XpsDocument();
```

## ステップ 2: 最初のドキュメントにグリフを追加する

フォント、サイズ、スタイル、位置を指定して、最初のドキュメントにグリフを追加します。

```csharp
//最初のドキュメントにグリフを追加する
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## ステップ 3: 画像ブラシでグリフを塗りつぶす

データ ディレクトリの画像を利用して、画像ブラシでグリフを塗りつぶします。

```csharp
//画像ブラシでグリフを塗りつぶす
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## ステップ 4: 2 番目の XPS ドキュメントを作成する

ここで、最初のドキュメントのグリフを組み込む 2 番目の XPS ドキュメントを作成します。

```csharp
// 2 番目の XPS ドキュメントを作成する
XpsDocument doc2 = new XpsDocument();
```

## ステップ 5: 最初のドキュメントのフォントを使用してグリフを追加する

最初のドキュメントのフォントを使用して、2 番目のドキュメントにグリフを追加します。

```csharp
//最初のドキュメントのフォントを使用してグリフを 2 番目のドキュメントに追加します
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## ステップ 6: 最初のドキュメントの塗りつぶしから画像ブラシを作成する

最初のドキュメントの塗りつぶしからイメージ ブラシを作成し、それを使用して 2 番目のドキュメントのグリフを塗りつぶします。

```csharp
//最初のドキュメントの塗りつぶしからイメージ ブラシを作成し、2 番目のドキュメントのグリフを塗りつぶします。
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## ステップ 7: ドキュメントを保存する

番目と 2 番目の XPS ドキュメントの両方を保存します。

```csharp
//最初の XPS ドキュメントを保存する
doc1.Save(dataDir + "out1.xps");

// 番目の XPS ドキュメントを保存します
doc2.Save(dataDir + "out2.xps");
//拡張終了:1
```

## 結論

おめでとう！ Aspose.Page for .NET を使用して、イメージ埋め込みグリフを追加し、外部イメージを組み込むことができました。このチュートリアルは、ドキュメント処理機能を強化し、クリエイティブで視覚的に魅力的なドキュメントの新たな可能性を開くための基礎を提供します。

## よくある質問

### Q1: グリフの塗りつぶしに別の画像形式を使用できますか?

A1: はい、Aspose.Page はさまざまな画像形式をサポートしています。選択した画像形式との互換性を確認してください。

### Q2: グリフの外観をさらにカスタマイズするにはどうすればよいですか?

A2: グリフの外観を微調整するための追加のプロパティとメソッドについては、Aspose.Page ドキュメントを参照してください。

### Q3: Aspose.Page は大規模なドキュメント セットの処理に適していますか?

A3: Aspose.Page は、小さいドキュメント セットと大きいドキュメント セットの両方を効率的に処理できるように設計されています。

### Q4: 個々のグリフに異なるスタイルを適用できますか?

A4: はい、各グリフのスタイルを個別にカスタマイズできるため、高いレベルの柔軟性が得られます。

### Q5: 他のドキュメント処理ツールと比べて、Aspose.Page を使用する利点は何ですか?

A5: Aspose.Page は、包括的な機能セット、優れたパフォーマンス、および広範なドキュメントを提供するため、多くの開発者にとって好ましい選択肢となっています。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
