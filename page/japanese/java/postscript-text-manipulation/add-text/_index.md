---
title: Aspose.Page Java テキスト操作
linktitle: Java PostScript でテキストを追加する
second_title: Aspose.Page Java API
description: PostScript ドキュメントへのテキストの追加に関するチュートリアルで、Aspose.Page for Java の威力を体験してください。システム フォントとカスタム フォントを簡単に使用する方法を学びましょう。
weight: 10
url: /ja/java/postscript-text-manipulation/add-text/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java テキスト操作

## 導入
Aspose.Page for Java を使用して Java PostScript にテキストを追加するためのステップバイステップ ガイドへようこそ。 Aspose.Page for Java は、開発者が PostScript ドキュメントを簡単に操作できるようにする強力なライブラリです。このチュートリアルでは、テキストの追加、システム フォントとカスタム フォントの使用、テキストのアウトライン化、および視覚的に魅力的な結果を得るストロークの組み込みのプロセスを順を追って説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
- Java プログラミングの基本的な知識。
-  Aspose.Page for Java ライブラリがインストールされています。からダウンロードできます。[Aspose.Page for Java のダウンロード ページ](https://releases.aspose.com/page/java/).
- 必要なフォントは指定したフォルダーにあります。追加情報については、[Aspose.Page for Java ドキュメント](https://reference.aspose.com/page/java/).
## パッケージのインポート
Java プロジェクトで、Aspose.Page for Java に必要なパッケージをインポートします。
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## ステップ 1: ドキュメントを設定する
```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
//PostScript ドキュメントの出力ストリームを作成する
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
//A4サイズで保存オプションを作成する
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
//PSファイルに書き込むテキスト
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
//新しい 1 ページの PS ドキュメントを作成する
PsDocument document = new PsDocument(outPsStream, options, false);
```
## ステップ 2: テキストの入力にシステム フォントを使用する
```java
//テキストを埋めるためにシステムフォントを使用する
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
//デフォルトまたはすでに定義されている色 (黒) でテキストを塗りつぶします。
document.fillText(str, font, 50, 100);
//テキストを青色で塗りつぶす
document.fillText(str, font, 50, 150, Color.BLUE);
```
## ステップ 3: テキストの入力にカスタム フォントを使用する
```java
//テキストの塗りつぶしにカスタム フォントを使用する
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
//デフォルトまたはすでに定義されている色 (黒) でテキストを塗りつぶします。
document.fillText(str, drFont, 50, 200);
//テキストを青色で塗りつぶす
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## ステップ 4: システム フォントを使用してテキストのアウトラインを作成する
```java
//テキストのアウトラインにシステムフォントを使用する
document.outlineText(str, font, 50, 300);
//青紫色の2ポイント幅のペンでテキストをアウトライン化します
document.outlineText(str, font, 50, 350, strokeColor, stroke);
//テキストをオレンジ色で塗りつぶし、青色の 2 ポイント幅のペンでストロークします。
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## ステップ 5: カスタム フォントを使用してテキストのアウトラインを作成する
```java
//テキストのアウトラインにカスタム フォントを使用する
document.outlineText(str, drFont, 50, 450);
//青紫色の2ポイント幅のペンでテキストをアウトライン化します
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
//テキストをオレンジ色で塗りつぶし、青色の 2 ポイント幅のペンでストロークします。
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## ステップ 6: ドキュメントを保存する
```java
//現在のページを閉じる
document.closePage();
//文書を保存する
document.save();
```
## 結論
おめでとう！ Aspose.Page for Java を使用して Java PostScript にテキストを追加する方法を学習しました。さまざまなフォント、色、アウトラインのオプションを試して、文書をさらに強化します。
## よくある質問
### Aspose.Page for Java で独自のカスタム フォントを使用できますか?
はい、フォント名とサイズを指定することでカスタム フォントを使用できます。`DrFont`クラス。
### 文字の色を変更するにはどうすればよいですか?
を使用して希望の色を設定できます。`Color`テキストを塗りつぶしたりアウトラインを作成するときにクラスを使用します。
### PostScript ドキュメントに複数のページを追加することはできますか?
絶対に！文書の作成と保存の手順を繰り返すことで、複数のページを作成できます。
### の目的は何ですか`ExternalFontCache` class?
`ExternalFontCache`カスタム フォントをフェッチし、それらがテキスト操作に確実に利用できるようにするために使用されます。
### アウトライン化されたテキストに別のストロークを適用できますか?
はい、ストロークの幅と色は、`Stroke`クラスと`Color`それぞれクラス。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
