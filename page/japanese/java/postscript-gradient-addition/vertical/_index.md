---
date: 2025-12-09
description: Aspose.Page を使用して Java で PostScript のグラデーションを作成する方法を学びましょう。このステップバイステップガイドでは、PostScript
  ドキュメントに垂直グラデーションを簡単に追加する方法を示します。
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: JavaでPostScriptグラデーションを作成 – 垂直グラデーションを追加
url: /ja/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# JavaでPostScriptグラデーションを作成 – 垂直グラデーションを追加

## Introduction
この包括的なチュートリアルでは、Aspose.Page for Java を使用して **JavaでPostScriptグラデーションを作成** する方法を学びます。垂直グラデーションを追加することで、ドキュメントがより鮮やかでプロフェッショナルに見えるようになり、数行のコードで驚くべきビジュアル効果を実現できます。各ステップを順に解説し、なぜその処理が重要なのかを説明し、一般的な落とし穴を回避する実用的なヒントも提供します。  
本ガイドでは **postscript gradient java をステップバイステップで作成** します。

## Quick Answers
- **必要なライブラリは？** Aspose.Page for Java  
- **色はカスタマイズできますか？** はい、任意の `java.awt.Color` が使用可能です  
- **回転はサポートされていますか？** はい、`AffineTransform` でグラデーションを回転できます  
- **生成される出力形式は？** 標準的な PostScript (.ps) ファイル  
- **本番環境でライセンスは必要ですか？** はい、商用ライセンスが必要です  

## Prerequisites
チュートリアルに入る前に、以下の前提条件が整っていることを確認してください：
- マシンにインストールされた Java Development Kit (JDK)。  
- Aspose.Page for Java ライブラリ。ダウンロードは [here](https://releases.aspose.com/page/java/) から。

## Import Packages
Java プロジェクトで必要なパッケージをインポートします：
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

それでは、Java の PostScript に垂直グラデーションを追加するプロセスを複数のステップに分けて解説します。

## How to create PostScript gradient Java
以下は Aspose.Page API を使用して **JavaでPostScriptグラデーションを作成** する手順を示したステップバイステップガイドです。

### Step 1: Set up Your Document Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Step 2: Create Output Stream for PostScript Document
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Step 3: Create Save Options with A4 Size
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Step 4: Create a New PS Document
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Step 5: Create a Rectangle
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Step 6: Set Up Colors and Fractions for the Gradient
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Step 7: Create the Gradient Transform
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Step 8: Create Vertical Linear Gradient Paint
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Step 9: Set Paint and Fill the Rectangle
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Step 10: Close Current Page and Save the Document
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

おめでとうございます！Aspose.Page for Java を使用して、Java の PostScript ドキュメントに垂直グラデーションを正常に追加できました。

## Why use vertical gradients in PostScript?
垂直グラデーションは、ファイルサイズを大幅に増やすことなくページに奥行きと視覚的な興味を与えます。特に次のようなシーンで有用です：
- レポートのヘッダーやフッター  
- チャートや図の背景塗りつぶし  
- 技術文書のセクション強調  

## Common Issues and Solutions
- **グラデーションが平坦に見える:** `AffineTransform` のスケーリングが矩形の寸法と一致しているか確認してください。  
- **色が薄く見える:** 正しい `ColorSpaceType` (SRGB) を使用し、fractions 配列が 0.0 から 1.0 の順序になっているか確認してください。  
- **ファイルが生成されない:** 出力ディレクトリ (`dataDir`) が存在し、アプリケーションに書き込み権限があるか確認してください。  

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other Java libraries?
はい、Aspose.Page for Java は他の Java ライブラリとシームレスに連携できるよう設計されています。

### Is there a free trial available for Aspose.Page for Java?
はい、無料トライアルは [here](https://releases.aspose.com/) から取得できます。

### Where can I find additional documentation?
詳細なドキュメントは [here](https://reference.aspose.com/page/java/) にあります。

### How can I purchase Aspose.Page for Java?
購入は [here](https://purchase.aspose.com/buy) から可能です。

### Is there a forum for Aspose.Page discussions?
はい、コミュニティフォーラムは [here](https://forum.aspose.com/c/page/39) で参加できます。

## Additional Frequently Asked Questions

**Q: Can I create other gradient directions (horizontal, diagonal)?**  
A: Absolutely. Adjust the start and end points in `LinearGradientPaint` and modify the rotation angle in the `AffineTransform`.

**Q: Does this work with PDF output as well?**  
A: The same gradient logic can be applied when saving to PDF by using `PdfSaveOptions` instead of `PsSaveOptions`.

**Q: How do I change the gradient size dynamically?**  
A: Calculate the rectangle dimensions at runtime and pass those values to both the `Rectangle2D` and the `AffineTransform` constructor.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Page for Java 24.11 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}