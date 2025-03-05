---
title: Java PostScriptで画像を追加
linktitle: Java PostScriptで画像を追加
second_title: Aspose.Page Java API
description: PostScript ドキュメントへの画像の追加に関するこのチュートリアルで、Aspose.Page Java のシームレスな統合を確認してください。ドキュメントの操作能力を向上させます。
type: docs
weight: 10
url: /ja/java/postscript-image-manipulation/add-image/
---
## 導入
このチュートリアルでは、Aspose.Page for Java ライブラリを使用して Java PostScript ドキュメントに画像を追加する方法を説明します。 Aspose.Page は、PostScript ファイルを操作するためのさまざまな機能を提供する強力なライブラリであり、開発者がドキュメントをシームレスに操作および強化できるようにします。
## 前提条件
チュートリアルに入る前に、次の前提条件を満たしていることを確認してください。
- Java Development Kit (JDK) がシステムにインストールされています。
-  Java ライブラリの Aspose.Page。ダウンロードできます[ここ](https://releases.aspose.com/page/java/).
- Java プログラミングの基本的な理解。
## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートします。次のコード スニペットを参考として使用してください。
```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## ステップ 1: グラフィックの書き込み保存
最初のステップでは、ドキュメントに保存するグラフィックを書き込みます。これにより、後で行われた変換や変更を必要に応じてロールバックできるようになります。
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//PostScript ドキュメントの出力ストリームを作成する
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
//A4サイズで保存オプションを作成する
PsSaveOptions options = new PsSaveOptions();
//ページを開いた状態で新しい PS ドキュメントを作成します
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```
## ステップ 2: 翻訳と変換
次に、ドキュメントを翻訳し、画像ファイルから BufferedImage オブジェクトを作成します。 AffineTransform を使用して、スケーリングや回転などの一連の変換を適用します。
```java
document.translate(100, 100);
//画像ファイルから BufferedImage オブジェクトを作成する
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
//画像変換を作成する
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```
## ステップ 3: ドキュメントに画像を追加する
次に、変換された画像をドキュメントに追加します。
```java
document.drawImage(image, transform, null);
```
## ステップ 4: グラフィックス復元の書き込み
イメージを追加した後、グラフィックスの復元を作成して変更を確定します。
```java
document.writeGraphicsRestore();
```
## ステップ 5: 現在のページを閉じて保存する
現在のページを閉じて、ドキュメントを保存します。
```java
document.closePage();
document.save();
```
これらの手順を繰り返して複数の画像を追加するか、要件に基づいて変換をカスタマイズします。
## 結論
おめでとう！ Aspose.Page for Java を使用して Java PostScript ドキュメントに画像を追加する方法を学習しました。を探索してください[ドキュメンテーション](https://reference.aspose.com/page/java/)より高度な機能を利用するには。
## よくある質問
### Aspose.Page for Java を他のプログラミング言語で使用できますか?
Aspose.Page は主に Java をサポートしていますが、他のプログラミング言語でも使用できるバージョンもあります。
### Aspose.Page for Java に利用できる無料トライアルはありますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.aspose.com/).
### Aspose.Page for Java の一時ライセンスを取得するにはどうすればよいですか?
仮免許が取得できる[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java に関連するコミュニティ サポートやディスカッションはどこで見つけられますか?
訪問[Aspose.Page フォーラム](https://forum.aspose.com/c/page/39)コミュニティサポートのために。
### Aspose.Page for Java を購入するための追加リソースはありますか?
図書館を購入できます[ここ](https://purchase.aspose.com/buy).