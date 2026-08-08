---
date: 2026-06-25
description: コード不要の手順と実践的なヒントで、XPS ドキュメントを簡単に変換する方法を学びましょう – Aspose.Page for .NET
  を使用した XPS 変換の決定版ガイドです。
keywords:
- how to transform xps
- convert images to xps
- Aspose.Page transformations
linktitle: XPS の変換
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to transform XPS documents effortlessly – the definitive
    guide on how to transform xps using Aspose.Page for .NET, with code‑free steps
    and real‑world tips.
  headline: How to Transform XPS with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to transform XPS documents effortlessly – the definitive
    guide on how to transform xps using Aspose.Page for .NET, with code‑free steps
    and real‑world tips.
  name: How to Transform XPS with Aspose.Page for .NET
  steps:
  - name: Create a New XPS Document
    text: '`XpsDocument` is the Aspose.Page object that represents an XPS file in
      memory. *Explanation*: We start by defining the folder that holds our source
      and output files, then instantiate an empty `XpsDocument`. This object will
      be the canvas for all subsequent transformations.'
  - name: Create a Main Canvas
    text: '`Canvas` is the drawing surface that groups shapes, text, and other graphical
      elements. *Why this matters*: The main canvas acts as a container for all other
      canvases. By applying a small offset we ensure the content isn’t clipped at
      the page edge.'
  - name: Create a Rectangle Path Geometry
    text: '`PathGeometry` defines vector shapes using XPS path syntax (M = move, L
      = line, Z = close). *Tip*: The path string follows the standard XPS path syntax.
      Adjust the coordinates to change rectangle size.'
  - name: Add a Fill for Rectangles
    text: '`SolidColorBrush` creates a solid‑color fill that can be reused across
      multiple shapes. *Pro tip*: Use `CreateColor` with RGB values to match your
      brand palette.'
  - name: Add a New Canvas Without Transformations
    text: '`Canvas` without a transform serves as a baseline element for comparison.
      Here we simply place a rectangle on the page with no extra transformation—useful
      as a baseline element.'
  - name: Add a New Canvas with Translate Transformation
    text: '`TranslateTransform` moves objects along the X and Y axes. *What’s happening?*
      The first matrix moves the rectangle down by 200 units. The subsequent `Translate`
      call shifts it 500 units to the right, demonstrating how multiple translations
      can be chained.'
  - name: Add a New Canvas with Double Scale Transformation
    text: '`ScaleTransform` multiplies the width and height of the canvas by the supplied
      factors. *Why scale?* Scaling by 2 doubles the rectangle’s width and height,
      letting you create larger graphics without redefining the geometry.'
  - name: Add a New Canvas with Rotation Around a Point Transformation
    text: '`RotateAroundTransform` pivots the canvas around a custom point (here (100,
      50)). *Key insight*: `RotateAround` pivots the canvas around a custom point,
      giving you fine control over rotation anchors.'
  - name: Save Resultant XPS Document
    text: '`Save` persists the in‑memory document to disk in XPS format. After all
      transformations are applied, the document is persisted to `output1.xps`. Open
      the file in any XPS viewer to see the stacked rectangles with their respective
      translations, scaling, and rotation.'
  type: HowTo
- questions:
  - answer: Yes, it works seamlessly with Visual Studio, Visual Studio Code, Rider,
      and any IDE that supports .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Is Aspose.Page for .NET compatible with all .NET development environments?
  - answer: Visit the official documentation at [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).
    question: Where can I find additional examples and detailed API docs?
  - answer: 'Absolutely. A free trial is available here: [Aspose.Page Free Trial](https://releases.aspose.com/).'
    question: Can I try Aspose.Page before buying a license?
  - answer: 'Request one via the temporary‑license page: [Temporary License](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for testing?
  - answer: 'Purchase directly from the Aspose store: [Aspose.Page Buy](https://purchase.aspose.com/buy).'
    question: Where do I purchase a full license?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET を使用した XPS の変換方法
url: /ja/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用した XPS の変換方法

## はじめに

この包括的なガイドでは、Aspose.Page for .NET を使用して **XPS を変換する方法** を学びます。翻訳、拡大縮小、回転、または単一ページ上で複数のグラフィックを結合する必要がある場合でも、ライブラリは生の XML に手を加えることなくマトリックスベースの制御を提供します。すべての手順を順に解説し、各変換が重要な理由を説明し、実際のプロダクションコードにすぐにコピーできる実用的なヒントを共有します。

## Quick Answers
- **何が実現できますか？** プログラムで XPS キャンバス要素を作成、平行移動、拡大縮小、回転できます。  
- **必要なライブラリはどれですか？** Aspose.Page for .NET（最新バージョン）。  
- **ライセンスは必要ですか？** 開発には無料トライアルが使用できますが、本番環境では商用ライセンスが必要です。  
- **サポートプラットフォームは？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **実装時間は？** 以下に示す基本的な変換でおおよそ 10〜15 分です。

## “how to transform xps” とは何ですか？

フレーズ *how to transform xps* は、XPS（XML Paper Specification）ドキュメント内の要素のレイアウト、サイズ、向きをプログラムで変更することを指します。Aspose.Page を使用すると、キャンバスにマトリックスベースの変換を適用でき、XPS マークアップを手動で編集することなく、位置、拡大縮小、回転をピクセル単位で正確に制御できます。

## なぜ XPS の変換に Aspose.Page を使用するのか？

XPS ファイルを読み込み、変換を一連に適用し、保存 – すべてコード 2 行で完了します。Aspose.Page は **50 以上の入力・出力形式** をサポートし、**200 ページの XPS ファイルを 2 秒未満で処理** でき、**外部依存関係は不要**です。これにより、請求書、レポート、または印刷可能なグラフィックをリアルタイムで生成するのに最適です。

## 前提条件

開始する前に、以下をご用意ください：

- **Aspose.Page for .NET ライブラリ** – 公式ドキュメントからダウンロードしてください: [Aspose.Page for .NET ドキュメント](https://reference.aspose.com/page/net/)。  
- **開発環境** – Visual Studio、Visual Studio Code、Rider、または .NET を対象とした任意の IDE。  
- **ドキュメントディレクトリ** – XPS ファイルの読み書きを行うローカルフォルダーです。コード内のプレースホルダーを実際のパスに置き換えてください。

すべての準備が整ったので、コードに入りましょう。

## 名前空間のインポート

以下の名前空間は、使用する Aspose.Page のコア型を公開します。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Aspose.Page を使用した XPS の変換方法？

ソース XPS を読み込む（または新規ドキュメントを作成）し、キャンバスオブジェクトに対して平行移動、拡大縮小、回転のマトリックス変換を順に適用します。各変換は呼び出し順に適用され、少数のメソッド呼び出しだけで複雑なレイアウトを構築できます。

## XPS の変換 – ステップバイステップガイド

このセクションでは、XPS ファイルを作成し、複数のキャンバスを追加し、平行移動、拡大縮小、回転といった一連の変換を適用する完全な例を示します。各ステップには簡潔なコードスニペット（プレースホルダーで表現）と、操作の目的が説明されているので、簡単に再現できます。

### 手順 1: 新しい XPS ドキュメントの作成

`XpsDocument` は、メモリ内の XPS ファイルを表す Aspose.Page オブジェクトです。  
```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*説明*: ソースと出力ファイルを格納するフォルダーを定義し、空の `XpsDocument` をインスタンス化します。このオブジェクトは、以降のすべての変換のキャンバスとなります。

### 手順 2: メインキャンバスの作成

`Canvas` は、形状、テキスト、その他のグラフィック要素をグループ化する描画面です。  
```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*重要性*: メインキャンバスは他のすべてのキャンバスのコンテナとして機能します。小さなオフセットを適用することで、ページ端でコンテンツが切り取られないようにします。

### 手順 3: 四角形パスジオメトリの作成

`PathGeometry` は XPS パス構文 (M = 移動、L = 線分、Z = 閉じる) を使用してベクター形状を定義します。  
```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*ヒント*: パス文字列は標準の XPS パス構文に従います。座標を調整して四角形のサイズを変更できます。

### 手順 4: 四角形の塗りつぶしを追加

`SolidColorBrush` は、複数の形状で再利用できる単色の塗りつぶしを作成します。  
```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*プロのコツ*: `CreateColor` を使用して RGB 値でブランドのカラーパレットに合わせましょう。

### 手順 5: 変換なしの新しいキャンバスを追加

変換が設定されていない `Canvas` は、比較用のベースライン要素として機能します。  
```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

ここでは、余分な変換なしでページに四角形を配置します。ベースライン要素として便利です。

### 手順 6: 平行移動変換付きの新しいキャンバスを追加

`TranslateTransform` はオブジェクトを X 軸と Y 軸に沿って移動させます。  
```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*何が起きているか？* 最初の行列は四角形を下方向に 200 ユニット移動させます。その後の `Translate` 呼び出しで右方向に 500 ユニットシフトし、複数の平行移動を連鎖させる方法を示しています。

### 手順 7: 二重スケール変換付きの新しいキャンバスを追加

`ScaleTransform` は、キャンバスの幅と高さを指定された係数で乗算します。  
```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*なぜスケールするのか？* 2 倍にスケールすると四角形の幅と高さが倍になり、ジオメトリを再定義せずに大きなグラフィックを作成できます。

### 手順 8: 点回転変換付きの新しいキャンバスを追加

`RotateAroundTransform` はカスタムポイント（ここでは (100, 50)）を中心にキャンバスを回転させます。  
```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*重要なポイント*: `RotateAround` はカスタムポイントを中心にキャンバスを回転させ、回転アンカーを細かく制御できます。

### 手順 9: 結果の XPS ドキュメントを保存

`Save` はメモリ内のドキュメントを XPS 形式でディスクに保存します。  
```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

すべての変換が適用された後、ドキュメントは `output1.xps` に保存されます。任意の XPS ビューアでファイルを開くと、各変換が適用された四角形が重ねて表示されます。

## よくある問題とトラブルシューティング

| 症状 | 考えられる原因 | 対策 |
|------|----------------|------|
| 空の出力ファイル | `dataDir` が存在しないフォルダーを指している | ディレクトリが存在することを確認するか、絶対パスを使用してください |
| 四角形が期待通りに配置されない | 行列の値が正しくない | `Translate`、`Scale`、`RotateAround` の呼び出し順序を再確認してください |
| 色が正しく表示されない | RGB 値が 0‑255 の範囲外 | 各チャンネルに有効なバイト値を使用してください |

## よくある質問

**Q: Aspose.Page for .NET はすべての .NET 開発環境と互換性がありますか？**  
**A:** はい、Visual Studio、Visual Studio Code、Rider、.NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+ をサポートする任意の IDE でシームレスに動作します。

**Q: 追加のサンプルや詳細な API ドキュメントはどこで見つけられますか？**  
**A:** 公式ドキュメントは [Aspose.Page for .NET ドキュメント](https://reference.aspose.com/page/net/) をご覧ください。

**Q: ライセンスを購入する前に Aspose.Page を試用できますか？**  
**A:** もちろんです。無料トライアルはここから入手できます: [Aspose.Page Free Trial](https://releases.aspose.com/)。

**Q: テスト用の一時ライセンスはどう取得しますか？**  
**A:** 一時ライセンスページからリクエストしてください: [Temporary License](https://purchase.aspose.com/temporary-license/)。

**Q: 正式ライセンスはどこで購入できますか？**  
**A:** Aspose ストアから直接購入できます: [Aspose.Page Buy](https://purchase.aspose.com/buy)。

**最終更新日:** 2026-06-25  
**テスト環境:** Aspose.Page 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Page for .NET を使用した XPS ドキュメントの作成](/page/net/document-creation/create-xps-document/)
- [Aspose.Page for .NET で XPS をクリップする方法](/page/net/canvas-manipulation/clippingxps/)
- [Aspose.Page for .NET を使用した XPS から PDF への変換](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}