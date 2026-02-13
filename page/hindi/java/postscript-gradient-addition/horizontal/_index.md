---
date: 2026-02-13
description: Aspose.Page for Java का उपयोग करके Linear Gradient Paint Java के साथ
  Java PostScript में ग्रेडिएंट कैसे जोड़ें, सीखें।
linktitle: How to Add Gradient in Java PostScript with Linear Gradient Paint
second_title: Aspose.Page Java API
title: जावा पोस्टस्क्रिप्ट में लीनियर ग्रेडिएंट पेंट के साथ ग्रेडिएंट कैसे जोड़ें
url: /hi/java/postscript-gradient-addition/horizontal/
weight: 11
---

 URLs.

Last Updated etc.

Let's do translation.

Make sure to keep **bold** formatting.

Also keep code block placeholders as they are.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript में Linear Gradient Paint के साथ ग्रेडिएंट कैसे जोड़ें

## Introduction
इस व्यापक ट्यूटोरियल में आप **ग्रेडिएंट कैसे जोड़ें** यह जानेंगे, Java का उपयोग करके एक PostScript दस्तावेज़ में। हम **Linear Gradient Paint Java** क्लास का उपयोग करके एक सुंदर क्षैतिज ग्रेडिएंट बनाना सीखेंगे, जो रंग संक्रमणों पर पिक्सेल‑परफेक्ट नियंत्रण देता है। Aspose.Page for Java के साथ आप ग्रेडिएंट को **आकारों और** टेक्स्ट दोनों पर रेंडर कर सकते हैं, जिससे आपके दस्तावेज़ों को एक पॉलिश्ड, आकर्षक लुक मिलता है।

## Quick Answers
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java (Linear Gradient Paint Java को सपोर्ट करता है)।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बेसिक ग्रेडिएंट के लिए लगभग 10‑15 मिनट।  
- **क्या मुझे लाइसेंस चाहिए?** प्रोडक्शन उपयोग के लिए एक टेम्पररी या फुल लाइसेंस आवश्यक है।  
- **कौन सा JDK संस्करण काम करता है?** Java 8 या नया।  
- **क्या मैं ग्रेडिएंट को आकारों और टेक्स्ट दोनों पर उपयोग कर सकता हूँ?** हाँ – आप एक ही ग्रेडिएंट से आकार भर सकते हैं और टेक्स्ट को स्ट्रोक या फ़िल कर सकते हैं।

## What is a Horizontal Gradient and Why Use It?
एक क्षैतिज ग्रेडिएंट बाएँ से दाएँ तक रंगों को स्मूदली ब्लेंड करता है, चाहे वह आकार हो या टेक्स्ट। यह आधुनिक UI एलिमेंट्स, हाइलाइटेड हेडिंग्स, या रिपोर्ट में सूक्ष्म बैकग्राउंड इफ़ेक्ट बनाने के लिए आदर्श है। **Linear Gradient Paint Java** का उपयोग करके आप सटीक स्टार्ट‑और‑एंड‑कलर, अपारदर्शिता, और स्केलिंग निर्धारित कर सकते हैं, जिससे परिणाम किसी भी डिवाइस पर स्पष्ट दिखे।

## Prerequisites
कोड में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हों:

- आपके मशीन पर Java Development Kit (JDK) इंस्टॉल हो।  
- Aspose.Page for Java लाइब्रेरी। आप इसे [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) से डाउनलोड कर सकते हैं।

## Import Packages
अपने Java प्रोजेक्ट में आवश्यक पैकेज इम्पोर्ट करके शुरू करें। ये इम्पोर्ट्स आपको ग्राफ़िक्स प्रिमिटिव्स, ग्रेडिएंट हैंडलिंग, और Aspose.Page API तक पहुंच देते हैं।

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Create a Rectangle
पहले, आउटपुट स्ट्रीम, डॉक्यूमेंट, और एक रेक्टैंगल सेट अप करें जो ग्रेडिएंट को होस्ट करेगा।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Step 2: Create Horizontal Linear Gradient Paint
यहाँ हम **Linear Gradient Paint Java** ऑब्जेक्ट बनाते हैं जो एक क्षैतिज रंग संक्रमण को परिभाषित करता है। `AffineTransform` ग्रेडिएंट को रेक्टैंगल की चौड़ाई और ऊँचाई के अनुसार स्केल करता है।

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Step 3: Fill the Rectangle
अब हम उस ग्रेडिएंट को रेक्टैंगल में फ़िल करते हैं जिसे हमने अभी परिभाषित किया है।

```java
// Fill the rectangle
document.fill(rectangle);
```

## Step 4: Fill a Text with the Gradient
आप वही ग्रेडिएंट टेक्स्ट पर भी लागू कर सकते हैं, जिससे एक प्रभावशाली विज़ुअल इफ़ेक्ट बनता है।

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Step 5: Stroke a Text with the Gradient
अंत में, टेक्स्ट को ग्रेडिएंट को स्ट्रोक कलर के रूप में उपयोग करके आउटलाइन करें।

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Common Issues and Solutions
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| ग्रेडिएंट स्ट्रेच्ड दिख रहा है | `AffineTransform` स्केलिंग गलत है | सुनिश्चित करें कि ट्रांसफ़ॉर्म की चौड़ाई और ऊँचाई रेक्टैंगल के आयाम (उदाहरण में 200 × 100) से मेल खाती हों। |
| रंग फीके लग रहे हैं | अल्फा वैल्यू बहुत कम सेट है | `new Color(r,g,b,alpha)` में अल्फा कॉम्पोनेंट को बढ़ाएँ। |
| टेक्स्ट दिखाई नहीं दे रहा | टेक्स्ट ड्रॉ करने से पहले पेंट सेट नहीं किया गया | `document.setPaint(paint)` को किसी भी `fillAndStrokeText` या `outlineText` कॉल से **पहले** कॉल करें। |

## Frequently Asked Questions
**Q:** क्या मैं Aspose.Page for Java को कमर्शियल प्रोजेक्ट्स में उपयोग कर सकता हूँ?  
**A:** हाँ, Aspose.Page for Java को कमर्शियल प्रोजेक्ट्स में उपयोग किया जा सकता है। लाइसेंसिंग विवरण के लिए देखें [Aspose.Purchase](https://purchase.aspose.com/buy)।

**Q:** क्या कोई फ्री ट्रायल उपलब्ध है?  
**A:** हाँ, आप Aspose.Page for Java का फ्री ट्रायल [यहाँ](https://releases.aspose.com/) से एक्सेस कर सकते हैं।

**Q:** अतिरिक्त डॉक्यूमेंटेशन और सपोर्ट कहाँ मिलेंगे?  
**A:** व्यापक संसाधनों के लिए [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) देखें। कम्युनिटी सपोर्ट के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) देखें।

**Q:** मैं टेम्पररी लाइसेंस कैसे प्राप्त करूँ?  
**A:** आप टेम्पररी लाइसेंस [Aspose.Purchase](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

**Q:** Aspose.Page for Java की सिस्टम रीक्वायरमेंट्स क्या हैं?  
**A:** विस्तृत सिस्टम रीक्वायरमेंट्स के लिए देखें [documentation](https://reference.aspose.com/page/java/)।

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}