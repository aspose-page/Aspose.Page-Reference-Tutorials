---
date: 2026-03-29
description: Aspose.Page for .NET を使用して、PostScript で疑似透明効果を作成するための C# の線形グラデーションブラシの使い方を学びましょう。
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: PSでの疑似透明性のためのC#リニアグラデーションブラシ
url: /ja/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript (PS) における疑似透過のための Linear Gradient Brush C#

## はじめに

PostScript (PS) ファイルにさりげない透過効果を追加したい場合、**linear gradient brush C#** が最適なツールです。Aspose.Page for .NET を使用すると、不透明および半透明のグラデーション塗りつぶしで矩形を描画でき、ドキュメントにモダンでレイヤードな外観を与えることができます。このチュートリアルでは、C# の linear gradient brush を使用して疑似透過を作成するために必要な正確な手順を順を追って説明します。

## クイック回答
- **linear gradient brush を提供するライブラリは何ですか？** Aspose.Page for .NET
- **どのグラフィックスクラスがグラデーションを作成しますか？** `LinearGradientBrush`
- **色ごとに不透明度を制御できますか？** はい、`Color.FromArgb(alpha, …)` を使用します
- **本番環境でライセンスが必要ですか？** 有効な Aspose.Page ライセンスが必要です
- **サポートされている .NET バージョンは？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+

## linear gradient brush C# とは？

`LinearGradientBrush` は、直線に沿って2色間の滑らかな遷移を描画する GDI+ オブジェクトです。各色のアルファチャンネル (0‑255) を指定することで、半透明のグラデーションを作成でき、これが PostScript における疑似透過に必要なものです。

## 疑似透過のために linear gradient brush C# を使用する理由は？

- **細かな不透明度制御:** 各色のアルファ値を調整して目的の透過レベルを実現します。  
- **デバイスに依存しないレンダリング:** ブラシは画面、PDF、EPS、PS の出力で同じように機能します。  
- **シンプルな API:** 数行の C# コードでプロフェッショナルな視覚効果を生成できます。

## 前提条件

コードに取り掛かる前に、以下が揃っていることを確認してください。

- Aspose.Page for .NET がインストールされていること。[Aspose.Page documentation](https://reference.aspose.com/page/net/) からダウンロードできます。
- 生成された PostScript ドキュメントを保存する書き込み可能なフォルダーがあること。

必要なツールが揃ったので、疑似透過矩形の作成を始めましょう。

## 名前空間のインポート

開始する前に、使用するクラスが含まれる名前空間をインポートします:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 手順 1: PostScript ドキュメント用の出力ストリームを作成する

結果の PS ファイルを保持するファイルストリームを作成し、`PsDocument` を初期化します。

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## 手順 2: **不透明** グラデーション塗りつぶしの矩形を作成する

ここでは、色が完全に不透明 (alpha = 255) の `LinearGradientBrush` を構築します。この矩形は背景レイヤーとして機能します。

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## 手順 3: **半透明** グラデーション塗りつぶしの矩形を作成する

今回は alpha 値が 255 未満 (例: 150 と 50) の **linear gradient brush C#** を使用します。これにより矩形が部分的に透け、疑似透過効果が得られます。

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## 手順 4: ページを閉じてドキュメントを保存する

最後にページを終了し、PS ファイルをディスクに書き込みます。

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

これらの 4 つの手順に従うことで、不透明矩形と半透明矩形をシームレスにブレンドし、任意の PostScript 出力で説得力のある疑似透過効果を実現できます。

## よくある問題と解決策

| 問題 | 発生原因 | 対策 |
|------|----------|------|
| 色が完全に不透明に見える | アルファ値が誤って 255 に設定されている | `alpha` < 255 の `Color.FromArgb(alpha, …)` を使用する |
| グラデーションが正しく伸びていない | 変換行列が正しくない | 行列パラメータが矩形の寸法と一致しているか確認する |
| 出力ファイルが空です | ストリームが閉じられていない、または `Save()` が呼び出されていない | `using` ブロック内で `document.ClosePage()` と `document.Save()` が実行されていることを確認する |

## よくある質問

**Q: Aspose.Page はすべての .NET バージョンと互換性がありますか？**  
A: Aspose.Page for .NET はさまざまな .NET フレームワークのバージョンと互換性があり、柔軟性と統合の容易さを提供します。

**Q: 矩形以外の他の形状にも疑似透過を適用できますか？**  
A: はい、同じ原理を使用して `GraphicsPath` を調整すれば任意の形状に適用できます。

**Q: 追加のサンプルやドキュメントはどこで見つけられますか？**  
A: 包括的なサンプルと詳細な API リファレンスは [Aspose.Page documentation](https://reference.aspose.com/page/net/) をご覧ください。

**Q: Aspose.Page の無料トライアルは利用できますか？**  
A: はい、[this link](https://releases.aspose.com/) から Aspose.Page の無料トライアルにアクセスできます。

**Q: Aspose.Page の一時ライセンスはどのように取得できますか？**  
A: [this link](https://purchase.aspose.com/temporary-license/) で Aspose.Page の一時ライセンスを取得できます。

---

**最終更新日:** 2026-03-29  
**テスト環境:** Aspose.Page 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}