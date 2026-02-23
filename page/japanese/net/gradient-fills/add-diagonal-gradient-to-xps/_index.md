---
date: 2026-02-23
description: Aspose.Page for .NET を使用して対角線グラデーションの XPS ドキュメントを作成する方法を学び、視覚的プレゼンテーションを簡単に向上させましょう。
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: .NET 用 Aspose.Page で対角線グラデーション XPS を作成する
url: /ja/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用して対角線グラデーション XPS を作成する

## はじめに

目を引く **対角線グラデーション XPS** ファイルを作成する必要がある場合、Aspose.Page for .NET が簡単に実現できます。このチュートリアルでは、Aspose.Page API を使用して XPS ドキュメントに対角線グラデーションを追加する方法をステップバイステップで学びます。最後には、任意の形状やカラースキームに適用できる再利用可能なパターンが手に入ります。

## クイック回答
- **API メソッドは何を行いますか？** パス全体に対角線に広がる線形グラデーションブラシを作成します。  
- **XPS ドキュメントを表すクラスはどれですか？** `XpsDocument`。  
- **サンプルを実行するのにライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境ではライセンスが必要です。  
- **グラデーションの方向を変更できますか？** はい—開始と終了の `PointF` 値を調整します。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## **create diagonal gradient xps** とは何ですか？

対角線グラデーションは、形状の一つの角から反対側の角へと滑らかに色が変化するものです。XPS では、`LinearGradientBrush` をパスの fill プロパティに適用することでこの効果が実現されます。Aspose.Page ライブラリは低レベルの XPS マークアップを抽象化し、色とジオメトリに集中できるようにします。

## 対角線グラデーションに Aspose.Page を使用する理由は？

- **高忠実度レンダリング** – 出力は XPS 仕様と完全に一致します。  
- **完全な .NET 統合** – C#、VB.NET、その他すべての .NET 言語で動作します。  
- **外部依存なし** – すべてがプロセス内で処理され、COM や Office は不要です。  
- **複雑なドキュメントにもスケーラブル** – 同じページ上で複数のグラデーション、画像、テキストを組み合わせることができます。

## 前提条件

1. **Aspose.Page for .NET ライブラリ** – こちらからダウンロードしてください [here](https://releases.aspose.com/page/net/)。  
2. **開発環境** – Visual Studio、Rider、または .NET プロジェクトをサポートする任意のエディタ。

それでは、コードを見ていきましょう。

## 名前空間のインポート

.NET プロジェクトで、必要なクラスやメソッドにアクセスできるよう Aspose.Page ライブラリから必要な名前空間をインクルードします。コードの先頭に以下の名前空間を追加してください:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## 手順 1: ドキュメント ディレクトリの設定

まず、ドキュメント ディレクトリへのパスを指定します。ここに対角線グラデーションを適用した XPS ドキュメントが保存されます。

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## 手順 2: 新しい XPS ドキュメントの作成

Aspose.Page ライブラリを使用して新しい `XpsDocument` を初期化します。

```csharp
XpsDocument doc = new XpsDocument();
```

## 手順 3: グラデーションカラーの定義

対角線グラデーション内の各色を表す `XpsGradientStop` オブジェクトのリストを作成します。

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## 手順 4: パスに対角線グラデーションを追加する

定義されたジオメトリを持つ新しいパスを作成し、そこに対角線グラデーションを適用します。必要に応じてレンダリング変換や fill プロパティを調整してください。

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## 手順 5: 結果の XPS ドキュメントを保存する

最後に、変更された XPS ドキュメントを指定したディレクトリに保存します。

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

これで **対角線グラデーション XPS** ファイルの作成に成功しました。さまざまなカラーストップ、ジオメトリ文字列、変換行列を試して、多彩なビジュアル効果を実現してください。

## よくある問題と解決策
- **グラデーションが表示されない** – パスジオメトリが閉じていること、ブラシの開始/終了ポイントがパスの境界内にあることを確認してください。  
- **色が正しくない** – 正しい ARGB 値で `CreateColor` を使用しているか確認してください。メソッドは 0‑255 の範囲の値を期待します。  
- **ファイルが保存されない** – `dataDir` が既存のフォルダーを指しているか、アプリケーションに書き込み権限があるか確認してください。

## よくある質問

**Q: ドキュメントの異なる部分に複数のグラデーションを適用できますか？**  
A: はい、複数のパスを作成し、それぞれに異なるグラデーションを適用できます。

**Q: 事前定義されたグラデーションスタイルは利用可能ですか？**  
A: Aspose.Page はカスタムグラデーションをサポートしており、色の遷移を完全にコントロールできます。

**Q: Aspose.Page for .NET を他のドキュメント形式で使用できますか？**  
A: Aspose.Page は主に XPS ドキュメントの操作に特化しています。

**Q: ドキュメント処理に関するエラーはどのように対処すればよいですか？**  
A: エラーハンドリングのベストプラクティスについては、[documentation](https://reference.aspose.com/page/net/) を参照してください。

**Q: 購入前に試用版はありますか？**  
A: はい、[free trial](https://releases.aspose.com/) で Aspose.Page for .NET を体験できます。

**Q: グラデーションの方向を垂直または水平に変更するには？**  
A: `CreateLinearGradientBrush` の `PointF` 引数を変更して、新しい開始点と終了点を設定します。

**Q: ライブラリはグラデーションで透明度をサポートしていますか？**  
A: はい—`CreateColor` で色を作成する際にアルファ値を含めます。

## 結論

Aspose.Page for .NET は、XPS ドキュメントに対角線グラデーションを追加するプロセスをシンプルにします。本ガイドでは、前提条件の設定から最終ファイルの保存までを順を追って解説しました。さまざまな形状やカラーパレットで実験し、XPS レポート、パンフレット、請求書などを真に際立たせてください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日：** 2026-02-23  
**テスト環境：** Aspose.Page 24.11 for .NET  
**作者：** Aspose  

---