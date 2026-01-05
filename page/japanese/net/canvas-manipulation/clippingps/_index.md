---
date: 2026-01-05
description: Aspose.Page for .NET を使用して PostScript にクリッピングパスを追加する方法を学びましょう – ペイントブラシの設定と破線矩形の描画テクニックを含むステップバイステップガイド。
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET を使用して PS にクリッピングパスを追加
url: /ja/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用して PS にクリッピングパスを追加する

## Introduction

この包括的なチュートリアルでは、Aspose.Page for .NET を使用して PostScript (PS) ドキュメントに **クリッピングパスを追加** する方法を学びます。各ステップを順に解説し、**ペイントブラシの設定** 方法と、クリップされたコンテンツの周囲に **破線の矩形を描画** する方法を示します。最後までに、形状によるクリッピングを示す完全に機能する PS ファイルが作成でき、グラフィックがよりダイナミックでプロフェッショナルになります。

## Quick Answers
- **“クリッピングパスを追加” は何をするのですか？** 定義された形状に描画操作を制限し、その形状外のすべてを非表示にします。  
- **.NET でクリッピングを扱うライブラリはどれですか？** Aspose.Page for .NET は PS/EPS 操作のための豊富な API を提供します。  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **ブラシの色を変更できますか？** はい、任意の `SolidBrush` またはグラデーションを使用して `SetPaint` してください。  
- **破線の矩形を描くことは可能ですか？** もちろんです。`DashStyle.Dash` を設定した `Pen` を作成し、`Draw` を使用します。  

## What is a clipping path in PostScript?

クリッピングパスは、以降の描画コマンドの表示領域を定義します。パスの外側に描画されたものは無視されるため、元のコンテンツを変更せずに複雑なマスクグラフィックを作成できます。

## Why use Aspose.Page for clipping?
- **外部依存なし** – 純粋な .NET ライブラリ。  
- **完全な制御** – グラフィックス状態（保存/復元、平行移動、回転）をフルコントロール。  
- **豊富な描画プリミティブ** – `SetPaint`、`Clip`、`Draw` など、カスタマイズ可能なペンやブラシを使用できます。  

## Prerequisites

- C# プログラミングの基本知識。  
- Aspose.Page for .NET ライブラリがインストールされていること – こちらからダウンロードできます [こちら](https://releases.aspose.com/page/net/)。  
- Visual Studio または好みの .NET IDE。  

## Import Namespaces

First, import the namespaces required for graphics manipulation:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Now let’s break down the example into clear, numbered steps.

### Step 1: Set Document Directory

Define the folder where your source and output files will live.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Step 2: Create Output Stream for PostScript Document

Create a writable stream that will hold the generated PS file.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Step 3: Create Save Options

Instantiate `PsSaveOptions` with default settings. You can customize later if needed.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Step 4: Create a New 1‑Paged PS Document

Initialize the `PsDocument` object that represents your PS file.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Step 5: Create Graphics Path from the Rectangle

We’ll use a rectangle as the base shape that later gets clipped.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Step 6: Clipping by Shape

Here we **add clipping path** using a circle, **set paint brush** to blue, and fill the rectangle within the clipped region.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### Step 7: Displace Upper Level Graphics State & Draw Dashed Rectangle

After restoring the previous state, we move the graphics cursor again, **draw a dashed rectangle**, and apply a blue stroke.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Step 8: Close and Save Document

Finish the page and write the PS file to disk.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

You have now successfully **added clipping path**, set a custom paint brush, and drawn a dashed rectangle around your graphics using Aspose.Page for .NET.

## Common Issues and Solutions

- **クリッピングが表示されない:** 平行移動前に `WriteGraphicsSave()` を呼び、塗りつぶし後に `WriteGraphicsRestore()` を呼び出してください。  
- **色が正しくない:** `Clip` の後、`Fill` の前に `SetPaint` が呼び出されていることを確認してください。  
- **破線が実線になる:** `SetStroke` の前に `Pen` の `DashStyle` が `DashStyle.Dash` に設定されていることを確認してください。  

## Frequently Asked Questions

### Q1: Aspose.Page for .NET を他のプログラミング言語で使用できますか？
A: Aspose.Page は主に .NET アプリケーション向けに設計されています。ただし、Aspose は他のプログラミング言語向けにも同様のライブラリを提供しています。

### Q2: Aspose.Page for .NET の追加サンプルやドキュメントはどこで見つけられますか？
A: 詳細なサンプルとドキュメントは、[Aspose.Page のドキュメント](https://reference.aspose.com/page/net/) で確認できます。

### Q3: Aspose.Page for .NET の無料トライアルはありますか？
A: はい、[こちら](https://releases.aspose.com/) から Aspose.Page for .NET の無料トライアルにアクセスできます。

### Q4: Aspose.Page for .NET の一時ライセンスはどのように取得できますか？
A: [こちら](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

### Q5: Aspose.Page に関するサポートや議論はどこでできますか？
A: コミュニティサポートとディスカッションは、[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) をご利用ください。

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}