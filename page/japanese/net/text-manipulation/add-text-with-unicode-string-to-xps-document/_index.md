---
title: Aspose.Page を使用して Unicode 文字列を含むテキストを XPS ドキュメントに追加する
linktitle: Unicode 文字列を含むテキストを XPS ドキュメントに追加する
second_title: Aspose.Page .NET API
description: Unicode テキストを XPS ドキュメントに追加するためのステップバイステップ ガイドを使用して、Aspose.Page for .NET の威力を体験してください。
weight: 12
url: /ja/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用して Unicode 文字列を含むテキストを XPS ドキュメントに追加する

## 導入

進化し続ける .NET 開発環境において、Aspose.Page は XPS ドキュメントを処理するための強力なツールとして際立っています。多くの機能の中でも、Unicode 文字列を含むテキストを XPS ドキュメントに追加する機能は貴重な機能です。このステップバイステップのガイドでは、プロセスを順を追って説明し、この機能を効果的に活用できるようにします。

## 前提条件

チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。

- .NET 開発の基本的な理解。
- Visual Studio がマシンにインストールされていること。
-  .NET ライブラリの Aspose.Page。からダウンロードできます[ここ](https://releases.aspose.com/page/net/).

## 名前空間のインポート

まず、必要な名前空間をプロジェクトにインポートしていることを確認してください。これにより、Aspose.Page を操作するために必要なクラスと機能が提供されます。重要な名前空間は次のとおりです。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ステップ 1: ドキュメントを設定する

まず、Unicode テキストを追加する新しい XPS ドキュメントを作成します。以下のコード スニペットに従ってください。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
//新しい XPS ドキュメントの作成
XpsDocument doc = new XpsDocument();
```

## ステップ 2: Unicode テキストを追加する

次に、XPS ドキュメントに Unicode テキストを追加しましょう。この例では、Arial フォントを使用し、フォント サイズを 20 に設定し、テキストを座標 (400f, 200f) に配置します。この場合の Unicode 文字列は「TEN.rof SPX.esopsA」です。以下のコード スニペットを確認してください。

```csharp
//テキストを追加
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## ステップ 3: ドキュメントを保存する

Unicode テキストを追加したら、結果の XPS ドキュメントを保存します。最後のステップは次のとおりです。

```csharp
//結果の XPS ドキュメントを保存する
doc.Save(dataDir + "AddTextRTL_out.xps");
```

おめでとう！ Aspose.Page for .NET を使用して Unicode テキストを XPS ドキュメントに追加することに成功しました。

## 結論

このチュートリアルでは、Aspose.Page for .NET を使用して Unicode テキストを XPS ドキュメントに追加するプロセスについて説明しました。この機能により、.NET 環境内での多様で動的なドキュメント作成への扉が開かれます。

## よくある質問

### Q1: Aspose.Page は最新の .NET フレームワークと互換性がありますか?

A1: はい、Aspose.Page は最新の .NET フレームワークとの互換性を確保するために定期的に更新されます。

### Q2: テキストを追加するときにフォントのスタイルとサイズをカスタマイズできますか?

A2: もちろんです！提供されているサンプル コードを使用すると、フォント スタイル、サイズ、その他の属性を簡単にカスタマイズできます。

### Q3: Aspose.Page の追加ドキュメントはどこで入手できますか?

 A3: ドキュメントを参照してください。[ここ](https://reference.aspose.com/page/net/)包括的な情報と例については、こちらをご覧ください。

### Q4: Aspose.Page を使い始めるための無料のリソースはありますか?

 A4: はい、探索できます。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティのサポートとディスカッションのために。

### Q5: 購入前に試用版はありますか?

 A5：確かに！無料試用版にアクセスできます[ここ](https://releases.aspose.com/)購入する前に。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
