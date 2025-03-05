---
title: Java PostScript で水平方向のグラデーションを追加する
linktitle: Java PostScript で水平方向のグラデーションを追加する
second_title: Aspose.Page Java API
description: Aspose.Page for Java を使用して Java PostScript に水平グラデーションを追加する方法を学びます。視覚的に美しいドキュメントを簡単に作成できます。
type: docs
weight: 11
url: /ja/java/postscript-gradient-addition/horizontal/
---
## 導入
Aspose.Page for Java を使用して Java PostScript に水平グラデーションを追加するためのこの包括的なチュートリアルへようこそ。 Aspose.Page は、開発者が PostScript やその他のドキュメント形式を操作できるようにする強力な Java ライブラリです。このチュートリアルでは、水平方向のグラデーションを持つ PostScript ドキュメントを作成するプロセスを、ステップバイステップの例を使用して説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
- Java Development Kit (JDK) がマシンにインストールされています。
- Java ライブラリの Aspose.Page。からダウンロードできます。[Aspose.Page Java ドキュメント](https://reference.aspose.com/page/java/).
## パッケージのインポート
まず、Java プロジェクトに必要なパッケージをインポートします。これらのパッケージは、Aspose.Page を操作するために重要です。
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
## ステップ 1: 長方形を作成する
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//PostScript ドキュメントの出力ストリームを作成する
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
//A4サイズで保存オプションを作成する
PsSaveOptions options = new PsSaveOptions();
//ページを開いた状態で新しい PS ドキュメントを作成します
PsDocument document = new PsDocument(outPsStream, options, false);
//長方形を作成する
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## ステップ 2: 水平方向の線形グラデーション ペイントを作成する
```java
//水平方向の線形グラデーション ペイントを作成します。変換内のスケール コンポーネントは、長方形の幅と高さに等しくなければなりません。
//移動コンポーネントは長方形のオフセットです。
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
//セットペイント
document.setPaint(paint);
```
## ステップ 3: 長方形を塗りつぶす
```java
//長方形を塗りつぶす
document.fill(rectangle);
```
## ステップ 4: テキストをグラデーションで塗りつぶす
```java
//テキストをグラデーションで塗りつぶす
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## ステップ 5: グラデーションでテキストをストロークする
```java
//テキストをグラデーションで描く
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## 結論
おめでとう！ Aspose.Page for Java を使用して、Java PostScript に水平グラデーションを正常に追加しました。このチュートリアルでは、視覚的に魅力的な PostScript ドキュメントを作成するのに役立つ詳細なステップバイステップ ガイドを提供しました。
## よくある質問
### Aspose.Page for Java を商用プロジェクトで使用できますか?
はい、Aspose.Page for Java は商用プロジェクトで使用できます。ライセンスの詳細については、次のサイトを参照してください。[処分、購入](https://purchase.aspose.com/buy).
### 無料トライアルはありますか?
はい、Aspose.Page for Java の無料トライアルにアクセスできます。[ここ](https://releases.aspose.com/).
### 追加のドキュメントとサポートはどこで入手できますか?
訪問[Aspose.Page Java ドキュメント](https://reference.aspose.com/page/java/)包括的なリソースを提供します。コミュニティサポートについては、[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39).
### 仮免許はどうやって取得できますか?
一時ライセンスは次から取得できます。[処分、購入](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java のシステム要件は何ですか?
を参照してください。[ドキュメンテーション](https://reference.aspose.com/page/java/)詳細なシステム要件については、