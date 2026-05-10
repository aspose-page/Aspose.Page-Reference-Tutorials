---
date: 2026-03-03
description: Aspose.Page for .NET を使用して XPS ドキュメント内の画像をタイル状に配置する方法を学びましょう。このステップバイステップガイドでは、画像を効率的にタイル状に配置し、視覚的な魅力を高める方法を示します。
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Aspose.Page を使用して XPS ドキュメントにタイル画像を追加する方法
url: /ja/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用して XPS ドキュメントにタイル画像を追加する方法

## Introduction

XPS ファイルによりリッチなビジュアルスタイルを付加したいと **Aspose の使い方** をお探しなら、ここが最適です。このチュートリアルでは、Aspose.Page for .NET を使用して XPS ドキュメント内に **画像をタイル状に配置** する手順を詳しく解説します。最後まで実行すれば、任意の .NET プロジェクトに組み込める再利用可能なコードスニペットが手に入ります。

## Quick Answers
- **What library is needed?** Aspose.Page for .NET  
- **Which method creates the tiled brush?** `CreateImageBrush` with `TileMode = XpsTileMode.Tile`  
- **Can I control opacity?** Yes – set `path.Fill.Opacity` (e.g., 0.5f)  
- **Do I need a license for testing?** A temporary license works for evaluation; a full license is required for production.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## What is Aspose.Page and Why Tile Images?

Aspose.Page は、Microsoft Office に依存せずに XPS、PDF、その他ページベースのフォーマットを生成・編集・レンダリングできる強力な API です。画像をタイル状に配置する（ビットマップを形状全体に繰り返す）ことで、パターンや透かし、背景テクスチャを大きな領域に低ファイルサイズで埋め込むことができます。

## How to Use Aspose.Page to Tile Images in XPS Documents

以下に、すぐに実行できる完全なサンプルを示します。各ステップはコードブロックの前に平易な説明を入れているので、**なぜその行が必要か** が分かります。

### Prerequisites

- **Aspose.Page for .NET** – 公式サイトの [here](https://reference.aspose.com/page/net/) からダウンロードし、プロジェクトに参照してください。  
- **Development environment** – Visual Studio（任意のエディション）またはお好みの .NET IDE。

### Import Namespaces

まず、必要な名前空間をインポートして XPS クラスが見つかるようにします。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Step 1: Define the Document Directory

生成した XPS ファイルと元画像が保存されるディレクトリを指定します。プレースホルダーは実際のフォルダーに置き換えてください。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Step 2: Create a New XPS Document

タイル画像を格納する空の XPS ドキュメントをインスタンス化します。

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Step 3: Add a Tiled Image

ここでは矩形パスを作成し、`ImageBrush` で塗りつぶし、ブラシをタイルモードに設定します。`TileMode` プロパティにより画像が水平・垂直方向に繰り返されます。矩形の座標やソース画像はシナリオに合わせて調整してください。

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Step 4: Save the Resultant XPS Document

最後にドキュメントをディスクに書き出します。出力ファイルは任意の XPS ビューアで開くか、Aspose.Page でさらに処理できます。

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Common Issues & Tips

- **Path errors** – `dataDir` の末尾にスラッシュがあるか確認するか、`Path.Combine` を使用してセパレーター欠如による問題を防ぎます。  
- **Image size mismatches** – タイル領域に対してソース画像が十分に大きいことを確認してください。小さすぎるとパターンが伸びて見えることがあります。  
- **Opacity not visible** – 一部のビューアは XPS の不透明度を無視します。XPS Viewer（Windows）など、完全に XPS をレンダリングできるビューアでテストしてください。

## Frequently Asked Questions

### Q1: Is Aspose.Page compatible with all .NET development environments?
A: Yes, Aspose.Page works with Visual Studio, Rider, VS Code, and any IDE that supports .NET.

### Q2: Can I adjust the opacity of the tiled image?
A: Absolutely. The example sets `path.Fill.Opacity = 0.5f;`—you can change the float value between 0 (transparent) and 1 (opaque).

### Q3: Are there other tile modes available in Aspose.Page for .NET?
A: Yes. Besides `XpsTileMode.Tile`, you can use `FlipX`, `FlipY`, and `FlipXY` to create mirrored patterns.

### Q4: How do I handle temporary licenses for Aspose.Page?
A: Refer to the [temporary license](https://purchase.aspose.com/temporary-license/) page on the Aspose website for details on obtaining and applying a trial license.

### Q5: Where can I seek help or connect with the Aspose.Page community?
A: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to ask questions, share snippets, and learn from other developers.

### Q6: Can I use this approach to create a watermark effect?
A: Yes. By lowering the opacity and choosing a semi‑transparent image, the tiled brush works perfectly as a repeating watermark.

## Conclusion

You now know **how to use Aspose** to add a tiled image to an XPS document, control its opacity, and save the result for further use. This technique is ideal for background patterns, watermarks, or any situation where a repeating graphic adds visual interest without inflating file size. Feel free to experiment with different shapes, images, and tile modes to suit your project’s needs.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Page for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}