---
title: Aspose.Page を使用した Java PostScript 放射状グラデーション
linktitle: Aspose.Page を使用した Java PostScript 放射状グラデーション
second_title: Aspose.Page Java API
description: Aspose.Page を使用して Java PostScript に放射状グラデーションを追加し、Java アプリケーションで美しいグラフィックスを実現するためのステップバイステップ ガイドをご覧ください。
type: docs
weight: 13
url: /ja/java/postscript-gradient-addition/radial2/
---
## 導入
Aspose.Page for Java を使用して Java PostScript に Radial Gradient 2 を追加するためのステップバイステップ ガイドへようこそ。このチュートリアルでは、美しい放射状のグラデーションを持つ PostScript ドキュメントを作成し、視覚的に魅力的なグラフィックスで Java アプリケーションを強化するプロセスを説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Java プログラミングに関する実用的な知識。
- マシンに Java Development Kit (JDK) がインストールされていること。
-  Aspose.Page for Java ライブラリ。[Aspose.Page Java ドキュメント](https://reference.aspose.com/page/java/).
## パッケージのインポート
Java プロジェクトで、Aspose.Page に必要なパッケージをインポートします。
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## ステップ 1: ドキュメント ディレクトリを設定する
ドキュメント ディレクトリへのパスを定義します。
```java
String dataDir = "Your Document Directory";
```
## ステップ 2: 出力ストリームの作成
PostScript ドキュメントの出力ストリームを作成します。
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## ステップ 3: 保存オプションを作成する
A4 サイズで保存オプションを作成します。
```java
PsSaveOptions options = new PsSaveOptions();
```
## ステップ 4: PS ドキュメントを作成する
ページを開いた状態で新しい PS ドキュメントを作成します。
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## ステップ 5: サークルを作成する
Ellipse2D.Float クラスを使用して円を定義します。
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## ステップ 6: グラデーションカラーを定義する
放射状グラデーションの色と分数の配列を作成します。
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## ステップ 7: AffineTransform を作成する
放射状グラデーションの AffineTransform を作成します。
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## ステップ 8: 放射状グラデーション ペイントを作成する
指定されたパラメータを使用して RadialGradientPaint を作成します。
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## ステップ 9: ペイントと塗りつぶし円を設定する
ペイントを設定し、円を放射状のグラデーションで塗りつぶします。
```java
document.setPaint(paint);
document.fill(circle);
```
## ステップ 10: ページを閉じてドキュメントを保存する
現在のページを閉じてドキュメントを保存します。
```java
document.closePage();
document.save();
```
おめでとう！ Aspose.Page for Java を使用して Java PostScript に Radial Gradient 2 を追加することに成功しました。
## 結論
このチュートリアルでは、PostScript ドキュメントの放射状グラデーションを使用して Java アプリケーションを強化する方法を検討しました。 Aspose.Page for Java は、見事なグラフィックを作成するための強力なツール セットを提供し、Java プロジェクトを次のレベルに引き上げることができます。
## よくある質問
### Q: Aspose.Page for Java のドキュメントはどこで見つけられますか?
 A: ドキュメントは入手可能です[ここ](https://reference.aspose.com/page/java/).
### Q: Java 用の Aspose.Page をダウンロードするにはどうすればよいですか?
 A: 以下からダウンロードできます。[リリースページ](https://releases.aspose.com/page/java/).
### Q: 無料トライアルはありますか?
 A: はい、無料トライアルにアクセスできます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Page for Java の一時ライセンスを取得できますか?
 A: はい、一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Q: どこでコミュニティのサポートを求めたり、ディスカッションに参加したりできますか?
 A: にアクセスしてください。[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39).