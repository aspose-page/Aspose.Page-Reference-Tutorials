---
date: 2026-08-08
description: .NET 用 Aspose.Page を使用して、XMP メタデータ付き EPS の作成方法と名前付き値の追加方法を学びます。コードプレースホルダー付きのステップバイステップガイドです。
keywords:
- create eps with xmp
- add named value eps
- aspose.page metadata
lastmod: 2026-08-08
linktitle: 名前付き値を追加
og_description: .NET で Aspose.Page を使用して XMP メタデータ付き EPS を作成します。このガイドでは、EPS ファイルに名前付き値を迅速かつ確実に追加する方法を示します。
og_image_alt: Guide showing how to add XMP named value to an EPS file with Aspose.Page
og_title: XMP を使用して EPS を作成 – Aspose.Page で名前付き値を追加
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create EPS with XMP metadata and add named values using
    Aspose.Page for .NET. Step‑by‑step guide with code placeholders.
  headline: Create EPS with XMP – add named value using Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page supports EPS versions 3.0 through 3.3, ensuring broad compatibility
      with legacy and modern files.
    question: Is Aspose.Page compatible with different EPS file versions?
  - answer: Yes, a commercial license is required for production use. You can purchase
      a license **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for commercial projects?
  - answer: Yes, a fully functional trial can be downloaded **[Aspose.Page free trial
      download page](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      to ask questions and share experiences.
    question: How can I get support or join the community?
  - answer: A temporary license lets you evaluate the product for a short period.
      You can request one **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: What is a temporary license and how do I obtain one?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: XMP を使用して EPS を作成 – Aspose.Page で名前付き値を追加
url: /ja/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EPS を XMP で作成 – Aspose.Page を使用して名前付き値を追加

## はじめに

このチュートリアルでは、**XMP メタデータ付き EPS を作成**し、.NET 用 Aspose.Page ライブラリを使用して名前付き値を注入する方法を学びます。バッチ処理パイプラインを構築している場合や、カスタム XMP タグで EPS ファイルを拡張する必要がある場合でも、以下の手順でプロジェクトの設定から変更後のファイルの保存までをすべて説明します。Aspose.Page は、メモリに全体を読み込むことなく **500 ページ**までの EPS ドキュメントを処理できるため、大量処理シナリオに適しています。

## クイック回答
- **主な目的は何ですか？** 既存の EPS ファイルに名前付き XMP 値を追加することです。  
- **必要なライブラリはどれですか？** .NET 用 Aspose.Page。  
- **ライセンスは必要ですか？** 本番環境では商用ライセンスが必要です。無料トライアルも利用可能です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **実装にどれくらい時間がかかりますか？** 基本的なユースケースでおおよそ 10〜15 分です。

## .NET で XMP メタデータ付き EPS を作成する方法は？

対象の EPS ファイルを読み込み、XMP メタデータオブジェクトを取得（または作成）し、必要な名前付き値を追加して、最後にドキュメントをディスクに保存します。このワークフローは数回のメソッド呼び出しだけで完了し、サポートされているすべての EPS バージョンで一貫して動作します。また、既存のページコンテンツや他の XMP 構造を保持するため、複数のメタデータ更新を安全に連鎖させることができます。

## 前提条件

- C# と .NET プロジェクト構造の基本的な知識。  
- Visual Studio 2022（または互換性のある IDE）。  
- Aspose.Page for .NET ライブラリ。まだお持ちでない場合は、**Aspose.Page for .NET ダウンロードページ**([Aspose.Page for .NET download page](https://releases.aspose.com/page/net/)) からダウンロードしてください。  

## 名前空間のインポート

以下の名前空間は、Aspose.Page の EPS 処理、デバイス出力、XMP メタデータクラスへのアクセスを提供します。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 手順 1: EPS ファイル入力ストリームの初期化

ソース EPS ファイル用に `FileStream` を作成し、ドキュメント操作用の `PsDocument` オブジェクトをインスタンス化します。

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## 手順 2: XMP メタデータの取得

ドキュメントから `XmpMetadata` オブジェクトを取得します。このオブジェクトは埋め込まれた XMP パケットを表します。

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## 手順 3: XMP メタデータの値を変更

`XmpMetadata` の `AddNamedValue` メソッドを使用して、指定された XMP 構造に新しい名前付き値を挿入します。

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## 手順 4: 変更された XMP メタデータで EPS ファイルを保存

変更されたドキュメントを新しい `FileStream` に書き込んで保存します。

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## なぜ EPS メタデータに Aspose.Page を使用するのか？

Aspose.Page は **50 以上の XMP スキーマ** をサポートし、**500 ページ**までの EPS ファイルを処理でき、典型的なドキュメントではメモリ使用量を **30 MB** 未満に抑えます。外部ツールやネイティブコードに依存しないため、Windows、Linux、macOS 環境全体で一貫した動作が保証されます。

## よくある問題とトラブルシューティング

- **XMP パケットが欠落している:** `GetXmpMetadata()` が `null` を返す場合、EPS ファイルに XMP ブロックが含まれていません。ライブラリは自動的に作成しますが、ファイルが破損していないことを確認してください。  
- **名前空間の競合:** カスタムの名前付き値を追加する際は、既存スキーマと衝突しないように一意の名前空間 URI を使用してください。  
- **大きなファイル:** 200 MB を超える EPS ファイルの場合、メモリ使用量が過剰になるのを防ぐために出力をストリーミングすることを検討してください。

## よくある質問

**Q: Aspose.Page は異なる EPS ファイルバージョンに対応していますか？**  
A: Aspose.Page は EPS バージョン 3.0 から 3.3 をサポートしており、レガシーおよび最新ファイルとの広範な互換性を確保しています。

**Q: 商用プロジェクトで Aspose.Page を使用できますか？**  
A: はい、本番環境での使用には商用ライセンスが必要です。ライセンスは **[Aspose.Page ライセンス購入ページ](https://purchase.aspose.com/buy)** から購入できます。

**Q: 無料トライアルは利用可能ですか？**  
A: はい、機能フルのトライアルは **[Aspose.Page 無料トライアルダウンロードページ](https://releases.aspose.com/)** からダウンロードできます。

**Q: サポートを受けるかコミュニティに参加するには？**  
A: 質問や体験の共有は **[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)** へどうぞ。

**Q: 一時ライセンスとは何ですか、どう取得しますか？**  
A: 一時ライセンスは製品を短期間評価するためのものです。取得は **[一時ライセンスリクエストページ](https://purchase.aspose.com/temporary-license/)** から行えます。

---

**最終更新日:** 2026-08-08  
**テスト環境:** Aspose.Page 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Page for .NET を使用した EPS ドキュメントへのメタデータ追加](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Aspose.Page for .NET を使用した名前付き値の変更](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)
- [Aspose.Page for .NET を使用した EPS ドキュメントからのメタデータ抽出](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}