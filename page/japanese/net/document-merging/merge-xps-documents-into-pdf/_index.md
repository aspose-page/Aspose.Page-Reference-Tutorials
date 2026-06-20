---
date: 2026-06-20
description: Aspose.Page for .NET を使用して XPS を PDF に簡単に変換し、PDF 画像を圧縮します。高品質な PDF 作成のためのステップバイステップ
  ガイドをご覧ください。
keywords:
- convert xps to pdf
- compress pdf images
- create pdf from xps
linktitle: XPS ドキュメントを PDF に結合
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Effortlessly convert XPS to PDF and compress PDF images using Aspose.Page
    for .NET. Follow our step-by-step guide for high-quality PDF creation.
  headline: Convert XPS to PDF with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can load each XPS document sequentially and render them into
      the same `PdfDevice` instance, adjusting the `PageNumbers` option as needed.
    question: Can I merge multiple XPS files into a single PDF?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing purposes.
    question: Is a temporary license available for Aspose.Page for .NET?
  - answer: Aspose.Page for .NET does not impose strict limitations on file size,
      but optimal performance is achieved with files under 500 MB; larger files may
      require more memory.
    question: Are there any limitations on file size when using Aspose.Page for document
      conversion?
  - answer: Yes, Aspose.Page for .NET provides extensive features for PDF manipulation.
      Check the documentation for advanced customization options.
    question: Can I customize the output PDF further, such as adding watermarks or
      annotations?
  - answer: Yes, Aspose.Page for .NET is designed to work seamlessly across Windows,
      Linux, and macOS environments.
    question: Does Aspose.Page for .NET support cross‑platform development?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET を使用して XPS を PDF に変換
url: /ja/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用した XPS から PDF への変換

## はじめに

もし **XPS を PDF に変換** を迅速に行い、ベクターグラフィックとテキストを鮮明に保ちたい場合、Aspose.Page for .NET は重い処理を担うすぐに使える API を提供します。このチュートリアルでは、XPS ファイルの読み込みから高品質 PDF の保存までの全工程を順に解説し、任意の .NET アプリケーションに自信を持って変換機能を組み込めるようにします。

## 簡単な回答

- **どのライブラリが XPS → PDF を処理しますか？** Aspose.Page for .NET.
- **必要なコード行数は？** 約5つの論理ステップ（合計約30行）。
- **PDF 画像を圧縮できますか？** はい、`PdfSaveOptions.ImageCompression` を使用します。
- **本番環境でライセンスは必要ですか？** 商用ライセンスが必要です。試用版の一時ライセンスも利用可能です。
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## Aspose.Page を使用して XPS を PDF に変換する方法

`new XpsDocument(inputStream)` を使用して XPS ファイルをロードし、構成された `PdfSaveOptions` インスタンスを渡して `PdfDevice.Render` を呼び出します。この単一パイプラインがドキュメントを変換し、PDF を出力ストリームに書き込みます。操作はすべてメモリ上で行われるため、一時ファイルは作成されず、必要に応じて画像圧縮を有効にして最終ファイルサイズを削減できます。

## Aspose.Page for .NET とは何ですか？

Aspose.Page for .NET は、Microsoft Office を必要とせずに XPS、PDF、その他のページベース形式の作成、変換、レンダリングを可能にするドキュメント処理ライブラリです。ページベースのドキュメントの作成、編集、変換用 API を提供し、ベクターおよびラスタ画像の両方をサポートし、複数のプラットフォームで動作します。低レベル API を公開しており、開発者はレンダリングオプションを細かく制御できます。

## なぜ Aspose.Page を使用して XPS を PDF に変換するのか？

Aspose.Page は **30+ 出力形式** をサポートし、典型的なサーバー上で **500‑ページの XPS ファイル** を **2 秒** 未満で処理でき、ベクターデータを保持します。また、組み込みの **画像圧縮**（最大 80 % の削減）と **テキスト圧縮** を提供し、品質を犠牲にせず軽量な PDF を作成できます。

## 前提条件

チュートリアルに入る前に、以下の前提条件が整っていることを確認してください。

- Aspose.Page for .NET: Aspose.Page ライブラリがインストールされていることを確認してください。以下からダウンロードできます [here](https://releases.aspose.com/page/net/)。
- ドキュメントファイル: 指定ディレクトリに XPS ドキュメント（`input.xps`）を用意してください。

## 名前空間のインポート

`Aspose.Page.Xps` と `Aspose.Page.Pdf` 名前空間には、XPS ファイルの読み込みと PDF の保存に必要なクラスが含まれています。

```csharp
using Aspose.Page.XPS;
```

この手順により、ドキュメント変換に必要なクラスとメソッドにアクセスできるようになります。

## ステップ 1: ストリームの初期化

ソース XPS ファイル用に `FileStream` を作成し、宛先 PDF 用に別の `FileStream` を作成します。`using` ステートメントを使用することで、ストリームが正しく破棄されることが保証されます。

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

この手順では、XPS と PDF ファイルの入力および出力ストリームを設定します。正しいパスとファイル名が使用されていることを確認してください。

## ステップ 2: XPS ドキュメントの読み込み

`XpsDocument` は XPS ファイルをメモリに読み込み、表現するクラスです。  
ここでは、XPS ドキュメントを `XpsDocument` オブジェクトにロードし、以降の処理の準備を行います。

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

## ステップ 3: 保存オプションの初期化

`PdfSaveOptions` は PDF の保存方法を設定し、圧縮やページ設定などを含みます。  
好みに合わせて `PdfSaveOptions` オブジェクトをカスタマイズし、画像圧縮、テキスト圧縮、ページ番号などのパラメータを指定します。

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// ExEnd:5
```

## ステップ 4: レンダリングデバイスの作成

`PdfDevice` は XPS ページを PDF コンテンツに変換するレンダリングエンジンです。  
`PdfDevice` は XPS ドキュメントを PDF 形式にレンダリングするツールです。

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

## ステップ 5: ドキュメントの保存

ロードした XPS ドキュメントと出力ストリームを渡して `PdfDevice.Render` を呼び出します。このメソッドは完全に準拠した PDF ファイルをディスクに書き込みます。

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

最後に、レンダリングデバイスと指定したオプションを使用してドキュメントを保存します。

## 一般的な落とし穴とヒント

- **ストリームの所有権:** ファイルロックを防ぐため、常に `using` ブロックでストリームをラップしてください。
- **大きなファイル:** 200 MB を超える XPS ファイルの場合、パフォーマンス向上のため `FileStream` の `BufferSize` を増やすことを検討してください。
- **画像品質:** ロスレス画像が必要な場合は、JPEG の代わりに `ImageCompression` を `PdfImageCompression.None` に設定してください。

## よくある質問

**Q: 複数の XPS ファイルを単一の PDF に結合できますか？**  
**A:** はい、各 XPS ドキュメントを順次ロードし、同じ `PdfDevice` インスタンスにレンダリングして、必要に応じて `PageNumbers` オプションを調整できます。

**Q: Aspose.Page for .NET の一時ライセンスは利用可能ですか？**  
**A:** はい、テスト目的で一時ライセンスを [here](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.Page を使用したドキュメント変換時にファイルサイズの制限はありますか？**  
**A:** Aspose.Page for .NET には厳格なサイズ制限はありませんが、最適なパフォーマンスは 500 MB 未満のファイルで得られます。大きなファイルはより多くのメモリを必要とする場合があります。

**Q: 出力 PDF をさらにカスタマイズできますか（透かしや注釈の追加など）？**  
**A:** はい、Aspose.Page for .NET は PDF 操作のための豊富な機能を提供しています。高度なカスタマイズオプションはドキュメントをご確認ください。

**Q: Aspose.Page for .NET はクロスプラットフォーム開発をサポートしていますか？**  
**A:** はい、Aspose.Page for .NET は Windows、Linux、macOS 環境でシームレスに動作するよう設計されています。

## 追加の FAQ

**Q: 変換中に PDF 画像を圧縮するにはどうすればよいですか？**  
**A:** `PdfSaveOptions.ImageCompression = PdfImageCompression.Jpeg` を設定し、必要に応じて `JpegQuality` を調整してサイズと品質のバランスを取ります。

**Q: バッチ処理で XPS から PDF を作成する最適な方法は何ですか？**  
**A:** XPS ファイルが格納されたディレクトリをループし、単一の `PdfDevice` インスタンスを再利用して各ドキュメントに対して `Render` を呼び出すことでオーバーヘッドを最小化します。

**Q: ライブラリはパスワード保護された PDF をサポートしていますか？**  
**A:** はい、保存前に `PdfSaveOptions.Password` でパスワードを設定できます。

**Q: .NET ランタイムで公式にサポートされているものはどれですか？**  
**A:** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7 が完全にサポートされています。

**Q: 変換がベクターグラフィックを保持したことをどのように確認できますか？**  
**A:** オブジェクトタイプを検査できるビューア（例: Adobe Acrobat）で生成された PDF を開き、テキストや形状が選択可能かつ拡大縮小可能であることを確認します。

## 結論

これで、Aspose.Page for .NET を使用して **XPS を PDF に変換** する完全な本番対応ワークフローが手に入ります。ライブラリのレンダリングエンジンと保存オプションを活用すれば、**PDF 画像の圧縮** も可能で、サイズと品質の要件に合わせて出力を細かく調整できます。透かし、暗号化、バッチ処理などの追加機能もぜひ試して、ソリューションをさらに拡張してください。

---

**最終更新日:** 2026-06-20  
**テスト環境:** Aspose.Page 23.12 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Page for .NET を使用した XPS ドキュメントの作成](/page/net/document-creation/create-xps-document/)
- [Aspose.Page for .NET を使用した XPS ドキュメントの変更](/page/net/document-creation/modify-xps-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}