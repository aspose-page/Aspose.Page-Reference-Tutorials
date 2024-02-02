---
title: Aspose.Page を使用して PostScript (PS) で擬似透明性を表示する
linktitle: PostScript で擬似透明性を表示する (PS)
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して、PostScript の擬似透明性の力を試してください。視覚的に美しいドキュメントを作成するには、ステップバイステップのガイドに従ってください。
type: docs
weight: 13
url: /ja/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---
## 導入

疑似透明機能を組み込むことで、PostScript (PS) ドキュメントの視覚的な魅力を強化したいと考えていますか? Aspose.Page for .NET は、この効果を簡単に実現する強力なソリューションを提供します。このステップバイステップのチュートリアルでは、Aspose.Page を使用して PostScript で擬似透明性を表示するプロセスを説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

- Aspose.Page for .NET: Aspose.Page for .NET ライブラリがインストールされていることを確認します。からダウンロードできます。[Aspose.Page ドキュメント](https://reference.aspose.com/page/net/).

- ドキュメント ディレクトリ: PostScript ドキュメントを保存するディレクトリを設定します。

必要なツールが揃ったので、Aspose.Page を使用して PostScript で擬似透明性を表現する方法を見てみましょう。

## 名前空間のインポート

例を詳しく調べる前に、必要な名前空間をインポートしていることを確認してください。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ステップ 1: PostScript ドキュメントの出力ストリームを作成する

```csharp
//例開始:1
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
//PostScript ドキュメントの出力ストリームを作成する
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//A4サイズで保存オプションを作成する
	PsSaveOptions options = new PsSaveOptions();

	//新しい 1 ページの PS ドキュメントを作成する
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## ステップ 2: 不透明なグラデーション塗りつぶしを使用して長方形を作成する

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

## ステップ 3: 半透明のグラデーション塗りつぶしを使用して長方形を作成する

```csharp
	offsetX = 350;

	//最初の四角形からグラフィックス パスを作成します
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//透明度が 255 ではなく、150 と 50 の線形グラデーション ブラシ カラーを作成します。つまり、半透明になります。
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## ステップ 4: 現在のページを閉じてドキュメントを保存する

```csharp
	document.ClosePage();
	document.Save();
}
//拡張終了:1
```

これらの手順に従うことで、Aspose.Page for .NET を使用して擬似透明性を PostScript ドキュメントにシームレスに統合できます。

## 結論

結論として、Aspose.Page for .NET は、PostScript ドキュメントの視覚要素を強化する簡単かつ効率的な方法を提供します。上記で概説した手順は、擬似透明性を組み込むための明確な道筋を提供し、視覚的に素晴らしい出力を作成できるようにします。

## よくある質問

### Q1: Aspose.Page は、.NET のすべてのバージョンと互換性がありますか?

A1: Aspose.Page for .NET は、.NET Framework のさまざまなバージョンと互換性があり、柔軟性と統合の容易さを保証します。

### Q2: 長方形以外の形状にも疑似透明を適用できますか?

A2: はい、GraphicsPath を適宜調整することで、同じ原則を他の形状にも適用できます。

### Q3: 追加の例やドキュメントはどこで入手できますか?

 A3: を探索してください。[Aspose.Page ドキュメント](https://reference.aspose.com/page/net/)包括的な例と詳細なドキュメントについては、こちらをご覧ください。

### Q4: Aspose.Page に利用できる無料トライアルはありますか?

 A4: はい、次のサイトから Aspose.Page の無料トライアルにアクセスできます。[このリンク](https://releases.aspose.com/).

### Q5: Aspose.Page の一時ライセンスを取得するにはどうすればよいですか?

 A5: 訪問[このリンク](https://purchase.aspose.com/temporary-license/) Aspose.Page の一時ライセンスを取得します。