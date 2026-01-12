---
date: 2026-01-12
description: Aspose.Page for .NET を使用して PostScript ファイルを保存し、PostScript ドキュメントを作成する方法を学び、動的グラフィックスのために複数の変換を適用します。
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: Aspose.Page Transformations (.NET) を使用して PostScript ファイルを保存する
url: /ja/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page の変換 (.NET) を使用した PostScript ファイルの保存

## はじめに

このチュートリアルでは、Aspose.Page for .NET を使用して **PostScript ファイルを保存** する方法を学びます。PostScript ドキュメントの作成、平行移動、拡大縮小、回転、せん断といった複数の変換を適用し、最終的に結果を保存する手順を順を追って説明します。最後まで読むと、プログラムで動的なグラフィックを作成することに慣れ、各変換をグラフィック状態のどこに配置すべきか正確に理解できるようになります。

## クイック回答
- **何を作成できますか？** 変換されたグラフィックを含むフル機能の PostScript ドキュメント。  
- **必要なライブラリは？** Aspose.Page for .NET（公式サイトからダウンロード可能）。  
- **ファイルはどうやって保存しますか？** グラフィック状態を設定した後、`PsDocument.Save()` を使用します。  
- **複数の変換を適用できますか？** はい。`Transform` または順次呼び出しで組み合わせられます。  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作しますが、製品版には商用ライセンスが必要です。

## “PostScript ファイルを保存” 操作とは？

PostScript ファイルを保存するとは、メモリ上に構築した描画コマンドをディスク上の `.ps` ファイルに永続化することです。このファイルは任意の PostScript インタプリタ、プリンター、またはビューアでレンダリングできます。

## なぜ .NET 用 Aspose.Page を使用して PostScript ドキュメントを作成するのか？

Aspose.Page は、低レベルの PostScript 構文を抽象化した高レベルでデバイスに依存しない API を提供します。得られるメリットは次のとおりです。

- パス、ブラシ、変換用の強く型付けされた C# オブジェクト。  
- グラフィック状態スタック（save/restore）の自動管理。  
- 手動計算なしで複雑な変換行列を完全にサポート。  

## 前提条件

開始する前に、以下が揃っていることを確認してください。

- **Aspose.Page for .NET** ライブラリをプロジェクトに統合します。 [download link](https://releases.aspose.com/page/net/) から取得してください。  
- 生成された `.ps` ファイルを保存できる書き込み可能なフォルダー。コード内のプレースホルダー パスを実際のディレクトリに置き換えてください。

## 名前空間のインポート

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

それでは、各変換をステップバイステップで見ていきましょう。

## 変換なし

### 手順 1: 出力ストリームの作成

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

このスニペットは、オレンジの矩形が 1 つだけの **PostScript ドキュメント** を作成し、**PostScript ファイルを保存** します。変換は適用されません。

## 平行移動

### 手順 1: グラフィック状態の保存

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

グラフィック状態を保存すると、オブジェクトを移動した後に元に戻すことができます。

### 手順 2: グラフィック状態の平行移動

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

この呼び出しの後に描画されるすべてのものが、右方向に 250 ユニット移動します。

### 手順 3: 平行移動変換で矩形を塗りつぶす

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

これで、オレンジの矩形の右側 250 ポイントに青い矩形が表示されます。

### 手順 4: グラフィック状態の復元

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

復元すると座標系が元の位置に戻り、以降の描画は平行移動の影響を受けません。

## 拡大縮小

> *同じパターン（状態の保存、`Scale` の適用、描画、復元）を使用できます。*  
> **プロのコツ:** 非均一スケーリング (`Scale(sx, sy)`) を使用すると、オブジェクトを一方向にだけ伸ばすことができます。

## 回転

> *`Rotate(angle)` を使用して、原点またはカスタムのピボット点を中心に回転させます。*  
> **プロのコツ:** 回転前に `Translate` を組み合わせると、特定の点を中心に回転できます。

## せん断

> *せん断変換 (`Shear(shx, shy)`) は形状を傾け、イタリック効果などに有用です。*

## 複合変換

> *高度なシナリオでは、カスタム `Matrix` を作成し、`Transform(matrix)` に渡します。*  
> ここで、**複数の変換を一度に適用** します。

## 結論

Aspose.Page for .NET を使用して **PostScript ファイルの保存**、**PostScript ドキュメントの作成**、そして **複数の変換の適用** 方法を学びました。さまざまな変換順序を試し、組み合わせて、グラフィックがどのように変化するかをご確認ください。

## よくある質問

**Q: 単一オブジェクトに複数の変換を適用するにはどうすればよいですか？**  
A: 必要な順序で平行移動、拡大縮小、回転、せん断を組み合わせたカスタム `Matrix` を使用し、`Transform` メソッドを呼び出します。

**Q: ドキュメントを保存する前に変換をプレビューできますか？**  
A: はい。`PsDocument` を画像にレンダリングするか、PostScript ビューアを使用して `Save()` を呼び出す前に出力を確認できます。

**Q: ドキュメント内の特定の要素に変換を適用できますか？**  
A: もちろんです。要素を描画する前にグラフィック状態を保存し、目的の変換を適用して描画し、最後に状態を復元します。

**Q: 複雑な変換を扱う際のパフォーマンス上の考慮点はありますか？**  
A: 複雑な行列は CPU の負荷を増大させます。変換はできるだけシンプルに保ち、同様のオブジェクトを多数描画する際は保存した状態を再利用してください。

**Q: Aspose.Page に関する質問やサポートはどこで受けられますか？**  
A: コミュニティの支援は [Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) で、直接のサポートは Aspose にお問い合わせください。

---

**最終更新日:** 2026-01-12  
**テスト環境:** Aspose.Page 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}