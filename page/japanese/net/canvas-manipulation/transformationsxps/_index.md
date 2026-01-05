---
date: 2026-01-05
description: Aspose.Page for .NET を使用して XPS ドキュメントを簡単に変換する方法を学びましょう。シームレスな変換のためのステップバイステップガイドに従ってください。
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: .NET 用 Aspose.Page で XPS を変換する方法
url: /ja/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET で XPS を変換する方法

## Introduction

Aspose.Page for .NET の世界へようこそ。この強力なライブラリを使用すれば、XPS ドキュメントに対するさまざまな変換を簡単に実行できます。**このチュートリアルでは、Aspose.Page for .NET を使用して XPS ドキュメントを変換する方法を学びます**。経験豊富な開発者でも、これから始める方でも、ステップごとに解説し、各変換の理由を説明し、実際のプロジェクトで活用できる実用的なヒントを提供します。

## Quick Answers
- **What can you achieve?** XPS キャンバス要素をプログラムで作成、平行移動、拡大縮小、回転させることができます。  
- **Which library is required?** Aspose.Page for .NET（最新バージョン）。  
- **Do I need a license?** 開発用途なら無料トライアルで動作します。商用環境では商用ライセンスが必要です。  
- **Supported platforms?** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **How long does implementation take?** 本稿で示す基本的な変換は約 10‑15 分で実装可能です。

## What is “how to transform xps”?
*how to transform xps* というフレーズは、XPS（XML Paper Specification）ドキュメント内部の要素のレイアウト、サイズ、向きをプログラムで変更することを指します。Aspose.Page を使用すれば、マトリックスベースの変換をキャンバスに適用でき、位置調整、拡大縮小、回転を手動で XML を編集することなく細かく制御できます。

## Why use Aspose.Page for XPS transformations?
- **Full .NET integration** – Visual Studio、Rider などの IDE とシームレスに連携します。  
- **No external dependencies** – API が XPS の低レベルな詳細をすべて処理します。  
- **Rich transformation support** – 平行移動、拡大縮小、回転、複数変換の組み合わせを 1 回の呼び出しで実行できます。  
- **Performance‑optimized** – レポートや請求書、印刷可能なグラフィックをリアルタイムで生成するシナリオに最適です。

## Prerequisites

開始する前に以下を用意してください。

- **Aspose.Page for .NET Library** – 公式ドキュメントからダウンロードしてインストールします: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/)。  
- **Development Environment** – Visual Studio、Visual Studio Code、またはその他の .NET 対応 IDE。  
- **Document Directory** – XPS ファイルの読み書きを行うローカルフォルダー。コード中のプレースホルダーを実際のパスに置き換えてください。

準備が整ったら、コードの詳細に入りましょう。

## Import Namespaces

まず、必要な Aspose.Page クラスを公開する名前空間をインポートします。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## How to Transform XPS – Step‑by‑Step Guide

### Step 1: Create a New XPS Document

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Explanation*: ソースファイルと出力ファイルが格納されているフォルダーを定義し、空の `XpsDocument` をインスタンス化します。このオブジェクトが以降のすべての変換のキャンバスとなります。

### Step 2: Create a Main Canvas

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Why this matters*: メインキャンバスは他のすべてのキャンバスのコンテナとして機能します。小さなオフセットを付与することで、ページ端でコンテンツが切り取られるのを防ぎます。

### Step 3: Create a Rectangle Path Geometry

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Tip*: パス文字列は標準的な XPS パス構文に従います（`M` が移動、`L` が直線、`Z` が閉鎖）。座標を変更すれば矩形のサイズを調整できます。

### Step 4: Add a Fill for Rectangles

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro tip*: `CreateColor` に RGB 値を渡して、ブランドカラーに合わせた塗りを作成します。

### Step 5: Add a New Canvas Without Transformations

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

ここでは変換を加えずに矩形をページに配置します。ベースライン要素として便利です。

### Step 6: Add a New Canvas with Translate Transformation

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

*What’s happening?* 最初のマトリックスで矩形を下方向に 200 ユニット移動し、続く `Translate` 呼び出しで右方向に 500 ユニットシフトします。複数の平行移動をチェーンできることを示しています。

### Step 7: Add a New Canvas with Double Scale Transformation

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

*Why scale?* 2 倍の拡大縮小により、矩形の幅と高さがそれぞれ 2 倍になり、ジオメトリを再定義せずに大きなグラフィックを作成できます。

### Step 8: Add a New Canvas with Rotation Around a Point Transformation

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

*Key insight*: `RotateAround` はカスタムポイント（ここでは (100, 50)）を中心にキャンバスを回転させます。回転アンカーを細かく制御できるのがポイントです。

### Step 9: Save Resultant XPS Document

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

すべての変換が適用された後、ドキュメントは `output1.xps` に保存されます。任意の XPS ビューアで開くと、平行移動、拡大縮小、回転が適用された矩形が重なって表示されます。

## Common Issues & Troubleshooting

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Blank output file | `dataDir` が存在しないフォルダーを指している | ディレクトリーが存在することを確認するか、絶対パスを使用してください |
| Rectangles not positioned as expected | マトリックス値が誤っている | `Translate`、`Scale`、`RotateAround` の呼び出し順序を再確認してください |
| Colors appear wrong | RGB 値が 0‑255 の範囲外 | 各チャンネルに有効なバイト値を使用してください |

## Frequently Asked Questions

**Q: Is Aspose.Page for .NET compatible with all .NET development environments?**  
A: Yes, it works seamlessly with Visual Studio, Visual Studio Code, Rider, and any IDE that supports .NET.

**Q: Where can I find additional examples and detailed API docs?**  
A: Visit the official documentation at [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**Q: Can I try Aspose.Page before buying a license?**  
A: Absolutely. A free trial is available here: [Aspose.Page Free Trial](https://releases.aspose.com/).

**Q: How do I obtain a temporary license for testing?**  
A: You can request one via the temporary‑license page: [Temporary License](https://purchase.aspose.com/temporary-license/).

**Q: Where do I purchase a full license?**  
A: Purchase directly from the Aspose store: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}