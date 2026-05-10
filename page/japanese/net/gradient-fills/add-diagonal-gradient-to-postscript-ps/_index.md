---
date: 2026-02-23
description: PostScript ファイルにグラデーションを追加し、A4 用紙サイズで PostScript ファイルを保存し、Aspose.Page
  for .NET を使用して矩形にグラデーションを塗りつぶす方法を学びましょう。
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Aspose.Page .NET を使用した PostScript (PS) での対角線グラデーションの追加方法
url: /ja/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

 exactly.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page .NET を使用した PostScript (PS) への対角グラデーションの追加方法

## はじめに

PostScript (PS) ドキュメントに対角グラデーションを追加すると、特に技術レポートやパンフレット、グラフィックが多用されるアプリケーションで **how to add gradient** 効果が必要な場合に、視覚的な魅力が大幅に向上します。このチュートリアルでは、Aspose.Page for .NET を使用して PostScript ファイルにグラデーションを追加し、A4 ページサイズを設定し、矩形を滑らかな色の遷移で塗りつぶす方法を正確に解説します。

## クイック回答
- **必要なライブラリは？** Aspose.Page for .NET  
- **サポートされている .NET バージョンは？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **グラデーションの方向を変更できますか？** はい – コードに示すようにブラシの変換を回転させます  
- **結果はどうやって保存しますか？** `PsDocument.Save()` を使用し、PostScript ファイルをディスクに書き込みます  
- **本番環境でライセンスは必要ですか？** はい、商用ライセンスで全機能が利用可能になります  

## PostScript における対角グラデーションとは？

対角グラデーションは、形状全体に対して角度（通常は 45°）で走る線形の色遷移です。PostScript では、`LinearGradientBrush` にカスタム変換行列を適用し、グラデーションを回転、スケーリング、平行移動させて目的の矩形に合わせることで実現します。

## グラデーション塗りに Aspose.Page を使用する理由は？

Aspose.Page は低レベルの PostScript コマンドを抽象化し、馴染みのある .NET グラフィックオブジェクトで操作できるようにします。複雑な塗りつぶしを作成し、ページサイズを設定し、**save PostScript file** に直接エクスポートできるため、生の PS 構文を扱う必要がありません。

## 前提条件

- **Aspose.Page for .NET ライブラリ** – [here](https://releases.aspose.com/page/net/) からダウンロードしてください。  
- **Document Directory** – 生成された `*.ps` ファイルが書き込まれるフォルダーです。

基本は以上ですので、実装手順をステップごとに見ていきましょう。

## 名前空間のインポート

まず、EPS デバイス、描画ユーティリティ、I/O クラスにアクセスできる名前空間をインポートします。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ステップ 1: PostScript ドキュメント用の出力ストリームを作成 (Create PostScript Document)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## ステップ 2: A4 ページサイズの設定 (Save Options)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## ステップ 3: 新しい 1 ページの PS ドキュメントを作成

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## ステップ 4: 矩形パラメータの定義

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## ステップ 5: グラフィックパスの作成

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## ステップ 6: Linear Gradient Brush の作成 (矩形のグラデーション塗り)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## ステップ 7: ブラシ用変換の作成

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## ステップ 8: ブラシに変換を適用 (回転、スケール、平行移動)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## ステップ 9: ブラシに変換を設定

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## ステップ 10: ペイントを設定し矩形を塗りつぶす

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## ステップ 11: 現在のページを閉じる

```csharp
	//Close current page
	document.ClosePage();
```

## ステップ 12: ドキュメントを保存 (Save PostScript File)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## PostScript ファイルの保存方法

`PsDocument.Save()` 呼び出しは、**ステップ 1** で開いたストリームに完全な PostScript コンテンツを書き込みます。`using` ブロックが完了すると、`DiagonaGradient_outPS.ps` ファイルが指定したディレクトリに作成されます。

## 主な使用例

- **技術文書** で、さりげない背景シェーディングが必要な場合。  
- **マーケティングパンフレット** で、対角グラデーションがモダンな外観を加える場合。  
- **自動レポートジェネレータ** で、即座に印刷可能な PS ファイルを生成する場合。

## トラブルシューティングとヒント

- **色が正しくない** – `LinearGradientBrush` に渡す ARGB 値を再確認してください。  
- **グラデーションが表示されない** – 変換行列が正しく回転・スケーリングされているか確認してください。`Rotate(-45)` 呼び出しが対角角度を設定します。  
- **ファイルが作成されない** – `dataDir` が既存のフォルダーを指しているか、アプリケーションに書き込み権限があるか確認してください。

## よくある質問

**Q: Aspose.Page はすべての .NET フレームワークと互換性がありますか？**  
A: Aspose.Page は .NET Framework 4.5+ から .NET 6+ まで幅広い .NET バージョンをサポートしており、広範な互換性を提供します。

**Q: Aspose.Page でグラデーションの色をカスタマイズできますか？**  
A: はい、`LinearGradientBrush` を作成する際に任意の ARGB カラーを指定でき、開始色と終了色を完全にコントロールできます。

**Q: Aspose.Page のトライアル版はありますか？**  
A: はい、[here](https://releases.aspose.com/) からトライアル版をダウンロードして Aspose.Page の機能を試すことができます。

**Q: Aspose.Page の一時ライセンスはどこで取得できますか？**  
A: 評価期間中に追加機能を有効にするための一時ライセンスは、[here](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.Page のコミュニティサポートはどこで見つけられますか？**  
A: サポートやディスカッションは、[forum](https://forum.aspose.com/c/page/39) で Aspose.Page コミュニティに参加してください。

---

**最終更新日:** 2026-02-23  
**テスト環境:** Aspose.Page for .NET (最新の安定版リリース)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}