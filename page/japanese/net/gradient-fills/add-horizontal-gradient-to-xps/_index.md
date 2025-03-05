---
title: Aspose.Page for .NET を使用して XPS に水平グラデーションを追加する
linktitle: XPS に水平方向のグラデーションを追加する
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して、XPS ドキュメントに見事な水平方向のグラデーションを追加する方法を学びます。視覚的な魅力を簡単に高めます。
type: docs
weight: 13
url: /ja/net/gradient-fills/add-horizontal-gradient-to-xps/
---
## 導入

このチュートリアルでは、Aspose.Page for .NET を使用して水平方向のグラデーションを追加して XPS ドキュメントを強化する方法を検討します。 Aspose.Page for .NET は、.NET アプリケーションで XPS (XML Paper Supplementation) ドキュメントをシームレスに処理できる強力なライブラリです。グラデーションを追加すると、ドキュメントに視覚的な魅力を加えることができます。このガイドでは、そのプロセスを段階的に説明します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.Page for .NET ライブラリ: 開発環境に Aspose.Page for .NET ライブラリがインストールされていることを確認します。からダウンロードできます。[Aspose.Page for .NET ドキュメント](https://reference.aspose.com/page/net/).

2. 開発環境: Visual Studio などのコード エディターを含む、適切な開発環境をセットアップします。

## 名前空間のインポート

まず、必要な名前空間をプロジェクトにインポートします。これらの名前空間は、Aspose.Page for .NET を操作するために不可欠です。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

ここで、提供された例を複数のステップに分解してみましょう。

## ステップ 1: ドキュメント ディレクトリのパスを設定する

```csharp
//例開始:3
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
//拡張終了:3
```

## ステップ 2: 新しい XPS ドキュメントを作成する

```csharp
//例開始:4
//新しい XPS ドキュメントの作成
XpsDocument doc = new XpsDocument();
//拡張終了:4
```

## ステップ 3: グラデーションストップを初期化する

```csharp
//例開始:5
//XpsGradientStop のリストを初期化する
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
//拡張終了:5
```

## ステップ 4: 新しいパスを作成する

```csharp
//例開始:6
//省略形でジオメトリを定義して新しいパスを作成します
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
//拡張終了:6
```

## ステップ 5: 結果の XPS ドキュメントを保存する

```csharp
//例開始:7
//結果の XPS ドキュメントを保存する
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
//拡張終了:7
```

これで、Aspose.Page for .NET を使用して、XPS ドキュメントに水平グラデーションが正常に追加されました。

## 結論

XPS ドキュメントをグラデーションで強化すると、視覚的な魅力が向上するだけでなく、より魅力的なユーザー エクスペリエンスも提供されます。 Aspose.Page for .NET はこのプロセスを簡素化し、プロフェッショナルな結果を簡単に達成できるようにします。

## よくある質問

### Q1: Aspose.Page for .NET ドキュメントはどこで見つけられますか?

 A1: ドキュメントは見つかります。[ここ](https://reference.aspose.com/page/net/).

### Q2: Aspose.Page for .NET をダウンロードするにはどうすればよいですか?

 A2: ライブラリは以下からダウンロードできます。[Aspose.Page for .NET ダウンロード ページ](https://releases.aspose.com/page/net/).

### Q3: Aspose.Page for .NET はどこで購入できますか?

 A3: Aspose.Page for .NET は、[購入ページ](https://purchase.aspose.com/buy).

### Q4: 無料トライアルはありますか?

 A4: はい、以下から無料トライアルを利用できます。[ここ](https://releases.aspose.com/).

### Q5: Aspose.Page for .NET の一時ライセンスを取得するにはどうすればよいですか?

 A5: 一時ライセンスは以下から取得できます。[このリンク](https://purchase.aspose.com/temporary-license/).