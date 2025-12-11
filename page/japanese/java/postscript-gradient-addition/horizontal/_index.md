---
date: 2025-12-07
description: Aspose.Page for Java を使用した Linear Gradient Paint Java による Java PostScript
  で水平グラデーションを追加する方法を学びましょう。
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: Java PostScriptでLinear Gradient Paintを使用してグラデーションを追加する
url: /ja/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Linear Gradient Paint Java を使用した Java PostScript へのグラデーション追加

## はじめに
この包括的なチュートリアルでは、**Linear Gradient Paint Java** を活用して PostScript ドキュメントに美しい水平グラデーションを作成する方法を学びます。Aspose.Page for Java を使用すれば、PostScript、PDF、その他のベクターフォーマットを簡単に扱うことができ、`LinearGradientPaint` クラスにより色の遷移を細かく制御できます。本ガイドの最後までに、シェイプ **および** テキストにグラデーションを描画し、ドキュメントにプロフェッショナルで目を引く外観を付与できるようになります。

## クイック回答
- **必要なライブラリは？** Aspose.Page for Java（Linear Gradient Paint Java をサポート）。  
- **実装にかかる時間は？** 基本的なグラデーションで約 10〜15 分。  
- **ライセンスは必要ですか？** 本番環境で使用する場合は、一時ライセンスまたはフルライセンスが必要です。  
- **対応 JDK バージョンは？** Java 8 以降。  
- **シェイプとテキストの両方にグラデーションを使用できますか？** はい、同じグラデーションでシェイプの塗りつぶしやテキストの塗りつぶし・ストロークが可能です。

## 前提条件
コードに取り掛かる前に、以下が揃っていることを確認してください。

- マシンにインストールされた Java Development Kit (JDK)。  
- Aspose.Page for Java ライブラリ。ダウンロードは [Aspose.Page Java ドキュメント](https://reference.aspose.com/page/java/) から行えます。

## パッケージのインポート
Java プロジェクトで必要なパッケージをインポートします。これらのインポートにより、グラフィックプリミティブ、グラデーション処理、Aspose.Page API へのアクセスが可能になります。

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

## 手順 1: 長方形の作成
出力ストリーム、ドキュメント、そしてグラデーションを配置する長方形を設定します。

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

## 手順 2: 水平リニアグラデーションペイントの作成
ここでは、水平の色遷移を定義する **Linear Gradient Paint Java** オブジェクトを構築します。`AffineTransform` が長方形の幅と高さに合わせてグラデーションをスケーリングします。

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

## 手順 3: 長方形の塗りつぶし
先ほど定義したグラデーションで長方形を塗りつぶします。

```java
// Fill the rectangle
document.fill(rectangle);
```

## 手順 4: テキストへのグラデーション塗りつぶし
同じグラデーションをテキストに適用し、印象的なビジュアル効果を作り出すこともできます。

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## 手順 5: テキストのストロークにグラデーションを使用
最後に、グラデーションをストロークカラーとしてテキストの輪郭を描画します。

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## よくある問題と解決策
| 問題 | 発生理由 | 対策 |
|------|----------|------|
| グラデーションが伸びて見える | `AffineTransform` のスケーリングが不適切 | 変換の幅と高さが長方形のサイズ（例: 200 × 100）と一致していることを確認 |
| 色が薄く見える | アルファ値が低すぎる | `new Color(r,g,b,alpha)` の alpha 成分を増やす |
| テキストが表示されない | テキスト描画前に Paint が設定されていない | `document.setPaint(paint)` を **fillAndStrokeText** や **outlineText** の呼び出しより前に実行 |

## FAQ
### Aspose.Page for Java を商用プロジェクトで使用できますか？
はい、商用プロジェクトで使用可能です。ライセンスの詳細は [Aspose.Purchase](https://purchase.aspose.com/buy) をご覧ください。

### 無料トライアルはありますか？
はい、Aspose.Page for Java の無料トライアルは [こちら](https://releases.aspose.com/) から入手できます。

### 追加のドキュメントやサポートはどこで入手できますか？
包括的なリソースは [Aspose.Page Java ドキュメント](https://reference.aspose.com/page/java/) にあります。コミュニティサポートは [Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) をご利用ください。

### 一時ライセンスはどのように取得できますか？
一時ライセンスは [Aspose.Purchase](https://purchase.aspose.com/temporary-license/) から取得できます。

### Aspose.Page for Java のシステム要件は何ですか？
詳細なシステム要件は [ドキュメント](https://reference.aspose.com/page/java/) を参照してください。

---

**最終更新日:** 2025-12-07  
**テスト環境:** Aspose.Page for Java 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}