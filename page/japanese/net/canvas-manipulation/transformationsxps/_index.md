---
title: Aspose.Page for .NET を使用した変換 XPS
linktitle: 変換 XPS
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して XPS ドキュメントを簡単に変換します。シームレスな変換については、ステップバイステップのガイドに従ってください。
weight: 13
url: /ja/net/canvas-manipulation/transformationsxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用した変換 XPS

## 導入

Aspose.Page for .NET の世界へようこそ。これは、XPS ドキュメントに対してさまざまな変換を簡単に実行できる強力なライブラリです。このチュートリアルでは、Aspose.Page for .NET を使用して XPS ドキュメントを変換するプロセスについて詳しく説明します。経験豊富な開発者であっても、初心者であっても、このガイドでは各ステップを順を追って説明し、概念を簡単に理解できるようにします。

## 前提条件

始める前に、次のものが揃っていることを確認してください。

-  Aspose.Page for .NET ライブラリ: からライブラリをダウンロードしてインストールします。[Aspose.Page for .NET ドキュメント](https://reference.aspose.com/page/net/).

- 開発環境: Visual Studio やその他の .NET 開発ツールなど、互換性のある開発環境をセットアップします。

- ドキュメント ディレクトリ: コード内のプレースホルダーをドキュメント ディレクトリへの実際のパスに置き換えます。

それでは、チュートリアルに移りましょう!

## 名前空間のインポート

まず、Aspose.Page for .NET の機能をコード内で使用できるようにするために、必要な名前空間をインポートしていることを確認します。スクリプトの先頭に次の名前空間を追加します。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ステップ 1: 新しい XPS ドキュメントを作成する

```csharp
//例開始:1
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";

//新しい XPS ドキュメントの作成
XpsDocument doc = new XpsDocument();
```

## ステップ 2: メイン キャンバスを作成する

```csharp
//すべてのページ要素に共通のメイン キャンバスを作成する
XpsCanvas canvas1 = doc.AddCanvas();

//メインキャンバスで左と上のオフセットを作成します。
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## ステップ 3: 長方形のパス ジオメトリを作成する

```csharp
//長方形のパス ジオメトリを作成する
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## ステップ 4: 長方形の塗りつぶしを追加する

```csharp
//長方形の塗りつぶしを作成する
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## ステップ 5: 変換を行わずに新しいキャンバスを追加する

```csharp
//メイン キャンバスに何も変更せずに新しいキャンバスを追加します。
XpsCanvas canvas2 = canvas1.AddCanvas();

//このキャンバスに長方形を作成して塗りつぶします
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## ステップ 6: 変換変換を使用して新しいキャンバスを追加する

```csharp
//変換変換を使用して新しいキャンバスをメイン キャンバスに追加します。
XpsCanvas canvas3 = canvas1.AddCanvas();

//このキャンバスを移動して、前の四角形の下に新しい四角形を配置します。
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

//このキャンバスをページの右側に移動します
canvas3.RenderTransform.Translate(500, 0);

//このキャンバスに長方形を作成して塗りつぶします
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## ステップ 7: 2 倍のスケール変換を使用して新しいキャンバスを追加する

```csharp
//メイン キャンバスに 2 倍のスケール変形を伴う新しいキャンバスを追加します
XpsCanvas canvas4 = canvas1.AddCanvas();

//このキャンバスを移動して、前の四角形の下に新しい四角形を配置します。
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

//このキャンバスを拡大縮小する
canvas4.RenderTransform.Scale(2, 2);

//このキャンバスに長方形を作成して塗りつぶします
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## ステップ 8: ポイント変換を中心に回転する新しいキャンバスを追加する

```csharp
//ポイント変換を中心に回転する新しいキャンバスをメイン キャンバスに追加します。
XpsCanvas canvas5 = canvas1.AddCanvas();

//このキャンバスを移動して、前の四角形の下に新しい四角形を配置します。
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

//このキャンバスを点を中心に 45 度回転します
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

//このキャンバスに長方形を作成して塗りつぶします
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## ステップ 9: 結果の XPS ドキュメントを保存する

```csharp
//結果の XPS ドキュメントを保存する
doc.Save(dataDir + "output1.xps");
//拡張終了:1
```

## 結論

おめでとう！ Aspose.Page for .NET を使用して XPS ドキュメントを正常に変換しました。このガイドでは、前提条件の設定からさまざまな変換の実行まで、重要な手順について説明しました。これらのテクニックを試して、プロジェクトで Aspose.Page for .NET の可能性を最大限に引き出します。

## よくある質問

### Q1: Aspose.Page for .NET はすべての .NET 開発環境と互換性がありますか?

A1: はい、Aspose.Page for .NET は、Visual Studio を含むさまざまな .NET 開発環境とシームレスに動作するように設計されています。

### Q2: Aspose.Page for .NET の追加の例とドキュメントはどこで見つけられますか?

 A2: にアクセスしてください。[Aspose.Page for .NET ドキュメント](https://reference.aspose.com/page/net/)包括的なドキュメントと例については、こちらをご覧ください。

### Q3: 購入する前に Aspose.Page for .NET を試すことはできますか?

 A3: はい、次のサイトにアクセスして無料試用版を試すことができます。[Aspose.Page の無料トライアル](https://releases.aspose.com/).

### Q4: Aspose.Page for .NET の一時ライセンスを取得するにはどうすればよいですか?

A4: にアクセスして仮免許を取得してください。[仮免許](https://purchase.aspose.com/temporary-license/).

### Q5: Aspose.Page for .NET はどこで購入できますか?

 A5: Aspose.Page for .NET を購入します。[Aspose.ページ購入](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
