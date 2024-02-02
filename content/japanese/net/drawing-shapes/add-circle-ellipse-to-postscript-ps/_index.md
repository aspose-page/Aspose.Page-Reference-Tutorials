---
title: Aspose.Page を使用して円楕円を PostScript (PS) に追加する
linktitle: PostScript に円楕円を追加 (PS)
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して PostScript (PS) ドキュメントに円楕円を簡単に追加する方法を学びます。シームレスな統合については、ステップバイステップのガイドに従ってください。
type: docs
weight: 10
url: /ja/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---
## 導入

Aspose.Page for .NET を使用して PostScript (PS) ドキュメントに円楕円を追加するためのこの包括的なチュートリアルへようこそ。 Aspose.Page は、開発者が PostScript やその他のドキュメント形式をシームレスに操作できるようにする強力なライブラリです。このガイドでは、PS ドキュメントに円楕円を簡単に組み込むプロセスを説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.Page for .NET ライブラリ:Aspose.Page for .NET ライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/page/net/).

2. 開発環境: マシン上に動作する .NET 開発環境がセットアップされていることを確認します。

それでは、ステップバイステップのガイドを始めましょう。

## 名前空間のインポート

最初のステップでは、コード内で Aspose.Page 機能を使用できるようにするために、必要な名前空間をインポートする必要があります。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

ここで、提供されている例を複数のステップに分けて、PostScript ドキュメントに円楕円を追加するプロセスを説明します。

## ステップ 1: ドキュメント ディレクトリを設定する

```csharp
//例開始:1
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
```

「Your Document Directory」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 2: PostScript ドキュメントの出力ストリームを作成する

```csharp
//PostScript ドキュメントの出力ストリームを作成する
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

ここでは、PostScript ドキュメントを書き込むために FileStream が作成され、新しいファイルを作成するようにファイル モードが設定されています。

## ステップ 3: 保存オプションと PS ドキュメントを作成する

```csharp
//A4サイズで保存オプションを作成する
PsSaveOptions options = new PsSaveOptions();

//新しい 1 ページの PS ドキュメントを作成する
PsDocument document = new PsDocument(outPsStream, options, false);
```

この手順には、A4 サイズの保存オプションの作成と、新しい 1 ページの PS ドキュメントの初期化が含まれます。

## ステップ 4: 最初の楕円のグラフィックス パスを作成する

```csharp
//最初の楕円からグラフィックス パスを作成します
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

最初の楕円のグラフィックス パスが作成され、その位置と寸法が指定されます。

## ステップ 5: ペイントを設定して楕円を塗りつぶす

```csharp
//セットペイント
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//楕円を塗りつぶす
document.Fill(path);
```

ここではペイントが設定され、最初の楕円が指定した色で塗りつぶされます。

## ステップ 6: 2 番目の楕円のグラフィックス パスを作成する

```csharp
//番目の楕円からグラフィックス パスを作成します
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

同様に、2 番目の楕円のグラフィックス パスが作成され、その位置と寸法が定義されます。

## ステップ 7: ストロークを設定して楕円を描画する

```csharp
//設定ストローク
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//楕円をストローク（輪郭）します
document.Draw(path);
```

このステップでは、ストロークが設定され、指定された色と線の太さで 2 番目の楕円の輪郭が描かれます。

## ステップ 8: 現在のページを閉じてドキュメントを保存する

```csharp
//現在のページを閉じる
document.ClosePage();

//文書を保存する
document.Save();
```

最後に、現在のページを閉じ、文書全体を保存してプロセスを完了します。

## 結論

おめでとう！ Aspose.Page for .NET を使用して PostScript ドキュメントに円楕円を追加する方法を学習しました。このチュートリアルでは、この機能をプロジェクトにシームレスに統合するのに役立つ詳細なステップバイステップ ガイドを提供しました。

## よくある質問

### Q1: Aspose.Page for .NET を他のドキュメント形式で使用できますか?

 A1: Aspose.Page は主に PostScript に重点を置いていますが、Aspose はさまざまなドキュメント形式用の他のライブラリを提供します。チェックしてください[Aspose ドキュメント](https://reference.aspose.com/page/net/)詳細については。

### Q2: 追加のサポートやコミュニティのディスカッションはどこで見つけられますか?

 A2: にアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティのディスカッションとサポートのために。

### Q3: Aspose.Page for .NET の無料トライアルはありますか?

 A3: はい、アクセスできます。[無料トライアル](https://releases.aspose.com/)Aspose.Page for .NET の機能を探索します。

### Q4: Aspose.Page の一時ライセンスを取得するにはどうすればよいですか?

 A4: 仮免許を取得する[ここ](https://purchase.aspose.com/temporary-license/)テストと評価の目的で。

### Q5: Aspose.Page for .NET はどこで購入できますか?

 A5: Aspose.Page for .NET を次のサイトから購入します。[購入ページ](https://purchase.aspose.com/buy).