---
title: Aspose.Page for .NET を使用して PostScript (PS) に四角形を追加する
linktitle: PostScript に四角形を追加 (PS)
second_title: Aspose.Page .NET API
description: Aspose.Page を使用して .NET でのドキュメント作成を強化します。 PostScript (PS) ファイルに四角形を追加する方法を段階的に学習します。
weight: 12
url: /ja/net/drawing-shapes/add-rectangle-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用して PostScript (PS) に四角形を追加する

## 導入

.NET でのドキュメント作成機能を強化したい場合、Aspose.Page は PostScript ドキュメントを処理するための強力なソリューションを提供します。このチュートリアルでは、Aspose.Page for .NET を使用して PostScript ドキュメントに四角形を追加するプロセスを説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Page for .NET ライブラリ:Aspose.Page for .NET ライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/page/net/).

- 開発環境: マシン上に .NET 開発環境がセットアップされていることを確認してください。

## 名前空間のインポート

コーディングを始める前に、必要なクラスとメソッドにアクセスするために必要な名前空間をインポートしてください。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

ここで、例を複数のステップに分けてみましょう。

## ステップ 1: ドキュメント ディレクトリを設定する

```csharp
//例開始:1
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
```

この手順では、「Your Document Directory」を PostScript ドキュメントを保存するパスに置き換えます。

## ステップ 2: PostScript ドキュメントの出力ストリームを作成する

```csharp
//PostScript ドキュメントの出力ストリームを作成する
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

ここでは、PostScript ドキュメントの出力ストリームを作成し、ファイル名 (「AddRectangle_outPS.ps」) を指定します。好みに応じてファイル名と場所を調整します。

## ステップ 3: 保存オプションを設定し、PS ドキュメントを作成する

```csharp
//A4サイズで保存オプションを作成する
PsSaveOptions options = new PsSaveOptions();

//新しい 1 ページの PS ドキュメントを作成する
PsDocument document = new PsDocument(outPsStream, options, false);
```

希望のページ サイズ (この場合は A4) を指定して、保存オプションを設定します。次に、新しい単一ページの PostScript ドキュメントを作成します。

## ステップ 4: 長方形を追加して塗りつぶす

```csharp
//最初の四角形からグラフィックス パスを作成します
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//セットペイント
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//長方形を塗りつぶす
document.Fill(path);
```

ここでは、最初の長方形を表すグラフィックス パスを作成し、ペイント カラー (この場合はオレンジ) を設定して、長方形を塗りつぶします。

## ステップ 5: 別の四角形とストロークを追加する

```csharp
//番目の長方形からグラフィックス パスを作成します
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//設定ストローク
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//長方形をストローク（輪郭）します
document.Draw(path);
```

前のステップと同様に、2 番目の長方形のグラフィックス パスを作成し、ストロークの色 (太さ 3 の赤) を設定し、長方形の輪郭を描きます。

## ステップ 6: ページを閉じてドキュメントを保存する

```csharp
//現在のページを閉じる
document.ClosePage();

//文書を保存する
document.Save();
```

最後に、現在のページを閉じて、文書全体を保存します。

## 結論

おめでとう！ Aspose.Page for .NET を使用して、PostScript ドキュメントに四角形を追加することに成功しました。このチュートリアルでは、開発環境のセットアップから最終ドキュメントの保存までの重要な手順を説明しました。

## よくある質問

### Q1: 長方形の色をカスタマイズできますか?

A1: はい、パラメータを調整することで色をカスタマイズできます。`SolidBrush`そして`Pen`クラス。

### Q2: Aspose.Page は他のドキュメント形式と互換性がありますか?

A2: はい、Aspose.Page は、XPS や PostScript などのさまざまなドキュメント形式をサポートしています。

### Q3: ドキュメントにテキストを追加するにはどうすればよいですか?

 A3: を使用できます。`TextFragment` Aspose.Page のクラスを使用して、ドキュメントにテキストを追加します。

### Q4: 追加の例やドキュメントはどこで入手できますか?

 A4: ドキュメントを参照してください[ここ](https://reference.aspose.com/page/net/)そして訪問してください[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティサポートのために。

### Q5: 購入する前に Aspose.Page を試すことはできますか?

 A5: はい、無料試用版を入手できます。[ここ](https://releases.aspose.com/) 、そして長期間使用する場合は、[仮免許](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
