---
date: 2026-09-14
description: Aspose.Page を使用して postscript gradient java の作成方法を学びましょう。このステップバイステップガイドでは、数行の
  Java コードで PostScript ファイルに垂直グラデーションを追加する方法を示します。
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: Java PostScript に垂直グラデーションを追加
og_description: Aspose.Page を使用して postscript gradient java の作成方法を学びましょう。このステップバイステップガイドでは、数行の
  Java コードで PostScript ファイルに垂直グラデーションを追加する方法を示します。
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: PostScript グラデーション（Java） – 垂直グラデーション
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: PostScript グラデーション（Java） – 垂直グラデーション
url: /ja/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript グラデーション Java の作成 – 垂直グラデーション

## はじめに
Aspose.Page for Java は、プログラムから PostScript および PDF ファイルの作成と操作を可能にするライブラリです。この包括的なチュートリアルでは、ライブラリを使用して **create postscript gradient java** を学びます。垂直グラデーションを追加すると、ドキュメントがより鮮やかでプロフェッショナルに見え、数行のコードで驚くべきビジュアル効果を実現できます。各ステップを順に解説し、各要素が重要な理由を説明し、一般的な落とし穴を回避する実用的なヒントを提供します。このガイドの最後までに、滑らかで目を引く垂直カラー遷移を持つ PostScript ファイルを生成できるようになります。

## クイック回答
- **必要なライブラリは何ですか？** Aspose.Page for Java  
- **色をカスタマイズできますか？** はい、任意の `java.awt.Color` が使用可能です  
- **回転はサポートされていますか？** はい、`AffineTransform` でグラデーションを回転できます  
- **生成される出力形式は何ですか？** 標準的な PostScript (.ps) ファイル  
- **本番環境でライセンスが必要ですか？** はい、商用ライセンスが必要です  

## なぜ PostScript ドキュメントに垂直グラデーションを追加するのか？
垂直グラデーションを追加すると、ページに奥行きが生まれ、視覚的階層が向上し、グラデーションがベクタ形式で定義されるためラスタ画像に比べてファイルサイズが低く抑えられます。この手法は、レポートのヘッダー、技術マニュアル、またはスケーラビリティを犠牲にせずモダンな外観が必要なチラシなどに最適です。

## 前提条件
チュートリアルに入る前に、以下の前提条件が整っていることを確認してください。
- マシンに Java Development Kit (JDK) がインストールされていること。  
- Aspose.Page for Java ライブラリ。以下の [Aspose.Page for Java release page](https://releases.aspose.com/page/java/) からダウンロードできます。

## パッケージのインポート
Java プロジェクトで必要なパッケージをインポートして開始します：
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

それでは、垂直グラデーションを追加するプロセスをステップバイステップで見ていきましょう。

## postscript gradient java の作成方法
Java 環境をロードし、`PsSaveOptions` インスタンスを作成して `Document.save` を呼び出します。これが垂直グラデーション付きの PostScript ファイルを生成するコアシーケンスです。API がカラー補間、座標変換、ページフラッシュを処理してくれるので、矩形とグラデーションパラメータの定義に集中すれば済みます。

### 手順 1: ドキュメントディレクトリの設定
`File` オブジェクトは出力先フォルダーを表します。ストリームを開く前にディレクトリが存在している必要があり、存在しない場合は `IOException` がスローされます。
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 手順 2: PostScript ドキュメント用の出力ストリームを作成
`FileOutputStream` はバイナリの PostScript データを書き込むために使用します。`try‑with‑resources` ブロックを使用することで、例外が発生してもストリームが確実に閉じられます。
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### 手順 3: A4 サイズの保存オプションを作成
`PsSaveOptions` ではページサイズ、DPI、フォント埋め込みの有無を指定できます。サイズを A4 (595 × 842 ポイント) に設定すると、ほとんどの印刷ドキュメントに適合します。
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### 手順 4: 新しい PS ドキュメントを作成
`Document` はメモリ内の単一 PostScript ファイルを表すトップレベルオブジェクトです。すべての描画コマンドはこのオブジェクトに対して発行されます。
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 手順 5: 矩形を作成
`Rectangle2D.Double` はグラデーションで塗りつぶす領域を定義します。矩形の座標はポイント単位 (1 ポイント = 1/72 インチ) で表されます。
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### 手順 6: グラデーションの色と位置（fraction）を設定
`float[]` 配列で各カラー ストップの位置 (0.0 から 1.0) を定義します。`Color` オブジェクトは実際の RGB 値を保持します。任意の `java.awt.Color` を使用できます。
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### 手順 7: グラデーション変換を作成
`AffineTransform` はスケーリングと回転を行います。純粋な垂直グラデーションの場合は Y 軸のスケーリングだけで十分です。必要に応じて後から回転を追加できます。
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### 手順 8: 垂直線形グラデーションペイントを作成
`LinearGradientPaint` は矩形、カラー ストップ、変換を結び付けます。このオブジェクトは後でグラフィックス コンテキストに渡されます。
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### 手順 9: ペイントを設定し矩形を塗りつぶす
`Graphics2D.setPaint` でグラデーションを適用し、`fill` で先に定義した矩形内に描画します。
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### 手順 10: 現在のページを閉じドキュメントを保存
`document.save` を呼び出すと、全 PostScript ストリームが出力ファイルに書き込まれ、すべてのネイティブリソースが解放されます。
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

おめでとうございます！Aspose.Page for Java を使用して、Java の PostScript ドキュメントに垂直グラデーションを正常に追加できました。

## よくある問題と解決策
- **グラデーションが平坦に見える:** `AffineTransform` のスケーリングが矩形の寸法と一致しているか確認してください。  
- **色がくすんで見える:** 正しい `ColorSpaceType` (SRGB) を使用しているか、fraction 配列が 0.0 から 1.0 の順序になっているか確認してください。  
- **ファイルが生成されない:** 出力ディレクトリ (`dataDir`) が存在し、アプリケーションに書き込み権限があるか確認してください。  

## よくある質問
**Q: Aspose.Page for Java を他の Java ライブラリと併用できますか？**  
A: はい、Aspose.Page for Java は Apache Commons や Spring などの他の Java ライブラリとシームレスに連携できるよう設計されています。

**Q: Aspose.Page for Java の無料トライアルはありますか？**  
A: はい、無料トライアルは [free trial download page](https://releases.aspose.com/) から入手できます。

**Q: 追加のドキュメントはどこで見つけられますか？**  
A: 詳細なドキュメントは [Aspose.Page Java API reference](https://reference.aspose.com/page/java/) にあります。

**Q: Aspose.Page for Java はどこで購入できますか？**  
A: 購入は [Aspose.Page purchase page](https://purchase.aspose.com/buy) から行えます。

**Q: Aspose.Page に関するフォーラムはありますか？**  
A: はい、コミュニティフォーラムは [Aspose.Page community forum](https://forum.aspose.com/c/page/39) で参加できます。

## 追加のよくある質問

**Q: 他のグラデーション方向（水平、対角線）も作成できますか？**  
A: もちろんです。`LinearGradientPaint` の開始点と終了点を調整し、`AffineTransform` の回転角度を変更すれば実現できます。

**Q: PDF 出力でも同様に機能しますか？**  
A: 同じグラデーションロジックを `PsSaveOptions` の代わりに `PdfSaveOptions` を使用すれば PDF にも適用できます。

**Q: グラデーションのサイズを動的に変更するには？**  
A: 実行時に矩形の寸法を計算し、その値を `Rectangle2D` と `AffineTransform` のコンストラクタに渡すことで動的にサイズを変更できます。

---

**最終更新日:** 2026-09-14  
**テスト環境:** Aspose.Page for Java 24.11 (latest)  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Page for Java を使用した PostScript の放射状グラデーションの作成](/page/java/postscript-gradient-addition/)
- [Aspose.Page Java API を使用した PostScript から PDF への変換方法](/page/java/postscript-conversion/to-pdf/)
- [Aspose.Page 透過チュートリアル – Java PostScript に透過を追加](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}