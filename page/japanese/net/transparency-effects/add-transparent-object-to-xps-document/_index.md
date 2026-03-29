---
date: 2026-03-29
description: Aspose.Page for .NET を使用して XPS ドキュメントに透明オブジェクトを追加し、XPS を PDF にエクスポートする方法を学びましょう。実践的なヒント付きのステップバイステップガイドです。
linktitle: Add Transparent Object to XPS Document
second_title: Aspose.Page .NET API
title: XPS を PDF にエクスポート – Aspose.Page で透明オブジェクトを追加
url: /ja/net/transparency-effects/add-transparent-object-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS を PDF にエクスポート – Aspose.Page で透明オブジェクトを追加

## はじめに

このチュートリアルでは、XPS ドキュメントに透明オブジェクトを追加し、Aspose.Page for .NET を使用して **export XPS to PDF** する方法を学びます。透明性を使用すると、ドキュメントがよりモダンに見え、重要な情報を強調しやすくなります。各ステップを順に解説し、コードの背後にある考え方を説明し、最終的に XPS ファイルを PDF に変換して簡単に共有できるようにする方法を示します。

## クイック回答
- **export XPS to PDF とは何ですか？** XPS ファイルをレイアウト、色、透明性を保持したまま PDF ファイルに変換することです。  
- **透明性を先に追加する理由は？** 透明オブジェクトを使用すると、最終的な PDF で見栄えの良いレイヤードグラフィックを作成できます。  
- **ライセンスは必要ですか？** はい、実稼働環境では有効な Aspose.Page ライセンスが必要です。  
- **.NET Core で実行できますか？** 完全に対応しています – Aspose.Page は .NET Core、.NET 5/6、フル .NET Framework をサポートしています。  
- **他のサンプルはどこで見つかりますか？** 以下の Aspose.Page ドキュメントとコミュニティフォーラムをご確認ください。

## 前提条件

チュートリアルに入る前に、以下の前提条件が整っていることを確認してください。

- Aspose.Page for .NET: Aspose.Page ライブラリがインストールされていることを確認してください。ダウンロードは [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/) から行えます。

## 名前空間のインポート

プロジェクトに必要な名前空間を追加して開始します。

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

それでは、ステップバイステップのガイドに進みましょう。

## ステップ 1: 新しい XPS ドキュメントの作成

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

このコードは Aspose.Page for .NET を使用して新しい XPS ドキュメントを初期化します。

## ステップ 2: 透明性のデモンストレーション

```csharp
// Just to demonstrate transparency
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

これらの行は、後で追加する透明形状の背景として機能する 2 つのグレーのパスを作成します。

## ステップ 3: 閉じた矩形ジオメトリを持つパスの作成

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

ここでは青い矩形を作成します。後で不透明度を変更するため、最終的な PDF では半透明に表示されます。

## ステップ 4: パスと色の操作

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

最初の矩形をクローンし、ページに追加して塗りの色を緑に切り替えます。これにより、既存ジオメトリの再利用がいかに簡単かが示されます。

## ステップ 5: パスのクローンと変形

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

クローンしたパスは 300 ユニット下にシフトされ、赤で塗られ、スタックされたレイヤー効果が得られます。

## ステップ 6: パスの繰り返しと修正

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

`path2` のジオメトリデータを再利用し、右方向に移動して再度青い塗りを適用します。

## ステップ 7: 不透明度の管理

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

`Opacity` プロパティを 0.8 に設定すると、この矩形は 80 % の不透明度となり、要素ごとに透明性を微調整できることが示されます。

## ステップ 8: XPS ドキュメントの保存

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

これで透明オブジェクトがすべて適用された XPS ファイルが保存されました。  

**Export to PDF:** **export XPS to PDF** を行うには、`.pdf` 拡張子を付けて `doc.Save` を再度呼び出すだけです。例: `doc.Save(dataDir + "TransparentDocument.pdf");`。不透明度設定を含む同一の視覚的忠実度が生成された PDF に保持されます。

## 透明性を追加した後に XPS を PDF にエクスポートする理由

- **Universal compatibility:** PDF はプラットフォーム間で広くサポートされているのに対し、XPS はニッチです。  
- **Preserved visual effects:** Aspose.Page は変換中に透明性、グラデーション、マトリックス変換をそのまま保持します。  
- **Easy sharing:** PDF はブラウザ、モバイルデバイス、数多くのサードパーティリーダーでプラグイン不要で開くことができます。

## 一般的な使用例

- **マーケティングブローシャー** – レイヤードグラフィックがプレミアム感を演出します。  
- **技術図面** – レイアウトを乱さずにハイライト部分を強調できます。  
- **レポート生成** – 透かしやロゴを部分的に不透明に重ね合わせたい場合に便利です。

## ヒントと注意点

- **Pro tip:** `Opacity` の値は常に 0 から 1 の間に設定してください。この範囲外の値はクランプされ、予期しない結果になる可能性があります。  
- **Performance tip:** ジオメトリ (`path2.Data`) を再利用すると、類似形状が多数必要な場合のメモリ使用量が削減されます。  
- **Pitfall:** 透明性を追加した直後に PDF に直接保存すれば問題なく動作しますが、後で他のツールで PDF を編集すると、一部の古いビューアでは不透明度が正しく表示されないことがあります。

## 結論

Aspose.Page for .NET を使用して XPS ドキュメントに透明オブジェクトを追加することで、視覚的なプレゼンテーションを柔軟に強化できます。XPS ファイルが希望通りに仕上がったら、1 行のコードで **export XPS to PDF** でき、透明効果を保持したまま広く配布できます。

## FAQ

### Q1: XPS ドキュメントの任意のオブジェクトに透明性を適用できますか？

A1: はい、パス、シェイプ、画像など、さまざまなオブジェクトに透明性を適用できます。

### Q2: 特定の要素の不透明度を調整するには？

A2: Fill または Stroke の `Opacity` プロパティを設定して、特定要素の透明度を調整できます。

### Q3: Aspose.Page は .NET Core と互換性がありますか？

A3: はい、Aspose.Page は .NET Core をサポートしており、クロスプラットフォーム開発が可能です。

### Q4: Aspose.Page を使用して XPS ドキュメントを他の形式にエクスポートできますか？

A4: はい、Aspose.Page は PDF や画像など、さまざまな形式へのエクスポート機能を提供します。

### Q5: 追加のサポートやコミュニティディスカッションはどこで見つかりますか？

A5: 追加のサポートやコミュニティディスカッションは、[Aspose.Page Forum](https://forum.aspose.com/c/page/39) をご覧ください。

### Q6: PDF 変換は透明性設定を保持しますか？

A6: 完全に保持します。Aspose.Page で XPS を PDF にエクスポートすると、すべての不透明度とブレンド設定がそのまま残ります。

### Q7: 複数の XPS ファイルをバッチ処理して PDF に変換できますか？

A7: はい、XPS ファイルのコレクションをループし、各ファイルに対して `doc.Save(...".pdf")` を呼び出すことで、一括変換を自動化できます。

---

**Last Updated:** 2026-03-29  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}