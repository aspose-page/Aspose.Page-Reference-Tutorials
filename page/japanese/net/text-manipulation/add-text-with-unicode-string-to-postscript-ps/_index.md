---
date: 2026-03-21
description: Aspose.Page for .NET を使用して、Unicode テキストを含む C# の PostScript ドキュメントの作成方法を学びましょう
  – ドキュメント操作を強化する高速な方法です。
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: UnicodeテキストでC#のPostScriptドキュメントを作成 – Aspose.Page
url: /ja/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用して PostScript (PS) に Unicode 文字列を追加する

## はじめに

C# で **PostScript ドキュメントを作成** し、Unicode 文字を埋め込む必要がある場合、Aspose.Page for .NET を使用すれば手順がシンプルです。このチュートリアルでは、実践的な完全例を通じて、PS ファイルに日本語テキスト（または任意の Unicode 文字列）を追加し、カスタムフォントを選択して保存する方法を示します。最後まで実行すれば、任意の C# プロジェクトに組み込める再利用可能なコードスニペットが手に入ります。

## クイック回答
- **このチュートリアルの内容は？** Aspose.Page を使用して C# で PostScript ファイルに Unicode テキストを追加する方法です。
- **必要なライブラリは？** Aspose.Page for .NET（最新バージョン）。
- **特別なフォントは必要ですか？** 必要な Unicode 範囲をサポートする任意の TrueType/OpenType フォント（例: *Arial Unicode MS*）です。
- **コード行数は？** 約 30 行で、明確なステップに分かれています。
- **ライセンスは必要ですか？** 評価用には一時ライセンスで動作しますが、本番環境では正式ライセンスが必要です。

## “create postscript document c#” とは？

C# で PostScript ドキュメントを作成するとは、PostScript 言語仕様に従った .ps ファイルをプログラムで生成することを指します。Aspose.Page は低レベルの詳細を抽象化し、テキスト、グラフィック、フォントなどのコンテンツに集中できるようにします。

## Unicode テキストに Aspose.Page を使用する理由

- **フル Unicode サポート** – 手動でエンコードすることなく、あらゆる言語の文字をレンダリングできます。
- **デバイス非依存** – 同じコードで PS、EPS、PDF の出力が可能です。
- **外部依存なし** – ライブラリがフォントのロードとグリフマッピングを内部で処理します。

## 前提条件

- C# と .NET 開発の基本的な知識があること。
- Aspose.Page for .NET ライブラリがインストールされていること。ダウンロードは [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) から可能です。
- 使用するフォントが格納されたフォルダー（例: *Arial Unicode MS*）があること。

## 名前空間のインポート

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ステップ 1: ドキュメントディレクトリとフォントフォルダーの設定

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## ステップ 2: PostScript ドキュメント用の出力ストリーム作成

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## ステップ 3: カスタムフォントで Unicode テキストを追加

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## ステップ 4: 現在のページを閉じる

```csharp
document.ClosePage();
```

## ステップ 5: ドキュメントを完了し保存

```csharp
document.Save();
```

## よくある問題と解決策

- **フォントが見つからない** – `AdditionalFontsFolders` パスが .ttf/.otf ファイルが入っているフォルダーを指していること、フォント名が正確に一致していることを確認してください。
- **文字化け** – ソース文字列が C# ソースファイルで UTF‑8 としてエンコードされているか確認してください（必要に応じて `#pragma warning disable 1591` を使用）。
- **ファイルが作成されない** – `dataDir` の書き込み権限と、ストリームが正しく破棄されているか（`using` ブロックが処理）を確認してください。

## よくある質問

**Q: Aspose.Page for .NET を他のプログラミング言語で使用できますか？**  
A: Aspose.Page は主に .NET 用に設計されていますが、Java 用の同等製品も提供されています。

**Q: Aspose.Page for .NET の一時ライセンスはどう取得しますか？**  
A: 一時ライセンスの取得は [Temporary License](https://purchase.aspose.com/temporary-license/) をご覧ください。

**Q: Aspose.Page のコミュニティフォーラムはありますか？**  
A: はい、コミュニティサポートは [Aspose.Page forum](https://forum.aspose.com/c/page/39) でご利用いただけます。

**Q: Aspose.Page for .NET が対応しているフォーマットは何ですか？**  
A: Aspose.Page は XPS、PS、EPS、PDF など、さまざまなフォーマットに対応しています。

**Q: 追加したテキストの外観をカスタマイズできますか？**  
A: はい、Aspose.Page ではフォント、サイズ、色、その他のプロパティをカスタマイズできます。

## 結論

このチュートリアルでは、**C# で PostScript ドキュメントを作成**し、Aspose.Page を使用して Unicode テキストを埋め込む方法を示しました。上記の手順に従うことで、任意の .NET アプリケーションに多言語テキストレンダリングを迅速に統合でき、ドキュメント生成とレイアウトを完全に制御できます。

---

**最終更新日:** 2026-03-21  
**テスト環境:** Aspose.Page 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}