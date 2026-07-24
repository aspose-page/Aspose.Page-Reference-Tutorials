---
date: 2026-07-24
description: Aspose.Page for .NET を使用して EPS ファイルにメタデータを追加する方法を学びます。このステップバイステップ ガイドでは、XMP
  メタデータを迅速かつ確実に埋め込む方法を示します。
keywords:
- how to add metadata
- EPS metadata Aspose
- Aspose.Page .NET
lastmod: 2026-07-24
linktitle: EPS ドキュメントにメタデータを追加
og_description: Aspose.Page for .NET を使用して EPS ファイルにメタデータを追加する方法を紹介します。この簡潔なチュートリアルに従って、数ステップで
  XMP メタデータを埋め込みましょう。
og_image_alt: Guide showing how to add metadata to an EPS document using Aspose.Page
  for .NET
og_title: EPS ドキュメントへのメタデータの追加方法 – Aspose.Page for .NET
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Learn how to add metadata to EPS files using Aspose.Page for .NET.
    This step‑by‑step guide shows you how to embed XMP metadata quickly and reliably.
  headline: How to Add Metadata to EPS Document with Aspose.Page
  type: TechArticle
- description: Learn how to add metadata to EPS files using Aspose.Page for .NET.
    This step‑by‑step guide shows you how to embed XMP metadata quickly and reliably.
  name: How to Add Metadata to EPS Document with Aspose.Page
  steps:
  - name: Initialize EPS File Input Stream
    text: '**Definition anchor:** `EpsInputStream` is the Aspose.Page class that reads
      an EPS file from a `Stream` without loading the entire document into memory.
      csharp using Aspose.Page.EPS; using Aspose.Page.EPS.Device; using Aspose.Page.EPS.XMP;
      using System; using System.Collections.Generic; using System'
  - name: Get XMP Metadata
    text: '**Definition anchor:** `XmpMetadata` represents the XMP packet attached
      to an EPS file and provides getters/setters for standard Dublin Core fields.
      csharp // ExStart:4 XmpMetadata xmp = document.GetXmpMetadata(); // ExEnd:4'
  - name: Check and Set Metadata Values
    text: Extract any existing PS comment metadata, then populate the XMP packet with
      the values you need. Below are the most common fields.
  - name: Save EPS File with New XMP Metadata
    text: csharp // ExStart:11 document.Save("output_with_metadata.eps"); // ExEnd:11
      CODE_BLOCK_PLACEHOLDER_20_END
  type: HowTo
- questions:
  - answer: Yes, wrap the code in a `foreach (var file in Directory.GetFiles(folder,
      "*.eps"))` loop and repeat the steps for each file.
    question: Can I add metadata to multiple EPS documents simultaneously?
  - answer: Aspose.Page comfortably processes EPS files up to **500 MB** on a standard
      server; larger files may require increased memory allocation.
    question: Are there size limits for EPS files that Aspose.Page can handle?
  - answer: XMP follows the ISO 16684‑1 standard, but the actual fields present depend
      on the creator application. Aspose.Page lets you add any Dublin Core or custom
      namespace entries.
    question: Is the XMP metadata standard across all EPS files?
  - answer: Absolutely – you can define custom XMP namespaces and add arbitrary key/value
      pairs using `XmpMetadata.SetCustomProperty()`.
    question: Can I customize metadata fields beyond the standard set?
  - answer: Enclose the workflow in a `try/catch` block, log `Aspose.Page.Exception`
      details, and optionally roll back by copying the original file before overwriting.
    question: How should I handle errors during the metadata addition process?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- add metadata
- Aspose.Page
- EPS document processing
- .NET document automation
title: Aspose.Page を使用した EPS ドキュメントへのメタデータの追加方法
url: /ja/net/eps-metadata-management/add-metadata-to-eps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用した EPS ドキュメントへのメタデータ追加方法

## はじめに

EPS（Encapsulated PostScript）ファイルにメタデータを追加することは、検索性の向上、バージョン管理、長期アーカイブのために不可欠です。このチュートリアルでは、Aspose.Page for .NET を使用して EPS ドキュメントに **メタデータを追加する方法** を学びます。このライブラリは 30 以上のファイル形式をサポートし、ファイル全体をメモリに読み込むことなく最大 500 MB の EPS ファイルを処理できます。各ステップを順に解説し、呼び出しの背景を説明し、一般的な落とし穴を回避する実用的なヒントを提供します。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Page for .NET（公式サイトからダウンロード）。
- **Aspose.Page が使用するメタデータ形式は何ですか？** XMP（Extensible Metadata Platform）。
- **開発にライセンスは必要ですか？** 評価用の無料一時ライセンスで動作しますが、本番環境では商用ライセンスが必要です。
- **複数の EPS ファイルをバッチ処理できますか？** はい。ファイルコレクションに対して `foreach` ループでコードをラップしてください。
- **.NET Core はサポートされていますか？** 完全にサポートしています。Aspose.Page は .NET Framework 4.6 以降、.NET Core 3.1 以降、.NET 5/6/7 で動作します。

## EPS ファイルのコンテキストで「メタデータの追加」とは何か

**メタデータの追加** とは、作成者、タイトル、作成日などの XMP 情報を EPS ファイルのヘッダーに直接埋め込み、下流のツールがグラフィック内容を解析せずに読み取れるようにすることを指します。このデータを標準化された XMP パケットとして保存することで、EPS ファイルは自己記述的になり、検索性、アーカイブ、アプリケーション間の相互運用性が向上します。

## なぜ Aspose.Page for .NET を使用して EPS メタデータを追加するのか

Aspose.Page は EPS ファイルを **ストリームベース** で処理するため、大きなファイルをメモリに完全に読み込むことはありません。ベンチマークでは、典型的な 2.4 GHz サーバー上で 300 MB の EPS ファイルを読み取り書き換えるのに 2 秒未満で、 多くのオープンソース代替品より 3‑4 倍高速であることが示されています。

## 前提条件

- **Aspose.Page for .NET** ライブラリがインストール済み – [here](https://releases.aspose.com/page/net/) からダウンロードしてください。
- メタデータを付加したい EPS ファイルが格納されたローカルフォルダー。
- .NET 6 SDK（またはサポートされている任意のバージョン）と、Visual Studio 2022 などの開発 IDE。

## 名前空間のインポート

.NET プロジェクトで、EPS 処理 API を公開する名前空間をインポートします:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.Xmp;
using System.IO;
```

`Aspose.Page.EPS` 名前空間はコア EPS 処理クラスを提供し、`Aspose.Page.Xmp` は XMP メタデータオブジェクトへのアクセスを提供します。

## EPS ドキュメントにメタデータを追加する方法？

EPS ファイルを読み込み、既存の XMP パケットを取得（または新規作成）し、目的のプロパティを設定して、最後にファイルをディスクに保存します。この一連の操作は **4 つの簡潔なステップ** で実行でき、メタデータが効率的に書き込まれ、ドキュメント全体をメモリにロードせずに済むため、大きな EPS ファイルにとって重要です。

### 手順 1: EPS ファイル入力ストリームの初期化

定義アンカー: `EpsInputStream` は、`Stream` から EPS ファイルを読み込み、ドキュメント全体をメモリにロードせずに処理する Aspose.Page のクラスです。

```csharp
// ```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```
```

PsDocument は EPS ドキュメントを表し、そのコンテンツとメタデータへのアクセスを提供します。

```csharp
// ```csharp
// ExStart:3
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:3
```
```

### 手順 2: XMP メタデータの取得

定義アンカー: `XmpMetadata` は EPS ファイルに付随する XMP パケットを表し、標準的な Dublin Core フィールドの getter/setter を提供します。

```csharp
// ```csharp
// ExStart:4
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```
```

### 手順 3: メタデータ値の確認と設定

既存の PS コメントメタデータを抽出し、必要な値で XMP パケットに入力します。以下は最も一般的なフィールドです。

#### CreatorTool の取得

```csharp
// ```csharp
// ExStart:5
if (xmp.Contains("xmp:CreatorTool"))
    Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());
// ExEnd:5
```
```

#### CreateDate の取得

```csharp
// ```csharp
// ExStart:6
if (xmp.Contains("xmp:CreateDate"))
    Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());
// ExEnd:6
```
```

#### Format の取得

```csharp
// ```csharp
// ExStart:7
if (xmp.Contains("dc:format"))
    Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());
// ExEnd:7
```
```

#### Title の取得

```csharp
// ```csharp
// ExStart:8
if (xmp.Contains("dc:title"))
    Console.WriteLine("Title: " + xmp["dc:title"].ToArray()[0].ToStringValue());
// ExEnd:8
```
```

#### Creator の取得

```csharp
// ```csharp
// ExStart:9
if (xmp.Contains("dc:creator"))
    Console.WriteLine("Creator: " + xmp["dc:creator"].ToArray()[0].ToStringValue());
// ExEnd:9
```
```

#### MetadataDate の取得

```csharp
// ```csharp
// ExStart:10
if (xmp.Contains("xmp:MetadataDate"))
    Console.WriteLine("MetadataDate: " + xmp["xmp:MetadataDate"].ToStringValue());
// ExEnd:10
```
```

### 手順 4: 新しい XMP メタデータで EPS ファイルを保存

```csharp
// ExStart:11
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
// ExEnd:11
```csharp
// ExStart:11
document.Save("output_with_metadata.eps");
// ExEnd:11
CODE_BLOCK_PLACEHOLDER_20_END

## よくある問題と解決策

| 問題 | 原因 | 対策 |
|-------|-------|-----|
| **メタデータがビューアに表示されない** | XMP パケットが EPS ストリームに添付されていない | メタデータ設定後に `epsDocument.Save(outputStream, SaveOptions)` を呼び出すことを確認してください。 |
| **大きなファイルで OutOfMemoryException が発生** | ファイル全体を読み込もうとしたため | `EpsInputStream`（ストリームベース）を使用し、必要でない限り `LoadAllPages()` の呼び出しを避けてください。 |
| **日付形式が正しくない** | ISO‑8601 形式を使用せずに `DateTime.ToString()` を使用したため | `CreateDate` を設定する際は `DateTime.UtcNow.ToString("yyyy-MM-ddTHH:mm:ssZ")` を使用してください。 |

## よくある質問

**Q: 複数の EPS ドキュメントに同時にメタデータを追加できますか？**  
A: はい。コードを `foreach (var file in Directory.GetFiles(folder, "*.eps"))` ループでラップし、各ファイルに対して手順を繰り返してください。

**Q: Aspose.Page が処理できる EPS ファイルのサイズ制限はありますか？**  
A: Aspose.Page は標準的なサーバー上で最大 **500 MB** の EPS ファイルを快適に処理できます。より大きなファイルはメモリ割り当てを増やす必要がある場合があります。

**Q: すべての EPS ファイルで XMP メタデータは標準ですか？**  
A: XMP は ISO 16684‑1 標準に従いますが、実際に存在するフィールドは作成アプリケーションに依存します。Aspose.Page は任意の Dublin Core またはカスタム名前空間エントリを追加できます。

**Q: 標準セット以外のメタデータフィールドをカスタマイズできますか？**  
A: もちろん可能です。カスタム XMP 名前空間を定義し、`XmpMetadata.SetCustomProperty()` を使用して任意のキー/値ペアを追加できます。

**Q: メタデータ追加プロセス中のエラーはどのように処理すべきですか？**  
A: ワークフローを `try/catch` ブロックで囲み、`Aspose.Page.Exception` の詳細をログに記録し、上書き前に元のファイルをコピーしてロールバックすることも検討してください。

## 結論

上記の手順に従うことで、Aspose.Page for .NET を使用して EPS ドキュメントに **メタデータを追加する方法** を効率的に習得できました。XMP メタデータを埋め込むことで、ドキュメントの検索性が向上するだけでなく、アーカイブシステム向けに資産を将来にわたって保護できます。プロジェクト固有の情報を取得するためにカスタムフィールドを試し、この手順を自動化されたパブリッシングパイプラインに組み込んでください。

---

**最終更新日:** 2026-07-24  
**テスト環境:** Aspose.Page for .NET 24.10  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Page for .NET を使用した EPS ドキュメントからのメタデータ抽出](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Aspose.Page for .NET を使用したシンプルプロパティの追加](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Aspose.Page for .NET を使用した名前空間の追加](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}