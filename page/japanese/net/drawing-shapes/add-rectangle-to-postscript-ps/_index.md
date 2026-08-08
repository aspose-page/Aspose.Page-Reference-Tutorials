---
date: 2026-06-30
description: Aspose.Page for .NET を使用して、PostScript ドキュメントを .NET で作成し、四角形を追加する方法を学びます。コードサンプル付きのステップバイステップガイド。
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: PostScript (PS) に四角形を追加
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: PostScript ドキュメントを .NET で作成 – 四角形を追加 Aspose.Page
url: /ja/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用して PostScript (PS) に矩形を追加する

## はじめに

Aspose.Page for .NET は、プログラムから PostScript、EPS、XPS ファイルの作成と操作を可能にするライブラリです。**create postscript document .net** を探している場合、このチュートリアルでは Aspose.Page を使用して PostScript ドキュメントに矩形を追加する方法を解説し、よりリッチなグラフィック生成のための確固たる基礎を提供します。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Page for .NET.  
- **最初から PostScript ドキュメントを作成できますか？** はい – API を使用してプログラムから PS ファイルを作成できます。  
- **サポートされている .NET バージョンはどれですか？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **開発にライセンスは必要ですか？** 無料トライアルはテストに使用できますが、製品版ではライセンスが必要です。  
- **実装にどれくらい時間がかかりますか？** 基本的な図形であれば、通常 10 minutes 未満で完了します。

## .NET で PostScript ドキュメントを作成するとは何ですか？

.NET で PostScript ドキュメントを作成することは、Aspose.Page API を使用してページ内容（テキスト、グラフィック、形状）を記述した `.ps` ファイルをプログラムから生成することを意味します。このアプローチは、サーバー側のグラフィック生成、レポートの自動作成、または出力形式を正確に制御する必要があるあらゆるシナリオに最適です。

## なぜ Aspose.Page for .NET を使用するのか？

Aspose.Page は **30+ graphics primitives** をサポートし、ドキュメント全体をメモリに読み込むことなく最大 **500 MB** のファイルを生成でき、Windows、Linux、macOS 上で高性能なレンダリングを実現します。低レベルの PostScript コードを書く必要がなく、形状、色、ストロークを完全に制御できます。

- **グラフィックの完全な制御** – 低レベルの PS 構文を扱わずに形状を描画し、色を設定し、ストロークを適用できます。  
- **クロスプラットフォーム** – Windows、Linux、macOS ランタイムで動作します。  
- **外部依存なし** – ライブラリが内部で PS 生成をすべて処理します。  
- **豊富なドキュメントとサンプル** – すぐに始められます。

## 前提条件

- **Aspose.Page for .NET ライブラリ** – [here](https://releases.aspose.com/page/net/) からダウンロードしてインストールしてください。  
- **開発環境** – Visual Studio、VS Code、または任意の .NET 対応 IDE。

## 名前空間のインポート

`Aspose.Page` 名前空間は、`Document`、`Page`、`SolidBrush`、`Pen` など、必要なコアクラスを提供します。コーディングを始める前にインポートしてください。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

それでは、例を明確な番号付きステップに分解しましょう。

## 手順 1: ドキュメント ディレクトリの設定

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

`"Your Document Directory"` を、生成された PS ファイルを保存したいフォルダーに置き換えてください。

## 手順 2: PostScript ドキュメント用の出力ストリームを作成

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

このストリームは **AddRectangle_outPS.ps** を指します。必要に応じてファイル名を変更したり、場所を変更したりしてください。

## 手順 3: 保存オプションを設定し、PS ドキュメントを作成

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

ここでは Aspose.Page に A4 用紙サイズを使用し、単一ページのドキュメントを作成するよう指示しています。

## 手順 4: 塗りつぶし矩形の追加

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

(250, 100) の位置に幅 150、高さ 100 の矩形を定義し、オレンジのブラシを設定して形状を塗りつぶします。

## 手順 5: 輪郭のみの矩形の追加

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

ページ下部に 2 番目の矩形を作成し、今回は赤色の 3 ポイントのストロークを使用します。

## 手順 6: ページを閉じてドキュメントを保存

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

ページを閉じることで描画が確定し、`Save()` が PS ファイルをディスクに書き込みます。

## .NET で PostScript ドキュメントを作成する方法は？

`Document` は Aspose.Page で PostScript ファイルを表す主要クラスです。`SaveOptions` はページサイズや出力形式などの設定を指定します。`Document` オブジェクトをロードし、A4 ページ用に `SaveOptions` を構成し、`SolidBrush` または `Pen` で形状を描画し、最後に `document.Save()` を呼び出します—このワークフローは数行のコードで完結し、サポートされている任意の .NET ランタイムで実行できます。このパターンにより、生の PS 構文に触れることなく完全に準拠した PostScript ファイルを生成できます。

## PostScript ファイルを生成する方法

Aspose.Page の `SaveOptions` クラスを使用して出力形式を PostScript（`SaveFormat.PS`）に指定します。ライブラリはコンテンツを直接ファイルまたはメモリストリームにストリームし、大きなドキュメントを効率的に生成でき、過剰なメモリ消費を抑えます。

## よくある問題とヒント

- **ファイルパスが正しくない** – `dataDir` がパス区切り文字（`\\` または `/`）で終わっていることを確認するか、`Path.Combine` を使用してください。  
- **ライセンスがない** – 本番環境では、ドキュメント作成前に Aspose ライセンスを適用し、評価版の透かしを回避してください。  
- **色の可視性** – 矩形が空白に見える場合、ブラシやペンの色がページ背景と対照的か確認してください。

## よくある質問

**Q:** 矩形の色をカスタマイズできますか？  
**A:** もちろんです。`SolidBrush` と `Pen` のコンストラクタで `Color.Orange` や `Color.Red` の値を、任意の `System.Drawing.Color` に変更してください。

**Q:** Aspose.Page は他のドキュメント形式と互換性がありますか？  
**A:** はい。PostScript に加えて、Aspose.Page は XPS と EPS の生成もサポートしています。

**Q:** 同じドキュメントにテキストを追加するには？  
**A:** `TextFragment` クラスを使用して目的の座標にテキストを配置し、`document.Draw(textFragment)` を呼び出します。

**Q:** 追加のサンプルや完全な API リファレンスはどこで見つけられますか？  
**A:** ドキュメントは [here](https://reference.aspose.com/page/net/) で確認でき、コミュニティは [Aspose.Page forum](https://forum.aspose.com/c/page/39) に参加してください。

**Q:** 購入前に Aspose.Page を試用できますか？  
**A:** はい、無料トライアルは [here](https://releases.aspose.com/) からダウンロードできます。長期評価が必要な場合は、[temporary license](https://purchase.aspose.com/temporary-license/) を検討してください。

---

**最終更新日:** 2026-06-30  
**テスト環境:** Aspose.Page 24.12 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.Page for .NET を使用して PostScript ドキュメントを作成する方法](/page/net/document-creation/create-postscript-document/)
- [Aspose.Page を使用して PostScript (PS) ドキュメントに画像を追加する方法](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Aspose.Page を使用して PostScript (PS) ドキュメントにテキストを追加する方法](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}