---
date: 2026-02-20
description: Aspose.Page for Java का उपयोग करके टेक्स्ट का रंग सेट करना, फ़ॉन्ट आकार
  बदलना, पोस्टस्क्रिप्ट फ़ाइल बनाना, टेक्स्ट को भरना और स्ट्रोक करना, और पोस्टस्क्रिप्ट
  दस्तावेज़ बनाते समय कस्टम फ़ॉन्ट्स का उपयोग करना सीखें।
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
Aspose.Page for Java का उपयोग करके PostScript फ़ाइलों के साथ काम करते हुए **set text color java** पर हमारा चरण‑दर‑चरण मार्गदर्शिका में आपका स्वागत है। Aspose.Page for Java एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को **create postscript document** फ़ाइलें बनाने, फ़ॉन्ट्स को नियंत्रित करने, और टेक्स्ट को सटीकता से स्टाइल करने की सुविधा देती है। इस ट्यूटोरियल में आप सीखेंगे कि टेक्स्ट कैसे जोड़ें, उसका रंग कैसे बदलें, **change font size java**, और यहाँ तक कि एक परिष्कृत लुक के लिए **apply fill and stroke text** कैसे लागू करें।

## Quick Answers
- **Java में टेक्स्ट रंग सेट करने वाली लाइब्रेरी कौन सी है?** Aspose.Page for Java.  
- **क्या मैं सिस्टम फ़ॉन्ट्स और कस्टम फ़ॉन्ट्स का उपयोग कर सकता हूँ?** हाँ, दोनों समर्थित हैं, और आप आसानी से **use custom fonts java** कर सकते हैं।  
- **टेक्स्ट का आकार कैसे बदलूँ?** `Font` या `DrFont` बनाते समय फ़ॉन्ट साइज निर्दिष्ट करके।  
- **क्या टेक्स्ट को साथ में आउटलाइन और फ़िल किया जा सकता है?** बिल्कुल – `fillAndStrokeText` का उपयोग करें।  
- **इस ट्यूटोरियल का आउटपुट फ़ॉर्मेट क्या है?** एक PostScript (`.ps`) दस्तावेज़, जिसे आप प्रोग्रामेटिकली **generate postscript file** कर सकते हैं।

## What is “set text color java”?
Java में टेक्स्ट रंग सेट करना का अर्थ है `Color` ऑब्जेक्ट को परिभाषित करना, जिसे रेंडरिंग इंजन (यहाँ Aspose.Page) पेज पर अक्षर ड्रॉ करते समय उपयोग करता है। यह ऑपरेशन दृश्य रूप से अलग दस्तावेज़ बनाने के लिए आवश्यक है, विशेष रूप से जब आपको प्रोग्रामेटिकली **generate postscript file** करने की आवश्यकता हो।

## Why use Aspose.Page for Java?
- **Full control** PostScript जनरेशन पर, बिना किसी नेेटिव इंटरप्रेटर की आवश्यकता के।  
- **Support for both system and external fonts**, जिससे आप अपनी ज़रूरत के किसी भी टाइपोग्राफी को एम्बेड कर सकते हैं।  
- **Easy API** फ़िल, आउटलाइन, और **fill and stroke text** करने के लिए, जिससे आपको स्टाइलिंग में लचीलापन मिलता है।  
- **Cross‑platform** संगतता – एक बार लिखें, जहाँ भी Java चलता है वहाँ चलाएँ।  

## Prerequisites
Before diving in, make sure you have:

- Java प्रोग्रामिंग का बुनियादी ज्ञान।  
- Aspose.Page for Java लाइब्रेरी स्थापित हो। आप इसे [Aspose.Page for Java download page](https://releases.aspose.com/page/java/) से डाउनलोड कर सकते हैं।  
- निर्दिष्ट फ़ोल्डर में आवश्यक फ़ॉन्ट्स उपलब्ध हों। अतिरिक्त विवरण के लिए [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) देखें।  

## Import Packages
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

## Step 1: Set Up the Document
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

## How to Set Text Color Java Using System Font
Now we demonstrate **set text color java** with a system‑provided font.

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
You can also **change font size java** and use a custom font stored in your fonts folder.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Outlining (Stroke) Text – Apply Stroke Text
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

## Outlining Text with Custom Font
The same technique works with custom fonts.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Step 6: Save the Document
Finally, close the page and write the file to disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Why This Matters
**set text color java** को फ़िल के साथ मिलाकर उपयोग करने से आपको अंतिम PostScript आउटपुट पर पूर्ण कलात्मक नियंत्रण मिलता है। चाहे आप इनवॉइस, प्रमाणपत्र, या कस्टम ग्राफ़िक्स जेनरेट कर रहे हों, **create postscript document** फ़ाइलों को सटीक स्टाइलिंग के साथ बनाना ग्राफ़िक एडिटर्स में पोस्ट‑प्रोसेसिंग की आवश्यकता को कम करता है।

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Font not found** | सुनिश्चित करें कि फ़ॉन्ट फ़ाइल `necessary_fonts` में रखी गई है और फ़ोल्डर पाथ `options.setAdditionalFontsFolders` के माध्यम से सही ढंग से जोड़ा गया है। |
| **Color not applied** | जाँचें कि आप `fillText` या `outlineText` के उस ओवरलोड को कॉल कर रहे हैं जिसमें `Color` आर्ग्यूमेंट शामिल है। |
| **Stroke appears too thin** | `BasicStroke` की चौड़ाई बढ़ाएँ (उदाहरण के लिए, `new BasicStroke(3)`)। |
| **Document not opening** | पुष्टि करें कि उत्पन्न `.ps` फ़ाइल सही एक्सटेंशन के साथ सेव हुई है और आपका व्यूअर PostScript को सपोर्ट करता है। |

## Frequently Asked Questions

**Q:** क्या मैं Aspose.Page for Java के साथ अपने कस्टम फ़ॉन्ट्स का उपयोग कर सकता हूँ?  
A: हाँ, आप `DrFont` क्लास में फ़ॉन्ट का नाम और साइज निर्दिष्ट करके **use custom fonts java** कर सकते हैं।

**Q:** मैं टेक्स्ट का रंग कैसे बदलूँ?  
A: फ़िल या आउटलाइन करते समय `Color` क्लास का उपयोग करके इच्छित रंग सेट कर सकते हैं।

**Q:** क्या PostScript दस्तावेज़ में कई पेज जोड़ना संभव है?  
A: बिल्कुल! आप दस्तावेज़ निर्माण और सेव करने के चरणों को दोहराकर कई पेज बना सकते हैं।

**Q:** `ExternalFontCache` क्लास का उद्देश्य क्या है?  
A: `ExternalFontCache` कस्टम फ़ॉन्ट्स को फ़ेच करने के लिए उपयोग किया जाता है, जिससे वे टेक्स्ट मैनिपुलेशन के लिए उपलब्ध रहें।

**Q:** क्या मैं आउटलाइन किए गए टेक्स्ट पर विभिन्न स्ट्रोक्स लागू कर सकता हूँ?  
A: हाँ, आप `Stroke` क्लास और `Color` क्लास का उपयोग करके स्ट्रोक की चौड़ाई और रंग को कस्टमाइज़ कर सकते हैं।

## Conclusion
बधाई हो! अब आप **set text color java**, **change font size java**, **apply fill and stroke text**, और Aspose.Page for Java का उपयोग करके **create postscript document** फ़ाइलें बनाना जानते हैं। विभिन्न फ़ॉन्ट्स, रंगों, और आउटलाइन स्टाइल्स के साथ प्रयोग करें ताकि पेशेवर‑दिखावट वाला PostScript आउटपुट प्राप्त हो सके।

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}