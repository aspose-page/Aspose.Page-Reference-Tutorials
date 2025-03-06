---
title: Aspose.Page for .NET を使用した XPS のクリッピング
linktitle: クリッピング XPS
second_title: Aspose.Page .NET API
description: XPS ドキュメントのクリッピングに関するこのステップバイステップ ガイドで、Aspose.Page for .NET の威力を探ってください。 XPS ファイルを簡単に作成、操作、保存できます。
weight: 11
url: /ja/net/canvas-manipulation/clippingxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用した XPS のクリッピング

## 導入

Aspose.Page for .NET を使用した XPS のクリッピングに関するこの包括的なチュートリアルへようこそ。このガイドでは、Aspose.Page for .NET を使用して XPS ドキュメントを作成、操作、保存するプロセスについて説明します。 XPS (XML Paper 仕様) は、標準化されたオープンなドキュメント形式であり、Aspose.Page for .NET は、.NET アプリケーションで XPS ドキュメントを操作するための強力なツールを提供します。

## 前提条件

チュートリアルに入る前に、次の前提条件を満たしていることを確認してください。

- Visual Studio がマシンにインストールされていること。
-  Aspose.Page for .NET ライブラリがプロジェクトに追加されました。ダウンロードできます[ここ](https://releases.aspose.com/page/net/).
- C# プログラミング言語の基本的な知識。

## 名前空間のインポート

Aspose.Page for .NET の機能を使用するには、必要な名前空間をプロジェクトにインポートする必要があります。次の手順を実行します：

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

ここで、提供したサンプル コードを複数のステップに分けてみましょう。

## ステップ 1: ドキュメント ディレクトリのパスを設定します。

```csharp
string dataDir = "Your Document Directory";
```

「Your Document Directory」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 2: 新しい XPS ドキュメントを作成します。

```csharp
XpsDocument doc = new XpsDocument();
```

これにより、作業する新しい XPS ドキュメントが作成されます。

## ステップ 3: メイン キャンバスを作成します。

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

このステップでは、すべてのページ要素に共通のメイン キャンバスを作成します。

## ステップ 4: メイン キャンバスの左と上のオフセットを設定します。

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

要件に応じて左と上のオフセットを調整します。

## ステップ 5: 長方形のパス ジオメトリを作成します。

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

これにより、長方形のパス ジオメトリが作成されます。

## ステップ 6: 長方形の塗りつぶしを作成します。

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

長方形の塗りつぶしの色を定義します。

## ステップ 7: クリップを含む別のキャンバスをメイン キャンバスに追加します。

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

このステップでは、メイン キャンバスに別のキャンバスを追加します。

## ステップ 8: クリップ用の円ジオメトリを作成します。

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

これにより、円形のクリップ ジオメトリが作成され、2 番目のキャンバスに適用されます。

## ステップ 9: 2 番目のキャンバスに長方形を作成し、塗りつぶします。

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

このステップでは、2 番目のキャンバスに長方形を作成し、それを塗りつぶします。

## ステップ 10: ストロークされた四角形を含む 2 番目のキャンバスをメイン キャンバスに追加します。

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

これにより、メイン キャンバスに別のキャンバスが追加されます。

## ステップ 11: 3 番目のキャンバスに長方形を作成し、ストロークします。

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

これにより、3 番目のキャンバスに長方形が作成され、それにストロークが適用されます。

## ステップ 12: 結果の XPS ドキュメントを保存します。

```csharp
doc.Save(dataDir + "output2.xps");
```

これにより、XPS ドキュメントが指定されたディレクトリに保存されます。

## 結論

おめでとう！ Aspose.Page for .NET を使用して XPS をクリップする方法を学習しました。このガイドでは、プロセスに含まれる手順の詳細なウォークスルーを提供しました。

## よくある質問

### Q1: Aspose.Page for .NET を他のドキュメント形式で使用できますか?

A1: Aspose.Page for .NET は主に XPS ドキュメントに焦点を当てていますが、Aspose はさまざまなドキュメント形式用の他のライブラリを提供します。

### Q2: Aspose.Page for .NET は初心者に適していますか?

A2: はい、Aspose.Page for .NET はユーザーフレンドリーになるように設計されており、初心者でも適切なドキュメントを読めば機能をすぐに理解できます。

### Q3: 他の例やリソースはどこで見つけられますか?

 A3: にアクセスしてください。[ドキュメンテーション](https://reference.aspose.com/page/net/)そして[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)豊富なリソースと例については、こちらをご覧ください。

### Q4: Aspose.Page for .NET の一時ライセンスを取得するにはどうすればよいですか?

 A4: 仮免許は取得できます。[ここ](https://purchase.aspose.com/temporary-license/).

### Q5: Aspose.Page for .NET の無料トライアルはありますか?

 A5: はい、無料トライアルを試すことができます[ここ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
