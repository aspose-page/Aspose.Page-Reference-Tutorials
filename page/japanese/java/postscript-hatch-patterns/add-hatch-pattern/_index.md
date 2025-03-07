---
title: Java PostScript でハッチング パターンを追加する
linktitle: Java PostScript でハッチング パターンを追加する
second_title: Aspose.Page Java API
description: Aspose.Page を使用して、魅力的なハッチング パターンを Java PostScript ドキュメントに追加する方法を学びます。ビジュアル コンテンツを簡単に向上させます。
weight: 10
url: /ja/java/postscript-hatch-patterns/add-hatch-pattern/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript でハッチング パターンを追加する

## 導入
Java プログラミングの世界では、視覚要素を強化することが開発者にとっての共通の要件です。興味深い視覚的な拡張機能の 1 つは、PostScript ドキュメントへのハッチング パターンの追加です。このチュートリアルでは、Aspose.Page for Java を使用してハッチング パターンを追加するプロセスについて説明します。
## 前提条件
チュートリアルに入る前に、次の設定が完了していることを確認してください。
- Java 開発環境: Java 開発環境が準備されていることを確認します。
-  Aspose.Page for Java ライブラリ: Aspose.Page for Java ライブラリをダウンロードしてインストールします。必要なファイルが見つかります[ここ](https://releases.aspose.com/page/java/).
## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートします。次のコード スニペットを使用します。
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## ステップ 1: 初期パラメータを設定する
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//PostScript ドキュメントの出力ストリームを作成する
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
//A4サイズで保存オプションを作成する
PsSaveOptions options = new PsSaveOptions();
//ページを開いた状態で新しい PS ドキュメントを作成します
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```
## ステップ 2: グラフィックス状態を保存して変換する
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```
## ステップ 3: 各パターンの正方形を作成する
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```
## ステップ 4: パターンの正方形のアウトライン用にペンを設定する
```java
BasicStroke stroke = new BasicStroke(2);
```
## ステップ 5: ハッチング パターンを反復処理する
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    //... (提供されたコードを続行します)
}
```
## ステップ 6: グラフィックス状態を復元する
```java
document.writeGraphicsRestore();
```
## ステップ 7: ハッチング パターンでテキストを塗りつぶす
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```
## ステップ 8: ハッチング パターンを使用してテキストをアウトライン化する
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```
## ステップ 9: ドキュメントを閉じて保存する
```java
document.closePage();
document.save();
```
以下の手順に従うと、Aspose.Page を使用して Java PostScript ドキュメントにハッチング パターンを正常に追加できます。
## 結論
ハッチング パターンなどの視覚要素を組み込むと、Java アプリケーションの魅力を大幅に高めることができます。 Aspose.Page for Java を使用すると、このプロセスがシームレスになり、視覚的に美しい PostScript ドキュメントを簡単に作成できるようになります。
## よくある質問
### Aspose.Page for Java を他の Java フレームワークで使用できますか?
はい、Aspose.Page for Java は、さまざまな Java フレームワークとシームレスに統合するように設計されています。
### Aspose.Page for Java の試用版は利用できますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.aspose.com/).
### Aspose.Page for Java の一時ライセンスを取得するにはどうすればよいですか?
仮免許を取得できます[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java のその他のチュートリアルとサポートはどこで見つけられますか?
を探索してください[Aspose.Page for Java フォーラム](https://forum.aspose.com/c/page/39)チュートリアルとコミュニティのサポートが必要です。
### Aspose.Page for Java の包括的なドキュメント リソースはありますか?
はい、ドキュメントを参照してください[ここ](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
