---
date: 2026-04-03
description: Aspose.Page を使用して .NET で透明な矩形を追加し、Grid Visual Brush を適用して、見事な XPS ドキュメントを作成する方法を学びましょう。
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: グリッド ビジュアル ブラシを適用
second_title: Aspose.Page .NET API
title: Grid Visual Brush を使用して透明な矩形を追加する (.NET)
url: /ja/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Grid Visual Brush (.NET) を使用して透明な矩形を追加する

## はじめに

XPS ドキュメントに **透明な矩形を追加** し、スタイリッシュな Grid Visual Brush を適用したい場合、ここが最適です。このチュートリアルでは Aspose.Page for .NET を使用した正確な手順を順に説明しますので、視覚的にリッチなドキュメントを作成できます。最後まで実行可能な完全なサンプルが得られ、両方の手法を単一の分かりやすいワークフローで示します。

## クイック回答
- **透明な矩形は何をするのですか？** 半透明のオーバーレイを追加し、背景のコンテンツが透過して表示されます。  
- **どの API がブラシを作成しますか？** `XpsDocument.CreateVisualBrush` が Grid Visual Brush を構築します。  
- **ライセンスは必要ですか？** 無料トライアルでテストは可能ですが、製品版には商用ライセンスが必要です。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **実装にどれくらい時間がかかりますか？** 基本的な例で約 10〜15 分です。

## XPS における透明な矩形とは何か

透明な矩形は、塗りつぶし色に 1.0 未満のアルファ成分が含まれる単純な形状で、下層のグラフィックが部分的に見えるようになります。背景を完全に隠すことなくセクションを強調表示するのに最適です。

## なぜ Grid Visual Brush を使用するのか

Grid Visual Brush は、小さなベクター画像を大きな領域にタイル状に配置でき、グリッドやハッチ、カスタムテクスチャなどのパターンを作成します。これを透明な矩形と組み合わせることで、軽量かつ解像度に依存しないレイヤードビジュアル効果が得られます。

## 前提条件

Before diving into the code, make sure you have:

- **Aspose.Page for .NET** – ダウンロードは [here](https://releases.aspose.com/page/net/) からできます。  
- .NET 開発環境 (Visual Studio、VS Code、またはお好みの IDE)。  
- 生成された XPS ファイルを保存するフォルダー。

## 名前空間のインポート

In your C# file, import the required namespaces:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

それでは、解決策を明確な番号付きステップに分解しましょう。

## ステップ 1: XpsDocument の初期化

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

`XpsDocument` インスタンスを作成します。これが以降のすべての描画操作を保持します。

## ステップ 2: マゼンタ グリッドジオメトリの作成

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

このジオメトリは、Visual Brush が塗りつぶすグリッドの輪郭を定義します。

## ステップ 3: マゼンタ グリッド VisualBrush の設計

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

ここでは、グリッド全体に繰り返される小さなマゼンタタイルを描画します。

## ステップ 4: VisualBrush をグリッドに適用

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

`CreateVisualBrush` 呼び出しにより、マゼンタタイルがグリッドジオメトリに結び付けられ、タイル化が有効になります。

## ステップ 5: グリッドをキャンバスに追加

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

タイル化されたグリッドをキャンバスに配置し、平行移動変換を適用して目的の位置に表示させます。

## ステップ 6: 透明な矩形を追加

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

このステップでは **透明な矩形を追加** します（`Opacity = 0.7f` の赤い形状）。不透明度の値を調整して、矩形の透過度を制御します。

## ステップ 7: ドキュメントを保存

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

XPS ファイルは、先に指定したフォルダーに書き込まれます。

## 一般的な使用例

- **レポートのハイライト:** グラフや表を強調するために半透明の矩形をオーバーレイします。  
- **透かし効果:** タイル化されたグリッドと透明なオーバーレイを組み合わせて、さりげないブランディングを実現します。  
- **インタラクティブ PDF/XPS:** パターンをフォームフィールドの背景として使用し、UI の可読性を保ちます。

## トラブルシューティングのヒント

- **不透明度が表示されませんか？** ビューアが XPS の透明性をサポートしていることを確認してください。古いビューアの中には `Opacity` プロパティを無視するものがあります。  
- **タイルサイズが正しくありませんか？** ソース矩形 (`new RectangleF(0f, 0f, 10f, 10f)`) がベクタタイルの寸法と一致しているか確認してください。  
- **ファイルが保存されませんか？** `dataDir` が存在し、書き込み可能なディレクトリを指しているか再確認してください。

## よくある質問

**Q: Aspose.Page for .NET を Web とデスクトップの両方のアプリケーションで使用できますか？**  
A: はい、このライブラリはすべての .NET アプリケーションタイプで動作します。

**Q: 購入前に試用版はありますか？**  
A: もちろん、無料トライアルは [here](https://releases.aspose.com/) から利用できます。

**Q: 追加のサポートやコミュニティディスカッションはどこで見つけられますか？**  
A: コミュニティや Aspose エンジニアからの支援は [Aspose.Page Forum](https://forum.aspose.com/c/page/39) をご覧ください。

**Q: 評価用の一時ライセンスはどのように取得できますか？**  
A: 一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.Page for .NET の他のドキュメントはどこにありますか？**  
A: 包括的なドキュメントは [here](https://reference.aspose.com/page/net/) でご確認ください。

---

**最終更新日:** 2026-04-03  
**テスト環境:** Aspose.Page 24.12 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}