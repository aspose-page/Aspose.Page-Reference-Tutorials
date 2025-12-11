---
date: 2025-12-07
description: Aspose.Page Java を使用して、Java の PostScript ドキュメントに対角線グラデーションを追加し、強化しましょう。Java
  の LinearGradientPaint を使ってグラデーション効果を加える方法を学び、手軽に鮮やかな色の遷移を実現できます。
linktitle: Add Diagonal Gradient in Java PostScript using Aspose.Page Java
second_title: Aspose.Page Java API
title: Aspose.Page Java を使用して Java PostScript に対角線グラデーションを追加する
url: /ja/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScriptで対角線グラデーションを追加する（Aspose.Page Java 使用）

## Introduction
PostScript ファイルに滑らかな対角線カラー遷移を加えたい場合、**Aspose.Page Java** を使えば驚くほど簡単に実現できます。このチュートリアルでは、Java 2D の `LinearGradientPaint` クラスを利用して **グラデーションを追加する方法** をステップバイステップで解説します。最後には、鮮やかな対角線グラデーションを持つ PostScript ドキュメントを生成する実行可能なコードスニペットが手に入ります。

## Quick Answers
- **必要なライブラリは？** Aspose.Page for Java。  
- **どのクラスがグラデーションを作成する？** `LinearGradientPaint`。  
- **色は変更できる？** はい – `Color[]` 配列を変更してください。  
- **本番環境でライセンスは必要？** 商用ライセンスが必要です；無料トライアルも利用可能です。  
- **実装にかかる時間は？** 基本的なグラデーションで約 10 分程度。

## What is Aspose.Page Java?
Aspose.Page Java は、開発者が外部ソフトウェアを必要とせずに PostScript および PDF ファイルを生成、編集、変換できる強力な API です。PostScript 言語のフルグラフィック機能を、クリーンでオブジェクト指向な Java インターフェイスを通じて提供します。

## Why use a diagonal gradient?
対角線グラデーションは、チャートやバナー、モダンな外観が求められるあらゆるグラフィック要素に奥行きと視覚的興味を加えます。角から対角の反対側へ伸びるため、背景、ボタンスキン、装飾形状などに最適です。

## Prerequisites
開始する前に以下を用意してください：

- Java Development Kit (JDK) 8 以上。  
- Eclipse、IntelliJ IDEA、または VS Code などの IDE。  
- **Aspose.Page for Java** ライブラリ – 最新バージョンは [公式ダウンロードページ](https://releases.aspose.com/page/java/) から取得できます。

## Import Packages
まず、必要な Java 2D と Aspose のクラスをインポートします。これらのインポートにより、カラー定義、幾何形状、グラデーション描画、PostScript ドキュメント API へのアクセスが可能になります。

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

## Step 1: Create Output Stream for PostScript Document
ファイルを保存するフォルダーを定義し、`FileOutputStream` を開きます。このストリームが生成された PostScript データを受け取ります。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Step 2: Create Save Options with A4 Size
`PsSaveOptions` を使用してページサイズ、解像度、その他の出力設定を指定します。ここではデフォルトの A4 サイズを使用します。

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Step 3: Create New PS Document
出力ストリームと保存オプションを渡して `PsDocument` をインスタンス化します。`false` フラグはコンストラクタに自動で新しいページを開かせないよう指示し、後で手動でページを作成します。

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 4: Create a Rectangle
グラデーション塗りつぶし対象となる矩形を定義します。矩形の位置 (200, 100) とサイズ (200 × 100) は、グラデーションがはっきり見えるように選択しています。

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Step 5: Create Gradient Transform
`AffineTransform` を使ってグラデーションを回転、スケール、平行移動し、矩形全体に対角線として走らせます。以下の数式は斜辺を計算し、スケーリング比率を調整します。

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Step 6: Create Diagonal Linear Gradient Paint
ここが **グラデーションを追加する方法** の核心です。矩形の左上から右下まで伸びる `LinearGradientPaint` を、先ほど定義した変換とともに作成します。`MultipleGradientPaint.CycleMethod.NO_CYCLE` によりグラデーションが繰り返されません。

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Step 7: Set Paint and Fill the Rectangle
作成したグラデーションペイントをドキュメントに適用し、矩形形状を塗りつぶします。このステップで対角線カラー遷移が PostScript ページに描画されます。

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Step 8: Close the Current Page and Save the Document
最後にページを閉じ、ストリームをフラッシュしてファイルを保存します。生成された `DiagonalGradient_outPS.ps` ファイルは任意の PostScript ビューアで開くことができます。

```java
// Close current page and save the document
document.closePage();
document.save();
```

これら 8 ステップを実行すれば、**Aspose.Page Java** を使用して PostScript ドキュメントに対角線グラデーションを正常に追加できます。色、角度、矩形サイズを変えて、オリジナルのビジュアルエフェクトを自由に試してみてください。

## Common Issues & Tips
- **グラデーションが平坦に見える** – 回転角度を再確認してください。45° の回転で真の対角線になります。  
- **色が薄く見える** – 正確な色再現のために `MultipleGradientPaint.ColorSpaceType.SRGB` を使用しているか確認してください。  
- **ファイルが見つからないエラー** – `dataDir` が実在するフォルダーを指しているか、アプリケーションに書き込み権限があるかを確認してください。

## Frequently Asked Questions

**Q: このライブラリを Java の他のグラフィック操作にも使えますか？**  
A: はい、Aspose.Page for Java は描画プリミティブ、テキストレンダリング、画像処理機能をフルセットで提供します。

**Q: Aspose.Page Java の無料トライアルはありますか？**  
A: もちろんです。完全機能のトライアルは [Aspose 無料トライアルページ](https://releases.aspose.com/) からダウンロードできます。

**Q: Aspose.Page Java のドキュメントはどこで見られますか？**  
A: 公式 API リファレンスは [こちら](https://reference.aspose.com/page/java/) にあります。

**Q: Aspose.Page Java のライセンスはどうやって購入できますか？**  
A: ライセンスは [Aspose 購入ポータル](https://purchase.aspose.com/buy) から直接購入できます。

**Q: サポートや質問がある場合は？**  
A: Aspose エンジニアや他の開発者から助言が得られるコミュニティ運営の [Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) をご利用ください。

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}