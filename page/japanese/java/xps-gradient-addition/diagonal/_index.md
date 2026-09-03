---
date: 2026-05-25
description: Aspose.Page を使用して Java で XPS ドキュメントに gradient を追加する方法を学びます。このステップバイステップ
  ガイドでは、対角 gradient の追加方法、linear gradient brushes の適用方法、そしてプロフェッショナルな XPS ファイルの作成方法を示します。
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: Java XPS で対角 Gradient を追加
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: Gradient の追加方法：Java XPS の対角 Gradient
url: /ja/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPSでのグラデーションの追加方法：対角線グラデーション

## はじめに
現代のJava開発において、XPSドキュメントに **グラデーションの追加方法** をマスターすることで、レポートに洗練された目を引く外観を与えることができます。このチュートリアルでは、Aspose.Page for Java を使用して、ゼロからXPSファイルを作成し、対角線グラデーションを追加し、結果を保存する手順を解説します。グラデーションが重要な理由を理解し、正確なAPI呼び出しを確認し、一般的な落とし穴を回避するための実用的なヒントを得られます。

## クイック回答
- **主要なライブラリは何ですか？** Aspose.Page for Java  
- **どのメソッドがグラデーションを追加しますか？** `createLinearGradientBrush` with gradient stops  
- **ライセンスは必要ですか？** 開発にはトライアルで動作しますが、製品版には商用ライセンスが必要です  
- **実装にどれくらい時間がかかりますか？** 基本的な対角線グラデーションで約10〜15分です  
- **他のJavaフレームワークでも使用できますか？** はい、APIはフレームワークに依存しません  

## XPSドキュメントにおける対角線グラデーションとは何ですか？
対角線グラデーションは、形状の一つの角から反対側の角へと滑らかに色が変化するもので、斜めの視覚効果を作り出します。XPSでは、この効果は、対角線上の色と相対位置を指定する順序付けられたグラデーションストップを含む線形グラデーションブラシによって定義されます。

## Aspose.Pageで対角線グラデーションを追加する理由は？
Aspose.Pageは、20以上のXPSビューアでグラデーションの**100 %レンダリング忠実度**を提供し、テキスト、画像、ベクター形状など**30以上のXPS機能**をサポートします。APIは複雑なXPSマークアップを抽象化し、デザインに集中できると同時に、同一ファイルがWindows、macOS、Linuxプラットフォームで同一に表示されることを保証します。

## 前提条件
- 基本的なJavaプログラミングの知識。  
- マシンにJDKがインストールされていること。  
- Aspose.Page for Java ライブラリ – ダウンロードは **[here](https://releases.aspose.com/page/java/)**。  
- IntelliJ IDEAやEclipseなどのIDE。

## パッケージのインポート
まず、必要なクラスをインポートします。これらのインポートにより、ジオメトリ、グラデーション処理、XPSドキュメント作成にアクセスできます。

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## ステップ 1: プロジェクトのセットアップ
好みのIDEで新しいJavaプロジェクトを作成し、Aspose.PageのJARファイルをプロジェクトのビルドパスに追加します。

## ステップ 2: ドキュメントディレクトリの定義
生成されたXPSファイルの保存先を指定します。

```java
String dataDir = "Your Document Directory";
```

## ステップ 3: XPSドキュメントの作成
`XpsDocument` は、メモリ内でXPSファイルを表すコアオブジェクトです。インスタンス化することで、ページ、シェイプ、ブラシを追加できるキャンバスが得られます。

```java
XpsDocument doc = new XpsDocument();
```

## ステップ 4: 対角線グラデーションパスの追加
グラデーションを適用する矩形パスを作成します。パスジオメトリはシンプルな move‑line‑close コマンドを使用します。  
XpsPath は、矩形やカスタムジオメトリなど、XPSドキュメント内のベクタ形状を定義します。

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## ステップ 5: 線形グラデーションストップの定義
色とその位置を設定します。各ストップは、特定の色が現れるグラデーション上のポイントを定義します。  
XpsGradientStop は、グラデーション内の単一のカラー ストップを表し、色とオフセットを指定します。

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## ステップ 6: パスに線形グラデーションを適用
`XpsLinearGradientBrush` は、線形カラー遷移用の Aspose.Page のブラシタイプです。グラデーション方向を定義する2つのポイントと、そのラインに沿った色を決定するグラデーションストップのコレクションを受け取ります。

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## ステップ 7: ドキュメントの保存
XPSファイルをディスクに永続化します。ファイルには、定義した対角線グラデーションで塗りつぶされた矩形が含まれます。

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Java XPSでグラデーションを追加する方法は？
XpsDocument をロードし、開始点 `(0,0)` と終了点 `(width,height)` を持つ `XpsLinearGradientBrush` を作成し、グラデーションストップを付加し、ブラシをシェイプの `Fill` に割り当て、最後に `save` を呼び出します。この簡潔なフローにより、少数のAPI呼び出しだけで対角線グラデーションを埋め込むことができ、コードをクリーンで保守しやすく保ちます。

## 一般的な落とし穴とヒント
- **グラデーション方向** – ブラシの開始点と終了点が目的の対角線を反映していることを確認してください。入れ替えるとグラデーションが反転します。  
- **カラー精度** – Aspose は ARGB を使用します。透過が必要な場合はアルファチャンネルを含めてください。  
- **ファイルパス** – 常に絶対パスを使用するか、相対パスが既存の書き込み可能なディレクトリを指していることを確認してください。

## 追加FAQ

**Q: 既存のXPSシェイプに **グラデーションの追加方法** をどうやって行いますか？**  
A: `XpsLinearGradientBrush` を作成し、グラデーションストップを定義し、Step 6 に示すようにシェイプの `Fill` プロパティに割り当てます。

**Q: **線形グラデーションを適用** が実際に内部で何を行うか？**  
A: 開始点/終了点とグラデーションストップのコレクションを参照するブラシ定義をXPSパッケージ内に生成し、ビューアが滑らかな色遷移としてレンダリングします。

**Q: 他のXPS機能に対して **Asposeの使い方** をすぐに知る方法はありますか？**  
A: はい、Aspose.Page API には画像、テキスト、カスタムシェイプを追加するメソッドが含まれています。`XpsDocument` クラスを調べれば追加のヘルパーが見つかります。

**Q: 非矩形シェイプに **グラデーションパスの追加** は可能ですか？**  
A: もちろんです。`createPathGeometry` を使用して任意のジオメトリを定義し、その `Fill` にグラデーションブラシを設定します。

**Q: グラデーションはファイルサイズに大きく影響しますか？**  
A: ほとんど影響はありません。グラデーション定義はXPSパッケージ内の軽量なXMLエントリです。

---

**最終更新日:** 2026-05-25  
**テスト環境:** Aspose.Page for Java 24.11  
**作者:** Aspose

## 関連チュートリアル

- [Aspose Page XPS グラデーション追加](/page/java/xps-gradient-addition/)
- [Java XPS テキスト追加 - Aspose.Page チュートリアル](/page/java/xps-text-manipulation/add-text/)
- [Java XPS ドキュメントへの画像追加方法 – Aspose.Page のシンプルガイド](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}