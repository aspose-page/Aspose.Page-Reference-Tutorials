---
date: 2026-03-13
description: Aspose.Page を使用して Java で XPS ドキュメントにグラデーションを追加する方法と、見事な水平効果を実現するためにグラデーションストップをカスタマイズする方法を学びましょう。
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
このステップバイステップガイドへようこそ。Javaを使用してXPSドキュメントに**グラデーションを追加する方法**を説明します。このチュートリアルでは水平グラデーションの追加方法、視覚的な仕上げに重要な理由、そして正確な色制御のための**グラデーションストップのカスタマイズ**方法を学びます。Aspose.Page for Java を使用すれば、XPS（XML Paper Specification）ドキュメントの操作がシンプルになり、低レベルのファイル処理ではなくデザインに集中できます。

## Quick Answers
- **必要なライブラリは？** Aspose.Page for Java  
- **対応するJavaバージョンは？** Java 8以降のランタイムならすべて対応  
- **ライセンスは必要ですか？** 開発目的であれば無料トライアルで利用可能。商用利用には製品ライセンスが必要です。  
- **グラデーションの方向を変更できますか？** はい – 線形ブラシの開始点/終了点を変更するだけです。  
- **複数のグラデーションを追加できますか？** もちろんです – 異なるブラシでパス作成手順を繰り返すだけです。  

## What is a Horizontal Gradient in XPS?
水平グラデーションとは、形状全体を左から右へ色が滑らかに変化するものです。XPSでは、定義された**グラデーションストップ**間を補間する線形グラデーションブラシで表現されます。この視覚効果はバナー、ボタン、背景の塗りつぶしなどで一般的に使用されます。

## Why Use Aspose.Page for Java?
- **フルXPSサポート** – サードパーティツールなしで作成、編集、レンダリングが可能です。  
- **シンプルなAPI** – `XpsDocument`、`XpsPath`、`XpsGradientBrush` などのハイレベルオブジェクトがXMLの複雑さを隠蔽します。  
- **パフォーマンス** – 大規模ドキュメントやバッチ処理に最適化されています。  

## Prerequisites
Before you begin, ensure you have:

1. **Java開発環境** – 最新のJDKを[java.com](https://www.java.com)からインストールしてください。  
2. **Aspose.Page for Java ライブラリ** – [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) からJARをダウンロードしてください。  

## Import Packages
必要なクラスをインポートします。このインポートにより、ドキュメント作成、グラデーション操作、基本的なジオメトリにアクセスできます。

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
Create a fresh `XpsDocument` instance and point to the folder where you want to save the result.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Step 2: Create Horizontal Gradient
Define a list of **gradient stops** that control the color and position of each transition point. The example below builds a vibrant rainbow‑like gradient.

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

## Step 3: Add Path with Gradient
Create a rectangular path, apply a transform if needed, and fill it with the linear gradient brush. The brush uses two points (`(10,0)` to `(228,0)`) to produce a horizontal effect. Because the Y‑coordinates are identical, this brush acts as a **horizontal gradient brush**.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Pro tip:** Re‑using the same `stops` list for multiple paths can improve performance, but remember to `clear()` it before adding new stops.

## Step 4: Save the Document
Persist the XPS file to disk. You can now open it with any XPS viewer to see the horizontal gradient in action.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## How to Apply Multiple Gradients
If you want to **apply multiple gradients** within the same XPS document, simply repeat the “Create Horizontal Gradient” and “Add Path with Gradient” steps for each new shape. Use a fresh list of `XpsGradientStop` objects (or clear the existing list) and assign a new `LinearGradientBrush` with its own start/end points. This approach lets you layer gradients, create complex backgrounds, or highlight different UI elements in a single page.

## Why This Matters – Benefits of the Horizontal Gradient Brush
- **Visual depth:** A horizontal gradient brush adds a subtle three‑dimensional feel without extra images.  
- **File size efficiency:** Gradients are stored as vector definitions, keeping the XPS file lightweight.  
- **Scalability:** Because the gradient is vector‑based, it scales cleanly on high‑resolution displays.  

## Common Issues & Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| グラデーションが単色に見える | グラデーションストップが追加されていない、またはブラシが設定されていない | `path.setFill(...)` が `LinearGradientBrush` を使用していること、`getGradientStops().addAll(stops)` でストップが追加されていることを確認してください。 |
| 色がくすんで見える | アルファ値（最初のパラメータ）が正しくない | 透過が不要な場合は `255` を使用して完全不透明にしてください。 |
| パスのサイズがずれる | 変換行列の値が間違っている | 行列パラメータ（`scaleX, skewY, skewX, scaleY, translateX, translateY`）を調整してください。 |

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

**Last Updated:** 2026-03-13  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}