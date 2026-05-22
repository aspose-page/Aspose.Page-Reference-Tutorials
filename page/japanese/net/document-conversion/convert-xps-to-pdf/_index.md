---
date: 2026-01-10
description: .NETでAspose.Pageを使用してXPSをPDFに簡単に変換できます。ライブラリをダウンロードし、ドキュメントを確認し、無料トライアルをご利用ください。
linktitle: Convert XPS to PDF
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET を使用して XPS を PDF に変換
url: /ja/net/document-conversion/convert-xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用した XPS から PDF への変換

## はじめに

このチュートリアルでは、Aspose.Page for .NET ライブラリを使用して **XPS を PDF に変換する方法** を学びます。XPS を PDF に変換することは、PDF リーダーしか持っていないユーザーと XPS ドキュメントを共有したい場合や、XPS コンテンツを大規模な PDF ワークフローに組み込みたい場合に一般的な要件です。各ステップを順に解説し、設定が重要な理由を説明し、JPEG 品質の設定や PDF 画像圧縮の適用など、出力を細かく調整する方法を示します。

## よくある質問
- **XPS から PDF への変換に最適なライブラリは？** Aspose.Page for .NET
- **本番環境でライセンスは必要ですか？** はい、商用ライセンスが必要です。無料トライアルも利用可能です。
- **画像品質を制御できますか？** もちろんです。`JpegQualityLevel` と `PdfImageCompression` を使用します。
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 .NET 5/6/7。
- **複数の XPS ファイルを 1 つの PDF に変換できますか？** はい、ファイルをループして結果をマージすれば可能です。

## 前提条件

この変換作業に取り掛かる前に、以下の前提条件が整っていることを確認してください。

- **Aspose.Page for .NET Library** – 開発環境に Aspose.Page for .NET ライブラリがインストールされていることを確認してください。ダウンロードは [Aspose.Page documentation](https://reference.aspose.com/page/net/) から行えます。
- **Development Environment** – Visual Studio などの .NET 開発環境をセットアップしてください。
- **XPS Document** – PDF に変換したい XPS ドキュメントを用意してください。対象ディレクトリに保存されたサンプル XPS ファイルでも構いません。

## 名前空間のインポート

コードに取り掛かる前に、Aspose.Page for .NET の機能をプロジェクトで利用できるよう、必要な名前空間をインポートしましょう。

```csharp
using Aspose.Page.XPS;
```

## ステップバイステップガイド

### ステップ1：ドキュメントディレクトリの初期化

ソース XPS ファイルが格納されているフォルダーと、生成された PDF を保存するフォルダーを定義します。

```csharp
string dataDir = "Your Document Directory";
```

`"Your Document Directory"` を、XPS ドキュメントが入っているフォルダーへの絶対パスまたは相対パスに置き換えてください。

### ステップ2：PDF出力とXPS入力のストリームを開く

2 つのファイルストリームを使用します。1 つは XPS ファイルの読み取り用、もう 1 つは生成された PDF の書き込み用です。

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

> **Pro tip:** パスが正しいこと、そしてアプリケーションが対象フォルダーに対して読み書き権限を持っていることを確認してください。

### ステップ3：XPSドキュメントを読み込む

XPS ストリームから `XpsDocument` インスタンスを作成します。`XpsLoadOptions` オブジェクトで読み込み設定を指定できますが、デフォルトでほとんどのシナリオに対応します。

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### ステップ4：PDF保存オプションの設定

ここで PDF の出力設定を行います。**PDF 画像圧縮** (`PdfImageCompression.Jpeg`) と **JPEG 品質** (`JpegQualityLevel = 100`) の使用に注目してください。これらの設定はファイルサイズと画質に直接影響します。

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

- **`JpegQualityLevel`** – PDF に埋め込まれる JPEG 画像の品質を制御します（数値が大きいほど高品質でファイルサイズも大きくなります）。
- **`ImageCompression`** – 圧縮アルゴリズムを選択します。JPEG は写真画像に最適です。
- **`TextCompression`** – Flate 圧縮によりテキストの品質を損なうことなく PDF サイズを削減します。
- **`PageNumbers`** – 特定のページだけを **XPS から PDF に保存** できるようにします。

### ステップ5：PDFレンダリングデバイスの作成

`PdfDevice` は、先ほど開いたストリームに PDF データを書き込むレンダリングターゲットとして機能します。

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### ステップ6：ドキュメントをPDFとして保存する

最後に `Save` メソッドを呼び出し、レンダリングデバイスと設定したオプションを渡します。

```csharp
document.Save(device, options);
```

コードの実行が完了すると、`XPStoPDF_out.pdf` が指定したディレクトリに作成され、設定した圧縮と品質オプションが適用された変換ページが格納されます。

## XPSをPDFに変換する理由

- **Universal accessibility** – PDF ビューアは事実上すべてのデバイスにインストールされているのに対し、XPS リーダーはほとんど存在しません。
- **Preserve layout** – PDF は元の XPS と同じビジュアルレイアウト、フォント、グラフィックを正確に保持します。
- **Further processing** – PDF に変換すれば、他の Aspose ライブラリを使って結合、注釈付け、デジタル署名などの追加処理が可能です。

## 一般的な使用例

- **Enterprise reporting** – レガシーシステムから生成した XPS レポートを PDF に変換し、配布します。
- **Archiving** – 長期保存のために PDF として文書を保管しつつ、必要に応じて XPS ソースから再生成できます。
- **Web services** – XPS アップロードを受け取り、リアルタイムで PDF ファイルを返す API エンドポイントを提供します。

## トラブルシューティングとヒント

- **File not found** – `dataDir` パスを再確認し、XPS ファイル名が正確に一致していることを確認してください。
- **Permission errors** – Visual Studio を管理者として実行するか、出力フォルダーに書き込み権限を付与してください。
- **Large PDFs** – 生成された PDF が大きすぎる場合は、`JpegQualityLevel` を下げるか、`ImageCompression` を `PdfImageCompression.Zip` に変更してください。

## よくある質問（AI対応）

**Q: XPSをPDFに変換する際に、JPEGの画質を設定するにはどうすればよいですか？** 

A: `PdfSaveOptions`内の`JpegQualityLevel`プロパティを使用してください。100に設定すると最高画質になります。

**Q: この文脈における「PDF画像圧縮」とは何ですか？** 

A: `ImageCompression`オプションのことです。このオプションは、PDF内の画像の圧縮方法（JPEG、Zipなど）を決定します。

**Q: XPSソースなしでプログラムからPDFを生成できますか？** 

A: はい、Aspose.Pageは描画コマンドから直接**C#でPDFを生成する**機能もサポートしていますが、このチュートリアルの範囲外です。

**Q: ベクターグラフィックを失わずにXPSをPDFに変換する方法はありますか？** 

A: 変換時にベクターデータは保持されます。`ImageCompression`を必要に応じてJPEGまたはZipに設定することで、画像のラスタライズを回避できます。


**Q: このライブラリは.NET Coreをサポートしていますか？** 

A: はい、サポートしています。Aspose.Page for .NETは、.NET Core、.NET 5、.NET 6、およびそれ以降のバージョンに対応しています。

---

**最終更新日:** 2026年1月10日
**テスト環境:** Aspose.Page 24.11 for .NET
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}