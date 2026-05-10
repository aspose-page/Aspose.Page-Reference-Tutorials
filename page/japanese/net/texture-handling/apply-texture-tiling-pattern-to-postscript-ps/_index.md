---
date: 2026-03-26
description: Aspose.Page を使用して、テクスチャタイルパターンを用いた .NET の PostScript ドキュメントの作成方法を学びましょう。ステップバイステップのガイドに従って、PS
  ファイルに豊かなテクスチャを追加してください。
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: テクスチャタイルを使用したPostScript .NETドキュメントの作成
url: /ja/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# テクスチャタイルで PostScript .NET ドキュメントを作成する

## テクスチャタイルで PostScript ドキュメント .NET を作成する方法

このチュートリアルでは、**PostScript ドキュメント .NET** を作成し、Aspose.Page ライブラリを使用してテクスチャタイルパターンで装飾する方法を学びます。プロジェクトのセットアップからテクスチャブラシでテキストを塗りつぶし・ストロークするまでの各ステップを順に解説するので、数分で視覚的に魅力的な PS ファイルを作成できます。

## クイック回答
- **使用されているライブラリは？** Aspose.Page for .NET  
- **.NET Core を使用できますか？** はい、ライブラリは .NET Core と .NET 5/6 をサポートしています  
- **テクスチャに使用できる画像形式は？** System.Drawing がサポートするすべての形式 (BMP、PNG、JPEG など) が使用可能です  
- **実装にかかる時間は？** 基本的な例で約10〜15分です  
- **ライセンスは必要ですか？** テストには無料トライアルで動作しますが、製品版ではライセンスが必要です  

## 前提条件

- [Visual Studio](https://visualstudio.microsoft.com/) がマシンにインストールされていること。  
- C# プログラミングの基本知識。  
- [Aspose.Page for .NET library](https://releases.aspose.com/page/net/) をダウンロードしてインストールする。  
- テクスチャパターン用の画像ファイル (例: **TestTexture.bmp**)。  

## 名前空間のインポート

C# ファイルで必要な名前空間をインポートし、コンパイラが使用する型を認識できるようにします:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 手順 1: ドキュメントディレクトリの設定

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

**Your Document Directory** を、生成した PS ファイルを保存したいフォルダーに置き換えてください。

## 手順 2: PS ドキュメント用の出力ストリームを作成する

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

このブロックはファイルストリームを開き、ページサイズ (デフォルトは A4) を設定し、描画対象となる新しい **PsDocument** インスタンスを作成します。

## 手順 3: テクスチャタイルパターンを適用する

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

ここではビットマップを読み込み、**TextureBrush** にラップし、必要に応じて水平方向に伸ばし、以降の描画操作で **PsDocument** がこのブラシを使用するよう指示します。

## 手順 4: 四角形パスを作成して塗りつぶす

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

シンプルな四角形を定義し、先ほど設定したテクスチャブラシで塗りつぶします。

## 手順 5: ストロークを設定して描画する

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

現在のペイント (テクスチャブラシ) を取得し、輪郭用に赤いペンを作成して四角形の枠線を描画します。

## 手順 6: テクスチャパターンでテキストを塗りつぶしストロークする

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

このステップでは **fill and stroke text** 機能を示します。文字列 “ABC” がテクスチャブラシで塗りつぶされ、続いて輪郭が描かれ、印象的なビジュアル効果が得られます。

## 手順 7: ドキュメントを保存して閉じる

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

ページを閉じることで描画コマンドが確定し、`Save()` が PostScript ファイルをディスクに書き込みます。

## よくある問題と解決策

- **テクスチャが不自然に伸びている** – `Matrix` の値を調整して X/Y のスケーリングを制御します。  
- **画像が見つからない** – `dataDir` が正しいフォルダーを指しているか、ファイル名が大文字小文字を含めて完全に一致しているか確認してください。  
- **色がずれて見える** – PostScript はデバイス非依存のカラースペースを使用することを覚えておき、`Color` オブジェクトが正しくマッピングされているか確認してください。  

## よくある質問

**Q:** テクスチャパターンに他の画像形式を使用できますか？  
**A:** はい、`System.Drawing.Bitmap` がサポートするすべての形式 (BMP、PNG、JPEG、GIF など) が使用可能です。

**Q:** Aspose.Page は .NET Core と互換性がありますか？  
**A:** もちろんです。ライブラリは .NET Framework、.NET Core、.NET 5/6 で動作します。

**Q:** テクスチャ付き四角形のサイズを変更するには？  
**A:** 四角形作成ステップの `RectangleF` の値を変更します (例: `new RectangleF(0, 0, 300, 150)`)。

**Q:** 1つのドキュメントで複数のテクスチャパターンを適用できますか？  
**A:** はい。別の画像で新しい `TextureBrush` を作成し、次の図形やテキストを描画する前に再度 `SetPaint` を呼び出すだけです。

**Q:** もっと例や API リファレンスはどこで見つけられますか？  
**A:** コミュニティサポートは [Aspose.Page Forum](https://forum.aspose.com/c/page/39) を、詳細な API 使用法は公式 [documentation](https://reference.aspose.com/page/net/) をご覧ください。

## 結論

これで **PostScript ドキュメント .NET** を作成し、テクスチャタイルパターンを適用する方法、さらにそのテクスチャで **テキストを塗りつぶしストローク** する方法が分かりました。さまざまな画像やスケーリング行列、描画プリミティブを試して、レポートやチラシ、グラフィックが多用される出力向けにカスタムスタイルの PS ファイルを作成してみてください。

---

**最終更新:** 2026-03-26  
**テスト済み:** Aspose.Page 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}