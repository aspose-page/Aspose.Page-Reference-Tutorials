---
date: 2026-02-25
description: Aspose.Page for .NET を使用して、線形グラデーション矩形で PostScript ドキュメントを強化しましょう。ステップバイステップのガイドに従って、グラデーション塗りつぶしテキストとアウトラインテキストのグラデーションの方法を学びましょう。
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Aspose.Page を使用して PostScript (PS) に線形グラデーション矩形を追加する
url: /ja/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用して PostScript (PS) に線形グラデーション矩形を追加する

## はじめに

Aspose.Page for .NET を使用して PostScript (PS) ドキュメントに **線形グラデーション矩形** を追加する包括的なチュートリアルへようこそ。Aspose.Page はさまざまな形式のドキュメントを作成、変更、レンダリングできる強力なライブラリで、今回は PS ファイルに目を引くグラデーションを取り入れる方法に焦点を当てます。

### クイック回答
- **線形グラデーション矩形は何をするものですか？** 矩形領域を一方の側からもう一方へ滑らかに色が変化するように塗りつぶします。  
- **どの API がグラデーション塗りつぶしテキストを扱いますか？** `LinearGradientBrush` と `SetPaint`、`FillAndStrokeText` の組み合わせです。  
- **テキストをグラデーションでアウトラインできますか？** はい — グラデーションブラシで `SetStroke` を使用し、`OutlineText` を呼び出します。  
- **本番環境でライセンスは必要ですか？** 評価版以外で使用する場合は、商用 Aspose.Page ライセンスが必要です。  
- **対応している .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 前提条件

開始する前に以下を確認してください：

- Aspose.Page for .NET ライブラリ: プロジェクトにライブラリが参照されていることを確認してください。ダウンロードは [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) から入手できます。
- ドキュメントディレクトリ: 生成された PS ファイルを保存するフォルダーをディスク上に作成し、コード中の **“Your Document Directory”** をそのパスに置き換えてください。

## 名前空間のインポート

まず、描画および PS 固有のクラスにアクセスできる名前空間をインポートします：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 線形グラデーション矩形とは？

**線形グラデーション矩形** は、内部が線形グラデーションで塗られた矩形です。色は直線に沿って滑らかに変化し、通常は左から右（水平）または上から下（垂直）へ移行します。Aspose.Page では、矩形を定義する `GraphicsPath` と、色の遷移を記述する `LinearGradientBrush` を組み合わせて実現します。

## なぜグラデーション塗りつぶしテキストとアウトラインテキストのグラデーションを使用するのか？

- **視覚的魅力:** グラデーション塗りつぶしテキストは、レポート、請求書、プロモーション資料に奥行きとモダンなスタイルを加えます。  
- **ブランドの一貫性:** 正確な ARGB 値で企業カラーに合わせられます。  
- **汎用性:** 同じブラシを形状の塗りつぶし、テキストの塗りつぶし、アウトラインのグラデーションに再利用でき、コードの重複を減らせます。

## 手順 1: ドキュメントの設定

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## 手順 2: グラデーション矩形と色の定義

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## 手順 3: ブラシの変換設定

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## 手順 4: ペイント設定と矩形の塗りつぶし

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## グラデーション塗りつぶしテキストの適用方法

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## アウトラインテキストのグラデーション使用

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## 手順 7: 現在のページを閉じてドキュメントを保存

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

おめでとうございます！PostScript ドキュメントに **線形グラデーション矩形** を正常に追加し、同じブラシを **グラデーション塗りつぶしテキスト** と **アウトラインテキストのグラデーション** に使用できました。

## 一般的な使用例とヒント

- **レポートヘッダー:** 大きなテキストブロックをグラデーションで塗りつぶし、セクションタイトルを強調します。  
- **ブランドロゴ:** ロゴ形状をグラデーション塗りつぶしで再現し、ブランドの一貫性を保ちます。  
- **プロのコツ:** 同じ `LinearGradientBrush` インスタンスを複数の描画呼び出しで再利用し、形状とテキスト間で色を完全に揃えます。

## よくある質問

### Q1: 矩形以外の形状にもグラデーションを適用できますか？

**A:** はい、`GraphicsPath` で定義された任意の形状にグラデーションを適用できます。`document.Fill(path)` を呼び出す前に、円や多角形、カスタムパスを追加するだけです。

### Q2: グラデーションの色を変更するには？

**A:** `LinearGradientBrush` を作成する際に `Color.FromArgb` の値を変更します。最初の色が開始色、2 番目が終了色です。

### Q3: Aspose.Page はさまざまなドキュメント形式に対応していますか？

**A:** もちろんです。Aspose.Page は XPS、PS、PDF など複数のベクタ形式をサポートしています。完全な一覧は公式ドキュメントをご確認ください。

### Q4: 商用プロジェクトで Aspose.Page を使用できますか？

**A:** はい、商用ライセンスが利用可能です。詳細は購入ページをご覧ください: [here](https://purchase.aspose.com/buy)。

### Q5: コミュニティサポートはどこで得られますか？

**A:** Aspose.Page コミュニティフォーラムに参加してください: [Aspose.Page Forum](https://forum.aspose.com/c/page/39)。

---

**最終更新日:** 2026-02-25  
**テスト環境:** Aspose.Page 24.10 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}