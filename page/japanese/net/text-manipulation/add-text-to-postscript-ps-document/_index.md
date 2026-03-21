---
date: 2026-03-21
description: Aspose.Page for .NET を使用して、PS ドキュメントにテキストを入力および追加する方法を学びましょう。コード例付きのステップバイステップガイド。
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Aspose.Page を使用して PostScript（PS）ドキュメントにテキストを埋め込む方法
url: /ja/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用した PostScript (PS) ドキュメントへのテキスト塗りつぶし方法

## はじめに

PostScript (PS) ファイル内で **テキストを塗りつぶす方法** が必要な場合、Aspose.Page for .NET を使用すれば簡単に実現できます。レポート、請求書、カスタムグラフィックの生成に関わらず、テキストの追加とスタイリングは重要な要件です。このチュートリアルでは、環境設定から最終的な PS ドキュメントの保存までの全工程を順を追って解説しますので、.NET アプリケーションで自信を持って PS ファイルにテキストを追加できるようになります。

## クイック回答
- **“fill text”とは何ですか？** 文字を実線のブラシで描画し、グリフをページに直接塗りつぶします。  
- **カスタムフォントは使用できますか？** はい—Aspose.Page は `add custom font ps` 機能でカスタムフォントをサポートします。  
- **PS ドキュメントはどうやって保存しますか？** ページを閉じた後に `document.Save()` を呼び出します。これによりファイルがディスクに書き込まれます（`save ps document`）。  
- **“fill and stroke text”はサポートされていますか？** もちろんです。`FillAndStrokeText` を使用して塗りつぶしとアウトラインの両方を適用します。  
- **必要な .NET バージョンは何ですか？** .NET Framework 4.5 以降、または .NET Core/5/6 以降のランタイムが使用できます。

## PS ドキュメントにおける “how to fill text” とは何か？

テキストを塗りつぶすとは、文字をアウトラインなしで実線の色（またはブラシ）で描画することです。PostScript では `fill` 演算子に相当します。Aspose.Page はこれを `FillText` や `FillAndStrokeText` のような使いやすいメソッドで抽象化しています。

## カスタムフォント ps を追加するために Aspose.Page を使用する理由

- **完全なフォントサポート** – システムフォントと外部の TrueType/OpenType フォントがそのまま使用できます。  
- **正確な位置指定** – X/Y 座標、サイズ、スタイルを制御できます。  
- **豊富なスタイリング** – 塗りつぶし、ストローク、ペンを組み合わせて “fill and stroke text” のような効果を実現できます。  
- **クロスプラットフォーム** – 同じ API で Windows、Linux、macOS 上で動作します。

## 前提条件

- **Aspose.Page for .NET** – ライブラリは [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/) からダウンロードしてください。  
- **Document Directory** – ソースと出力の PS ファイルが保存されるローカルフォルダー（コード中では *Your Document Directory* と呼ばれます）。  
- **Fonts Folder** – 使用するカスタムフォントを格納するサブフォルダーです。

## 名前空間のインポート

まず、必要な名前空間をインポートして、コンパイラが使用するクラスの場所を認識できるようにします。

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ステップバイステップ ガイド

### ステップ 1: PS ドキュメント用の出力ストリームを作成  

`FileStream` を開き、生成された PS ファイルを保持し、`PsSaveOptions` をカスタムフォントフォルダーに設定し、`PsDocument` をインスタンス化します。

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **プロのコツ:** `using` ブロックを保持して、ストリームが自動的に閉じられ、PS ファイルが確実に完了するようにします（`save ps document`）。

### ステップ 2: システムフォントでテキストを塗りつぶす  

ここでは、組み込みの *Times New Roman* フォントを使用した基本的な **テキストを塗りつぶす** 操作を示します。

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### ステップ 3: カスタムフォントでテキストを塗りつぶす  

特定の外観が必要な場合は、`ExternalFontCache.FetchDrFont` を使用してフォントフォルダーからカスタムフォントをロードします。これにより **add custom font ps** の要件が満たされます。

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### ステップ 4: システムフォントでテキストにアウトライン（ストローク）を付ける  

アウトラインはグリフの輪郭を描画します。塗りつぶしと組み合わせて “fill and stroke” 効果を得られます。

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **重要なポイント:** `FillAndStrokeText` の呼び出しは、**fill and stroke text** を一度の操作で行う方法を示し、よりリッチなタイポグラフィ制御が可能になります。

### ステップ 5: カスタムフォントでテキストにアウトラインを付ける  

同じアウトライン手法は、ロードした任意のカスタムフォントでも機能します。

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### ステップ 6: ページを閉じてドキュメントを保存  

最後の手順は簡単です。現在のページを閉じ、`Save()` を呼び出して PS ファイルをディスクに書き込みます。

```csharp
document.ClosePage();
document.Save();
}
```

> **結果:** *Your Document Directory* に `AddText_outPS.ps` が作成され、システムフォントとカスタムフォントで描画された塗りつぶしテキストとストロークテキストの両方が含まれます。

## 一般的な問題と解決策

| 問題 | 解決策 |
|-------|----------|
| **カスタムフォントが見つかりません** | `AdditionalFontsFolders` で参照されているフォルダーにフォントファイル（.ttf/.otf）が存在することを確認してください。 |
| **テキストが誤った位置に表示される** | `FillText`/`OutlineText` に渡す X/Y 座標を調整してください。PostScript はポイント（1/72 インチ）を使用することを忘れないでください。 |
| **色が異なって見える** | 正しい `Color` 値を持つ `SolidBrush` または `Pen` を使用していることを確認してください。 |
| **ドキュメントが保存されない** | `using` ブロックが例外なく完了し、アプリケーションが対象フォルダーへの書き込み権限を持っていることを確認してください。 |

## よくある質問

**Q: Aspose.Page を他の .NET ライブラリと併用できますか？**  
A: はい、Aspose.Page は他の .NET コンポーネントとスムーズに統合でき、同じソリューションで PDF、画像、またはチャートライブラリを組み合わせて使用できます。

**Q: このプロセスにカスタムフォントは必須ですか？**  
A: システムフォントでも問題ありませんが、カスタムフォントを使用するとデザインの自由度が高まり、ブランド固有のタイポグラフィが必要な場合に便利です。

**Q: 大規模なドキュメント処理に Aspose.Page は適していますか？**  
A: はい。ライブラリは高スループットシナリオ向けに最適化されており、数千の PS ファイルを効率的に処理できます。

**Q: PS ドキュメント内のテキスト位置を変更できますか？**  
A: もちろんです。`FillText` または `OutlineText` の呼び出しで数値の X/Y 値を変更するだけです。

**Q: Aspose.Page に関する質問はどこでサポートを受けられますか？**  
A: [Aspose.Page Forum](https://forum.aspose.com/c/page/39) を訪れてコミュニティとつながり、専門家の支援を受けてください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2026-03-21  
**テスト環境:** Aspose.Page 24.11 for .NET  
**作者:** Aspose