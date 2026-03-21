---
date: 2026-03-21
description: .NET 用 Aspose.Page を使用して XPS ドキュメントに Unicode テキストを追加する方法を学びましょう。このガイドでは、C#
  で XPS ドキュメントを作成し、Aspose.Page で Unicode 文字列を使用してテキストを追加する手順を示します。
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Aspose.Page を使用して XPS ドキュメントに Unicode テキストを追加する方法
url: /ja/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用して XPS ドキュメントに Unicode テキストを追加する方法

## Introduction

XPS ファイルに **Unicode 文字を追加する方法** が必要な場合は、ここが最適です。このチュートリアルでは、Aspose.Page for .NET を使用して **C# スタイルで XPS ドキュメントを作成** する手順を詳しく解説し、Unicode 文字列を使用した **aspose page add text** 機能を実演します。最後まで実行すれば、右から左 (RTL) の Unicode テキストが正しく表示される完全な XPS ドキュメントが作成できます。

## Quick Answers
- **このチュートリアルで扱う内容は？** Aspose.Page for .NET を使って XPS ドキュメントに Unicode テキストを追加する方法。  
- **使用言語は？** C#（.NET Framework と .NET Core の両方に対応）。  
- **ライセンスは必要ですか？** 開発目的であれば無料トライアルで動作します。商用環境では商用ライセンスが必要です。  
- **フォントやサイズは変更できますか？** はい – サンプルでは Arial 20 pt を使用していますが、インストールされている任意のフォントが使用可能です。  
- **RTL サポートは含まれていますか？** `BidiLevel = 1` を設定することで、Unicode 文字列の右から左描画が有効になります。

## What is “how to add unicode” in XPS?

Unicode テキストを追加するとは、アラビア語、ヘブライ語、中国語など、任意の言語の文字を XPS ドキュメントに挿入することを指します。Aspose.Page の `XpsGlyphs` クラスが低レベルのグリフ配置を担当し、`BidiLevel` プロパティが RTL スクリプトの文字方向を制御します。

## Why use Aspose.Page to add text?

- **フル .NET 統合** – .NET Framework、.NET Core、.NET 5/6+ で動作。  
- **外部依存なし** – 純粋なマネージドコードで、COM 相互運用が不要。  
- **豊富なタイポグラフィサポート** – フォント、スタイル、カラー、双方向テキストに対応。  
- **高性能** – XPS ファイルの作成と保存が高速で、サーバーサイド生成に最適。

## Prerequisites

- C# と .NET 開発の基本知識。  
- Visual Studio（最新バージョンのいずれか）。  
- Aspose.Page for .NET ライブラリ – [こちら](https://releases.aspose.com/page/net/) からダウンロード。

## Import Namespaces

まず、XPS モデルと描画ユーティリティにアクセスできる名前空間をインポートします。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Set up the Document – create XPS document C#

Unicode テキストを格納する新しい XPS ドキュメントを作成します。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Step 2: Add Unicode Text – aspose page add text

実際の Unicode 文字列を追加します。この例では Arial フォント、サイズ 20、位置 (400 f, 200 f) に配置しています。`BidiLevel` を 1 に設定することで、文字列が右から左としてレンダリングされます。

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Step 3: Save the Document

最後に、XPS ファイルをディスクに保存します。

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Congratulations! You have successfully **how to add unicode** text to an XPS document using Aspose.Page for .NET.

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| テキストが文字化けする | フォントが対象 Unicode 範囲をサポートしていない | 必要なグリフを含むフォント（例: Arial Unicode MS）を使用してください。 |
| RTL テキストが左から右に表示される | `BidiLevel` が設定されていない、または 0 のまま | RTL スクリプトでは `glyphs.BidiLevel = 1;` を確実に設定してください。 |
| ファイルが保存されない | `dataDir` パスが無効 | ディレクトリが存在し、アプリに書き込み権限があることを確認してください。 |

## Frequently Asked Questions

**Q: Aspose.Page は最新の .NET フレームワークに対応していますか？**  
A: はい、Aspose.Page は .NET Framework、.NET Core、.NET 5/6+ をサポートするよう定期的に更新されています。

**Q: テキスト追加時にフォントのスタイルやサイズをカスタマイズできますか？**  
A: もちろんです！`AddGlyphs` メソッドを使用すれば、任意のフォントファミリー、サイズ、`FontStyle` を指定できます。

**Q: Aspose.Page の追加ドキュメントはどこで確認できますか？**  
A: 詳細な API 情報は [こちら](https://reference.aspose.com/page/net/) のドキュメントをご参照ください。

**Q: Aspose.Page の入門に役立つ無料リソースはありますか？**  
A: はい、[Aspose.Page forum](https://forum.aspose.com/c/page/39) のコミュニティフォーラムでヒントやサンプル、サポートを得られます。

**Q: 購入前に試用版はありますか？**  
A: もちろんです！評価用に無料トライアルを [こちら](https://releases.aspose.com/) からダウンロードしてください。

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}