---
date: 2025-12-25
description: Aspose.Page を使用して Java で XPS ドキュメントにグラデーションを追加する方法と、見事な水平効果を得るためにグラデーションストップをカスタマイズする方法を学びましょう。
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Java XPSでグラデーションを追加する方法 – 水平グラデーション
url: /ja/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPSでグラデーションを追加する方法 – 水平グラデーション

## Introduction
このステップバイステップガイドへようこそ。**グラデーションを XPS ドキュメントに追加する方法**を Java で解説します。本チュートリアルでは水平グラデーションの追加方法、その視覚的な効果の重要性、そして**グラデーション ストップのカスタマイズ**による正確な色制御について学びます。Aspose.Page for Java を使用すれば、XPS (XML Paper Specification) ドキュメントの操作がシンプルになり、低レベルのファイル処理に煩わされることなくデザインに集中できます。

## Quick Answers
- **必要なライブラリは？** Aspose.Page for Java  
- **対応 Java バージョンは？** Java 8 以上のランタイム  
- **ライセンスは必要？** 開発目的であれば無料トライアルで可。商用利用には製品ライセンスが必要です。  
- **グラデーションの方向は変更できる？** はい – リニア ブラシの開始点/終了点を変更するだけです。  
- **複数のグラデーションを追加できる？** もちろん – 異なるブラシでパス作成手順を繰り返すだけです。  

## What is a Horizontal Gradient in XPS?
水平グラデーションとは、形状全体を左から右へ滑らかに色が変化する効果です。XPS では、定義された **グラデーション ストップ** 間を補間するリニア グラデーション ブラシで表現されます。この視覚効果はバナー、ボタン、背景塗りつぶしなどで頻繁に使用されます。

## Why Use Aspose.Page for Java?
- **フル XPS サポート** – サードパーティーツール不要で作成、編集、レンダリングが可能。  
- **シンプル API** – `XpsDocument`、`XpsPath`、`XpsGradientBrush` などの高レベルオブジェクトが XML の複雑さを隠蔽します。  
- **パフォーマンス** – 大規模ドキュメントやバッチ処理に最適化されています。  

## Prerequisites
開始する前に以下を確認してください。

1. **Java 開発環境** – 最新の JDK を [java.com](https://www.java.com) からインストール。  
2. **Aspose.Page for Java ライブラリ** – [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) から JAR をダウンロード。  

## Import Packages
必要なクラスをインポートします。このインポートにより、ドキュメント作成、グラデーション操作、基本ジオメトリへのアクセスが可能になります。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Step 1: Initialize the XPS Document
新しい `XpsDocument` インスタンスを作成し、結果を保存したいフォルダーを指定します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Step 2: Create Horizontal Gradient
**グラデーション ストップ** のリストを定義します。これにより各遷移点の色と位置が制御されます。以下の例は鮮やかな虹色のグラデーションを構築します。

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### How to customize gradient stops
- **Color** – 任意の ARGB 値は `doc.createColor(alpha, red, green, blue)` で設定します。  
- **Position** – 2 番目の引数（`0` から `1` の `float`）がグラデーションライン上の停止位置を決めます。値を調整して色を左または右にシフトできます。

## Step 3: Add Path with Gradient
矩形パスを作成し、必要に応じて変形を適用し、リニア グラデーション ブラシで塗りつぶします。ブラシは `(10,0)` から `(228,0)` の 2 点を使用し、水平効果を実現します。

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Pro tip:** 複数のパスで同じ `stops` リストを再利用するとパフォーマンスが向上しますが、新しい停止を追加する前に必ず `clear()` してください。

## Step 4: Save the Document
XPS ファイルをディスクに保存します。保存後は任意の XPS ビューアで開き、水平グラデーションが正しく表示されることを確認できます。

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Common Issues & Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| Gradient appears solid | No gradient stops added or brush not set | Ensure `path.setFill(...)` uses a `LinearGradientBrush` and that stops are added via `getGradientStops().addAll(stops)`. |
| Colors look muted | Incorrect alpha value (first parameter) | Use `255` for fully opaque colors unless transparency is desired. |
| Path size is off | Transform matrix values are wrong | Adjust the matrix parameters (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Frequently Asked Questions

**Q: Can I apply multiple gradients in a single XPS document?**  
A: Yes, you can add multiple paths, each with its own gradient brush, to create complex layered designs.

**Q: Is Aspose.Page compatible with the latest Java versions?**  
A: Aspose.Page for Java is regularly updated and works with Java 8 and newer releases.

**Q: Are there other gradient types available in Aspose.Page?**  
A: Besides linear gradients, Aspose.Page also supports radial gradients for circular color transitions.

**Q: Can I customize the colors and positions of gradient stops?**  
A: Absolutely! You have full control over each stop’s ARGB color and its relative position (0‑1 range).

**Q: Is there a community forum for Aspose.Page where I can seek help?**  
A: Yes, you can visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to connect with the community and get assistance.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}