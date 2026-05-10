---
date: 2026-03-13
description: Aspose.Page का उपयोग करके जावा में XPS दस्तावेज़ों में ग्रेडिएंट कैसे
  जोड़ें और शानदार क्षैतिज प्रभावों के लिए ग्रेडिएंट स्टॉप्स को कैसे कस्टमाइज़ करें,
  सीखें।
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: जावा XPS में ग्रेडिएंट कैसे जोड़ें – क्षैतिज ग्रेडिएंट
url: /hi/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ग्रेडिएंट कैसे जोड़ें – जावा XPS में क्षैतिज ग्रेडिएंट

## Introduction
जावा का उपयोग करके XPS दस्तावेज़ में **ग्रेडिएंट कैसे जोड़ें** इस चरण‑दर‑चरण गाइड में आपका स्वागत है। इस ट्यूटोरियल में आप सीखेंगे कि क्षैतिज ग्रेडिएंट कैसे जोड़ें, यह दृश्य परिष्कार के लिए क्यों महत्वपूर्ण है, और सटीक रंग नियंत्रण के लिए **ग्रेडिएंट स्टॉप्स को कैसे कस्टमाइज़ करें**। Aspose.Page for Java XPS (XML Paper Specification) दस्तावेज़ों के साथ काम करना आसान बनाता है, जिससे आप डिज़ाइन पर ध्यान केंद्रित कर सकते हैं न कि लो‑लेवल फ़ाइल हैंडलिंग पर।

## Quick Answers
- **कौनसी लाइब्रेरी चाहिए?** Aspose.Page for Java  
- **कौनसा जावा संस्करण काम करता है?** कोई भी Java 8+ रनटाइम  
- **क्या लाइसेंस चाहिए?** विकास के लिए फ्री ट्रायल काम करता है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है  
- **क्या मैं ग्रेडिएंट दिशा बदल सकता हूँ?** हाँ – बस लीनियर ब्रश के शुरू/अंत बिंदुओं को बदलें  
- **क्या कई ग्रेडिएंट जोड़ना संभव है?** बिल्कुल – विभिन्न ब्रश के साथ पाथ निर्माण चरणों को दोहराएँ  

## What is a Horizontal Gradient in XPS?
एक क्षैतिज ग्रेडिएंट एक आकार के बाएँ से दाएँ तक रंगों का सुगम संक्रमण है। XPS में इसे एक लीनियर ग्रेडिएंट ब्रश द्वारा दर्शाया जाता है जो परिभाषित **ग्रेडिएंट स्टॉप्स** के बीच इंटरपोलेशन करता है। यह दृश्य प्रभाव आमतौर पर बैनर, बटन और बैकग्राउंड फ़िल्स में उपयोग किया जाता है।

## Why Use Aspose.Page for Java?
- **पूर्ण XPS समर्थन** – थर्ड‑पार्टी टूल्स के बिना बनाएं, संपादित करें और रेंडर करें।  
- **सरल API** – `XpsDocument`, `XpsPath`, और `XpsGradientBrush` जैसे हाई‑लेवल ऑब्जेक्ट्स XML जटिलता को छुपाते हैं।  
- **प्रदर्शन** – बड़े दस्तावेज़ों और बैच प्रोसेसिंग के लिए अनुकूलित।  

## Prerequisites
Before you begin, ensure you have:

1. **Java Development Environment** – Install the latest JDK from [java.com](https://www.java.com).  
2. **Aspose.Page for Java Library** – Download the JAR from the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  

## Import Packages
Start by importing the necessary classes. These imports give you access to document creation, gradient handling, and basic geometry.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Step 1: Initialize the XPS Document
Create a fresh `XpsDocument` instance and point to the folder where you want to save the result.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Step 2: Create Horizontal Gradient
Define a list of **gradient stops** that control the color and position of each transition point. The example below builds a vibrant rainbow‑like gradient.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### How to customize gradient stops
- **रंग** – किसी भी ARGB मान को सेट करने के लिए `doc.createColor(alpha, red, green, blue)` का उपयोग करें।  
- **स्थिति** – दूसरा आर्ग्यूमेंट (`float` 0 और 1 के बीच) निर्धारित करता है कि ग्रेडिएंट लाइन पर स्टॉप कहाँ दिखाई देगा। इन मानों को समायोजित करके रंगों को बाएँ या दाएँ शिफ्ट करें।

## Step 3: Add Path with Gradient
Create a rectangular path, apply a transform if needed, and fill it with the linear gradient brush. The brush uses two points (`(10,0)` to `(228,0)`) to produce a horizontal effect. Because the Y‑coordinates are identical, this brush acts as a **horizontal gradient brush**.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**प्रो टिप:** कई पाथ्स के लिए वही `stops` सूची पुनः उपयोग करने से प्रदर्शन में सुधार हो सकता है, लेकिन नई स्टॉप्स जोड़ने से पहले `clear()` करना याद रखें।

## Step 4: Save the Document
Persist the XPS file to disk. You can now open it with any XPS viewer to see the horizontal gradient in action.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## How to Apply Multiple Gradients
If you want to **apply multiple gradients** within the same XPS document, simply repeat the “Create Horizontal Gradient” and “Add Path with Gradient” steps for each new shape. Use a fresh list of `XpsGradientStop` objects (or clear the existing list) and assign a new `LinearGradientBrush` with its own start/end points. This approach lets you layer gradients, create complex backgrounds, or highlight different UI elements in a single page.

## Why This Matters – Benefits of the Horizontal Gradient Brush
- **दृश्य गहराई:** एक क्षैतिज ग्रेडिएंट ब्रश अतिरिक्त छवियों के बिना सूक्ष्म त्रि‑आयामी एहसास जोड़ता है।  
- **फ़ाइल आकार दक्षता:** ग्रेडिएंट्स को वेक्टर परिभाषाओं के रूप में संग्रहीत किया जाता है, जिससे XPS फ़ाइल हल्की रहती है।  
- **स्केलेबिलिटी:** चूँकि ग्रेडिएंट वेक्टर‑आधारित है, यह हाई‑रिज़ॉल्यूशन डिस्प्ले पर साफ़ स्केल होता है।  

## Common Issues & Solutions
| समस्या | कारण | समाधान |
|-------|--------|-----|
| ग्रेडिएंट सॉलिड दिख रहा है | कोई ग्रेडिएंट स्टॉप नहीं जोड़े गए या ब्रश सेट नहीं है | सुनिश्चित करें कि `path.setFill(...)` एक `LinearGradientBrush` का उपयोग करता है और स्टॉप्स को `getGradientStops().addAll(stops)` के माध्यम से जोड़ा गया है। |
| रंग म्यूट दिख रहे हैं | गलत अल्फा मान (पहला पैरामीटर) | यदि पारदर्शिता नहीं चाहिए तो पूर्णतः अपारदर्शी रंगों के लिए `255` उपयोग करें। |
| पाथ का आकार गलत है | ट्रांसफ़ॉर्म मैट्रिक्स मान गलत हैं | मैट्रिक्स पैरामीटर्स (`scaleX, skewY, skewX, scaleY, translateX, translateY`) को समायोजित करें। |

## Frequently Asked Questions

**Q: क्या मैं एक ही XPS दस्तावेज़ में कई ग्रेडिएंट लागू कर सकता हूँ?**  
A: हाँ, आप कई पाथ्स जोड़ सकते हैं, प्रत्येक का अपना ग्रेडिएंट ब्रश होगा, जिससे जटिल लेयरड डिज़ाइन बन सकते हैं।

**Q: क्या Aspose.Page नवीनतम जावा संस्करणों के साथ संगत है?**  
A: Aspose.Page for Java नियमित रूप से अपडेट किया जाता है और Java 8 और उसके बाद के संस्करणों के साथ काम करता है।

**Q: क्या Aspose.Page में अन्य ग्रेडिएंट प्रकार उपलब्ध हैं?**  
A: लीनियर ग्रेडिएंट के अलावा, Aspose.Page रेडियल ग्रेडिएंट भी सपोर्ट करता है जो गोलाकार रंग संक्रमण के लिए होते हैं।

**Q: क्या मैं ग्रेडिएंट स्टॉप्स के रंग और स्थितियों को कस्टमाइज़ कर सकता हूँ?**  
A: बिल्कुल! आपके पास प्रत्येक स्टॉप के ARGB रंग और उसकी सापेक्ष स्थिति (0‑1 रेंज) पर पूर्ण नियंत्रण है।

**Q: क्या Aspose.Page के लिए कोई कम्युनिटी फ़ोरम है जहाँ मैं मदद ले सकूँ?**  
A: हाँ, आप [Aspose.Page फ़ोरम](https://forum.aspose.com/c/page/39) पर जाकर समुदाय से जुड़ सकते हैं और सहायता प्राप्त कर सकते हैं।

---

**Last Updated:** 2026-03-13  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}