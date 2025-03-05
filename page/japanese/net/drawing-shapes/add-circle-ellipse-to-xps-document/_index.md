---
title: Aspose.Page for .NET を使用して XPS ドキュメントに円楕円を追加する
linktitle: XPS ドキュメントに円楕円を追加する
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して、鮮やかな放射状グラデーションで XPS ドキュメントを強化します。素晴らしい視覚効果を得るには、ステップバイステップのガイドに従ってください。
type: docs
weight: 11
url: /ja/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---
## 導入

視覚的に魅力的な XPS ドキュメントを作成することは、さまざまなアプリケーションで共通の要件です。 Aspose.Page for .NET は、XPS ドキュメントを効率的に操作するための強力な機能セットを提供します。このチュートリアルでは、Aspose.Page for .NET を使用して XPS ドキュメントに円楕円を追加することに焦点を当てます。以下の手順に従って、XPS ドキュメントを鮮やかな放射状グラデーションで強化します。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Page for .NET ライブラリがインストールされました。からダウンロードできます[ここ](https://releases.aspose.com/page/net/).
- 開発環境、できれば Visual Studio またはその他の .NET 開発ツール。
- C# プログラミングの基本的な知識。

## 名前空間のインポート

まず、必要な名前空間を C# コードに含めます。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

ここで、例を複数のステップに分けてみましょう。

## ステップ 1: ドキュメントを設定する

```csharp
//例開始:1
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
//新しい XPS ドキュメントの作成
XpsDocument doc = new XpsDocument();
```

ここでは、Aspose.Page for .NET を使用して新しい XPS ドキュメントを初期化します。

## ステップ 2: 放射状グラデーション楕円を定義する

```csharp
//左下の放射状グラデーションストローク楕円
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

このステップには、さまざまなカラーストップを使用して放射状のグラデーション楕円を定義することが含まれます。

## ステップ 3: 放射状グラデーション ブラシを設定する

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

ここでは、楕円のストロークを放射状グラデーション ブラシに設定し、必要なパラメーターを提供します。

## ステップ 4: ストロークの太さを調整する

```csharp
path.StrokeThickness = 12f;
```

このステップには、視覚化を向上させるためにストロークの太さを調整することが含まれます。

## ステップ 5: 結果の XPS ドキュメントを保存する

```csharp
//結果の XPS ドキュメントを保存する
doc.Save(dataDir + "AddEllipse_outXPS.xps");
//拡張終了:1
```

最後に、変更した XPS ドキュメントを目的の場所に保存します。

## 結論

おめでとう！ Aspose.Page for .NET を使用して、放射状グラデーションを持つ円楕円を XPS ドキュメントに追加することができました。ドキュメント内で目的の視覚効果を実現するには、さまざまなパラメーターと色を試してください。

## よくある質問

### Q1: Aspose.Page for .NET を他のドキュメント形式で使用できますか?

A1: Aspose.Page for .NET は、特に XPS ドキュメントの操作を処理します。他の形式の場合は、関連する Aspose ライブラリの使用を検討してください。

### Q2: 一時ライセンスはテスト目的で利用できますか?

 A2: はい、次のサイトにアクセスしてテスト用の一時ライセンスを取得できます。[このリンク](https://purchase.aspose.com/temporary-license/).

### Q3: 追加のヘルプやディスカッションはどこで見つけられますか?

 A3: にアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティのサポートとディスカッションのために。

### Q4: 参考となるサンプルドキュメントはありますか?

 A4: を探索してください。[ドキュメンテーション](https://reference.aspose.com/page/net/)包括的な例とガイドラインについては、こちらをご覧ください。

### Q5: Aspose.Page for .NET を購入できますか?

 A5: はい、ライブラリを購入できます。[ここ](https://purchase.aspose.com/buy).