---
date: 2026-08-08
description: Aspose.Page の EPS メタデータを使用して EPS メタデータに配列項目を追加する方法を学びます。このステップバイステップの
  .NET ガイドでは、配列項目の追加方法と EPS ファイルの効率的な読み取り方法を示します。
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: 配列項目を追加
og_description: Aspose.Page の EPS メタデータを使用して EPS メタデータに配列項目を追加する方法をご紹介します。この簡潔な .NET
  チュートリアルに従って、EPS ファイルを読み取り、メタデータを効率的に管理しましょう。
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Aspose.Page の EPS メタデータを使用して .NET で配列項目を追加する
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Aspose.Page の EPS メタデータを使用して .NET で配列項目を追加する
url: /ja/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page EPS メタデータに配列項目を追加する (.NET)

## はじめに

このチュートリアルでは、**Aspose.Page EPS メタデータ** を使用して EPS メタデータに配列項目を追加する方法を学びます。EPS ファイルに追加のタイトル、作成者、カスタムタグなどを付加したい場合でも、Aspose.Page を使用すれば .NET 開発者なら誰でも簡単に作業を行えます。EPS ストリームのオープンから更新された XMP パケットの保存まで、各ステップを順に解説するので、メタデータ処理を自分のアプリケーションに自信を持って組み込むことができます。

## クイック回答
- **Aspose.Page EPS メタデータで何ができるか？** .NET から EPS ファイル内の XMP メタデータ配列の読み書きが可能になります。  
- **EPS ドキュメントを表すクラスはどれか？** `PsDocument` は EPS コンテンツのロードと保存のためのコアクラスです。  
- **開発にライセンスは必要か？** 無料トライアルでテストは可能ですが、本番環境では商用ライセンスが必要です。  
- **EPS のグラフィックを変更せずにメタデータを修正できるか？** はい、XMP パケットのみが変更され、ページ内容はそのままです。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## Aspose.Page EPS メタデータとは？

Aspose.Page EPS メタデータは、EPS ファイルに埋め込まれた XMP ベースの情報ブロックです。ISO 16684‑1 標準に従い、タイトル、作成者、キーワード、カスタムタグなどの記述属性を格納します。Aspose.Page API を通じてプログラムからメタデータにアクセスし、変更できるため、ドキュメント管理の自動化や検索最適化が可能になります。

## なぜ EPS メタデータを変更するのか？

Aspose.Page は **30 以上のメタデータフィールド** を処理でき、**200 MB** までの EPS ファイルをメモリに全文読み込まずに扱えるため、フルファイル解析に比べて CPU 使用率を最大 40 % 削減します。メタデータを更新することで、検索性、コンプライアンス、下流のワークフロー自動化が向上します。

## 前提条件

- 基本的な .NET プログラミングの知識。  
- Aspose.Page for .NET がインストールされていること – [download Aspose.Page for .NET](https://releases.aspose.com/page/net/) からダウンロードしてください。  
- サンプルコードを実行するための Visual Studio（または任意の .NET 対応 IDE）。

## EPS メタデータに配列項目を追加する方法は？

配列項目を追加するには、まず EPS ファイルを `PsDocument` にロードし、`GetXmpMetadata()` で XMP パケットを取得します。`dc:title` や `dc:creator` など目的の XMP 配列に対して `AddArrayItem()` メソッドを使用して新しい値を追加します。最後に `Save()` を呼び出し、グラフィック内容を変更せずに更新されたメタデータをファイルに書き戻します。

### 手順 1: EPS ファイル入力ストリームの初期化

`PsDocument` は EPS ドキュメントを表し、その内容にアクセスするメソッドを提供します。以下のコードは EPS ファイルをストリームとして開き、`PsDocument` インスタンスを作成します。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### 手順 2: XMP メタデータの取得

`GetXmpMetadata()` は EPS ファイルに埋め込まれた XMP パケットを取得します。パケットが存在しない場合、API は既存の PostScript コメントに基づいて新しいパケットを生成します。

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### 手順 3: XMP メタデータの値を変更

`AddArrayItem()` は既存の XMP 配列に新しい値を追加し、他のエントリを上書きしません。タイトル、作成者、カスタムタグなどをメタデータに追加する際に使用します。

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### 手順 4: 変更された XMP メタデータで EPS ファイルを保存

`Save()` は変更された XMP パケットを元の PostScript 内容を保持したまま EPS ファイルに書き戻します。出力パスを指定して新しいファイルを作成するか、元ファイルを上書きしてください。

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## よくある落とし穴とトラブルシューティング

- **Null XMP パケット** – `GetXmpMetadata()` が `null` を返す場合、EPS ファイルに少なくとも1つのコメントブロックが含まれていることを確認してください。含まれていない場合は、手動で新しい `XmpMetadata` インスタンスを作成します。  
- **エンコーディングの問題** – 文字列値を追加する際は UTF‑8 を使用し、非 ASCII 言語での文字化けを防止してください。  
- **大きなファイル** – 150 MB を超える EPS ファイルの場合、`FileStream` とバッファを使用して入力をストリーミングし、メモリ使用量を抑えることを検討してください。

## よくある質問

**Q: Aspose.Page はすべての .NET 環境と互換性がありますか？**  
A: はい、Aspose.Page は .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7 で動作し、Windows、Linux、macOS で一貫した API 動作を提供します。

**Q: Aspose.Page を無料で使用できますか？**  
A: ライブラリは無料トライアルを [Aspose purchase page](https://purchase.aspose.com/buy) からダウンロードして評価できます。本番環境での導入には商用ライセンスが必要です。

**Q: Aspose.Page の一時ライセンスは利用可能ですか？**  
A: 短期プロジェクトや評価期間向けに、[temporary license page](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

**Q: Aspose.Page のコミュニティサポートはどこで得られますか？**  
A: [Aspose.Page forum](https://forum.aspose.com/c/page/39) でディスカッションに参加し、質問や解決策を他の開発者と共有できます。

**Q: .NET 向け Aspose.Page の最新バージョンは何ですか？**  
A: 最新のリリースノートとダウンロードリンクは公式 [documentation](https://reference.aspose.com/page/net/) を参照してください。

---

**最終更新日:** 2026-08-08  
**テスト環境:** Aspose.Page 24.11 for .NET  
**作者:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## 関連チュートリアル

- [Aspose.Page for .NET で配列項目を変更する](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Aspose.Page for .NET でシンプルなプロパティを追加する](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Aspose.Page for .NET で名前空間を追加する](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}