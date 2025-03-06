---
title: Aspose.Page for .NET を使用してグリッド ビジュアル ブラシを適用する
linktitle: グリッドビジュアルブラシを適用
second_title: Aspose.Page .NET API
description: Aspose.Page を使用して、.NET でのドキュメント処理の動的な世界を探索してください。グリッド ビジュアル ブラシを適用して、視覚的に美しいドキュメントを作成する方法を学びます。
weight: 10
url: /ja/net/visual-brushes/apply-grid-visual-brush/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用してグリッド ビジュアル ブラシを適用する

## 導入

.NET 開発の世界では、Aspose.Page はドキュメント処理タスクを処理するための強力なツールとして際立っています。それが提供する魅力的な機能の 1 つは、ドキュメントに新しい次元をもたらすグリッド ビジュアル ブラシを適用する機能です。このチュートリアルでは、Aspose.Page for .NET を使用してマゼンタ グリッド ビジュアル ブラシを実装するプロセスを段階的に説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件を満たしていることを確認してください。

-  Aspose.Page for .NET: ライブラリが .NET 環境にインストールされ、セットアップされていることを確認します。ダウンロードできます[ここ](https://releases.aspose.com/page/net/).

- 開発環境: 実用的な .NET 開発環境を準備し、C# プログラミングの基本を理解している必要があります。

- ドキュメント ディレクトリ: 処理されたファイルが保存されるドキュメント用のディレクトリを作成します。

## 名前空間のインポート

Aspose.Page の機能を効果的に利用するには、C# コードで必要な名前空間をインポートする必要があります。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

ここで、例を複数のステップに分けてみましょう。

## ステップ 1: XpsDocument を初期化する

```csharp
//例開始:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
//拡張終了:3
```

ここでは、次のインスタンスを作成します。`XpsDocument` XPS ドキュメントを操作するには。

## ステップ 2: マゼンタのグリッド ジオメトリを作成する

```csharp
//例開始:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
//拡張終了:4
```

このステップには、マゼンタ グリッドのパス ジオメトリの作成が含まれます。

## ステップ 3: マゼンタ グリッド VisualBrush をデザインする

```csharp
//例開始:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
//拡張終了:5
```

ここでは、ベクター グラフィックスを使用してマゼンタ グリッドの視覚的な側面をデザインします。

## ステップ 4: VisualBrush をグリッドに適用する

```csharp
//例開始:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
//拡張終了:6
```

ビジュアル ブラシをグリッド パスに適用し、適切にタイル化されていることを確認します。

## ステップ 5: キャンバスにグリッドを追加する

```csharp
//例開始:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
//拡張終了:7
```

グリッドをキャンバスに追加し、必要な変換を指定します。

## ステップ 6: 赤い四角形で強調する

```csharp
//例開始:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f;
//拡張終了:8
```

赤い透明な長方形を追加して、視覚的な魅力を高めます。

## ステップ 7: ドキュメントを保存する

```csharp
//例開始:9
doc.Save(dataDir + "AddGrid_out.xps");
//拡張終了:9
```

結果の XPS ドキュメントを指定したディレクトリに保存します。

## 結論

おめでとう！ Aspose.Page for .NET を使用して、ドキュメントにグリッド ビジュアル ブラシを適用することに成功しました。この手法により、ドキュメントの視覚要素が大幅に強化され、ダイナミックで魅力的なユーザー エクスペリエンスが提供されます。

## よくある質問

### Q1: Aspose.Page for .NET を Web アプリケーションとデスクトップ アプリケーションの両方で使用できますか?

A1: はい、Aspose.Page for .NET は多用途であり、さまざまな種類のアプリケーションで使用できます。

### Q2: 購入前に体験版はありますか?

 A2: もちろん、無料トライアルにアクセスできます。[ここ](https://releases.aspose.com/).

### Q3: 追加のサポートやコミュニティのディスカッションはどこで見つけられますか?

 A3: にアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)ディスカッションとサポートのために。

### Q4: Aspose.Page for .NET の一時ライセンスを取得するにはどうすればよいですか?

 A4: 仮免許を取得できます。[ここ](https://purchase.aspose.com/temporary-license/).

### Q5: Aspose.Page for .NET については他にどのようなドキュメントがありますか?

 A5: 包括的なドキュメントを参照してください。[ここ](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
