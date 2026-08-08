---
date: 2026-03-26
description: Aspose.Page for .NET を使用して、XPS ドキュメントで不透明度マスクを設定し、複数の不透明度マスクを適用する方法を学びましょう。
linktitle: Set Opacity Mask in XPS Document
second_title: Aspose.Page .NET API
title: .NET 用 Aspose.Page で XPS ドキュメントに複数の不透明度マスクを設定する
url: /ja/net/transparency-effects/set-opacity-mask-in-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS ドキュメントで Aspose.Page for .NET を使用して複数の不透明度マスクを設定する

## はじめに

不透明度マスクを使用すると、任意のビジュアル要素の透明度を制御できます。**複数の不透明度マスク** を組み合わせることで、XPS ドキュメントを際立たせる高度なレイヤー効果を実現できます。このチュートリアルでは、**形状に不透明度マスクを設定する方法** を解説し、複数のマスクを組み合わせてよりリッチなビジュアル結果を得る手順を示します。最後には、数行の C# コードで任意の XPS 要素に 1 つまたは複数の不透明度マスクを追加できるようになります。

## クイック回答
- **不透明度マスクとは何ですか？** 形状のピクセル単位の透明度を定義するビットマップ、グラデーション、または単色ブラシです。  
- **なぜ複数の不透明度マスクを使用するのですか？** マスクを重ねることで、単一のマスクでは実現できない複雑な透明パターンを作成できます。  
- **どのライブラリがこれをサポートしていますか？** Aspose.Page for .NET は XPS グラフィックス上の不透明度マスクをフルサポートしています。  
- **ライセンスは必要ですか？** 開発目的であれば無料トライアルで動作しますが、製品環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## “複数の不透明度マスク” とは？
複数の不透明度マスクとは、1 つ以上のマスクを順次またはレイヤー状に適用し、各マスクが最終的な透明度マップに寄与する手法です。このアプローチは、画像編集ツールを使わずにグラデーション、テクスチャ、パターン化された透明度を作成するのに便利です。

## なぜ Aspose.Page for .NET を使用して不透明度マスクを設定するのか？
- **フル XPS 機能セット** – すべての XPS グラフィック機能がクリーンな .NET API で提供されます。  
- **外部依存なし** – 追加の画像処理ライブラリは不要で、XPS オブジェクトを直接操作できます。  
- **パフォーマンス最適化** – 大規模ドキュメントや高解像度マスクも効率的に処理します。  

## 前提条件

チュートリアルに入る前に、以下の前提条件を満たしていることを確認してください。

- Aspose.Page for .NET: ライブラリがインストールされていることを確認してください。未インストールの場合は、[website](https://releases.aspose.com/page/net/) からダウンロードできます。  
- Document Directory: XPS ドキュメントを保存するディレクトリを用意してください。

## 名前空間のインポート

.NET プロジェクトで、必要な名前空間をインポートします。

```csharp
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using Aspose.Page.Xps.XpsModel.Shapes;
using Aspose.Page.Xps.XpsModel.Text;
using System.Drawing;
```

## 手順 1: 新しい XPS ドキュメントを作成する

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Aspose.Page for .NET を使用して新しい XPS ドキュメントを作成します。

## 手順 2: XpsDocument インスタンスに Canvas を追加する

```csharp
// Add Canvas to XpsDocument instance
XpsCanvas canvas = doc.AddCanvas();
```

XPS ドキュメントに Canvas を追加します。Canvas はさまざまなグラフィック要素のコンテナとして機能します。

## 手順 3: 不透明度マスク付きの矩形を追加する

```csharp
// Rectangle with opacity masked by ImageBrush
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.OpacityMask = doc.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)path.OpacityMask).TileMode = XpsTileMode.Tile;
```

Canvas に矩形を追加し、`OpacityMask` プロパティで不透明度を設定します。この例では画像を不透明度マスクとして使用しています。別のブラシを使用して同じ形状に **複数の不透明度マスク** を適用すれば、レイヤー化された透明効果を実現できます。

## 手順 4: 結果の XPS ドキュメントを保存する

```csharp
// Save resultant XPS document
doc.Save(dataDir + "OpacityMask_out.xps");
```

不透明度マスクが適用された XPS ドキュメントを保存します。

## 複数の不透明度マスクの一般的な使用例
- **透かし** – テキストマスクとパターンマスクを組み合わせて半透明の透かしを作成します。  
- **テーママップ** – ラスター画像の上にグラデーションマスクを重ね、特定領域を強調表示します。  
- **ブランディング** – ロゴ画像マスクとカラーグラデーションマスクを組み合わせ、洗練されたブランド要素を作成します。

## トラブルシューティングとヒント
- **マスクの位置合わせ** – ソース矩形のサイズが対象形状と一致していることを確認し、伸びや歪みを防ぎます。  
- **TileMode** – `XpsTileMode.Tile` または `XpsTileMode.None` を試して、マスクの繰り返し方法を制御します。  
- **パフォーマンス** – 同じマスクを複数要素に適用する場合は、`XpsImageBrush` インスタンスを再利用してください。

## FAQ

### Q1: 矩形以外の形状にも不透明度マスクを適用できますか？

A1: はい、Aspose.Page for .NET は円形、ポリゴン、カスタムパスなど、さまざまな形状に不透明度マスクを適用できます。

### Q2: 不透明度マスクは画像に限定されていますか？

A2: いいえ、このチュートリアルでは画像を使用しましたが、単色、グラデーション、パターンなどもマスクとして利用可能です。

### Q3: 不透明度レベルを細かく調整する高度なオプションはありますか？

A3: もちろんです。Aspose.Page for .NET は不透明度設定に対する詳細なコントロールを提供し、正確な透明効果を実現できます。

### Q4: 1 つの要素に複数の不透明度マスクを適用できますか？

A4: はい、複数の不透明度マスクをレイヤー化して、複雑な透明効果を作り出すことができます。

### Q5: Aspose.Page は他のドキュメント形式にも対応していますか？

A5: Aspose.Page は主に XPS ドキュメントに特化していますが、Aspose はさまざまな形式を扱う製品群を提供しています。

**追加の質問**

**Q: 同じ形状に 2 つの異なるマスクを組み合わせるにはどうすればよいですか？**  
A: 2 つの `XpsImageBrush`（またはグラデーションブラシ）オブジェクトを作成し、1 つを `OpacityMask` に割り当てた後、形状を `XpsCanvas` でラップし、2 番目のマスクをその Canvas に適用します。

**Q: API はアニメーション化された不透明度の変化をサポートしていますか？**  
A: XPS 自体はアニメーションをサポートしていませんが、マスクの不透明度を変化させた複数の XPS ページを生成することで、アニメーション効果をシミュレートできます。

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.Page for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}