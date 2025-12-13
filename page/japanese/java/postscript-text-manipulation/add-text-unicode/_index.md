---
date: 2025-12-13
description: JavaでASPページにテキストを追加し、フォントスタイルを設定し、Aspose.Pageを使用してUnicodeテキストを追加する方法を学びましょう。ステップバイステップのガイドに従ってください。
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: ASPページにテキストを追加 – Java PostScriptのUnicode
url: /ja/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – Java PostScript における Unicode

## Introduction
Unicode 文字を保持したまま Java PostScript ワークフローで **asp page add text** が必要な方は、正しい場所に来ました。このチュートリアルでは、Unicode テキストの追加、フォントスタイルの設定、そして **Aspose.Page for Java** を使用した結果の保存手順を解説します。最後まで読むと、font style java の設定方法と Unicode テキストの効率的な追加方法が理解できるようになります。

## Quick Answers
- **What library can add Unicode text in Java PostScript?** Aspose.Page for Java.  
- **Which primary method adds text?** `doc.addGlyphs(...)` with a `XpsGlyphs` object.  
- **Do I need a special font for Unicode?** Any TrueType/OpenType font that supports the required code points (e.g., Arial).  
- **Can I change the font style?** Yes, using `XpsFontStyle` (Regular, Bold, Italic, etc.).  
- **Is a license required for production?** Yes, a valid Aspose.Page license is needed for non‑trial use.

## What is asp page add text?
`asp page add text` は、Aspose.Page API を使用して PostScript または XPS ドキュメントにテキスト文字列を挿入するプロセスを指します。API は低レベルの PostScript コマンドを抽象化し、`XpsGlyphs` のような高レベルオブジェクトで操作できるようにします。

## Why use Aspose.Page to set font style java and add Unicode text?
- **Full Unicode support** – Handles right‑to‑left scripts and complex glyphs.  
- **Simple API** – One‑line calls to add text and apply styles.  
- **Cross‑platform** – Works on any Java‑compatible environment.  
- **No external dependencies** – No need for additional rendering engines.

## Prerequisites
Before we dive into the tutorial, ensure that you have the following prerequisites in place:

1. **Java Development Kit (JDK)** – Make sure Java is installed on your machine.  
2. **Aspose.Page for Java** – Download and install the Aspose.Page library from the [download link](https://releases.aspose.com/page/java/).  
3. **Integrated Development Environment (IDE)** – Choose your preferred Java IDE such as IntelliJ IDEA or Eclipse.

## Import Packages
In your Java project, import the necessary packages for Aspose.Page. Add the following lines to your code:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Step 1: Set Up Your Project
Create a new Java project in your IDE and set up the project structure. Make sure to include the Aspose.Page library in your project dependencies.

## Step 2: Initialize XPS Document
Start by initializing a new XPS document within your project:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Step 3: Add Unicode Text
Now, let's add Unicode text to your XPS document using the Aspose.Page library. Use the following code snippet:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

This code segment adds Unicode text **"AVAJ rof SPX.esopsA"** to the XPS document at coordinates (400, 200) with the specified font and style. Notice how the `setBidiLevel(1)` call enables right‑to‑left rendering for proper Unicode display.

## Step 4: Save the Document
Save the resultant XPS document using the following code:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## Conclusion
Congratulations! You've successfully **asp page add text** and set the font style in a Java PostScript scenario using Aspose.Page. This method gives you fine‑grained control over Unicode rendering and styling, making it ideal for internationalized reports, invoices, and graphics.

Feel free to explore more features and capabilities of Aspose.Page in the [documentation](https://reference.aspose.com/page/java/).

## Frequently Asked Questions

**Q:** Can I use Aspose.Page for Java with other programming languages?  
**A:** Aspose.Page is primarily designed for Java, but Aspose provides libraries for various programming languages.

**Q:** Is there a free trial available?  
**A:** Yes, you can access a free trial of Aspose.Page [here](https://releases.aspose.com/).

**Q:** Where can I find support and discussions about Aspose.Page?  
**A:** Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for support and discussions.

**Q:** How can I obtain a temporary license for Aspose.Page?  
**A:** You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q:** What are the available font styles in Aspose.Page?  
**A:** Aspose.Page supports font styles such as Regular, Bold, Italic, and BoldItalic.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-13  
**Tested With:** Aspose.Page for Java (latest)  
**Author:** Aspose  

---