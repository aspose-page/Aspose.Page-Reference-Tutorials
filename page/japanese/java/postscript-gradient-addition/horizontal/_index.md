---
date: 2026-02-13
description: Aspose.Page for Java を使用して、Java の PostScript に Linear Gradient Paint
  Java でグラデーションを追加する方法を学びましょう。
linktitle: How to Add Gradient in Java PostScript with Linear Gradient Paint
second_title: Aspose.Page Java API
title: Java PostScriptで線形グラデーションペイントを使用してグラデーションを追加する方法
url: /ja/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript で Linear Gradient Paint を使用してグラデーションを追加する方法

## Introduction
この包括的なチュートリアルでは、Java を使って PostScript ドキュメントに **グラデーションを追加する方法** を学びます。**Linear Gradient Paint Java** クラスを活用して、美しい水平グラデーションを作成する手順を解説します。Aspose.Page for Java を使用すれば、図形 **および** テキストの両方にグラデーションを描画でき、文書に洗練された目を引く外観を与えることができます。

## Quick Answers
- **必要なライブラリは？** Aspose.Page for Java（Linear Gradient Paint Java をサポート）。  
- **実装にかかる時間は？** 基本的なグラデーションで約 10〜15 分。  
- **ライセンスは必要ですか？** 本番環境で使用する場合は、一時ライセンスまたはフルライセンスが必要です。  
- **対応 JDK バージョンは？** Java 8 以降。  
- **図形とテキストの両方にグラデーションを使用できますか？** はい、同じグラデーションで図形を塗りつぶしたり、テキストを塗りつぶし・ストロークしたりできます。

## What is a Horizontal Gradient and Why Use It?
水平グラデーションは、形状やテキストの左側から右側へ滑らかに色を変化させます。モダンな UI 要素や強調見出し、レポートの微妙な背景効果を作成するのに最適です。**Linear Gradient Paint Java** を使用すると、開始色・終了色・不透明度・スケーリングを正確に定義でき、どのデバイスでも鮮明に表示されます。

## Prerequisites
コードに取り掛かる前に、以下を用意してください。

- Java Development Kit (JDK) がインストールされていること。  
- Aspose.Page for Java ライブラリ。ダウンロードは [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) から。

## Import Packages
Java プロジェクトで必要なパッケージをインポートします。これらのインポートにより、グラフィックプリミティブ、グラデーション処理、Aspose.Page API が利用可能になります。

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Create a Rectangle
まず、出力ストリーム、ドキュメント、およびグラデーションを配置する矩形を設定します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Step 2: Create Horizontal Linear Gradient Paint
ここでは、水平カラー遷移を定義する **Linear Gradient Paint Java** オブジェクトを作成します。`AffineTransform` が矩形の幅と高さに合わせてグラデーションをスケーリングします。

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Step 3: Fill the Rectangle
先ほど定義したグラデーションで矩形を塗りつぶします。

```java
// Fill the rectangle
document.fill(rectangle);
```

## Step 4: Fill a Text with the Gradient
同じグラデーションをテキストに適用し、印象的なビジュアル効果を作り出すこともできます。

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Step 5: Stroke a Text with the Gradient
最後に、グラデーションをストロークカラーとしてテキストの輪郭を描画します。

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Common Issues and Solutions
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| グラデーションが伸びて見える | `AffineTransform` のスケーリングが不正確 | 変換の幅と高さが矩形の寸法（例: 200 × 100）と一致していることを確認してください。 |
| 色が薄く見える | アルファ値が低すぎる | `new Color(r,g,b,alpha)` の alpha 成分を増やしてください。 |
| テキストが表示されない | テキスト描画前に Paint が設定されていない | `document.setPaint(paint)` を **fillAndStrokeText** または **outlineText** を呼び出す前に実行してください。 |

## Frequently Asked Questions
**Q:** Aspose.Page for Java を商用プロジェクトで使用できますか？  
**A:** はい、Aspose.Page for Java は商用プロジェクトで使用可能です。ライセンスの詳細は [Aspose.Purchase](https://purchase.aspose.com/buy) をご覧ください。

**Q:** 無料トライアルはありますか？  
**A:** はい、Aspose.Page for Java の無料トライアルは [here](https://releases.aspose.com/) から入手できます。

**Q:** 追加のドキュメントやサポートはどこで入手できますか？  
**A:** 包括的なリソースは [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) にあります。コミュニティサポートは [Aspose.Page forum](https://forum.aspose.com/c/page/39) をご利用ください。

**Q:** 一時ライセンスはどのように取得できますか？  
**A:** 一時ライセンスは [Aspose.Purchase](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q:** Aspose.Page for Java のシステム要件は何ですか？  
**A:** 詳細なシステム要件は [documentation](https://reference.aspose.com/page/java/) を参照してください。

---

**最終更新日:** 2026-02-13  
**テスト環境:** Aspose.Page for Java 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}