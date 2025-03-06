---
title: Aspose.Page for .NET を使用して XPS を PDF に変換する
linktitle: XPSをPDFに変換
second_title: Aspose.Page .NET API
description: Aspose.Page を使用すると、.NET で XPS を PDF に簡単に変換できます。ライブラリをダウンロードし、ドキュメントを調べて、無料トライアルを入手してください。
weight: 11
url: /ja/net/document-conversion/convert-xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用して XPS を PDF に変換する

## 導入

このチュートリアルでは、強力な Aspose.Page for .NET ライブラリを使用して、XPS (XML Paper Supplement) ドキュメントを PDF (Portable Document Format) に変換するプロセスを詳しく説明します。 Aspose.Page for .NET は、XPS ファイルを操作するための堅牢な機能セットを提供し、開発者がさまざまなカスタマイズ オプションを使用してファイルを PDF 形式にシームレスに変換できるようにします。

## 前提条件

この変換作業に着手する前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Page for .NET ライブラリ: 開発環境に Aspose.Page for .NET ライブラリがインストールされていることを確認します。からダウンロードできます。[Aspose.Page ドキュメント](https://reference.aspose.com/page/net/).

- 開発環境: Visual Studio またはその他の互換性のある IDE を使用して .NET 開発環境をセットアップします。

- XPS ドキュメント: PDF に変換する XPS ドキュメントを準備します。これは、指定されたディレクトリに保存されているサンプル XPS ファイルである可能性があります。

## 名前空間のインポート

コードに入る前に、コード内で Aspose.Page for .NET の機能にアクセスできるようにするために必要な名前空間をインポートしましょう。

```csharp
using Aspose.Page.XPS;
```

## ステップ 1: ドキュメント ディレクトリを初期化する

```csharp
string dataDir = "Your Document Directory";
```

「Your Document Directory」を、XPS ドキュメントが含まれるディレクトリへのパスに置き換えます。

## ステップ 2: PDF および XPS ストリームを初期化する

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

出力 PDF ファイルと入力 XPS ファイルの両方のストリームを開きます。適切なファイル パスが設定されていることを確認してください。

## ステップ 3: XPS ドキュメントをロードする

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Aspose.Page for .NET ライブラリを使用して XPS ドキュメントを読み込みます。

## ステップ 4: PDF 保存オプションを初期化する

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

JPEG 品質レベル、画像圧縮、テキスト圧縮、含める特定のページ番号などのパラメータを含む PDF 保存オプションを設定します。

## ステップ 5: PDF レンダリング デバイスを作成する

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Aspose.Page for .NET ライブラリを使用して、PDF 形式のレンダリング デバイスを作成します。

## ステップ 6: ドキュメントを PDF に保存する

```csharp
document.Save(device, options);
```

指定したレンダリング デバイスとオプションを使用して、XPS ドキュメントを PDF に保存します。

## 結論

おめでとう！ Aspose.Page for .NET を使用して XPS ドキュメントを PDF に変換することに成功しました。この多用途ライブラリは、さまざまなドキュメント形式を簡単に処理するための強力なツールセットを開発者に提供します。

## よくある質問

### Q1: Aspose.Page for .NET を使用して、複数の XPS ファイルを 1 つの PDF に変換できますか?

A1: はい、複数の XPS ファイルをループし、同じ手順に従ってそれらを 1 つの PDF に結合できます。

### Q2: Aspose.Page for .NET でサポートされている他の出力形式はありますか?

A2: はい、Aspose.Page for .NET は、TIFF、JPEG、PNG などのさまざまな出力形式をサポートしています。

### Q3: 変換された PDF ドキュメントの外観をカスタマイズするにはどうすればよいですか?

A3: 画像圧縮やテキスト圧縮などのオプション オブジェクト パラメータを微調整して、希望の外観を実現できます。

### Q4: Aspose.Page for .NET の試用版はありますか?

 A4: はい、次から無料トライアルを入手して、Aspose.Page for .NET の機能を調べることができます。[ここ](https://releases.aspose.com/).

### Q5: Aspose.Page for .NET のコミュニティ サポートはどこで受けられますか?

 A5: にアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティのディスカッションとサポートのために。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
