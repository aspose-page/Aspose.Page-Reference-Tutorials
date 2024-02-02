---
title: Aspose.Page for .NET を使用してタイル化されたイメージを XPS ドキュメントに追加する
linktitle: タイル化された画像を XPS ドキュメントに追加
second_title: Aspose.Page .NET API
description: Aspose.Page for .NET を使用して、タイル化された画像を XPS ドキュメントに簡単に追加してみましょう。視覚的な魅力を高め、魅力的なドキュメントを作成します。
type: docs
weight: 12
url: /ja/net/image-management/add-tiled-image-to-xps-document/
---
## 導入

視覚的に魅力的なタイル画像を追加して、XPS ドキュメントを強化したいと考えていますか? Aspose.Page for .NET は、開発者がこれをシームレスに実現できるようにします。このステップバイステップ ガイドでは、Aspose.Page for .NET を使用してタイル イメージを XPS ドキュメントに追加するプロセスを説明します。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Page for .NET: Aspose.Page ライブラリがインストールされていることを確認してください。詳細なドキュメントを検索し、ライブラリをダウンロードできます。[ここ](https://reference.aspose.com/page/net/).
- 開発環境: Visual Studio など、好みの .NET 開発環境をセットアップします。

## 名前空間のインポート

まず、必要な名前空間をプロジェクトにインポートします。これにより、Aspose.Page を操作するために必要なクラスとメソッドに確実にアクセスできるようになります。コードの先頭に次の名前空間を追加します。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

ここで、例を複数のステップに分けてみましょう。

## ステップ 1: ドキュメント ディレクトリを定義する

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
```

「Your Document Directory」を、XPS ドキュメントを保存する実際のパスに置き換えてください。

## ステップ 2: 新しい XPS ドキュメントを作成する

```csharp
//新しい XPS ドキュメントの作成
XpsDocument doc = new XpsDocument();
```

を使用して新しい XPS ドキュメントをインスタンス化します。`XpsDocument`クラス。

## ステップ 3: タイル画像を追加する

```csharp
//タイル画像
//右上下の ImageBrush で塗りつぶされた四角形
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

この手順では、タイル化されたイメージを XPS ドキュメントに追加します。要件に応じて座標と画像ファイルのパスを調整します。

## ステップ 4: 結果の XPS ドキュメントを保存する

```csharp
//結果の XPS ドキュメントを保存する
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

変更した XPS ドキュメントを指定したディレクトリに保存します。

## 結論

おめでとう！ Aspose.Page for .NET を使用して、タイル化されたイメージを XPS ドキュメントに追加する方法を学習しました。このシンプルかつ強力な機能を使用すると、ドキュメントの視覚的な魅力を簡単に高めることができます。

## よくある質問

### Q1: Aspose.Page はすべての .NET 開発環境と互換性がありますか?

A1: はい、Aspose.Page は、Visual Studio を含むさまざまな .NET 開発環境とシームレスに動作するように設計されています。

### Q2: タイル画像の不透明度を調整できますか?

A2: 確かに、例で示したように、塗りつぶされた四角形の不透明度は、`Opacity`財産。

### Q3: Aspose.Page for .NET で利用できる他のタイル モードはありますか?

 A3: はい、Aspose.Page はさまざまなタイル モードを提供します。このチュートリアルでは、`XpsTileMode.Tile`ですが、ドキュメントで他のオプションを調べることもできます。

### Q4: Aspose.Page の一時ライセンスはどのように処理すればよいですか?

 A4: を参照してください。[仮免許](https://purchase.aspose.com/temporary-license/)一時ライセンスの取得と実装に関するガイダンスについては、Aspose Web サイトのページを参照してください。

### Q5: どこで助けを求めたり、Aspose.Page コミュニティに連絡したりできますか?

 A5: にアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティに参加し、質問し、解決策を見つけるために。