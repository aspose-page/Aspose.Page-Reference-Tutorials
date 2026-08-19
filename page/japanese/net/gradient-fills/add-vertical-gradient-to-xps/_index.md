---
date: 2026-02-25
description: Aspose.Page for .NET を使用して XPS ドキュメントの作成方法と線形グラデーションの適用方法を学びましょう。ステップバイステップのガイドに従って
  XPS ファイルを保存してください。
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Aspose.Page を使用して垂直グラデーションの XPS ドキュメントを作成する
url: /ja/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET を使用して XPS に垂直グラデーションを追加する

## はじめに

このチュートリアルでは、滑らかな垂直グラデーションを備えた **XPS ドキュメント** を作成します。グラデーションを追加することは、XPS ファイルをよりプロフェッショナルに見せる一般的な方法で、レポート、パンフレット、または印刷可能なグラフィックに最適です。プロジェクトの設定から最終的な XPS ファイルの保存まで、すべての手順を順に説明するので、任意のパスに線形グラデーションをすぐに適用できます。

## クイック回答
- **このチュートリアルの内容は？** XPS ドキュメント内のパスに垂直線形グラデーションを追加することです。  
- **必要なライブラリは？** Aspose.Page for .NET。  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作しますが、製品版には商用ライセンスが必要です。  
- **実装にかかる時間は？** 基本的な例で約 10〜15 分です。  
- **結果を XPS ファイルとして保存できますか？** はい、`Save` メソッドでディスクに書き込みます。

## XPS における垂直グラデーションとは？

垂直グラデーションは、形状の上部から下部へ向かう色の遷移です。XPS では、開始点と終了点を定義し、特定の位置での色を制御するグラデーション ストップのコレクションを持つ **linear gradient brush** によって実現されます。

## なぜ Aspose.Page を使用してグラデーション付き XPS ドキュメントを作成するのか？

- **フル .NET 統合** – .NET Framework、.NET Core、.NET 5/6+ で動作します。  
- **外部依存なし** – すべてのレンダリングはライブラリが処理します。  
- **高忠実度** – グラデーションは定義通りに正確に描画され、XPS 仕様に一致します。  
- **保守が容易** – パス、ブラシ、カラーのオブジェクトモデルが明確です。

## 前提条件

- Aspose.Page for .NET ライブラリ: 開発環境に Aspose.Page for .NET ライブラリがインストールされていることを確認してください。ダウンロードは [here](https://releases.aspose.com/page/net/) から行えます。  
- 開発環境: Visual Studio など、お好みの IDE を使用して .NET 開発環境をセットアップしてください。

これで準備が整ったので、コードに入りましょう。

## 名前空間のインポート

.NET アプリケーションで、Aspose.Page のクラスとメソッドにアクセスするために必要な名前空間をインクルードします。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## 手順 1: ドキュメント ディレクトリの設定

生成された XPS ファイルを保存するフォルダーを定義します。

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## 手順 2: 新しい XPS ドキュメントの作成

後でグラデーションで塗りつぶしたパスを追加するための新しい XPS ドキュメントをインスタンス化します。

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## 手順 3: グラデーション ストップの定義

グラデーション ストップは、グラデーション線上の色とその位置を決定します。ここでは、滑らかな垂直遷移を作るために 5 つのストップを作成します。

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## 手順 4: グラデーション付きパスの作成

矩形形状のパスを描画し、点 (10, 110) から点 (10, 200) へ垂直に走る **linear gradient brush** を適用します。ブラシは先に定義したグラデーション ストップを受け取ります。

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## 手順 5: 結果の XPS ドキュメントを保存する

最後に、XPS ドキュメントをディスクに書き込みます。この **save XPS file** 手順により、指定したフォルダーに `AddVerticalGradient_outXPS.xps` が生成されます。

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**プロのコツ:** Windows XPS Viewer や任意のサードパーティ ビューアで XPS ファイルを開き、グラデーションが期待通りに表示されているか確認してください。

## よくある問題とトラブルシューティング

| 症状 | 考えられる原因 | 対策 |
|------|----------------|------|
| グラデーションが単色で表示される | グラデーション ストップがブラシに追加されていない | `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` が実行されていることを確認してください。 |
| 保存時にファイルが見つからない | `dataDir` が存在しないフォルダーを指している | 先にディレクトリを作成するか、絶対パスを使用してください。 |
| 色が異なって見える | カラー値が ARGB 順になっている; チャンネル順序を確認する | `CreateColor(alpha, red, green, blue)` を正しく使用してください。 |

## よくある質問

**Q: Aspose.Page は Visual Studio 2019 と互換性がありますか？**  
A: はい、Aspose.Page は Visual Studio 2019 と互換性があります。正しいバージョンのライブラリがインストールされていることを確認してください。

**Q: 商用プロジェクトで Aspose.Page を使用できますか？**  
A: はい、Aspose.Page は商用プロジェクトで使用できます。ライセンスオプションは [here](https://purchase.aspose.com/buy) でご確認ください。

**Q: 無料トライアルは利用可能ですか？**  
A: はい、Aspose.Page の無料トライアルは [here](https://releases.aspose.com/) から取得できます。

**Q: Aspose.Page のドキュメントはどこで見つけられますか？**  
A: ドキュメントは [here](https://reference.aspose.com/page/net/) にあります。

**Q: サポートや質問はどこで受けられますか？**  
A: コミュニティサポートは [Aspose.Page forum](https://forum.aspose.com/c/page/39) をご利用ください。

## 結論

これで、Aspose.Page for .NET を使用して **XPS ドキュメントを作成**、**線形グラデーションを適用**、そして **XPS ファイルを保存** する方法が分かりました。この手法により、XPS 出力のビジュアルスタイルを完全にコントロールでき、印刷物が際立ちます。

---  

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}