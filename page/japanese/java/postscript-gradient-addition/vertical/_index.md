---
title: Java PostScriptで垂直グラデーションを追加する
linktitle: Java PostScriptで垂直グラデーションを追加する
second_title: Aspose.Page Java API
description: Aspose.Page for Java を使用して Java PostScript に垂直グラデーションを追加するためのステップバイステップ ガイドをご覧ください。鮮やかなビジュアルでドキュメントを簡単に強化できます。
weight: 14
url: /ja/java/postscript-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScriptで垂直グラデーションを追加する

## 導入
Aspose.Page for Java を使用して Java PostScript に垂直グラデーションを追加するためのこのステップバイステップ ガイドへようこそ。目を引くグラデーションでドキュメントを強化したい場合は、このチュートリアルが最適です。 Aspose.Page for Java は、PostScript ドキュメントをシームレスに操作するための強力なツールを提供します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Java Development Kit (JDK) がマシンにインストールされています。
-  Java ライブラリの Aspose.Page。ダウンロードできます[ここ](https://releases.aspose.com/page/java/).
## パッケージのインポート
Java プロジェクトで、開始するために必要なパッケージをインポートします。
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
ここで、Java PostScript で垂直グラデーションを追加するプロセスを複数のステップに分けてみましょう。
## ステップ 1: ドキュメント ディレクトリを設定する
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
```
## ステップ 2: PostScript ドキュメントの出力ストリームを作成する
```java
//PostScript ドキュメントの出力ストリームを作成する
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## ステップ 3: A4 サイズで保存オプションを作成する
```java
//A4サイズで保存オプションを作成する
PsSaveOptions options = new PsSaveOptions();
```
## ステップ 4: 新しい PS ドキュメントを作成する
```java
//ページを開いた状態で新しい PS ドキュメントを作成します
PsDocument document = new PsDocument(outPsStream, options, false);
```
## ステップ 5: 長方形を作成する
```java
//長方形を作成する
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## ステップ 6: グラデーションの色と分数を設定する
```java
//グラデーションの色と分数の配列を作成します。
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## ステップ 7: グラデーション変換を作成する
```java
//勾配変換を作成します。変換内のスケール コンポーネントは、長方形の幅と高さに等しくなければなりません。
//移動コンポーネントは長方形のオフセットです。
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
//原点を中心にグラデーションを 90 度回転します
transform.rotate(90 * (Math.PI / 180));
```
## ステップ 8: 垂直方向の線形グラデーション ペイントを作成する
```java
//垂直方向の線形グラデーション ペイントを作成します。
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## ステップ 9: ペイントを設定して長方形を塗りつぶす
```java
//セットペイント
document.setPaint(paint);
//長方形を塗りつぶす
document.fill(rectangle);
```
## ステップ 10: 現在のページを閉じてドキュメントを保存する
```java
//現在のページを閉じる
document.closePage();
//文書を保存する
document.save();
```
おめでとう！ Aspose.Page for Java を使用して、Java PostScript ドキュメントに垂直グラデーションを正常に追加しました。
## 結論
このチュートリアルでは、Aspose.Page for Java を使用して、鮮やかな垂直グラデーションでドキュメントを強化するプロセスについて説明しました。素晴らしいビジュアルを組み込むことで、ドキュメントの操作を次のレベルに引き上げることができます。
## よくある質問
### Aspose.Page for Java を他の Java ライブラリと一緒に使用できますか?
はい、Aspose.Page for Java は、他の Java ライブラリとシームレスに動作するように設計されています。
### Aspose.Page for Java に利用できる無料トライアルはありますか?
はい、無料トライアルを利用できます[ここ](https://releases.aspose.com/).
### 追加のドキュメントはどこで入手できますか?
詳細なドキュメントが利用可能です[ここ](https://reference.aspose.com/page/java/).
### Aspose.Page for Java を購入するにはどうすればよいですか?
 Aspose.Page for Java を購入できます[ここ](https://purchase.aspose.com/buy).
### Aspose.Page についてディスカッションするフォーラムはありますか?
はい、コミュニティ フォーラムに参加できます[ここ](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
