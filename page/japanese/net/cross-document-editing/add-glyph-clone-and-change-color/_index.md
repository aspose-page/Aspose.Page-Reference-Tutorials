---
date: 2026-01-07
description: Aspose.Page for .NET を使用して XPS ドキュメントの作成方法、グリフクローンの追加、単色ブラシの使用、XPS ファイルの保存方法を学びます。
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: XPSドキュメントの作成 – Aspose.Page for .NETでグリフをクローンし、色を変更
url: /ja/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS ドキュメントの作成 – Aspose.Page for .NET でグリフ クローンを追加し色を変更する

## Introduction

このステップバイステップ ガイドへようこそ。**XPS ドキュメント** を作成し、グリフをクローンし、色を変更する方法を Aspose.Page for .NET を使用して解説します。動的レポート、請求書、カスタム グラフィックの作成において、これらのテクニックを習得すれば、.NET エコシステムを離れることなく視覚的にリッチな XPS 出力を実現できます。

## Quick Answers
- **What is the primary goal?** XPS ドキュメントを作成し、グリフ クローンを追加し、色を変更します。  
- **Which library is used?** Aspose.Page for .NET。  
- **Do I need a license?** 評価用の一時ライセンスが利用可能です。製品版ではフル ライセンスが必要です。  
- **What .NET versions are supported?** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **How do I save the result?** `Save` メソッドを使用して XPS ファイルをディスクに書き込みます。

## Prerequisites

チュートリアルに入る前に、以下の前提条件を満たしていることを確認してください。

- C# プログラミング言語の基本的な理解。  
- Visual Studio またはその他のお好みの C# 開発環境がインストール済み。  
- Aspose.Page for .NET ライブラリ。ダウンロードは [こちら](https://releases.aspose.com/page/net/)。  
- XPS ドキュメント形式に関する基本的な知識。

## Import Namespaces

開始するには、C# プロジェクトに必要な名前空間をインポートします:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## How to Create XPS Document and Add Glyph Clones

### Step 1: Set up Your Document Directory

ドキュメントを保存するディレクトリを設定します:

```csharp
string dataDir = "Your Document Directory";
```

### Step 2: Create the First XPS Document

最初の XPS ドキュメントを作成します:

```csharp
XpsDocument doc1 = new XpsDocument();
```

### Step 3: Add Glyphs to the First Document

指定したパラメータで最初のドキュメントにグリフを追加します:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Step 4: Fill Glyphs with a Solid Color Brush

最初のドキュメントのグリフを **ソリッド カラーブラシ** で塗りつぶします。例として緑色を使用します:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### Step 5: Create the Second XPS Document

次に、2 番目の XPS ドキュメントを作成します:

```csharp
XpsDocument doc2 = new XpsDocument();
```

### Step 6: How to Add Glyph Clone to Another Document

最初のドキュメントからグリフをクローンし、2 番目のドキュメントに追加します:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### Step 7: How to Change Color of the Cloned Glyph

クローンしたグリフの色を変更します。例として赤色に変更し、**グリフの色を変更する方法** を示します:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### Step 8: Save XPS File – First Document

先に定義したフォルダーに最初の XPS ドキュメントを保存します:

```csharp
doc1.Save(dataDir + "out1.xps");
```

### Step 9: Save XPS File – Second Document

2 番目の XPS ドキュメントを保存します:

```csharp
doc2.Save(dataDir + "out2.xps");
```

Congratulations! You have successfully **created XPS document** files, added glyph clones, and changed their colors using Aspose.Page for .NET.

## Why Use Glyph Cloning and Color Changes?

- **Reusability:** 既存のグリフをクローンして、複雑なベクター形状を再定義せずに再利用できます。  
- **Performance:** ゼロからグリフを作成するよりも処理時間が短縮されます。  
- **Design Flexibility:** 同じグリフに対して異なる `SolidColorBrush` インスタンスを適用し、さまざまなビジュアルテーマを実現できます。  
- **Cross‑Document Editing:** 複数の XPS ファイル間でグリフをクローンでき、レポート全体で一貫したブランディングが可能です。

## Common Issues & Troubleshooting

| Issue | Solution |
|-------|----------|
| **Clone returns null** | ソース グリフ（`glyphs`）がクローン前に最初のドキュメントに追加されていることを確認してください。 |
| **Color does not change** | Step 7 のように `glyphs.Fill` を `XpsSolidColorBrush` にキャストしてから `Color` プロパティを設定します。 |
| **File not saved** | `dataDir` が有効で書き込み可能なフォルダーを指しているか、ファイルシステムの権限が適切か確認してください。 |
| **Unexpected glyph size** | `AddGlyphs` の第2引数でフォントサイズを調整し、グリフのスケールを変更します。 |

## Frequently Asked Questions

**Q1: Can I use Aspose.Page for .NET with other document formats?**  
A1: Aspose.Page for .NET は XPS ドキュメント専用に設計されています。他の形式を操作する必要がある場合は、対象形式向けの他の Aspose ライブラリをご検討ください。

**Q2: Is a temporary license available for Aspose.Page for .NET?**  
A2: はい、テスト目的の一時ライセンスを取得できます。詳細は [こちら](https://purchase.aspose.com/temporary-license/) をご覧ください。

**Q3: How can I get support or seek assistance for any issues?**  
A3: [Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) へアクセスし、コミュニティと交流してサポートを受けてください。

**Q4: Are there any limitations to the free trial version?**  
A4: 無料トライアル版にはいくつかの制限があります。使用前にドキュメントで詳細をご確認ください。

**Q5: Where can I find comprehensive documentation for Aspose.Page for .NET?**  
A5: 詳細情報とサンプルはドキュメント [こちら](https://reference.aspose.com/page/net/) を参照してください。

**Q6: How do I change the stroke color of a glyph instead of the fill?**  
A6: `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);` のようにストローク ブラシを設定します。

**Q7: Can I add multiple glyph clones to the same document?**  
A7: はい、`doc2.Add(glyphs.Clone());` を必要な回数だけ呼び出し、位置を調整すれば複数のクローンを追加できます。

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}