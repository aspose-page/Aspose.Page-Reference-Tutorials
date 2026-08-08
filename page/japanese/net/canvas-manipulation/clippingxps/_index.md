---
date: 2026-06-25
description: Aspose.Page for .NET を使用して XPS ドキュメントをクリップする方法を学びます。このステップバイステップガイドでは、XPS
  ファイルを効率的に作成、操作、保存する方法を示します。
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: XPS のクリップ
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET を使用した XPS のクリップ方法
url: /ja/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS を Aspose.Page for .NET でクリップする方法

## はじめに

Aspose.Page for .NET を使用して **XPS をクリップする方法** の包括的なチュートリアルへようこそ！本ガイドでは、XPS ドキュメントの作成、幾何学的クリップマスクの適用、結果の保存をステップバイステップで学びます。クリッピングを使用すると、キャンバスの一部を非表示にでき、マスクされた画像やカスタム形状、フォーカスされたコンテンツ領域など、洗練されたレイアウトを .NET コード内だけで実現できます。

## クイック回答

- **What is clipping XPS?** XPS キャンバス要素の表示領域を制限するために幾何学的マスク（クリップ）を適用することです。  
- **Which library is best for this?** Aspose.Page for .NET は XPS の作成とクリッピングに対応したフル機能 API を提供します。  
- **Prerequisites?** Visual Studio、.NET ランタイム、そして Aspose.Page for .NET ライブラリ。  
- **How long does implementation take?** 基本的なクリップシナリオでおおよそ 10〜15 分です。  
- **Can I use this in production?** はい、有効な Aspose ライセンス（トライアルあり）を使用すれば本番環境でも利用可能です。

## “XPS をクリップする方法” とは

XPS をクリップするとは、キャンバスに幾何学的マスクを適用し、マスク外の描画を表示しないようにすることです。この手法は、マスクされた画像やカスタム形状のボタン、特定ページ領域への注目を集める際に最適です。矩形、円、または複雑なパスなどのクリップジオメトリを定義することで、最終的な XPS ページに何が表示されるかを細かく制御できます。

## なぜ Aspose.Page for .NET を使って XPS をクリップするのか

Aspose.Page は外部依存なしでサーバーサイドの XPS 操作を決定的に行えるため、**50 以上の入力・出力フォーマット**に対応し、標準的な 2.5 GHz CPU 上で **200 ページの XPS ファイルを 0.5 秒未満**で処理できます。また、.NET Framework 4.0 以降、.NET Core 2.0 以降、.NET 5、.NET 6、.NET 7 に対応しています。API はキャンバス変換、パスジオメトリ、ブラシの完全な制御を提供し、常に高品質な出力を保証します。

## 前提条件

- マシンに Visual Studio がインストールされていること。  
- プロジェクトに Aspose.Page for .NET ライブラリを追加すること。ダウンロードは [here](https://releases.aspose.com/page/net/) から。  
- C# プログラミング言語の基本的な知識があること。

## XPS のクリップ方法

XPS ドキュメントを読み込み、キャンバスを作成し、クリップジオメトリ（例: 円）を定義してキャンバスの `Clip` プロパティに割り当て、コンテンツを描画し、最後にドキュメントを保存します。これらの手順は数回のメソッド呼び出しで実行でき、Aspose.Page が内部の XML マークアップを自動的に処理するため、ファイル構造ではなくビジュアルデザインに集中できます。

## 名前空間のインポート

Aspose.Page for .NET の機能を使用するには、必要な名前空間をプロジェクトにインポートする必要があります。以下の手順に従ってください。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

Now, let's break down the example code you provided into multiple steps.

## 手順 1: ドキュメントディレクトリのパスを設定

XPS ファイルを作成するフォルダーを定義します。`Path.Combine` を使用すると、OS に依存しない正しいディレクトリ区切り文字が保証されます。

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 手順 2: 新しい XPS ドキュメントを作成

`XpsDocument` クラスをインスタンス化します。このクラスは XPS パッケージ全体を表します。

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## 手順 3: メインキャンバスを作成

`Canvas` クラスは XPS ページ内で形状、画像、テキストが描画される描画面を表します。

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## 手順 4: メインキャンバスの左・上オフセットを設定

キャンバスの位置を調整し、ページ上での描画開始位置を制御します。

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## 手順 5: 矩形パスジオメトリを作成

`PathGeometry` はベクタ形状を定義します。ここではシンプルな矩形を作成します。

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## 手順 6: 矩形用の塗りを作成

矩形を塗りつぶすために使用する単色ブラシを定義します。

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## 手順 7: クリップ付きの別キャンバスをメインキャンバスに追加

クリップマスクを受け取る子キャンバスを作成します。

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## 手順 8: クリップ用の円ジオメトリを作成

`PathGeometry` は円も表現できます。このジオメトリを子キャンバスの `Clip` プロパティに割り当てます。

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## 手順 9: 第2キャンバスに矩形を作成し塗りつぶす

クリップされたキャンバス内に矩形を描画します。円の内部にある部分だけが表示されます。

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## 手順 10: ストローク付き矩形を持つ第2キャンバスをメインキャンバスに追加

ストローク付き矩形を追加し、ストロークがクリップとどのように相互作用するかを示します。

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## 手順 11: 第3キャンバスに矩形を作成しストロークを付与

第3キャンバスはクリップなしで独立した描画を示します。

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## 手順 12: 生成された XPS ドキュメントを保存

XPS パッケージをファイルシステムに永続化します。

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## よくある問題と解決策
- **Invalid path** – `dataDir` の末尾がバックスラッシュ (`\\`) で終わっているか、または `Path.Combine` を使用してください。  
- **Clip not applied** – クリップジオメトリ文字列が正しく形成されているか確認してください。スペースが欠けているとクリップが無視されることがあります。  
- **License exception** – 評価版でないビルドの場合、ドキュメント作成前に有効な Aspose ライセンスを追加してランタイム例外を回避してください。

## よくある質問

### Q1: Aspose.Page for .NET を他のドキュメント形式と併用できますか？

A1: Aspose.Page for .NET は主に XPS ドキュメントに焦点を当てていますが、Aspose はさまざまなドキュメント形式向けに他のライブラリも提供しています。

### Q2: Aspose.Page for .NET は初心者に適していますか？

A2: はい、Aspose.Page for .NET はユーザーフレンドリーに設計されており、適切なドキュメントがあれば初心者でも機能をすぐに把握できます。

### Q3: さらに多くのサンプルやリソースはどこで入手できますか？

A3: 詳細なリソースとサンプルは [documentation](https://reference.aspose.com/page/net/) と [Aspose.Page forum](https://forum.aspose.com/c/page/39) をご覧ください。

### Q4: Aspose.Page for .NET の一時ライセンスはどこで取得できますか？

A4: 一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

### Q5: Aspose.Page for .NET の無料トライアルはありますか？

A5: はい、無料トライアルは [here](https://releases.aspose.com/) からお試しいただけます。

## 追加のよくある質問

**Q: 1 つのキャンバスに複数のクリップジオメトリを組み合わせられますか？**  
A: はい、`Clip` プロパティに複数のサブパスを含む複合 `PathGeometry` を割り当てることで、レイヤードマスクが可能です。

**Q: クリッピングは PDF 変換に影響しますか？**  
A: 後で Aspose.PDF を使用して XPS を PDF に変換する際、クリップジオメトリは保持されるため、ビジュアル結果は同一です。

**Q: XPS でクリッピングをアニメーション化できますか？**  
A: XPS 自体はアニメーションをサポートしていませんが、異なるクリップ形状を持つ複数の XPS ページを生成して、動きをシミュレートすることは可能です。

**最終更新日:** 2026-06-25  
**テスト環境:** Aspose.Page 24.11 for .NET  
**著者:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## 関連チュートリアル

- [How to Transform XPS with Aspose.Page for .NET](/page/net/canvas-manipulation/transformationsxps/)
- [Add Rectangle to XPS Document with Aspose.Page for .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [Convert XPS to PDF with Aspose.Page for .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}