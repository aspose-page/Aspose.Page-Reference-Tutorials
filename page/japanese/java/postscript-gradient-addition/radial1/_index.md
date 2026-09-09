---
date: 2026-09-09
description: Aspose.Page を使用して Java PostScript で放射状グラデーションを作成する方法を学びます。このステップバイステップガイドでは、カラー
  ストップ グラデーションの追加、半径の設定、そして PS ファイルの迅速な生成方法を示します。
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Java で放射状グラデーションをマスターする
og_description: Aspose.Page を使用して Java PostScript で放射状グラデーションを作成する方法を学びます。このガイドでは、カラー
  ストップ グラデーションの追加、半径の設定、そして数分で PS ファイルを生成する方法を解説します。
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Java PostScript で放射状グラデーションを作成する方法
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Java PostScript で放射状グラデーションを作成する方法
url: /ja/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript で Aspose.Page を使用して放射状グラデーションを作成する方法

## はじめに
PostScript ファイル内で **放射状グラデーションを作成** する必要がある場合、ここが正しい場所です。このチュートリアルでは、**Aspose.Page for Java** を使用して滑らかな放射状グラデーションを含む PostScript ドキュメントを生成するために必要なすべての手順を順に解説します。最後まで読むと、API の理解が深まり、完全に実行可能なサンプルを確認でき、任意のデザインシナリオに合わせて色、位置、半径を調整する方法が分かります。

## クイック回答
- **PostScript で放射状グラデーションを作成するライブラリは何ですか？** Aspose.Page for Java.  
- **実装にどれくらい時間がかかりますか？** 基本的な例で約 10‑15 分です。  
- **コードを実行するのにライセンスは必要ですか？** 開発には無料トライアルで動作しますが、製品版には商用ライセンスが必要です。  
- **サポートされている Java バージョンはどれですか？** Java 8 以上です。  
- **グラデーションの形状を変更できますか？** はい – `RadialGradientPaint` コンストラクタで半径と中心点を調整します。

## Java で放射状グラデーションを作成する方法
Java プロジェクトをロードし、必要なクラスをインポートして、以下のステップバイステップガイドに従ってください。核心となる答えは、色ストップを指定して `RadialGradientPaint` をインスタンス化し、それを `PsDocument` 上に描画した矩形に適用することです。この 2 つのオブジェクトのアプローチにより、低レベルの PostScript コマンドはすべて自動で処理されます。

## 放射状グラデーションとは？
`RadialGradientPaint` は、中心点から外側へ円形の色変化を定義する Java AWT クラスです。複数のカラーストップを滑らかにブレンドし、スポットライトや柔らかい背景、あるいは色が焦点から放射するあらゆる効果に最適です。

## 放射状グラデーションに Aspose.Page を使用する理由
Aspose.Page は、低レベルの PS 構文の重い処理を自動で行いながら、PostScript 出力を完全にプログラムで制御できます。**50 以上の入力および出力フォーマット**をサポートし、ファイル全体をメモリに読み込むことなく数百ページのドキュメントをレンダリングでき、Java 8+ をサポートする任意の OS 上で動作します。このような定量的な機能により、エンタープライズ向けグラフィック生成に信頼できる選択肢となります。

## 前提条件
- **Java Development Kit (JDK) 8+** – `java -version` で確認してください。  
- **Aspose.Page for Java** – 公式の [Aspose.Page download page](https://releases.aspose.com/page/java/) から最新の JAR をダウンロードしてください。  
- **お好みの IDE** – Eclipse、IntelliJ IDEA、または Java 拡張機能付き VS Code。  
- **書き込み可能なフォルダー** – 生成された `.ps` ファイルを保存する場所。

## パッケージのインポート
まず、必要なクラスをインポートします。`java.awt` パッケージはグラデーションペイントオブジェクトを提供し、`com.aspose.eps` には PostScript ドキュメント処理クラスが含まれています。

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ステップバイステップガイド

### 手順 1: 矩形を作成し PS ドキュメントを開く
`PsDocument` は Aspose.Page のクラスで、PostScript ドキュメントを表し、図形、テキスト、画像を描画するメソッドを提供します。まず出力ストリームを作成し、ページサイズ（デフォルトは A4）を設定し、グラデーションを配置する矩形を定義します。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **プロのコツ:** 矩形の座標 (`200, 100, 200, 200`) を調整して、ページ上の任意の位置にグラデーションを配置できます。

### 手順 2: 色と分割点を定義する
放射状グラデーションは *カラーストップ*（色）と *分割点*（それらの相対位置）から構成されます。ここでは 6 つの色とそれに対応する分割点の配列を作成します。

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **重要な理由:** `fractions` を調整することで色の遷移速度を制御でき、微妙な効果から劇的な効果まで実現できます。

### 手順 3: 放射状グラデーションペイントを作成する
`RadialGradientPaint` は、中心点、半径、焦点、分割点、色、サイクルメソッド、カラースペースなど、放射状カラーグラデーションを記述するコアクラスです。先ほど定義した配列を使用して `RadialGradientPaint` オブジェクトを作成します。

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **注:** 追加のスケーリングや回転が不要な場合、`transform` は `null` にできます。歪んだグラデーションを試したい場合は `AffineTransform` を自由に実験してください。

### 手順 4: ペイントを設定し矩形を塗りつぶす
ペイントが準備できたら、`PsDocument` にそれを使用するよう指示し、先に定義した矩形を塗りつぶします。

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

この時点で、PostScript ページには設定した放射状グラデーションで滑らかに塗りつぶされた矩形が含まれます。

### 手順 5: ドキュメントを閉じて保存する
最後に、現在のページを閉じてファイルをディスクに書き出します。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

`RadialGradient1_outPS.ps` を任意の PostScript ビューア（例: Ghostscript）で開くと、定義どおりにグラデーションがレンダリングされているのが確認できます。

## よくある問題と解決策
| 症状 | 考えられる原因 | 対策 |
|---------|--------------|-----|
| グラデーションが単色で表示される | `fractions` 配列が `0.0f` で始まっていない、または `1.0f` で終わっていない | 最初の分割点が `0.0f`、最後が `1.0f` であることを確認してください。 |
| 色がくすんで見える | 誤った `ColorSpaceType` を使用している | より鮮やかな出力のために `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` に切り替えてください。 |
| 出力ファイルが生成されない | `FileOutputStream` のパスが無効、または書き込み不可 | `dataDir` が存在し、アプリケーションに書き込み権限があることを確認してください。 |

## よくある質問

**Q: Aspose.Page for Java を商用プロジェクトで使用できますか？**  
A: はい。製品版で使用するには商用ライセンスが必要です。ライセンスは [Aspose licensing page](https://purchase.aspose.com/buy) から購入できます。

**Q: 公式 API リファレンスはどこで見つけられますか？**  
A: 完全なドキュメントは [Aspose.Page Java API reference](https://reference.aspose.com/page/java/) で利用できます。

**Q: テスト用の無料トライアルはありますか？**  
A: もちろんです。トライアル版は [Aspose.Page releases page](https://releases.aspose.com/) からダウンロードできます。

**Q: 評価用の一時ライセンスはどう取得しますか？**  
A: 一時ライセンスは [temporary license request page](https://purchase.aspose.com/temporary-license/) からリクエストできます。

**Q: コミュニティサポートはどこで得られますか？**  
A: Aspose.Page のコミュニティフォーラムは [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39) です。

## 結論
これで、Aspose.Page を使用して Java の PostScript ドキュメントに **放射状グラデーションを作成する方法** がわかりました。矩形のサイズ、カラーストップ、グラデーションの半径を調整することで、微妙な背景の塗りつぶしから大胆なスポットライトグラフィックまで、無限のビジュアル効果を作り出せます。さまざまな `AffineTransform` の値を試してグラデーションを回転や歪めても構いませんし、この手法をテキストや画像と組み合わせて、よりリッチな PDF や EPS 出力を実現してください。

---

**最終更新日:** 2026-09-09  
**テスト環境:** Aspose.Page for Java 最新版（執筆時点）  
**作者:** Aspose

## 関連チュートリアル

- [グラデーションで形状を塗りつぶす: Java PostScript 放射状例](/page/java/postscript-gradient-addition/radial2/)
- [Java で PostScript グラデーションを作成 – 縦方向グラデーションを追加](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page 透明度チュートリアル – Java PostScript に透明度を追加](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}