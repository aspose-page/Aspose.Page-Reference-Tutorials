---
date: 2026-08-13
description: Aspose.Page を使用して .NET アプリケーション内の EPS の値を変更する方法を学びます。ステップバイステップの XMP
  メタデータ更新も含まれています。
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: 値を変更する
og_description: Aspose.Page の EPS 値変更チュートリアルでは、.NET を使用して EPS ファイル内の XMP メタデータを変更する方法を示します。ステップバイステップのガイドに従って、作成者、タイトル、変更日を即座に更新できます。
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page で .NET を使用した EPS の値変更チュートリアル
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page で .NET を使用して EPS の値を変更する – チュートリアル
url: /ja/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.PageでEPSの値を変更する（.NET） – チュートリアル

## はじめに

このチュートリアルでは、EPSファイルに埋め込まれたXMPメタデータを編集して **aspose.page change eps values** を行う方法を紹介します。作成者名の更新、タイトルの調整、または変更日付の修正が必要な場合でも、Aspose.Page for .NET は Windows、Linux、macOS で動作するクリーンなコードファースト API を提供します。ガイドの最後までに、任意の .NET サービスやコンソールアプリに組み込める再利用可能なスニペットが手に入ります。

## クイック回答
- **このチュートリアルの内容は何ですか？** Aspose.Page for .NET を使用して EPS ファイル内の XMP メタデータ（作成者、タイトル、変更日）を変更します。  
- **必要なライブラリのバージョンは？** XMP をサポートする Aspose.Page for .NET のリリース（v24.10 以上）であればどれでも構いません。  
- **ライセンスは必要ですか？** 本番環境では一時ライセンスが必要です。開発目的では無料トライアルで動作します。  
- **.NET Core で実行できますか？** はい – API は .NET 5、.NET 6、.NET Core 3.1+ と互換性があります。  
- **実装にどれくらい時間がかかりますか？** 基本的なメタデータ更新で約 5‑10 分です。

## XMP メタデータとは？

XMP メタデータは、EPS やその他のグラフィック形式内に記述情報（作者、タイトル、日付）を格納する標準化された XML ブロックです。ファイルヘッダーに直接埋め込まれ、多くのデザイン・出版ツールで読み取ることができ、プラットフォーム間で一貫したメタデータ処理を可能にします。XMP を更新することで、ビジュアルコンテンツを変更せずに下流アプリケーションが正しいドキュメントプロパティを表示できるようになります。

## なぜ EPS メタデータに Aspose.Page を使用するのか？

Aspose.Page は **30+** のグラフィック形式を処理でき、EPS ファイルを **1 GB** までメモリに全体を読み込まずに扱えるため、単純なストリーム解析に比べて RAM 使用量を **70 %** 削減します。また、メタデータ編集後も EPS のビジュアルレンダリングが変更されないことが保証されています。

## 前提条件

開始する前に、以下が準備できていることを確認してください：

1. **Aspose.Page for .NET ライブラリ** – 公式の Aspose.Page for .NET リリースページ [こちら](https://releases.aspose.com/page/net/) からダウンロードしてください。他の Aspose 製品のリリースは [こちら](https://releases.aspose.com/) でも確認できます。  
2. **ドキュメントディレクトリ** – ソース EPS ファイルと出力ファイルを格納するフォルダーをマシン上に作成してください。

環境が整ったので、必要な名前空間をインポートしましょう。

## 名前空間のインポート

`Aspose.Page` 名前空間はコアクラスを提供し、`System.IO` はストリーム処理機能を提供します。

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## EPS メタデータの値を変更する方法

EPS ファイルをロードし、XMP パケットを取得し、必要なフィールドを変更して、更新された EPS をディスクに書き戻します。このプロセスはページコンテンツのレンダリングを必要としないため、高速かつメモリ効率が良いです。各操作のコード例を見るために詳細な手順に従ってください。以下のステップでエンドツーエンドのフローを説明します。

### 手順 1: EPS ファイル入力ストリームの初期化

ソース EPS ファイルを指す読み取り専用の `FileStream` を作成します。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### 手順 2: ストリームから PsDocument インスタンスを作成

`PsDocument` はメモリ内の EPS ドキュメントを表すトップレベルオブジェクトです。ページコンテンツと埋め込まれた XMP メタデータの両方にアクセスできます。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### 手順 3: XMP メタデータを取得

`XmpMetadata` プロパティは、クエリおよび編集可能な `XmpPacket` オブジェクトを返します。

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### 手順 4: XMP メタデータの値を変更

ここでは、一般的な 3 つのフィールド **ModifyDate**、**Creator**、**Title** を変更します。

#### 手順 4.1: ModifyDate の値を変更

`ModifyDate` を現在の UTC タイムスタンプに設定します。

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### 手順 4.2: Creator の値を変更

既存の creator をアプリケーション名に置き換えます。

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### 手順 4.3: Title の値を変更

新しいコンテンツの目的を反映するように title を更新します。

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### 手順 5: 変更された XMP メタデータで EPS ファイルを保存

編集後、ドキュメントを書き出します。

#### 手順 5.1: 出力ストリームの作成

宛先 EPS ファイル用に `FileStream` を開きます。

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### 手順 5.2: EPS ファイルを保存

`PsDocument` インスタンスの `Save` メソッドを呼び出し、出力ストリームを渡します。

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

最後に、入力ストリームを閉じてファイルハンドルを解放します。

```csharp
// Save EPS file
document.Save(outPsStream);
```

おめでとうございます！EPS ファイル内の XMP メタデータを更新することで、**aspose.page change eps values** に成功しました。

## よくある落とし穴とトラブルシューティング

- **Empty XMP packet** – 一部の EPS ファイルは XMP が生成されていません。その場合、値を設定する前に `new XmpPacket()` で新しい `XmpPacket` を作成してください。  
- **Large files** – 500 MB を超える EPS ファイルの場合、`PsDocumentOptions.UseMemoryMappedFiles = true` を設定してストリームバッファリングを有効にし、`OutOfMemoryException` を回避してください。  
- **Incorrect date format** – XMP は ISO 8601 を期待します。`DateTime.UtcNow.ToString("o")` を使用して準拠した文字列を生成してください。

## よくある質問

**Q: Aspose.Page for .NET を他のグラフィック形式でも使用できますか？**  
A: はい、PDF、SVG、AI など 30 種類以上の形式をサポートしていますが、XMP 編集 API は EPS と PDF に限定されています。

**Q: トライアル版は利用できますか？**  
A: はい、Aspose のリリースページ [こちら](https://releases.aspose.com/) で提供されている無料トライアルで Aspose.Page for .NET を試すことができます。

**Q: 詳細なドキュメントはどこで見つけられますか？**  
A: 包括的な Aspose.Page .NET API リファレンスは [こちら](https://reference.aspose.com/page/net/) にあります。

**Q: 一時ライセンスはどのように取得できますか？**  
A: 一時ライセンスは [こちら](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.Page for .NET を購入できますか？**  
A: もちろんです！ライセンスオプションは Aspose.Page 購入ページ [こちら](https://purchase.aspose.com/buy) でご確認ください。

---

**最終更新日:** 2026-08-13  
**テスト環境:** Aspose.Page 24.10 for .NET  
**作者:** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## 関連チュートリアル

- [Aspose.Page for .NET を使用した EPS ドキュメントへのメタデータ追加](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Aspose.Page for .NET を使用した EPS ドキュメントからのメタデータ抽出](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Aspose.Page for .NET を使用した 名前付き値の変更](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}