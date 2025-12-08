---
date: 2025-12-08
description: Aspose.Page के साथ Java PostScript में रेडियल ग्रेडिएंट कैसे जोड़ें,
  सीखें। यह चरण‑दर‑चरण गाइड आपको आपके दस्तावेज़ों में शानदार ग्रेडिएंट प्रभाव बनाने
  का तरीका दिखाता है।
language: hi
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: Aspose.Page के साथ Java PostScript में रेडियल ग्रेडिएंट कैसे जोड़ें
url: /java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript में Radial Gradient कैसे जोड़ें Aspose.Page के साथ

## Introduction
यदि आपको कभी अपने PostScript आउटपुट में एक स्मूथ, आकर्षक रंग संक्रमण देना आवश्यक रहा हो, तो **how to add radial gradient** सीखना शुरू करने के लिए बिल्कुल सही जगह है। इस ट्यूटोरियल में हम हर कदम से गुजरेंगे जो एक सुंदर radial gradient वाला PostScript फ़ाइल उत्पन्न करने के लिए आवश्यक है, **Aspose.Page for Java** लाइब्रेरी का उपयोग करके। अंत तक आप API को समझेंगे, एक पूर्ण runnable उदाहरण देखेंगे, और किसी भी डिज़ाइन के अनुसार रंग, स्थिति और त्रिज्या को कैसे ट्यून करें, यह जानेंगे।

## Quick Answers
- **What library creates radial gradients in PostScript?** Aspose.Page for Java.  
- **How long does the implementation take?** बेसिक उदाहरण के लिए लगभग 10‑15 मिनट।  
- **Do I need a license to run the code?** विकास के लिए फ्री ट्रायल काम करता है; प्रोडक्शन के लिए कमर्शियल लाइसेंस आवश्यक है।  
- **Which Java version is supported?** Java 8 या उससे ऊपर।  
- **Can I change the gradient’s shape?** हाँ – `RadialGradientPaint` कन्स्ट्रक्टर में radius और center point को समायोजित करें।

## What is a Radial Gradient?
एक radial gradient रंगों को केंद्रीय बिंदु से बाहर की ओर फैलाता है, धीरे‑धीरे किनारों की ओर मिश्रित करता है। लीनियर ग्रेडिएंट के विपरीत, रंग संक्रमण एक वृत्तीय (या अंडाकार) पैटर्न का अनुसरण करता है, जो हाइलाइट्स, स्पॉटलाइट्स या सॉफ्ट बैकग्राउंड फ़िल्स के लिए आदर्श है।

## Why Use Aspose.Page for Radial Gradients?
- **Full control over PostScript output** – लो‑लेवल PS कमांड्स को हाथ से लिखने की जरूरत नहीं।  
- **Cross‑platform** – वह किसी भी OS पर काम करता है जहाँ Java चलती है।  
- **Rich color management** – कई color stops, विभिन्न color spaces, और cycle methods को सपोर्ट करता है।  
- **Integration‑ready** – टेक्स्ट, इमेजेज और वेक्टर शैप्स जैसे अन्य Aspose.Page फीचर्स के साथ संयोजन आसान।

## Prerequisites
कोड में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित उपलब्ध हैं:

- **Java Development Kit (JDK) 8+** – `java -version` से सत्यापित करें।  
- **Aspose.Page for Java** – आधिकारिक [Aspose.Page download page](https://releases.aspose.com/page/java/) से नवीनतम JAR डाउनलोड करें।  
- **IDE of your choice** – Eclipse, IntelliJ IDEA, या Java एक्सटेंशन वाले VS Code।  
- **A writable folder** – जहाँ उत्पन्न `.ps` फ़ाइल सहेजी जाएगी।

## Import Packages
पहले उन क्लासेज़ को इम्पोर्ट करें जिनकी हमें आवश्यकता होगी। `java.awt` पैकेज ग्रेडिएंट पेंट ऑब्जेक्ट्स प्रदान करता है, जबकि `com.aspose.eps` PostScript डॉक्यूमेंट हैंडलिंग क्लासेज़ रखता है।

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step‑by‑Step Guide

### Step 1: Create a Rectangle and Open a PS Document
हम आउटपुट स्ट्रीम बनाते हैं, पेज साइज (डिफ़ॉल्ट A4) कॉन्फ़िगर करते हैं, और एक रेक्टेंगल परिभाषित करते हैं जो ग्रेडिएंट को होस्ट करेगा।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Pro tip:** रेक्टेंगल के कोऑर्डिनेट्स (`200, 100, 200, 200`) को समायोजित करके ग्रेडिएंट को पेज पर कहीं भी रख सकते हैं।

### Step 2: Define Colors and Fractions
एक radial gradient *color stops* (रंग) और *fractions* (उन स्टॉप्स की सापेक्ष स्थितियाँ) से बनता है। यहाँ हम छह रंगों और उनके संबंधित fractions की एरे बनाते हैं।

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Why this matters:** `fractions` को ट्यून करके आप रंगों के संक्रमण की गति नियंत्रित कर सकते हैं, जिससे सूक्ष्म या नाटकीय प्रभाव मिलते हैं।

### Step 3: Create Radial Gradient Paint
अब हम `RadialGradientPaint` ऑब्जेक्ट बनाते हैं। कन्स्ट्रक्टर में ग्रेडिएंट का केंद्र बिंदु, radius, फोकस पॉइंट, fractions, colors, cycle method, color space, और वैकल्पिक transform शामिल होते हैं।

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Note:** यदि अतिरिक्त स्केलिंग या रोटेशन की आवश्यकता नहीं है तो `transform` को `null` रखा जा सकता है। `AffineTransform` के साथ प्रयोग करके skewed ग्रेडिएंट बना सकते हैं।

### Step 4: Set Paint and Fill the Rectangle
पेंट तैयार होने के बाद, हम `PsDocument` को इसे उपयोग करने के लिए सेट करते हैं और पहले परिभाषित रेक्टेंगल को भरते हैं।

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

इस चरण पर PostScript पेज में वह रेक्टेंगल स्मूथली radial gradient से भर गया है जिसे हमने कॉन्फ़िगर किया था।

### Step 5: Close and Save the Document
अंत में वर्तमान पेज को बंद करें और फ़ाइल को डिस्क पर लिखें।

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

`RadialGradient1_outPS.ps` को किसी भी PostScript व्यूअर (जैसे Ghostscript) में खोलें और आप देखेंगे कि ग्रेडिएंट ठीक उसी तरह रेंडर हुआ है जैसा हमने परिभाषित किया था।

## Common Issues & Solutions
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Gradient appears as a solid color | `fractions` array does not start at `0.0f` or end at `1.0f` | सुनिश्चित करें कि पहला fraction `0.0f` और अंतिम `1.0f` हो। |
| Colors look washed out | Using the wrong `ColorSpaceType` | अधिक जीवंत आउटपुट के लिए `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` पर स्विच करें। |
| No output file generated | `FileOutputStream` path is invalid or not writable | Verify `dataDir` exists and the application has write permissions. |

## Frequently Asked Questions

**Q: Can I use Aspose.Page for Java in commercial projects?**  
A: हाँ। प्रोडक्शन उपयोग के लिए कमर्शियल लाइसेंस आवश्यक है। आप इसे [Aspose licensing page](https://purchase.aspose.com/buy) से खरीद सकते हैं।

**Q: Where can I find the official API reference?**  
A: पूरी डॉक्यूमेंटेशन यहाँ उपलब्ध है: [here](https://reference.aspose.com/page/java/)।

**Q: Is a free trial available for testing?**  
A: बिल्कुल। ट्रायल संस्करण को [Aspose.Page releases page](https://releases.aspose.com/) से डाउनलोड करें।

**Q: How do I obtain a temporary license for evaluation?**  
A: एक टेम्पररी लाइसेंस यहाँ से अनुरोध किया जा सकता है: [here](https://purchase.aspose.com/temporary-license/)।

**Q: Where can I get community support?**  
A: Aspose.Page कम्युनिटी फ़ोरम में शामिल हों: [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39)।

## Conclusion
अब आप **how to add radial gradient** को Java PostScript डॉक्यूमेंट में Aspose.Page का उपयोग करके जानते हैं। रेक्टेंगल आकार, color stops, और gradient radius को समायोजित करके आप अनगिनत विज़ुअल इफ़ेक्ट बना सकते हैं—सूक्ष्म बैकग्राउंड फ़िल से लेकर बोल्ड स्पॉटलाइट ग्राफ़िक्स तक। विभिन्न `AffineTransform` मानों के साथ प्रयोग करके ग्रेडिएंट को घुमा या तिरछा कर सकते हैं, और इस तकनीक को टेक्स्ट और इमेजेज़ के साथ मिलाकर richer PDF या EPS आउटपुट बना सकते हैं।

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}