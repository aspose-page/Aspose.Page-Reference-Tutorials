---
date: 2025-12-14
description: Aspose.Page for Java का उपयोग करके जावा में टेक्स्ट रंग सेट करना, पोस्टस्क्रिप्ट
  में टेक्स्ट जोड़ना, और समृद्ध दस्तावेज़ शैलीकरण के लिए स्ट्रोक टेक्स्ट लागू करना
  सीखें।
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page के साथ जावा में टेक्स्ट रंग सेट करें – टेक्स्ट मैनिपुलेशन गाइड
url: /hi/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Text Color Java with Aspose.Page – Text Manipulation Guide

## Introduction
Aspose.Page for Java का उपयोग करके PostScript फ़ाइलों के साथ काम करते समय **set text color java** पर हमारा चरण‑दर‑चरण गाइड में आपका स्वागत है। Aspose.Page for Java एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को **generate postscript file** दस्तावेज़ बनाने, फ़ॉन्ट को नियंत्रित करने और सटीकता के साथ टेक्स्ट को स्टाइल करने की सुविधा देती है। इस ट्यूटोरियल में आप सीखेंगे कि टेक्स्ट कैसे जोड़ें, उसका रंग बदलें, आकार समायोजित करें, और एक परिष्कृत लुक के लिए **apply stroke text** कैसे लागू करें।

## Quick Answers
- **What library lets me set text color in Java?** Aspose.Page for Java.  
- **Can I use system fonts and custom fonts?** Yes, both are supported.  
- **How do I change the text size?** By specifying the font size when creating the `Font` or `DrFont`.  
- **Is it possible to outline and fill text together?** Absolutely – use `fillAndStrokeText`.  
- **What output format does this tutorial produce?** A PostScript (`.ps`) document.

## What is “set text color java”?
Java में टेक्स्ट का रंग सेट करना मतलब `Color` ऑब्जेक्ट को परिभाषित करना है, जिसे रेंडरिंग इंजन (यहाँ Aspose.Page) पेज पर अक्षर ड्रॉ करते समय उपयोग करता है। यह ऑपरेशन दृश्य रूप से अलग दस्तावेज़ बनाने के लिए आवश्यक है, विशेषकर जब आप **postscript documents** को प्रोग्रामेटिकली जेनरेट कर रहे हों।

## Why use Aspose.Page for Java?
- **Full control** over PostScript generation without needing a native PostScript interpreter.  
- **Support for both system and external fonts**, letting you embed any typography you need.  
- **Easy API** to fill, outline, and **fill and stroke text**, giving you flexibility in styling.  
- **Cross‑platform** compatibility – write once, run anywhere Java runs.

## Prerequisites
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- Java प्रोग्रामिंग का बेसिक ज्ञान।  
- Aspose.Page for Java लाइब्रेरी स्थापित हो। आप इसे [Aspose.Page for Java download page](https://releases.aspose.com/page/java/) से डाउनलोड कर सकते हैं।  
- निर्दिष्ट फ़ोल्डर में आवश्यक फ़ॉन्ट उपलब्ध हों। अतिरिक्त विवरण के लिए देखें [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)।

## Import Packages
अपने Java प्रोजेक्ट में Aspose.Page for Java के आवश्यक पैकेज इम्पोर्ट करें:

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
पहले, हम एक नया **PostScript document** बनाते हैं और आउटपुट विकल्प कॉन्फ़िगर करते हैं।

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
अब हम **set text color java** को एक सिस्टम‑प्रदान फ़ॉन्ट के साथ प्रदर्शित करेंगे।

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tip:** `fillText` मेथड स्वचालित रूप से वर्तमान रंग का उपयोग करता है यदि आप `Color` आर्ग्यूमेंट नहीं पास करते, जो डिफ़ॉल्ट रूप से काला होता है।

## Using Custom Font and Changing Text Size
आप **change text size** भी कर सकते हैं और अपने फ़ॉन्ट फ़ोल्डर में संग्रहीत कस्टम फ़ॉन्ट का उपयोग कर सकते हैं।

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Outlining (Stroke) Text – Apply Stroke Text
टेक्स्ट को आउटलाइन करने से उसे स्पष्ट किनारा मिलता है। यहाँ हम `BasicStroke` का उपयोग करके **apply stroke text** करते हैं।

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
उसी तकनीक को कस्टम फ़ॉन्ट के साथ भी उपयोग किया जा सकता है।

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Step 6: Save the Document
अंत में, पेज को बंद करें और फ़ाइल को डिस्क पर लिखें।

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
A: Yes, you can use custom fonts by specifying the font name and size in the `DrFont` class.

**Q:** How can I change the color of the text?  
A: You can set the desired color using the `Color` class when filling or outlining the text.

**Q:** Is it possible to add multiple pages to a PostScript document?  
A: Absolutely! You can create multiple pages by repeating the document creation and saving steps.

**Q:** What is the purpose of the `ExternalFontCache` class?  
A: `ExternalFontCache` is used to fetch custom fonts, ensuring they are available for text manipulation.

**Q:** Can I apply different strokes to the outlined text?  
A: Yes, you can customize the width and color of the stroke using the `Stroke` class and `Color` class, respectively.

## Conclusion
बधाई हो! अब आप **set text color java**, फ़ॉन्ट आकार बदलना, **apply stroke text**, और Aspose.Page for Java का उपयोग करके **create postscript document** फ़ाइलें बनाना जानते हैं। विभिन्न फ़ॉन्ट, रंग और आउटलाइन स्टाइल के साथ प्रयोग करें ताकि पेशेवर‑दिखावट वाले PostScript आउटपुट तैयार कर सकें।

---

**Last Updated:** 2025-12-14  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}