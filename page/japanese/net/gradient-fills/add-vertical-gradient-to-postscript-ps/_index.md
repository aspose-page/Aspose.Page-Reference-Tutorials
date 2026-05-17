---
date: 2026-02-25
description: C# の線形グラデーションブラシを使用して PS ファイルにグラデーションを追加し、Aspose.Page for .NET で矩形をグラデーションで塗りつぶす方法を学びましょう。
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# リニアグラデーションブラシ – Aspose.Page を使用して PostScript (PS) に垂直グラデーションを追加
url: /ja/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – Aspose.Page を使用して PostScript (PS) に垂直グラデーションを追加

## はじめに

ドキュメントの操作と作成の領域において、**Aspose.Page for .NET** は開発者にとって強力なツールとして際立っています。このガイドでは、**C# linear gradient brush** を使用して **PS** ファイルに **グラデーションを追加** し、**矩形をグラデーションで塗りつぶす** 方法を紹介します。チュートリアルの最後までに、必要なコードのステップバイステップの理解と、この手法が PostScript 出力で滑らかな垂直グラデーションを生成する理由が明確になります。

## クイック回答
- **C# linear gradient brush は何をしますか？** 形状全体にわたって複数の色の間で滑らかな遷移を作成します。
- **任意の .NET バージョンで使用できますか？** はい、Aspose.Page は .NET Framework 4.5+ および .NET Core/5+ をサポートしています。
- **本番環境でライセンスは必要ですか？** 評価版以外のビルドでは商用ライセンスが必要です。
- **グラデーションは本当に垂直ですか？** ブラシは 90° 回転されており、垂直方向の流れが保証されています。
- **出力はどこに保存されますか？** `dataDir` で指定したパスに保存されます（例: `VerticalGradient_outPS.ps`）。

## C# Linear Gradient Brush とは？

**C# linear gradient brush** は、定義されたポイント間で線形の色遷移を描画する GDI+ オブジェクト (`LinearGradientBrush`) です。Aspose.Page の描画 API と組み合わせることで、PostScript (PS) ドキュメントに直接高度なグラデーションをレンダリングできます。

## なぜ PostScript で Linear Gradient Brush を使用するのか？

- **高品質な出力:** グラデーションはプリンターレベルでレンダリングされ、忠実度が保たれます。
- **フルコントロール:** カスタムのカラーストップ、回転、スケーリングを設定できます。
- **再利用可能なコード:** 同じブラシロジックは PDF、SVG、その他 Aspose.Page がサポートするフォーマットでも機能します。

## 前提条件

チュートリアルに入る前に、以下が整っていることを確認してください。

- Aspose.Page for .NET: Aspose.Page ライブラリがインストールされていることを確認してください。必要なリソースとドキュメントは[here](https://reference.aspose.com/page/net/)で見つけられます。
- 開発環境: .NET 開発用の統合開発環境 (IDE) を含む、適切な開発環境をセットアップしてください。
- 基本的な理解: ストリーム、グラフィックパス、カラー操作など、.NET 開発の基本に慣れておいてください。

## 名前空間のインポート

C# プロジェクトのコードファイルの先頭で、必要な名前空間をインクルードします。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 手順 1: ドキュメントディレクトリの設定

PS ドキュメントを保存するディレクトリのパスを指定します。

```csharp
string dataDir = "Your Document Directory";
```

## 手順 2: PostScript ドキュメント用の出力ストリームを作成

`FileStream` クラスを使用して PostScript ドキュメント用の出力ストリームを生成します。

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## 手順 3: 保存オプションと PS ドキュメントを作成

A4 サイズの保存オプションを作成し、1 ページの PS ドキュメントを初期化します。

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 手順 4: 矩形のサイズを定義

垂直グラデーションを適用する矩形の位置とサイズを指定します。

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## 手順 5: グラフィックパスを作成

定義した矩形からグラフィックパスを構築します。

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## 手順 6: 補間色を定義

グラデーション用の補間色と位置の配列を作成します。

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## 手順 7: Linear Gradient Brush を作成

矩形を境界として、開始色と終了色を指定して線形グラデーションブラシを作成します。

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## 手順 8: ブラシの変換を設定

ブラシの変換を設定し、X と Y のスケールコンポーネントが矩形の幅と高さに一致するようにします。

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## 手順 9: ペイントを設定し矩形を塗りつぶす

ドキュメントのペイントを設定し、**fill rectangle with gradient** を使用して先に定義したパスで矩形を塗りつぶします。

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## 手順 10: 現在のページを閉じてドキュメントを保存

現在のページを閉じ、PostScript ドキュメントを保存します。

```csharp
document.ClosePage();
document.Save();
```

おめでとうございます！Aspose.Page for .NET の **C# linear gradient brush** を使用して、**PostScript ドキュメントに垂直グラデーションを追加** できました。さまざまなパラメータやカラーを試して、ドキュメントに多彩なビジュアル効果を実現してください。

## よくある問題と解決策

| 問題 | 発生原因 | 解決方法 |
|------|----------|----------|
| グラデーションが水平に見える | ブラシの回転が適用されていない | `brushTransform.Rotate(90);` が `brush.Transform` に割り当てる前に呼び出されていることを確認してください。 |
| 色がくすんで見える | 低解像度の出力ストリーム | より高解像度の `PsSaveOptions` を使用するか、ドキュメントサイズを大きくしてください。 |
| 出力ファイルが空 | ストリームがフラッシュされていない | `using` ブロックの外で `document.Save();` が呼び出されていることを確認してください。 |

## よくある質問

**Q1: 同じドキュメントの異なる領域に複数のグラデーションを適用できますか？**  
A: はい、可能です。各領域ごとにサイズとカラースキームを指定して手順を繰り返してください。

**Q2: このコードを既存の .NET プロジェクトに統合するにはどうすればよいですか？**  
A: コードをプロジェクトファイルにコピー＆ペーストし、Aspose.Page ライブラリが参照されていることを確認してください。

**Q3: Aspose.Page for .NET で利用できる他のグラデーションタイプはありますか？**  
A: Aspose.Page は放射状やパスグラデーションなど、さまざまなグラデーションタイプをサポートしています。詳細はドキュメントをご参照ください。

**Q4: 商用プロジェクトで Aspose.Page を使用できますか？**  
A: はい、使用可能です。ライセンスオプションは[here](https://purchase.aspose.com/buy)でご確認ください。

**Q5: Aspose.Page のコミュニティフォーラムはありますか？**  
A: もちろんです！[Aspose.Page forum](https://forum.aspose.com/c/page/39) にアクセスして、他の開発者と交流しサポートを受け取ってください。

**最終更新日:** 2026-02-25  
**テスト環境:** Aspose.Page 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}