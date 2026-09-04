---
date: 2026-09-04
description: Aspose.Page Java を使用して Java PostScript にグラデーションを追加する方法を学び、LinearGradientPaint
  を使った対角の色遷移で鮮やかなドキュメントを作成します。
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'グラデーションの追加方法: Aspose.Page Java を使用した Java PostScript の対角グラデーション'
og_description: Aspose.Page Java を使用して Java PostScript にグラデーションを追加する方法を学びます。このガイドでは、LinearGradientPaint
  を使って数ステップで対角グラデーションを作成する方法を示します。
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: Aspose.Page Java を使用した Java PostScript のグラデーションの追加方法
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'グラデーションの追加方法: Aspose.Page Java を使用した Java PostScript の対角グラデーション'
url: /ja/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScriptでAspose.Page Javaを使用して対角線グラデーションを追加する

## はじめに
PostScript ファイルに滑らかな対角線のカラー遷移を加えたい場合、**Aspose.Page Java** を使えば驚くほど簡単に実現できます。このチュートリアルでは、Java 2D の `LinearGradientPaint` クラスを使用して **グラデーションを追加する方法** をステップバイステップで学びます。最後には、鮮やかな対角線グラデーションを持つ PostScript ドキュメントを生成する実行可能なコードスニペットが手に入り、手作業で生の PostScript コマンドを書くよりも保守性が高い理由が理解できるようになります。

## Java PostScriptでグラデーションを追加する方法
グラデーションの追加はグラフィック専用の作業のように思えるかもしれませんが、Aspose.Page を使えば純粋な Java の中で基礎となる PostScript コマンドを完全にコントロールしながら実装できます。このセクションでは、なぜこのアプローチが機能するのか、手作業で生の PostScript を記述する場合と比べて何が得られるのかを説明します。

## クイック回答
- **必要なライブラリは？** Aspose.Page for Java。  
- **どのクラスがグラデーションを作成するか？** `LinearGradientPaint`。  
- **色は変更できるか？** はい – `Color[]` 配列を変更します。  
- **本番環境でライセンスは必要か？** 商用ライセンスが必要です；無料トライアルが利用可能です。  
- **実装にかかる時間は？** 基本的なグラデーションで約 10 分程度です。

## Aspose.Page Java とは？
Aspose.Page Java は、開発者が外部ソフトウェアなしで PostScript および PDF ファイルを生成、編集、変換できるフル機能の API です。ライブラリは **50 以上の入力・出力フォーマット** をサポートし、**500 ページ以上** のドキュメントをメモリ使用量 100 MB 未満で処理できます。

## なぜ対角線グラデーションを使うのか？
対角線グラデーションは、チャート、バナー、またはモダンな外観が必要な任意のグラフィック要素に奥行きと視覚的な興味を加えます。グラデーションが一つの角から対角の角へ走るため、背景、ボタンスキン、装飾形状などに最適で、余分な画像アセットなしでプロフェッショナルな仕上がりを実現できます。

## 前提条件
開始する前に以下を用意してください：

- Java Development Kit (JDK) 8 以上。  
- Eclipse、IntelliJ IDEA、または VS Code などの IDE。  
- **Aspose.Page for Java** ライブラリ – 最新バージョンは [公式ダウンロードページ](https://releases.aspose.com/page/java/) から取得してください。

## パッケージのインポート
`java.awt` パッケージはコアグラフィッククラスを提供し、`com.aspose.page` パッケージは PostScript 固有の API へのアクセスを提供します。

`LinearGradientPaint` クラスは Aspose.Page が Java 2D のグラデーション機能と橋渡しする役割を担います。  
`AffineTransform` はグラデーションを回転・スケーリングして対角線に合わせるために使用します。

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

## 手順 1: PostScript ドキュメント用の出力ストリームを作成
まず、ファイルを保存するフォルダーを定義し、`FileOutputStream` を開きます。このストリームが生成された PostScript データを受け取ります。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## 手順 2: A4 サイズの保存オプションを作成
`PsSaveOptions` でページサイズ、解像度、その他の出力設定を指定できます。ここではデフォルトの A4 サイズ（595 × 842 ポイント、72 dpi）を使用します。

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## 手順 3: 新しい PS ドキュメントを作成
`PsDocument` クラスは PostScript ドキュメントを表し、ページ作成やグラフィック描画のメソッドを提供します。  
出力ストリームと保存オプションを渡して `PsDocument` をインスタンス化します。`false` フラグはコンストラクタに自動的に新しいページを開かせないよう指示し、後で手動でページを開きます。

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 手順 4: 四角形を作成
グラデーション塗りつぶしを受け取る四角形を定義します。四角形の位置 (200, 100) とサイズ (200 × 100) は、グラデーションがはっきり見えるように選択しています。

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## 手順 5: グラデーション変換を作成
`AffineTransform` を使用してグラデーションを回転、スケーリング、平行移動し、四角形全体に対角線として走らせます。以下の数式は斜辺を計算し、スケーリング比率を調整します。

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

## 手順 6: 対角線リニアグラデーションペイントを作成
`LinearGradientPaint` はカラー遷移を生成する中心クラスです。四角形の左上から右下までを対象とし、先ほど定義した変換を使用します。`MultipleGradientPaint.CycleMethod.NO_CYCLE` によりグラデーションが繰り返されません。

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## 手順 7: ペイントを設定し四角形を塗りつぶす
ドキュメントにグラデーションペイントを適用し、四角形シェイプを塗りつぶします。このステップで対角線カラー遷移が PostScript ページに描画されます。

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## 手順 8: 現在のページを閉じてドキュメントを保存
最後にページを閉じ、ストリームをフラッシュし、ファイルを保存します。生成された `DiagonalGradient_outPS.ps` ファイルは任意の PostScript ビューアで開くことができます。

```java
// Close current page and save the document
document.closePage();
document.save();
```

## よくある問題とヒント
- **グラデーションが平坦に見える** – 回転角度を再確認してください。45° の回転で真の対角線が得られます。  
- **色がくすんで見える** – 正確な色再現のために `MultipleGradientPaint.ColorSpaceType.SRGB` を使用しているか確認してください。  
- **ファイルが見つからないエラー** – `dataDir` が既存のフォルダーを指しているか、アプリケーションに書き込み権限があるか確認してください。  
- **大きなドキュメントでメモリが急増** – `PsSaveOptions.setCompress(true)` を使用してメモリフットプリントを削減してください。

## FAQ

**Q: このライブラリを Java の他のグラフィック操作にも使えますか？**  
A: はい、Aspose.Page for Java は描画プリミティブ、テキストレンダリング、画像処理機能をフルセットで提供します。

**Q: Aspose.Page Java の無料トライアルはありますか？**  
A: もちろんです。完全機能のトライアルは [Aspose 無料トライアルページ](https://releases.aspose.com/) からダウンロードできます。

**Q: Aspose.Page Java のドキュメントはどこにありますか？**  
A: 公式 API リファレンスは [Aspose.Page Java API reference](https://reference.aspose.com/page/java/) で利用可能です。

**Q: Aspose.Page Java のライセンスはどうやって購入しますか？**  
A: ライセンスは [Aspose 購入ポータル](https://purchase.aspose.com/buy) から直接購入できます。

**Q: サポートが必要、または質問がありますか？**  
A: Aspose エンジニアや他の開発者から助けが得られるコミュニティ運営の [Aspose.Page フォーラム](https://forum.aspose.com/c/page/39) をご利用ください。

---

**最終更新日:** 2026-09-04  
**テスト環境:** Aspose.Page for Java 24.12（最新）  
**作者:** Aspose

## 関連チュートリアル

- [Create Radial Gradient in PostScript with Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [How to Add Gradient in Java PostScript with Linear Gradient Paint](/page/java/postscript-gradient-addition/horizontal/)
- [Create PostScript Gradient in Java – Add Vertical Gradient](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}