---
date: 2026-08-08
description: Aspose.Page for .NET を使用して、Aspose.Page ドキュメントの初期化、XML 名前空間の追加、EPS ファイルの
  XMP メタデータの変更方法を学びます。
keywords:
- initialize aspose page document
- c# add xml namespace
- open eps file stream
- how to add xmp namespace
lastmod: 2026-08-08
linktitle: 名前空間を追加
og_description: Aspose.Page for .NET を使用して、Aspose.Page ドキュメントを初期化し、XML 名前空間を追加し、EPS
  ファイルの XMP メタデータを編集します。簡潔な手順とコードスニペットに従ってください。
og_image_alt: Guide showing how to add namespace to EPS metadata using Aspose.Page
  for .NET
og_title: Aspose.Page ドキュメントを初期化し、.NET で名前空間を追加する
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to initialize Aspose.Page document, add an XML namespace,
    and modify XMP metadata in EPS files using Aspose.Page for .NET.
  headline: Initialize Aspose.Page document and add namespace in .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for .NET works with .NET Framework 4.5+, .NET Core 3.1+,
      and .NET 5/6+.
    question: Is Aspose.Page compatible with all versions of .NET?
  - answer: Absolutely. Retrieve the `XmpMetadata` object and read its properties
      without invoking `SetProperty` or `AddNamespace`.
    question: Can I extract metadata without modifying it?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support or assistance?
  - answer: Yes, you can explore a free trial of Aspose.Page on the [Aspose.Page free
      trial](https://releases.aspose.com/) page.
    question: Is there a free trial available for Aspose.Page?
  - answer: Obtain a temporary license on the [temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/)
      page for testing purposes.
    question: How can I obtain a temporary license for Aspose.Page?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- Aspose.Page
- c# document processing
title: Aspose.Page ドキュメントを初期化し、.NET で名前空間を追加する
url: /ja/net/eps-metadata-management/modify-eps-metadata-add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET で Aspose.Page ドキュメントを初期化し、名前空間を追加する

## はじめに

モダンな .NET 開発において、**initialize aspose page document** は、プログラムで EPS ファイルを操作する必要があるときの最初のステップになることが多いです。Aspose.Page for .NET は XMP メタデータを完全に制御でき、カスタム XML 名前空間の追加、既存プロパティの編集、変更内容のファイルへの保存が可能です。このチュートリアルでは、適切な名前空間のインポートから変更された EPS ファイルの永続化まで、すべての詳細を順を追って説明しますので、メタデータ管理を自信を持ってワークフローに組み込むことができます。

## クイック回答
- **最初のコード行は何ですか？** Create a `new Document("yourfile.eps")` to load the EPS file.
- **どのメソッドが名前空間を追加しますか？** Use `XmpMetadata.AddNamespace(prefix, uri)`.
- **開発にライセンスは必要ですか？** A free trial works for testing; a license is required for production.
- **大きな EPS ファイルをストリーミングできますか？** Yes—use a `FileStream` to open the file without loading it entirely into memory.
- **.NET 6+ と互換性がありますか？** Absolutely; Aspose.Page supports .NET Framework 4.5+, .NET Core 3.1+, and .NET 6+.

## initialize aspose page document とは何ですか？

`Document` クラスは、メモリにロードされた EPS ファイルを表します。`new Document("file.eps")` でファイルをロードすると、ページ、グラフィック、XMP メタデータに直接アクセスでき、ドキュメントの任意の部分を読み取ったり変更したりできます。また、XMP メタデータやページコンテンツを操作するためのメソッドも提供されます。

## EPS メタデータに XML 名前空間を追加する理由

カスタム XML 名前空間を追加すると、メタデータスキーマが拡張され、標準の XMP フィールドと共に独自情報を保存できるようになります。Aspose.Page は **50+** の XMP プロパティをサポートし、**200+ ページ** のファイルでもドキュメント全体を RAM に常駐させる必要がないため、処理が高速化されメモリ消費が抑えられます。

## 前提条件

1. **Aspose.Page for .NET ライブラリ** – [Aspose.Page documentation](https://reference.aspose.com/page/net/) からダウンロードしてください。  
2. **.NET 開発環境** – Visual Studio 2022、Rider、または .NET 6+ をサポートする任意の IDE。

続行する前に、プロジェクトにライブラリが参照されていること（NuGet または直接 DLL 参照）を確認してください。

## 名前空間のインポート

Aspose.Page を使用するには、`Document` と XMP クラスを公開するコア名前空間をインポートする必要があります。

必要なものは次のとおりです：

```csharp
using Aspose.Page.EPS;
using Aspose.Page.XMP;
using System.IO;
```

これらのインポートにより、今後の手順で必要となる `Document`、`XmpMetadata`、およびストリーム処理クラスにアクセスできます。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 手順 1: プロジェクトの初期化

コードを配置したいソースファイルを開きます。まず `Document` クラスのインスタンスを作成します。これにより、**initialize aspose page document** がさらに操作できるようになります。`Document` クラスは EPS ドキュメントを表し、そのコンテンツとメタデータへのアクセスを提供します。

```csharp
var epsDocument = new Document("sample.eps");
```

この行は EPS ファイルを `epsDocument` オブジェクトにロードし、以降のすべての API 呼び出しを可能にします。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## 手順 2: eps ファイルストリームを開く

`FileStream` クラスはファイルの読み書き用ストリームを提供し、EPS ファイル全体をメモリにロードすることを回避できます。

```csharp
using (FileStream fs = new FileStream("sample.eps", FileMode.Open, FileAccess.ReadWrite))
{
    // Stream is ready for XMP operations
}
```

`open eps file stream` パターンは本番環境のワークロードで推奨されます。

```csharp
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);

// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

## 手順 3: xmp メタデータを取得する

`XmpMetadata` クラスは EPS ドキュメントの XMP メタデータをカプセル化します。

```csharp
XmpMetadata xmp = epsDocument.XmpMetadata;
```

これで、現在のすべてのメタデータエントリを保持する操作可能な `xmp` オブジェクトが得られます。

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments.
XmpMetadata xmp = document.GetXmpMetadata();
```

## 手順 4: xmp メタデータを変更する

`AddNamespace` メソッドはプレフィックスと URI で新しい XML 名前空間を登録し、`SetProperty` メソッドはメタデータプロパティに値を割り当てます。

```csharp
// Define a new namespace
string prefix = "myNs";
string uri = "http://mycompany.com/metadata";

// Register the namespace with the XMP metadata object
xmp.AddNamespace(prefix, uri);

// Add a custom property under the new namespace
xmp.SetProperty($"{prefix}:Author", "John Doe");
```

`AddNamespace` 呼び出しでプレフィックスが登録され、`SetProperty` でそのプレフィックスを使用して値が保存されます。

```csharp
// Add new XML namespace "tmp".
xmp.RegisterNamespaceUri("tmp", "http://www.some.org/schema/tmp#");

// Add new string property in the new namespace.
xmp.Add("tmp:newKey", new XmpValue("NewValue"));
```

## 手順 5: eps ファイルを保存する

`Save` メソッドはドキュメントとそのメタデータをファイルシステムに書き戻します。

```csharp
epsDocument.Save("sample-updated.eps");
```

この手順の後、EPS ファイルには新しく追加された名前空間とプロパティが含まれます。

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_namespace_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
```

## よくある問題とトラブルシューティング

- **名前空間はすでに存在します** – If `AddNamespace` throws an error, the prefix is already registered. Use a different prefix or retrieve the existing URI with `xmp.GetNamespaceUri(prefix)`.
- **別のプロセスによってファイルがロックされている** – Ensure the `FileStream` is disposed (`using` block) before calling `Save`.
- **メタデータが永続化されない** – Verify that the EPS file actually supports XMP (most modern EPS files do). Older files may need to be regenerated。

## よくある質問

**Q: Aspose.Page はすべての .NET バージョンと互換性がありますか？**  
A: はい、Aspose.Page for .NET は .NET Framework 4.5+、.NET Core 3.1+、および .NET 5/6+ で動作します。

**Q: メタデータを変更せずに抽出できますか？**  
A: もちろんです。`XmpMetadata` オブジェクトを取得し、`SetProperty` や `AddNamespace` を呼び出さずにプロパティを読み取ります。

**Q: 追加のサポートや支援はどこで得られますか？**  
A: コミュニティサポートとディスカッションは [Aspose.Page forum](https://forum.aspose.com/c/page/39) をご覧ください。

**Q: Aspose.Page の無料トライアルは利用できますか？**  
A: はい、[Aspose.Page free trial](https://releases.aspose.com/) ページで無料トライアルを試すことができます。

**Q: Aspose.Page の一時ライセンスはどう取得できますか？**  
A: テスト目的で [temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/) ページから一時ライセンスを取得してください。

---

**最終更新日:** 2026-08-08  
**テスト環境:** Aspose.Page 24.11 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Page for .NET を使用した EPS ドキュメントへのメタデータ追加](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Aspose.Page for .NET を使用したシンプルプロパティの追加](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Aspose.Page for .NET を使用した EPS ドキュメントからのメタデータ抽出](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}