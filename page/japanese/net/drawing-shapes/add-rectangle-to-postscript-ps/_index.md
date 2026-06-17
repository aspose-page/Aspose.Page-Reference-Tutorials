---
date: 2026-01-18
description: Aspose.Page for .NET を使用して PostScript ドキュメントを作成し、矩形を追加する方法を学びましょう。コードサンプル付きのステップバイステップガイドです。
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: .NETでPostScriptドキュメントを作成 – Aspose.Pageで矩形を追加
url: /ja/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用して PostScript (PS) に矩形を追加する

## はじめに

**postscript document .net** を作成したい場合、Aspose.Page は PostScript ファイルを扱うための強力なソリューションを提供します。このチュートリアルでは、Aspose.Page for .NET を使って PostScript ドキュメントに矩形を追加する手順を解説し、よりリッチなグラフィック生成の基礎を身につけられるようにします。

## クイック回答
- **必要なライブラリは？** Aspose.Page for .NET。
- **ゼロから PostScript ドキュメントを作成できますか？** はい – API を使ってプログラムから PS ファイルを構築できます。
- **対応している .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。
- **開発用にライセンスは必要ですか？** 無料トライアルでテスト可能です。製品版ではライセンスが必要です。
- **実装にどれくらい時間がかかりますか？** 基本的な図形であれば通常 10 分未満です。

## postscript document .net とは何か？
.NET で PostScript ドキュメントを作成することは、Aspose.Page API を利用してページ内容（テキスト、グラフィック、図形）を記述した .ps ファイルをプログラムから生成することを意味します。この手法はサーバーサイドのグラフィック生成や自動レポート作成、出力フォーマットを正確に制御したいシナリオに最適です。

## Aspose.Page for .NET を使う理由
- **グラフィックをフルコントロール** – 低レベルの PS 構文を意識せずに図形を描画し、色やストロークを設定できます。
- **クロスプラットフォーム** – Windows、Linux、macOS のランタイムで動作します。
- **外部依存なし** – ライブラリ単体で PS の生成を完結します。
- **充実したドキュメントとサンプル** – すぐに使い始められるリソースが豊富です。

## 前提条件

- **Aspose.Page for .NET ライブラリ** – [here](https://releases.aspose.com/page/net/) からダウンロードしてインストールしてください。
- **開発環境** – Visual Studio、VS Code、または任意の .NET 対応 IDE。

## 名前空間のインポート

コーディングを始める前に、必要なクラスを公開する名前空間をインポートします。

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

それでは、例を明確なステップに分けて解説します。

## 手順 1: ドキュメントディレクトリの設定

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

`"Your Document Directory"` を、生成した PS ファイルを保存したいフォルダーに置き換えてください。

## 手順 2: PostScript ドキュメント用の出力ストリームを作成

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

このストリームは **AddRectangle_outPS.ps** を指します。必要に応じてファイル名や保存場所を変更してください。

## 手順 3: 保存オプションを設定し PS ドキュメントを作成

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

ここでは Aspose.Page に A4 用紙サイズを使用し、1 ページのドキュメントを作成するよう指示しています。

## 手順 4: 塗りつぶし矩形を追加

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

座標 (250, 100) に幅 150、高さ 100 の矩形を定義し、オレンジのブラシで塗りつぶします。

## 手順 5: 線枠のみの矩形を追加

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

ページ下部に 2 番目の矩形を作成し、今回は赤色の 3 ポイントストロークを適用します。

## 手順 6: ページを閉じてドキュメントを保存

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

ページを閉じることで描画が確定し、`Save()` が PS ファイルをディスクに書き出します。

## よくある問題とヒント

- **ファイルパスが正しくない** – `dataDir` の末尾にパス区切り文字（`\\` または `/`）が付いているか確認するか、`Path.Combine` を使用してください。
- **ライセンスが未設定** – 本番環境では評価版の透かしを防ぐため、ドキュメント作成前に Aspose のライセンスを適用してください。
- **色が見えない** – 矩形が空白に見える場合、ブラシやペンの色がページ背景とコントラストが取れているか確認してください。

## FAQ

**Q:** 矩形の色はカスタマイズできますか？  
**A:** もちろんです。`SolidBrush` と `Pen` のコンストラクタで使用している `Color.Orange` や `Color.Red` を、任意の `System.Drawing.Color` に変更してください。

**Q:** Aspose.Page は他のドキュメント形式にも対応していますか？  
**A:** はい。PostScript に加えて、XPS や EPS の生成もサポートしています。

**Q:** 同じドキュメントにテキストを追加するには？  
**A:** `TextFragment` クラスを使用して任意の座標にテキストを配置し、`document.Draw(textFragment)` を呼び出します。

**Q:** 追加のサンプルや完全な API リファレンスはどこで確認できますか？  
**A:** ドキュメントは [here](https://reference.aspose.com/page/net/) で確認でき、コミュニティは [Aspose.Page forum](https://forum.aspose.com/c/page/39) で参加できます。

**Q:** 購入前に Aspose.Page を試すことはできますか？  
**A:** はい、無料トライアルを [here](https://releases.aspose.com/) からダウンロードできます。長期評価が必要な場合は、[temporary license](https://purchase.aspose.com/temporary-license/) の取得をご検討ください。

---

**最終更新日:** 2026-01-18  
**テスト環境:** Aspose.Page 24.12 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}