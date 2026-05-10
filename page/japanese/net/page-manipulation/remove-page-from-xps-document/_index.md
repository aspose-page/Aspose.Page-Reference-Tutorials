---
date: 2026-03-19
description: Aspose.Page for .NET を使用して **remove page xps** ドキュメントと **delete page
  at index** を削除する方法を学びましょう – 前提条件、コードサンプル、FAQ を含む完全なステップバイステップ ガイドです。
linktitle: Remove Page from XPS Document
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET を使用して XPS ドキュメントからページを削除する
url: /ja/net/page-manipulation/remove-page-from-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用した XPS ドキュメントからページを削除する

## はじめに

プログラムで **remove page xps** ファイルを削除する必要がある場合、Aspose.Page for .NET はクリーンで信頼性の高い方法を提供します。このチュートリアルでは、XPS ドキュメントから特定のページを削除するために必要な正確な手順を順に解説し、この操作が重要な理由を説明し、更新されたファイルをディスクに保存する方法を示します。

## クイック回答
- **What does “remove page xps” mean?** XPS (XML Paper Specification) ドキュメントから単一のページを削除することを指します。  
- **Which method deletes a page?** インデックスはゼロベースの `RemovePageAt(index)` を使用します。  
- **Can I delete a page at any position?** はい – 必要に応じて **delete page at index** 0、1、2 などのページを削除できます。  
- **Do I need a license for Aspose.Page?** テストには一時ライセンスが必要で、製品版には正式ライセンスが必要です。  
- **Is the code compatible with .NET 6?** もちろんです – Aspose.Page は .NET Framework、.NET Core、.NET 5/6 をサポートしています。

## “remove page xps” とは何ですか？

XPS ドキュメントからページを削除することは、残りのコンテンツ、レイアウト、メタデータを保持しながら、ドキュメントのページの一つを取り除くことを意味します。この操作は、PDF をトリミングしたり、カスタムレポートを生成したり、ドキュメントサイズの制限に対応したりする際に便利です。

## なぜ Aspose.Page for .NET を使用するのか？

- **No external dependencies** – 純粋な .NET ライブラリです。  
- **High fidelity** – ベクターグラフィックとレイアウトの精度を保持します。  
- **Cross‑platform** – Windows、Linux、macOS で動作します。  
- **Simple API** – 単一のメソッド呼び出し（`RemovePageAt`）で主要な処理を行います。

## 前提条件

コードに取り掛かる前に、以下が揃っていることを確認してください：

- **Aspose.Page for .NET** – [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) からダウンロードしてください。  
- **.NET 開発環境**（Visual Studio、VS Code、またはお好みの IDE）  
- **sample XPS document**（例: `Sample.xps`）を、プロジェクトから参照できるフォルダーに配置してください。

## 名前空間のインポート

C# ファイルの先頭に必要な名前空間を追加し、コンパイラが XPS クラスを見つけられるようにします。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ステップ 1: ドキュメントディレクトリの設定

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **Pro tip:** クロスプラットフォームのパス構築には `Path.Combine` を使用してください。

## ステップ 2: 新しい XPS ドキュメントの作成

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument(dataDir + "Sample.xps");
// ExEnd:4
```

この行は既存の XPS ファイル（`Sample.xps`）を `XpsDocument` オブジェクトに読み込み、操作できる状態にします。

## ステップ 3: インデックスでページを削除

```csharp
// ExStart:5
// Remove the first page (at index 1).
doc.RemovePageAt(1);
// ExEnd:5
```

`RemovePageAt` メソッドは **指定したインデックスのページを削除します**。インデックスは 0 から始まることに注意してください。したがって `1` は2ページ目を削除します。削除したいページに合わせてインデックスを調整してください。

## ステップ 4: 結果の XPS ドキュメントを保存

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "Sample_out.xps");
// ExEnd:6
```

削除後、ドキュメントは `Sample_out.xps` として保存されます。不要なページが削除されたことを確認するために、このファイルを開くことができます。

## 一般的な問題と解決策

| Issue | Cause | Fix |
|-------|-------|-----|
| **Index out of range** | 存在しないページを削除しようとしています。 | `RemovePageAt` を呼び出す前に `doc.Pages.Count` でページ数を確認してください。 |
| **File locked** | XPS ファイルが別のプログラムで開かれています。 | コードを実行する前に、ビューアを閉じるか、ファイルが使用中でないことを確認してください。 |
| **License not applied** | 本番環境で有効なライセンスなしでライブラリを使用しています。 | `License license = new License(); license.SetLicense("Aspose.Page.lic");` を使用して一時または永続ライセンスを適用してください。 |

## よくある質問

**Q1: Aspose.Page for .NET を使用して複数のページを一度に削除できますか？**  
A1: はい、`RemovePageAt` を繰り返し呼び出すか、インデックスのリストをループ処理してください（残りのインデックスが有効になるよう、最高インデックスから最低インデックスの順に削除することを忘れずに）。

**Q2: Aspose.Page は最新の .NET フレームワークと互換性がありますか？**  
A2: Aspose.Page は定期的に更新され、.NET 6 や .NET 7 を含む最新の .NET リリースをサポートしています。

**Q3: 商用アプリケーションで Aspose.Page を使用できますか？**  
A3: もちろんです。ライセンスの詳細は [Aspose.Purchase](https://purchase.aspose.com/buy) ページをご覧ください。

**Q4: Aspose.Page に関する追加のサポートやディスカッションはどこで見つけられますか？**  
A4: ヒント、サンプル、トラブルシューティングの支援については、[Aspose.Page forum](https://forum.aspose.com/c/page/39) コミュニティに参加してください。

**Q5: Aspose.Page のテストに一時ライセンスは必要ですか？**  
A5: はい、購入前にライブラリを評価するための [temporary license](https://purchase.aspose.com/temporary-license/) を取得できます。

**Q6: ページ削除後にドキュメントのメタデータを保持するにはどうすればよいですか？**  
A6: `RemovePageAt` メソッドは元のメタデータを自動的に保持します。必要に応じて変更する場合は、`doc.DocumentProperties` コレクションを使用してください。

## 結論

これで、Aspose.Page for .NET を使用して **remove page xps** ドキュメントと **delete page at index** の方法を学びました。この簡潔なアプローチにより、ページ削除ロジックを .NET アプリケーションに直接組み込むことができ、XPS ドキュメントの内容を完全に制御できます。

---

**最終更新日:** 2026-03-19  
**テスト環境:** Aspose.Page 24.12 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}