---
title: Aspose.Page for .NET を使用して XPS ドキュメントを PDF に結合
linktitle: XPS ドキュメントを PDF に結合
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して、XPS ドキュメントを高品質の PDF に簡単に結合します。ステップバイステップのガイドに従って、ドキュメントをスムーズに変換してください。
type: docs
weight: 11
url: /ja/net/document-merging/merge-xps-documents-into-pdf/
---
## 導入

進化し続けるドキュメント処理の状況において、Aspose.Page for .NET は、XPS ドキュメントを PDF 形式にシームレスに結合するための強力なツールとして浮上しています。このチュートリアルでは、プロセスをガイドし、スムーズかつ効果的に実行できるように各ステップを詳しく説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Page for .NET: Aspose.Page ライブラリがインストールされていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/page/net/).

- ドキュメント ファイル: XPS ドキュメント (`input.xps`) 指定したディレクトリに準備が整いました。

## 名前空間のインポート

.NET プロジェクトに、Aspose.Page を操作するために必要な名前空間を含めます。

```csharp
using Aspose.Page.XPS;
```

この手順により、ドキュメント変換に必要なクラスとメソッドにアクセスできるようになります。

## ステップ 1: ストリームを初期化する

```csharp
//例開始:3
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
// PDF 出力ストリームを初期化する
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
//XPS入力ストリームを初期化する
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
//拡張終了:3
```

この手順には、XPS ファイルと PDF ファイルの入力ストリームと出力ストリームの設定が含まれます。正しいパスとファイル名が使用されていることを確認してください。

## ステップ 2: XPS ドキュメントをロードする

```csharp
//例開始:4
//ストリームから XPS ドキュメントをロードします
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
//または、XPS ドキュメントをファイルから直接ロードします。その場合、xpsStream は必要ありません。
//XpsDocument ドキュメント = new XpsDocument(inputFileName, new XpsLoadOptions());
//拡張終了:4
```

ここでは、XPS ドキュメントを`XpsDocument`オブジェクトを処理し、さらなる処理の準備をします。

## ステップ 3: 保存オプションを初期化する

```csharp
//例開始:5
//必要なパラメータを使用してオプション オブジェクトを初期化します。
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
//拡張終了:5
```

をカスタマイズします。`PdfSaveOptions`画像圧縮、テキスト圧縮、ページ番号などのパラメータを指定して、好みに基づいてオブジェクトを作成します。

## ステップ 4: レンダリング デバイスを作成する

```csharp
//例開始:6
//PDF 形式用のレンダリング デバイスを作成する
PdfDevice device = new PdfDevice(pdfStream);
//拡張終了:6
```

の`PdfDevice`XPS ドキュメントを PDF 形式にレンダリングするツールです。

## ステップ 5: ドキュメントを保存する

```csharp
//例開始:7
document.Save(device, options);
//拡張終了:7
```

最後に、レンダリング デバイスと指定されたオプションを使用してドキュメントを保存します。

## 結論

おめでとう！ Aspose.Page for .NET を使用して XPS ドキュメントを PDF に結合することに成功しました。このシームレスなプロセスにより、文書の品質と書式が確実に維持されます。

## よくある質問

### Q1: 複数の XPS ファイルを 1 つの PDF に結合できますか?

 A1: はい、可能です。単に調整するだけです`PageNumbers`のパラメータ`PdfSaveOptions`さまざまな XPS ファイルから目的のページを含めます。

### Q2: Aspose.Page for .NET の一時ライセンスは利用できますか?

 A2: はい、一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/)テスト目的のため。

### Q3: ドキュメント変換に Aspose.Page を使用する場合、ファイル サイズに制限はありますか?

A3: Aspose.Page for .NET はファイル サイズに厳密な制限を課しませんが、適切なファイル サイズで最適なパフォーマンスが実現されます。

### Q4: ウォーターマークや注釈の追加など、出力 PDF をさらにカスタマイズできますか?

A4: はい、Aspose.Page for .NET は PDF 操作のための広範な機能を提供します。高度なカスタマイズ オプションについてはドキュメントを確認してください。

### Q5: Aspose.Page for .NET はクロスプラットフォーム開発をサポートしていますか?

A5: はい、Aspose.Page for .NET は、さまざまなプラットフォーム間でシームレスに動作するように設計されています。