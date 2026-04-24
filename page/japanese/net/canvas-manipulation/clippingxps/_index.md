---
date: 2026-01-05
description: Aspose.Page for .NET を使用して XPS ドキュメントをクリップする方法を学びましょう。このステップバイステップガイドでは、XPS
  ファイルの作成、操作、保存を効率的に行う方法を示します。
linktitle: Clipping XPS
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET を使用して XPS をクリップする方法
url: /ja/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用した XPS のクリッピング方法

## はじめに

Aspose.Page for .NET を使用した **XPS のクリッピング** に関する包括的なチュートリアルへようこそ！本ガイドでは、ライブラリを使って XPS ドキュメントを作成、操作、保存する手順をご案内します。XPS（XML Paper Specification）は標準化されたオープンな文書フォーマットであり、Aspose.Page for .NET は .NET アプリケーション内で XPS ドキュメントを扱うための強力なツールを提供します。

## Quick Answers
- **XPS のクリッピングとは何ですか？** XPS キャンバス要素の表示領域を制限するために、幾何学的マスク（クリップ）を適用します。  
- **どのライブラリが最適ですか？** Aspose.Page for .NET は XPS の作成とクリッピングに対応したフル機能 API を提供します。  
- **前提条件は？** Visual Studio、.NET ランタイム、そして Aspose.Page for .NET ライブラリ。  
- **実装にどれくらい時間がかかりますか？** 基本的なクリッピングシナリオでおおよそ 10〜15 分です。  
- **本番環境で使用できますか？** はい、有効な Aspose ライセンス（トライアルあり）を使用すれば問題ありません。

## 「XPS のクリッピング」とは？
XPS のクリッピングは、**クリップジオメトリ**（例: 円や矩形）を定義し、キャンバスに割り当てることで機能します。そのジオメトリの外側に描画されたものはレンダリングされず、マスクされた画像やカスタム形状、フォーカスされたコンテンツ領域など、洗練されたページレイアウトを作成できます。

## なぜ Aspose.Page for .NET で XPS をクリップするのか？
- **キャンバス変換、パスジオメトリ、ブラシ** をフルコントロールできます。  
- **外部依存関係なし** – すべて .NET アプリケーション内部で完結します。  
- **クロスプラットフォーム** – .NET Framework、.NET Core、.NET 5/6+ をサポート。  
- **高性能** – 軽量 API で有効な XPS ファイルを高速に生成します。

## 前提条件

作業を始める前に、以下が揃っていることを確認してください。

- ご使用のマシンに Visual Studio がインストールされていること。  
- プロジェクトに Aspose.Page for .NET ライブラリを追加済みであること。ダウンロードは [here](https://releases.aspose.com/page/net/) から可能です。  
- C# の基本的なプログラミング知識。

## 名前空間のインポート

Aspose.Page for .NET の機能を使用するには、必要な名前空間をプロジェクトにインポートする必要があります。以下の手順に従ってください。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

それでは、提供されたサンプルコードを複数のステップに分解して説明します。

## Step 1: Set the document directory path.

```csharp
string dataDir = "Your Document Directory";
```

**「Your Document Directory」** を実際のドキュメントディレクトリへのパスに置き換えてください。

## Step 2: Create a new XPS Document.

```csharp
XpsDocument doc = new XpsDocument();
```

これにより、作業対象となる新しい XPS ドキュメントが作成されます。

## Step 3: Create the main canvas.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

このステップでは、すべてのページ要素で共通に使用するメインキャンバスを作成します。

## Step 4: Set left and top offsets in the main canvas.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

必要に応じて左・上オフセットを調整してください。

## Step 5: Create a rectangle path geometry.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

矩形用のパスジオメトリを作成します。

## Step 6: Create a fill for rectangles.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

矩形の塗りつぶしカラーを定義します。

## Step 7: Add another canvas with clip to the main canvas.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

メインキャンバスに、クリップ付きの別キャンバスを追加します。

## Step 8: Create a circle geometry for clip.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

円形のクリップジオメトリを作成し、2 番目のキャンバスに適用します。

## Step 9: Create a rectangle in the second canvas and fill it.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

2 番目のキャンバス内に矩形を作成し、塗りつぶします。

## Step 10: Add the second canvas with a stroked rectangle to the main canvas.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

メインキャンバスに、枠線付き矩形を持つ 2 番目のキャンバスを追加します。

## Step 11: Create a rectangle in the third canvas and stroke it.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

3 番目のキャンバスに矩形を作成し、枠線を設定します。

## Step 12: Save the resultant XPS document.

```csharp
doc.Save(dataDir + "output2.xps");
```

指定したディレクトリに XPS ドキュメントを保存します。

## よくある問題と解決策
- **パスが無効** – `dataDir` の末尾にバックスラッシュ（`\\`）が付いているか、`Path.Combine` を使用してください。  
- **クリップが適用されない** – クリップジオメトリ文字列が正しく構成されているか確認してください。スペースが欠落するとクリップが無視されることがあります。  
- **ライセンス例外** – 評価版でないビルドの場合、ドキュメント作成前に有効な Aspose ライセンスを追加してランタイム例外を防止してください。

## Frequently Asked Questions

### Q1: Aspose.Page for .NET を他のドキュメント形式と併用できますか？

A1: Aspose.Page for .NET は主に XPS ドキュメントに特化していますが、Aspose には他のドキュメント形式向けのライブラリも多数提供されています。

### Q2: Aspose.Page for .NET は初心者に適していますか？

A2: はい、Aspose.Page for .NET はユーザーフレンドリーに設計されており、初心者でも公式ドキュメントを参照すればすぐに機能を把握できます。

### Q3: もっと多くのサンプルやリソースはどこで入手できますか？

A3: 詳細なリソースやサンプルは [documentation](https://reference.aspose.com/page/net/) と [Aspose.Page forum](https://forum.aspose.com/c/page/39) をご覧ください。

### Q4: Aspose.Page for .NET の一時ライセンスはどのように取得できますか？

A4: 一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

### Q5: Aspose.Page for .NET の無料トライアルはありますか？

A5: はい、無料トライアルは [here](https://releases.aspose.com/) からダウンロードできます。

## Additional Frequently Asked Questions

**Q: 1 つのキャンバスに複数のクリップジオメトリを組み合わせられますか？**  
A: はい、`Clip` プロパティに複数のサブパスを含む複合 `PathGeometry` を割り当てることで、階層的なマスクが可能です。

**Q: クリッピングは PDF 変換に影響しますか？**  
A: 後で Aspose.PDF を使用して XPS を PDF に変換する際、クリップジオメトリは保持されるため、視覚的な結果は同一です。

**Q: XPS でクリッピングをアニメーション化できますか？**  
A: XPS 自体はアニメーションをサポートしていませんが、異なるクリップ形状を持つ複数の XPS ページを生成して順次表示することで、疑似的な動きを表現できます。

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}