---
title: Aspose.Page を使用してテクスチャ タイル パターンを PostScript (PS) に適用する
linktitle: テクスチャ タイリング パターンを PostScript に適用する (PS)
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して、テクスチャ タイル パターンで PostScript (PS) ドキュメントを強化します。ステップバイステップのガイドに従って、クリエイティブなタッチを加えてください。
type: docs
weight: 10
url: /ja/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---
## 導入

Aspose.Page for .NET を使用してテクスチャ タイル パターンを PostScript (PS) ドキュメントに適用する方法に関するステップバイステップのチュートリアルへようこそ。 Aspose.Page は、さまざまなドキュメント形式を操作できる強力なライブラリです。このチュートリアルでは、テクスチャ タイル パターンを追加して PS ドキュメントを強化する方法を検討します。

## 前提条件

チュートリアルに入る前に、次のものが揃っていることを確認してください。

- [ビジュアルスタジオ](https://visualstudio.microsoft.com/)あなたのマシンにインストールされています。
- C# プログラミングの基本的な知識。
- ダウンロードしてインストールします[.NET ライブラリの Aspose.Page](https://releases.aspose.com/page/net/).
- テクスチャ パターンの画像ファイル (例: "TestTexture.bmp")。

## 名前空間のインポート

C# コードで、必要な名前空間をインポートしていることを確認してください。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

提供された例を複数のステップに分けて、プロセスをガイドしてみましょう。

## ステップ 1: ドキュメント ディレクトリを設定する

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
```

「Your Document Directory」を PS ドキュメントを保存するパスに置き換えてください。

## ステップ 2: PS ドキュメントの出力ストリームを作成する

```csharp
//PostScript ドキュメントの出力ストリームを作成する
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    //A4サイズで保存オプションを作成する
    PsSaveOptions options = new PsSaveOptions();

    //新しい 1 ページの PS ドキュメントを作成する
    PsDocument document = new PsDocument(outPsStream, options, false);
```

このステップでは、ドキュメント サイズの定義を含め、PS ドキュメントの出力ストリームを設定します。

## ステップ 3: テクスチャ タイリング パターンを適用する

```csharp
//画像ファイルからビットマップオブジェクトを作成する
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    //画像からテクスチャブラシを作成
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //パターンに X 方向のスケーリングを追加します
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    //このテクスチャ ブラシを現在のペイントとして設定します
    document.SetPaint(brush);
}
```

この手順では、画像からテクスチャ ブラシを作成し、それをドキュメントの現在のペイントとして設定します。

## ステップ 4: 長方形のパスを作成して塗りつぶす

```csharp
//長方形のパスを作成する
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

//長方形を塗りつぶす
document.Fill(path);
```

ここでは、長方形のパスを定義し、以前に設定したテクスチャ ブラシで塗りつぶします。

## ステップ 5: ストロークと描画を設定する

```csharp
//現在のペイントを取得する
Brush paint = document.GetPaint();

//赤のストロークを設定します
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

//長方形をストロークします
document.Draw(path);
```

この手順には、ストロークのプロパティを設定し、輪郭を描かれた四角形を描画することが含まれます。

## ステップ 6: テクスチャ パターンでテキストを塗りつぶし、輪郭を描く

```csharp
//テキストをテクスチャパターンで塗りつぶす
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

//テクスチャ パターン付きのアウトライン テキスト
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

最後に、テキストをテクスチャ パターンで塗りつぶして輪郭を描き、ドキュメントの視覚的な魅力を高めます。

## ステップ 7: 文書を保存して閉じる

```csharp
//現在のページを閉じる
document.ClosePage();

//文書を保存する
document.Save();
```

変更を適用するには、必ず現在のページを閉じてドキュメントを保存してください。

## 結論

おめでとう！ Aspose.Page for .NET を使用してテクスチャ タイル パターンを PostScript ドキュメントに適用する方法を学習しました。さまざまな画像やパターンを試して、PS ドキュメントをさらにカスタマイズします。

## よくある質問

### Q1: テクスチャ パターンに他の画像形式を使用できますか?

A1: はい、Aspose.Page はさまざまな画像形式をサポートしています。ライブラリのドキュメントとの互換性を確保します。

### Q2: Aspose.Page は .NET Core と互換性がありますか?

A2: はい、Aspose.Page は .NET Framework と .NET Core の両方と互換性があります。

### Q3: テクスチャ付きの長方形のサイズを調整するにはどうすればよいですか?

 A3: の寸法を変更します。`RectangleF`パス作成時のパラメータ。

### Q4: 1 つのドキュメントに複数のテクスチャ パターンを追加できますか?

A4: はい、異なる画像とパスを使用してプロセスを繰り返すことができます。

### Q5: 追加のリソースやサポートはどこで入手できますか?

 A5: にアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティのサポートを求めて、[ドキュメンテーション](https://reference.aspose.com/page/net/).
