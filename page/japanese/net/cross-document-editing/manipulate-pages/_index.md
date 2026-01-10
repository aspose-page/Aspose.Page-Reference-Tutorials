---
date: 2026-01-10
description: Aspose.Page for .NET を使用して XPS ドキュメントを結合する方法を学びましょう。このステップバイステップガイドでは、効率的な結果を得るためのページ操作テクニックを示します。
linktitle: Manipulate Pages
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET を使用して XPS ドキュメントを結合
url: /ja/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用した XPS ドキュメントの結合

## はじめに

このチュートリアルでは、**XPS ドキュメントの結合**とページ操作を Aspose.Page ライブラリを使って .NET 環境で実行する方法を学びます。複数のレポートを 1 つの XPS ファイルにまとめたり、ページ順序を調整して洗練された出力を作成したりする必要がある場合、本ガイドがステップバイステップで分かりやすく解説し、すぐに実行できるコード例を提供します。

## クイック回答
- **Aspose.Page で何ができますか？** XPS ドキュメントの結合、ページの挿入・追加・削除、そして結果の保存が可能です。  
- **テスト用にライセンスは必要ですか？** 評価用の一時ライセンスが利用できます。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **Visual Studio は必須ですか？** 必須ではありませんが、C# をサポートする任意の IDE が使用可能です。Visual Studio が推奨されます。  
- **結合にかかる時間は？** 標準サイズの XPS ファイルで数秒程度です。

## XPS ドキュメントの結合とは？

XPS ドキュメントの結合とは、2 つ以上の既存 XPS ファイルからページを取得し、1 つの XPS ドキュメントにまとめることを指します。統合レポートの作成、マルチページマニュアルの編纂、または別フォーマットに変換せずに印刷用パッケージを準備する際に便利です。

## .NET で Aspose.Page を使用する理由

Aspose.Page は **純粋な .NET API** を提供し、外部ツールやサードパーティコンポーネントを必要とせずに XPS ファイルを直接操作できます。ページ順序、挿入位置、コンテンツの保持を細かく制御できるため、結合プロセスが信頼性高く高速に実行できます。

## 前提条件

- **Aspose.Page for .NET** – [Aspose.Page for .NET ドキュメント](https://reference.aspose.com/page/net/) からダウンロードしてください。  
- **開発環境** – Visual Studio、Rider、または C# をサポートする任意の IDE。  
- **入力 XPS ファイル** – 既知のフォルダーに配置した 3 つのサンプルファイル（`input1.xps`、`input2.xps`、`input3.xps`）。

## 名前空間のインポート

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

これらの名前空間により、コア XPS ドキュメントクラス、ページモデル、基本的な描画ユーティリティにアクセスできます。

## 手順 1: ドキュメント ディレクトリの設定

```csharp
string dataDir = "Your Document Directory";
```

**Your Document Directory** を XPS ファイルが格納されているフルパス（例: `C:\\Docs\\XpsFiles\\`）に置き換えてください。

## 手順 2: XPS ドキュメント インスタンスの作成

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`、`doc2`、`doc3` は結合したい元のドキュメントを表します。  
- `doc4` は結合結果を保持する空の XPS ドキュメントです。

## 手順 3: ページの挿入、追加、削除

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

各行の動作は次のとおりです。

1. **InsertPage(1, doc2.Page, false)** – `doc2` の最初のページを `doc4` の位置 1 に挿入します。  
2. **AddPage(doc3.Page, false)** – `doc3` の最初のページを `doc4` の末尾に追加します。  
3. **RemovePageAt(2)** – 現在インデックス 2 にあるページを削除します（不要なページの除去に便利）。  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – `doc1` の 3 ページ目を位置 2 に挿入し、結合を完了します。

これらの操作により、**XPS ドキュメントの結合**と同時にページの再配置や除外が簡単に行えます。

## 手順 4: 結合されたドキュメントの保存

```csharp
doc4.Save(dataDir + "out.xps");
```

最終的な結合 XPS ファイル（`out.xps`）は同じディレクトリに書き込まれます。任意の XPS ビューアで開くか、Aspose.Page でさらに処理できます。

## よくある問題と解決策
- **ファイルが見つからない** – `dataDir` のパスを再確認し、入力ファイルが存在することを確認してください。  
- **無効なページインデックス** – ページインデックスは 1 ベースです。存在しないページを挿入しようとすると例外がスローされます。  
- **ライセンスエラー** – 本番環境にデプロイする前に、一時ライセンスまたは正式ライセンスを適用してください。

## FAQ

### Q1: 異なる XPS ドキュメントからページを操作できますか？

A1: はい。本チュートリアルの通り、複数の XPS ドキュメントからページを新しいドキュメントに挿入できます。

### Q2: 特定のページをドキュメントから削除するには？

A2: `RemovePageAt` メソッドを使用し、削除したいページのインデックスを指定してください。

### Q3: Aspose.Page は Visual Studio と互換性がありますか？

A3: はい、Aspose.Page は Visual Studio と完全に互換性があり、.NET プロジェクトへの統合が容易です。

### Q4: ライセンスオプションはありますか？

A4: はい、[こちら](https://purchase.aspose.com/temporary-license/) でライセンスオプションを確認し、一時ライセンスを取得できます。

### Q5: サポートや質問はどこで受けられますか？

A5: [Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) でサポートを受け、コミュニティと交流できます。

## よくある質問

**Q: 3 つ以上の XPS ファイルを結合できますか？**  
A: もちろんです。追加の `XpsDocument` インスタンスを作成し、`InsertPage` または `AddPage` を繰り返し使用して、より大きな結合ドキュメントを構築できます。

**Q: 結合は元の書式やグラフィックを保持しますか？**  
A: はい。Aspose.Page はページコンテンツをバイト単位でコピーするため、テキスト、画像、ベクターグラフィックはそのまま保持されます。

**Q: インデックスを指定せずに末尾にページを挿入するには？**  
A: `AddPage(sourcePage, false)` を使用すると、ページがドキュメントの末尾に追加されます。

**Q: UI がなくてもサーバー上で XPS ドキュメントを結合できますか？**  
A: API は完全にヘッドレスです。ASP.NET、Azure Functions、または任意のサーバーサイド .NET 環境で同じコードを実行できます。

**Q: XPS ファイルがパスワード保護されている場合は？**  
A: 現在 Aspose.Page は暗号化された XPS ファイルをサポートしていません。結合前にファイルを復号する必要があります。

**最終更新日:** 2026-01-10  
**テスト環境:** Aspose.Page for .NET 24.10  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}