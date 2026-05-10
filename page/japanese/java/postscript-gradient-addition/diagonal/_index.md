---
date: 2026-02-13
description: Aspose.Page Java を使用して、Java の PostScript ドキュメントに対角線グラデーションを追加し、強化しましょう。LinearGradientPaint
  を使って Java でグラデーション効果を加える方法を学び、手軽に鮮やかな色の遷移を作成できます。
linktitle: 'How to Add Gradient: Diagonal Gradient in Java PostScript using Aspose.Page
  Java'
second_title: Aspose.Page Java API
title: Aspose.Page Java を使用した Java PostScript でのグラデーションの追加方法：対角グラデーション
url: /ja/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScriptで対角線グラデーションを追加する（Aspose.Page Java使用）

## はじめに
PostScript ファイルに滑らかな対角線カラーグラデーションを加えたい場合、**Aspose.Page Java** が驚くほど簡単に実現できます。このチュートリアルでは、Java 2D の `LinearGradientPaint` クラスを使用して、**グラデーションを追加する方法** をステップバイステップで解説します。最後には、鮮やかな対角線グラデーションを持つ PostScript ドキュメントを生成する実行可能なコードスニペットが手に入ります。

## Java PostScriptでグラデーションを追加する方法
グラデーションの追加はグラフィック専用の作業に思えるかもしれませんが、Aspose.Page を使えば純粋な Java の中で基礎となる PostScript コマンドを完全にコントロールできます。このセクションでは、なぜこのアプローチが有効なのか、手書きの生の PostScript と比較して得られるメリットを説明します。

## クイック回答
- **必要なライブラリは？** Aspose.Page for Java。  
- **グラデーションを作成するクラスは？** `LinearGradientPaint`。  
- **色を変更できますか？** はい – `Color[]` 配列を変更してください。  
- **本番環境でライセンスが必要ですか？** 商用ライセンスが必要です。無料トライアルが利用可能です。  
- **実装にどれくらい時間がかかりますか？** 基本的なグラデーションで約10分です。

## Aspose.Page Javaとは？
Aspose.Page Java は、開発者が外部ソフトウェアを必要とせずに PostScript および PDF ファイルを生成、編集、変換できる強力な API です。PostScript 言語の完全なグラフィック機能を、クリーンでオブジェクト指向の Java インターフェイスを通じて提供します。

## なぜ対角線グラデーションを使用するのか？
対角線グラデーションは、チャートやバナー、モダンな外観が求められる任意のグラフィック要素に深みと視覚的な興味を加えます。角から対角の反対側へ伸びるため、背景、ボタンスキン、装飾形状などに最適です。

## 前提条件
開始する前に、以下を用意してください：

- Java Development Kit (JDK) 8 以上。  
- Eclipse、IntelliJ IDEA、VS Code などの IDE。  
- **Aspose.Page for Java** ライブラリ – 最新バージョンは[公式ダウンロードページ](https://releases.aspose.com/page/java/)から取得してください。

## パッケージのインポート
まず、必要な Java 2D と Aspose のクラスをインポートします。これらのインポートにより、カラー定義、幾何形状、グラデーション描画、PostScript ドキュメント API にアクセスできます。

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

## ステップ 1: PostScript ドキュメント用の出力ストリームを作成する
ファイルを保存するフォルダーを定義し、`FileOutputStream` を開きます。このストリームが生成された PostScript データを受け取ります。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## ステップ 2: A4 サイズで保存オプションを作成する
`PsSaveOptions` を使用すると、ページサイズ、解像度、その他の出力設定を指定できます。ここではデフォルトの A4 サイズを使用します。

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## ステップ 3: 新しい PS ドキュメントを作成する
出力ストリームと保存オプションを使用して `PsDocument` をインスタンス化します。`false` フラグはコンストラクタに自動で新しいページを開かないよう指示し、後で手動でページを開きます。

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## ステップ 4: 四角形を作成する
グラデーション塗りつぶしを適用する四角形を定義します。位置 (200, 100) とサイズ (200 × 100) は、グラデーションがはっきり見えるように選択しています。

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## ステップ 5: グラデーション変換を作成する
`AffineTransform` を使用して、グラデーションを回転、スケーリング、平行移動させ、四角形全体に対角線として走らせます。以下の数式で斜辺を計算し、スケーリング比率を調整します。

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

## ステップ 6: 対角線リニアグラデーションペイントを作成する
**グラデーションを追加する** コア部分です。四角形の左上から右下まで伸びる `LinearGradientPaint` を、先ほど定義した変換を使用して構築します。`MultipleGradientPaint.CycleMethod.NO_CYCLE` により、グラデーションが繰り返されないようにします。

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## ステップ 7: ペイントを設定し四角形を塗りつぶす
ドキュメントにグラデーションペイントを適用し、四角形シェイプを塗りつぶします。このステップで対角線カラー遷移が PostScript ページに描画されます。

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## ステップ 8: 現在のページを閉じてドキュメントを保存する
最後にページを閉じ、ストリームをフラッシュし、ファイルを保存します。生成された `DiagonalGradient_outPS.ps` ファイルは任意の PostScript ビューアで開くことができます。

```java
// Close current page and save the document
document.closePage();
document.save();
```

## よくある問題とヒント
- **グラデーションが平坦に見える** – 回転角度を再確認してください。45° の回転で真の対角線になります。  
- **色が薄く見える** – 正確な色再現のために `MultipleGradientPaint.ColorSpaceType.SRGB` を使用しているか確認してください。  
- **ファイルが見つからないエラー** – `dataDir` が既存のフォルダーを指しているか、アプリケーションに書き込み権限があるか確認してください。

## よくある質問

**Q: このライブラリは Java の他のグラフィック操作にも使えますか？**  
A: はい、Aspose.Page for Java は描画プリミティブ、テキストレンダリング、画像処理機能のフルセットを提供します。

**Q: Aspose.Page Java の無料トライアルはありますか？**  
A: もちろんです。完全に機能するトライアルは[Aspose 無料トライアルページ](https://releases.aspose.com/)からダウンロードできます。

**Q: Aspose.Page Java のドキュメントはどこで見つけられますか？**  
A: 公式 API リファレンスは[こちら](https://reference.aspose.com/page/java/)にあります。

**Q: Aspose.Page Java のライセンスはどうやって購入できますか？**  
A: ライセンスは[Aspose 購入ポータル](https://purchase.aspose.com/buy)から直接購入できます。

**Q: サポートが必要、または質問がありますか？**  
A: コミュニティ運営の[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)で、Aspose エンジニアや他の開発者から支援を受けられます。

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}