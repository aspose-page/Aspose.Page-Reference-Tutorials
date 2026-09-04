---
date: 2026-09-04
description: Aspose.Page for Java の Linear Gradient Paint Java を使用して、PostScript ファイル内で水平グラデーション
  java を作成する方法を学びます。ステップバイステップのコード、一般的な落とし穴、FAQ を紹介します。
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: Aspose を使用して PostScript で水平グラデーション java を作成
og_description: Linear Gradient Paint Java を使用して PostScript で水平グラデーション java を作成します。この
  Aspose.Page チュートリアルでは、正確な手順、前提条件、トラブルシューティングのヒントを 15 分以内で紹介します。
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: Aspose を使用して PostScript で水平グラデーション java を作成
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: Aspose を使用して PostScript で水平グラデーション java を作成
url: /ja/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScriptでLinear Gradient Paintを使用して水平グラデーションを追加する方法

## はじめに
この包括的なチュートリアルでは、Aspose.Page for Java に同梱されている **Linear Gradient Paint Java** クラスを使用して、PostScript ドキュメント内に **水平グラデーション Java を作成する方法** を学びます。プロジェクトの設定から、形状とテキストの両方にグラデーションを描画するまでのすべての手順を順を追って説明するので、数分で洗練された印刷対応のグラフィックを作成できます。レポートエンジン、デザイン自動化ツール、またはカスタムプリンタドライバを構築する場合でも、本ガイドは必要なコードを正確に提供します。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Page for Java（Linear Gradient Paint Java を含む）。  
- **実装にどれくらい時間がかかりますか？** 基本的な水平グラデーションで約10〜15分です。  
- **ライセンスは必要ですか？** 本番環境で使用するには、一時ライセンスまたはフルライセンスが必要です。  
- **対応する JDK バージョンは？** Java 8 以降。  
- **形状とテキストの両方にグラデーションを使用できますか？** はい。同じ `LinearGradientPaint` インスタンスで形状を塗りつぶし、テキストのストロークや塗りにも適用できます。

## 水平グラデーションとは何か、なぜ使用するのか
水平グラデーションは、オブジェクトの左端から右端へ色をブレンドし、滑らかな遷移で奥行きと視覚的な興味を加えます。モダンな UI コンポーネント、強調見出し、または PDF や PostScript レポートの微妙な背景シェーディングに最適です。**Linear Gradient Paint Java** を使用すると、開始色と終了色、透明度、スケーリングを正確に制御でき、任意のデバイスやプリンタでも鮮明な結果が得られます。

## 前提条件
コードに取り掛かる前に、以下が揃っていることを確認してください。

- Java Development Kit（JDK）がマシンにインストールされていること。  
- Aspose.Page for Java ライブラリ。以下の [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) からダウンロードできます。

## パッケージのインポート
まず、Java プロジェクトで必要なパッケージをインポートします。これらのインポートにより、グラフィックのプリミティブ、グラデーション処理、Aspose.Page API にアクセスできます。

`PsDocument` クラスは、グラフィックを描画できる PostScript ドキュメントを表します。  

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

## ステップ 1: 四角形を作成する
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

## ステップ 2: 水平線形グラデーションペイントを作成する
`LinearGradientPaint` は線形カラー遷移を定義するコアクラスです。  
`LinearGradientPaint` クラスは、直線に沿ってグラデーションを描画するペイントオブジェクトを表します。開始点と終了点、カラー ストップ、そしてオプションで `AffineTransform` を指定して形状に合わせてスケーリングできます。

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

## ステップ 3: 四角形を塗りつぶす
先ほど定義したグラデーションで矩形を塗りつぶします。

```java
// Fill the rectangle
document.fill(rectangle);
```

## ステップ 4: テキストにグラデーションを塗りつぶす
同じグラデーションをテキストに適用して、印象的なビジュアル効果を作り出すこともできます。

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## ステップ 5: テキストにグラデーションでストロークを付ける
最後に、グラデーションをストロークカラーとしてテキストに輪郭を付けます。

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## 一般的な問題と解決策
| 問題 | 発生理由 | 対策 |
|-------|----------------|-----|
| グラデーションが伸びて見える | `AffineTransform` のスケーリングが正しくない | 変換の幅と高さが矩形のサイズ（例では 200 × 100）と一致していることを確認してください。 |
| 色が薄く見える | アルファ値が低すぎる | `new Color(r,g,b,alpha)` の 4 番目の値であるアルファ成分を増やしてください。 |
| テキストが表示されない | テキスト描画前にペイントが設定されていない | `fillAndStrokeText` や `outlineText` を呼び出す前に `document.setPaint(paint)` を **呼び出してください**。 |

## よくある質問
**Q:** Aspose.Page for Java を商用プロジェクトで使用できますか？  
**A:** はい、Aspose.Page for Java は商用プロジェクトで使用できます。ライセンスの詳細は [Aspose.Purchase](https://purchase.aspose.com/buy) ページをご覧ください。

**Q:** 無料トライアルは利用できますか？  
**A:** はい、[Aspose.Page for Java free trial](https://releases.aspose.com/) ページから無料トライアルにアクセスできます。

**Q:** 追加のドキュメントやサポートはどこで見つけられますか？  
**A:** 包括的なリソースは [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) をご覧ください。コミュニティのサポートは [Aspose.Page forum](https://forum.aspose.com/c/page/39) をチェックしてください。

**Q:** 一時ライセンスはどのように取得できますか？  
**A:** [Aspose.Purchase temporary license page](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

**Q:** Aspose.Page for Java のシステム要件は何ですか？  
**A:** 詳細なシステム要件は [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) を参照してください。

**最終更新日:** 2026-09-04  
**テスト環境:** Aspose.Page for Java 24.11  
**作者:** Aspose

## 関連チュートリアル

- [Java で PostScript グラデーションを作成 – 垂直グラデーションを追加](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page Java を使用して Java PostScript に対角グラデーションを追加する方法](/page/java/postscript-gradient-addition/diagonal/)
- [Java で PostScript グラデーションを作成 – 放射状グラデーション](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}