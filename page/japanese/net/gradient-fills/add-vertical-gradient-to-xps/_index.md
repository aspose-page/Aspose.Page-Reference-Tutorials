---
title: Aspose.Page for .NET を使用して XPS に垂直グラデーションを追加する
linktitle: XPS に垂直グラデーションを追加する
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して、XPS ドキュメントを垂直方向のグラデーションで強化する方法を学びます。シームレスな統合については、ステップバイステップのガイドに従ってください。
type: docs
weight: 15
url: /ja/net/gradient-fills/add-vertical-gradient-to-xps/
---
## 導入

Aspose.Page for .NET を使用して XPS ドキュメントに垂直グラデーションを追加する方法に関するステップバイステップのチュートリアルへようこそ。 Aspose.Page は、.NET アプリケーションで XPS (XML Paper Specification) ファイルを操作できるようにする強力な API です。このチュートリアルでは、新しい XPS ドキュメントを作成し、パスに垂直グラデーションを追加し、結果を保存するプロセスを説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件を満たしていることを確認してください。

-  Aspose.Page for .NET ライブラリ: 開発環境に Aspose.Page for .NET ライブラリがインストールされていることを確認します。ダウンロードできます[ここ](https://releases.aspose.com/page/net/).

- 開発環境: Visual Studio などの好みの IDE を使用して .NET 開発環境をセットアップします。

それでは、Aspose.Page for .NET を使用して XPS ドキュメントに垂直グラデーションを追加してみましょう。

## 名前空間のインポート

.NET アプリケーションに、Aspose.Page クラスとメソッドにアクセスするために必要な名前空間を含めます。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## ステップ 1: ドキュメント ディレクトリを設定する

開始する前に、結果の XPS ドキュメントを保存するドキュメント ディレクトリへのパスを設定します。

```csharp
//例開始:3
string dataDir = "Your Document Directory";
//拡張終了:3
```

## ステップ 2: 新しい XPS ドキュメントを作成する

次のコードを使用して、新しい XPS ドキュメントを初期化します。

```csharp
//例開始:4
XpsDocument doc = new XpsDocument();
//拡張終了:4
```

## ステップ 3: グラデーション停止点を定義する

各ストップの色と位置を指定して、グラデーションストップのリストを作成します。この例では、5 つのストップを持つ垂直グラデーションを定義します。

```csharp
//例開始:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
//拡張終了:5
```

## ステップ 4: グラデーションのあるパスを作成する

ジオメトリを指定してパスを定義し、それに線形グラデーション ブラシを適用します。

```csharp
//例開始:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
//拡張終了:6
```

## ステップ 5: 結果の XPS ドキュメントを保存する

変更した XPS ドキュメントを指定したディレクトリに保存します。

```csharp
//例開始:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
//拡張終了:7
```

おめでとう！ Aspose.Page for .NET を使用して、XPS ドキュメントに垂直グラデーションを追加することに成功しました。

## 結論

このチュートリアルでは、Aspose.Page for .NET を活用して XPS ドキュメントを垂直方向のグラデーションで強化する方法を検討しました。 Aspose.Page は複雑なタスクを簡素化し、開発者に .NET アプリケーションで XPS ファイルを操作するシームレスな方法を提供します。

## よくある質問

### Q1: Aspose.Page は Visual Studio 2019 と互換性がありますか?

A1: はい、Aspose.Page は Visual Studio 2019 と互換性があります。正しいバージョンのライブラリがインストールされていることを確認してください。

### Q2: Aspose.Page を商用プロジェクトに使用できますか?

 A2: はい、Aspose.Page は商用プロジェクトに使用できます。訪問[ここ](https://purchase.aspose.com/buy)ライセンス オプションを検討します。

### Q3: 無料トライアルはありますか?

A3: はい、Aspose.Page の無料トライアルを入手できます。[ここ](https://releases.aspose.com/).

### Q4: Aspose.Page のドキュメントはどこで見つけられますか?

 A4: ドキュメントは入手可能です[ここ](https://reference.aspose.com/page/net/).

### Q5: サポートを受けたり、質問したりするにはどうすればよいですか?

 A5: にアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティサポートのために。