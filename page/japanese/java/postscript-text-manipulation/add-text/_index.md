---
date: 2026-02-20
description: Aspose.Page for Java を使用してテキストの色を設定する方法、フォントサイズを変更する方法、PostScript ファイルを生成する方法、テキストの塗りつぶしとストローク、カスタムフォントを使用して
  PostScript ドキュメントを作成する方法を学びましょう。
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page を使用した Java のテキストカラー設定 – テキスト操作ガイド
url: /ja/java/postscript-text-manipulation/add-text/
weight: 10
---

 unchanged.

Now produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page を使用した Java のテキストカラー設定 – テキスト操作ガイド

## はじめに
Welcome to our step‑by‑step guide on **set text color java** while working with PostScript files using Aspose.Page for Java. Aspose.Page for Java is a powerful library that lets developers **create postscript document** files, manipulate fonts, and style text with precision. In this tutorial you’ll learn how to add text, change its color, **change font size java**, and even **apply fill and stroke text** for a polished look.

## クイック回答
- **Java でテキストカラーを設定できるライブラリは何ですか？** Aspose.Page for Java.  
- **システムフォントとカスタムフォントの両方を使用できますか？** はい、どちらもサポートされており、**use custom fonts java** を簡単に使用できます。  
- **テキストサイズはどう変更しますか？** `Font` または `DrFont` を作成する際にフォントサイズを指定します。  
- **テキストを輪郭と塗りつぶしの両方にすることは可能ですか？** もちろんです – `fillAndStrokeText` を使用します。  
- **このチュートリアルの出力形式は何ですか？** PostScript（`.ps`）ドキュメントで、プログラムで **generate postscript file** が可能です。

## 「set text color java」とは？
Java でテキストカラーを設定することは、ページに文字を描画する際にレンダリングエンジン（ここでは Aspose.Page）が使用する `Color` オブジェクトを定義することを意味します。この操作は、視覚的に区別されたドキュメントを作成するために不可欠で、特に **generate postscript file** をプログラムで行う必要がある場合に重要です。

## なぜ Aspose.Page for Java を使用するのか？
- **Full control**：ネイティブインタプリタを必要とせずに PostScript の生成を完全に制御できます。  
- **Support for both system and external fonts**：システムフォントと外部フォントの両方をサポートし、必要なタイポグラフィを埋め込めます。  
- **Easy API**：塗りつぶし、輪郭、**fill and stroke text** を簡単に行える API で、スタイリングの柔軟性を提供します。  
- **Cross‑platform** 互換性 – 一度書けば、Java が動くあらゆる環境で実行できます。  

## 前提条件
- Java プログラミングの基本知識。  
- Aspose.Page for Java ライブラリがインストールされていること。[Aspose.Page for Java ダウンロードページ](https://releases.aspose.com/page/java/) からダウンロードできます。  
- 指定フォルダーに必要なフォントがあること。詳細は [Aspose.Page for Java ドキュメント](https://reference.aspose.com/page/java/) を参照してください。  

## パッケージのインポート
In your Java project, import the necessary packages for Aspose.Page for Java:

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

## ステップ 1: ドキュメントの設定
First, we create a new **PostScript document** and configure the output options.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## システムフォントを使用したテキストカラー設定（Java）
Now we demonstrate **set text color java** with a system‑provided font.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tip:** `fillText` メソッドは `Color` 引数を渡さない場合、自動的に現在のカラーを使用し、デフォルトは黒です。

## カスタムフォントの使用とテキストサイズの変更
You can also **change font size java** and use a custom font stored in your fonts folder.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## テキストの輪郭（ストローク） – ストロークテキストの適用
Outlining text gives it a crisp edge. Here we **apply stroke text** using a `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## カスタムフォントでのテキスト輪郭
The same technique works with custom fonts.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## ステップ 6: ドキュメントの保存
Finally, close the page and write the file to disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## なぜ重要なのか
**set text color java** ができ、塗りつぶしと輪郭を組み合わせることで、最終的な PostScript 出力に対して完全なアーティスティックコントロールが得られます。請求書、証明書、カスタムグラフィックの生成であっても、**create postscript document** ファイルを正確なスタイリングで作成できるため、グラフィックエディタでの後処理が不要になります。

## 一般的な問題と解決策
| Issue | Solution |
|-------|----------|
| **Font not found** | フォントファイルが `necessary_fonts` に配置され、`options.setAdditionalFontsFolders` でフォルダー パスが正しく追加されていることを確認してください。 |
| **Color not applied** | `Color` 引数を含む `fillText` または `outlineText` のオーバーロードを呼び出しているか確認してください。 |
| **Stroke appears too thin** | `BasicStroke` の幅を増やします（例: `new BasicStroke(3)`）。 |
| **Document not opening** | 生成された `.ps` ファイルが正しい拡張子で保存され、ビューアが PostScript をサポートしていることを確認してください。 |

## よくある質問

**Q:** Aspose.Page for Java で自分のカスタムフォントを使用できますか？  
**A:** はい、`DrFont` クラスでフォント名とサイズを指定することで **use custom fonts java** が可能です。

**Q:** テキストの色はどう変更できますか？  
**A:** 塗りつぶしまたは輪郭を付ける際に `Color` クラスを使用して目的の色を設定できます。

**Q:** PostScript ドキュメントに複数ページを追加できますか？  
**A:** もちろんです！ドキュメント作成と保存の手順を繰り返すことで複数ページを作成できます。

**Q:** `ExternalFontCache` クラスの目的は何ですか？  
**A:** `ExternalFontCache` はカスタムフォントを取得するために使用され、テキスト操作に利用できるようにします。

**Q:** 輪郭テキストに異なるストロークを適用できますか？  
**A:** はい、`Stroke` クラスと `Color` クラスを使用して、ストロークの幅と色をそれぞれカスタマイズできます。

## 結論
おめでとうございます！これで Aspose.Page for Java を使用して **set text color java**、**change font size java**、**apply fill and stroke text**、そして **create postscript document** ファイルの作成方法が分かりました。さまざまなフォント、カラー、輪郭スタイルを試して、プロフェッショナルな PostScript 出力を作成してください。

---

**最終更新日:** 2026-02-20  
**テスト環境:** Aspose.Page for Java 23.12（最新）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}