---
title: Java PostScript でテクスチャ タイル パターンを追加する
linktitle: Java PostScript でテクスチャ タイル パターンを追加する
second_title: Aspose.Page Java API
description: Aspose.Page for Java を使用すると、PostScript ドキュメントにテクスチャ タイル パターンを簡単に追加できます。創造的な可能性については、シームレスな統合ガイドをご覧ください。
type: docs
weight: 10
url: /ja/java/postscript-texture-patterns/add-texture-tiling-pattern/
---
## 導入
Java 開発の領域では、PostScript ドキュメントで複雑なパターンやテクスチャを作成することが一般的な要件です。 Aspose.Page for Java は、このタスクを簡単に達成するための貴重なツールであることがわかります。このチュートリアルでは、Aspose.Page を使用して Java PostScript ドキュメントにテクスチャ タイル パターンを追加するプロセスを説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Java プログラミング言語の基本的な理解。
- PostScript ドキュメント構造に精通していること。
-  Aspose.Page for Java ライブラリがインストールされています。ダウンロードできます[ここ](https://releases.aspose.com/page/java/).
## パッケージのインポート
まず、Java プロジェクトに必要なパッケージをインポートします。
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## ステップ 1: PostScript ドキュメントを作成する
まず、新しい PostScript ドキュメントを作成し、出力ストリームと保存オプションを指定します。必要なパスが設定されていることを確認してください。
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//PostScript ドキュメントの出力ストリームを作成する
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
//A4サイズで保存オプションを作成する
PsSaveOptions options = new PsSaveOptions();
//ページを開いた状態で新しい PS ドキュメントを作成します
PsDocument document = new PsDocument(outPsStream, options, false);
//ページを開いた状態で新しい PS ドキュメントを作成します
PsDocument document = new PsDocument(outPsStream, options, false);
```
## ステップ 2: グラフィック環境をセットアップする
原点を変換し、テクスチャ イメージ ファイルから BufferedImage を作成することで、グラフィックス環境をセットアップします。
```java
document.writeGraphicsSave();
document.translate(200, 100);
//画像ファイルからBufferedImageオブジェクトを作成する
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```
## ステップ 3: テクスチャ ブラシを作成する
画像からテクスチャ ブラシを定義し、テクスチャでカバーされる領域を指定します。
```java
//幅を2倍にした画像領域を作成する
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
//画像からテクスチャブラシを作成
TexturePaint paint = new TexturePaint(image, imageArea);
```
## ステップ 4: 図形を描画して塗りつぶす
長方形を作成し、定義されたテクスチャ ブラシで塗りつぶします。さらに、視覚的にアピールするために、形状を描画して輪郭を描きます。
```java
//長方形の作成
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
//このテクスチャ ブラシを現在のペイントとして設定します
document.setPaint(paint);
//長方形を塗りつぶす
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```
## ステップ 5: テクスチャ パターンを使用してテキストを追加する
ドキュメントにテキストを追加し、テクスチャ パターンで塗りつぶすかストロークします。必要に応じて、フォント、位置、その他のパラメータをカスタマイズします。
```java
//テキストをテクスチャパターンで塗りつぶす
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
//テクスチャパターンでテキストの輪郭を描く
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## ステップ 6: 保存して閉じる
現在のページを閉じ、ドキュメントを保存し、シームレスに実行できるようにしてプロセスを終了します。
```java
//現在のページを閉じる
document.closePage();
//文書を保存する
document.save();
```
## 結論
おめでとう！ Aspose.Page for Java を使用して、Java PostScript ドキュメントにテクスチャ タイル パターンを正常に追加しました。自由にさらなるカスタマイズ オプションを探索し、この強力なライブラリの可能性を最大限に引き出してください。

## よくある質問
### Aspose.Page for Java は初心者に適していますか?
絶対に！ Aspose.Page for Java は包括的なドキュメントを提供し、あらゆるスキル レベルの開発者がアクセスできるようにします。
### Aspose.Page for Java を既存の Java プロジェクトに統合できますか?
はい、提供されているドキュメントに従って、Aspose.Page for Java をプロジェクトに簡単に統合できます。[ここ](https://reference.aspose.com/page/java/).
### Aspose.Page 関連のクエリについてサポートを見つけたり、議論したりできる場所はどこですか?
訪問[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティと関わり、支援を求めます。
### Aspose.Page for Java に利用できる無料トライアルはありますか?
はい、無料トライアルを試すことができます[ここ](https://releases.aspose.com/).
### Aspose.Page for Java の一時ライセンスを取得するにはどうすればよいですか?
訪問[このリンク](https://purchase.aspose.com/temporary-license/)仮免許を取得するためです。