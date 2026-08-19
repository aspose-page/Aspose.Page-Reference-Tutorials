---
date: 2026-02-25
description: Aspose.Page for .NET を使用して、水平塗りつぶしの XPS グラデーションの作成方法を学びましょう。ドキュメントの視覚的魅力を手軽に高めることができます。
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'XPS グラデーションの作成: .NET 用 Aspose.Page で水平塗り'
url: /ja/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS グラデーションの作成 – Aspose.Page for .NET を使用して XPS に水平グラデーションを追加

## はじめに

このチュートリアルでは、ページ全体に水平に走る **XPS グラデーション** 塗りを作成します。水平グラデーションを追加するだけで、レポートやパンフレット、ビジュアルが豊富な出力物など、XPS ドキュメントの見た目がすぐに洗練され、魅力的になります。環境設定から最終的な XPS ファイルの保存まで、Aspose.Page for .NET を使った手順をすべて解説します。

## クイック回答
- **このチュートリアルの内容は？** Aspose.Page for .NET を使用して XPS ドキュメントに水平グラデーションを追加します。  
- **必要なライブラリは？** Aspose.Page for .NET（最新バージョンであれば可）。  
- **ライセンスは必要ですか？** 開発目的ならトライアルで動作しますが、商用利用には正式ライセンスが必要です。  
- **実装にかかる時間は？** 基本的なグラデーションであれば 5〜10 分程度です。  
- **グラデーションの方向は変更できますか？** はい – `LinearGradientBrush` の開始点と終了点を変更すれば方向を変えられます。

## Aspose.Page for .NET で XPS グラデーションを作成する方法

以下に、**なぜ**各コード行が必要なのか、**何を**するのかを説明したステップバイステップのガイドを示します。Visual Studio でも好みの .NET エディタでも自由に試してください。

## 前提条件

開始する前に、以下の項目が揃っていることを確認してください。

1. **Aspose.Page for .NET ライブラリ**: 開発環境に Aspose.Page for .NET ライブラリがインストールされていることを確認してください。ダウンロードは [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/) から行えます。  
2. **開発環境**: Visual Studio などのコードエディタを含む、適切な開発環境を整えてください。

## 名前空間のインポート

プロジェクトに必要な名前空間をインポートします。これらの名前空間は Aspose.Page for .NET を操作するために必須です。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

それでは、提供されたサンプルを複数のステップに分解して説明します。

## Step 1: Set the Document Directory Path

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Step 2: Create a New XPS Document

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Step 3: Initialize Gradient Stops

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Step 4: Create a New Path

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Step 5: Save the Resultant XPS Document

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

これで、Aspose.Page for .NET を使用して XPS ドキュメントに水平グラデーションを正常に追加できました。

## よくある問題と解決策

| 問題 | 原因 | 対策 |
|------|------|------|
| グラデーションが単色に見える | グラデーションストップが正しく追加されていない | ブラシを設定した後に `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` が実行されていることを確認してください。 |
| 保存されたファイルが空です | `dataDir` が存在しないフォルダーを指している | フォルダーが存在するか確認するか、絶対パスを使用してください。 |
| `PointF` のコンパイルエラー | `System.Drawing` の参照が欠如している | `.NET Core/5+` 用に `System.Drawing.Common` への参照を追加してください。 |

## FAQ

### Q1: Aspose.Page for .NET のドキュメントはどこで見つけられますか？

A1: ドキュメントは[こちら](https://reference.aspose.com/page/net/)でご覧いただけます。

### Q2: Aspose.Page for .NET をダウンロードするには？

A2: ライブラリは[Aspose.Page for .NET ダウンロードページ](https://releases.aspose.com/page/net/)から取得できます。

### Q3: Aspose.Page for .NET の購入先は？

A3: 購入は[購入ページ](https://purchase.aspose.com/buy)から行えます。

### Q4: 無料トライアルは利用可能ですか？

A4: はい、[こちら](https://releases.aspose.com/)から無料トライアルを入手できます。

### Q5: Aspose.Page for .NET の一時ライセンスはどう取得しますか？

A5: 一時ライセンスは[このリンク](https://purchase.aspose.com/temporary-license/)から取得できます。

## よくある質問

**Q: 既に画像が含まれている XPS ドキュメントでもこのグラデーション手法は使用できますか？**  
A: もちろんです。グラデーションはパスレイヤーに適用されるため、既存の画像はそのまま残ります。

**Q: 垂直グラデーションを作成することは可能ですか？**  
A: はい。`LinearGradientBrush` の開始点と終了点の Y 座標を変えて、X 座標は同じにすれば垂直グラデーションになります。

**Q: Aspose.Page は .NET Core をサポートしていますか？**  
A: ライブラリは .NET Core、.NET 5 以降のバージョンと完全に互換性があります。

**Q: 複数ページで同じグラデーションを再利用するには？**  
A: `XpsLinearGradientBrush` を一度作成し、変数に保持して各ページのパスに割り当てれば再利用できます。

## 結論

XPS ドキュメントにグラデーションを加えることで、視覚的な魅力が向上し、ユーザー体験もより引き込まれるものになります。Aspose.Page for .NET を使えば、**XPS グラデーション** 塗りを迅速かつ確実に作成でき、レポートやパンフレット、電子書籍にプロフェッショナルな仕上がりを提供できます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2026-02-25  
**テスト環境:** Aspose.Page for .NET 24.11  
**作者:** Aspose  

---