---
date: 2025-12-14
description: Aspose.Page for Java を使用して Java でテキストの色を設定し、PostScript にテキストを追加し、リッチな文書スタイリングのためにストロークテキストを適用する方法を学びましょう。
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page を使用した Java のテキストカラー設定 – テキスト操作ガイド
url: /ja/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Text Color Java with Aspose.Page – Text Manipulation Guide

## Introduction
Aspose.Page for Java を使用して PostScript ファイルを操作する際の **set text color java** に関するステップバイステップガイドへようこそ。Aspose.Page for Java は、開発者が **generate postscript file** ドキュメントを作成し、フォントを操作し、テキストを正確にスタイリングできる強力なライブラリです。本チュートリアルでは、テキストの追加、色の変更、サイズの調整、さらには **apply stroke text** を使用した洗練された外観の実装方法を学びます。

## Quick Answers
- **What library lets me set text color in Java?** Aspose.Page for Java.  
- **Can I use system fonts and custom fonts?** Yes, both are supported.  
- **How do I change the text size?** By specifying the font size when creating the `Font` or `DrFont`.  
- **Is it possible to outline and fill text together?** Absolutely – use `fillAndStrokeText`.  
- **What output format does this tutorial produce?** A PostScript (`.ps`) document.

## What is “set text color java”?
Java でテキストの色を設定することは、レンダリングエンジン（ここでは Aspose.Page）が文字をページに描画する際に使用する `Color` オブジェクトを定義することを意味します。この操作は、特に **postscript documents** をプログラムで生成する際に、視覚的に区別されたドキュメントを作成するために不可欠です。

## Why use Aspose.Page for Java?
- **Full control** over PostScript generation without needing a native PostScript interpreter.  
- **Support for both system and external fonts**, letting you embed any typography you need.  
- **Easy API** to fill, outline, and **fill and stroke text**, giving you flexibility in styling.  
- **Cross‑platform** compatibility – write once, run anywhere Java runs.

## Prerequisites
開始する前に、以下を確認してください。

- Java プログラミングの基本知識。  
- Aspose.Page for Java ライブラリがインストール済み。ダウンロードは [Aspose.Page for Java download page](https://releases.aspose.com/page/java/) から。  
- 指定フォルダーに必要なフォントが配置されていること。詳細は [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) を参照。

## Import Packages
Java プロジェクトで Aspose.Page for Java に必要なパッケージをインポートします。

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

## Step 1: Set Up the Document
まず、**PostScript document** を新規作成し、出力オプションを設定します。

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

## How to Set Text Color Java Using System Font
次に、システムフォントを使用した **set text color java** の例を示します。

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tip:** `fillText` メソッドは `Color` 引数を渡さない場合、現在の色（デフォルトは黒）を自動的に使用します。

## Using Custom Font and Changing Text Size
カスタムフォントを使用し、テキストサイズを変更する方法も紹介します。

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Outlining (Stroke) Text – Apply Stroke Text
テキストにアウトライン（ストローク）を付けると、はっきりとしたエッジが得られます。ここでは `BasicStroke` を使って **apply stroke text** を実装します。

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

## Outlining Text with Custom Font
同様の手法はカスタムフォントでも利用可能です。

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Step 6: Save the Document
最後にページを閉じ、ファイルをディスクに書き出します。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Font not found** | Ensure the font file is placed in `necessary_fonts` and the folder path is correctly added via `options.setAdditionalFontsFolders`. |
| **Color not applied** | Verify you are calling the overload of `fillText` or `outlineText` that includes a `Color` argument. |
| **Stroke appears too thin** | Increase the `BasicStroke` width (e.g., `new BasicStroke(3)`). |
| **Document not opening** | Confirm the generated `.ps` file is saved with the correct extension and that your viewer supports PostScript. |

## Frequently Asked Questions

**Q:** Can I use my own custom fonts with Aspose.Page for Java?  
**A:** Yes, you can use custom fonts by specifying the font name and size in the `DrFont` class.

**Q:** How can I change the color of the text?  
**A:** You can set the desired color using the `Color` class when filling or outlining the text.

**Q:** Is it possible to add multiple pages to a PostScript document?  
**A:** Absolutely! You can create multiple pages by repeating the document creation and saving steps.

**Q:** What is the purpose of the `ExternalFontCache` class?  
**A:** `ExternalFontCache` is used to fetch custom fonts, ensuring they are available for text manipulation.

**Q:** Can I apply different strokes to the outlined text?  
**A:** Yes, you can customize the width and color of the stroke using the `Stroke` class and `Color` class, respectively.

## Conclusion
おめでとうございます！これで **set text color java** の方法、フォントサイズの変更、**apply stroke text** の適用、そして Aspose.Page for Java を使った **create postscript document** の作成方法が習得できました。さまざまなフォント、色、アウトラインスタイルを試して、プロフェッショナルな PostScript 出力を実現してください。

---

**Last Updated:** 2025-12-14  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}