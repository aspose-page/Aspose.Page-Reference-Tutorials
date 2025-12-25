---
date: 2025-12-25
description: जावा में Aspose.Page का उपयोग करके XPS दस्तावेज़ों में ग्रेडिएंट कैसे
  जोड़ें और शानदार क्षैतिज प्रभावों के लिए ग्रेडिएंट स्टॉप्स को कैसे कस्टमाइज़ करें,
  यह सीखें।
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: जावा XPS में ग्रेडिएंट कैसे जोड़ें – क्षैतिज ग्रेडिएंट
url: /hi/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Add Gradient – Horizontal Gradient in Java XPS

## Introduction
इस चरण‑दर‑चरण गाइड में आपका स्वागत है, जहाँ आप **ग्रेडिएंट जोड़ना** सीखेंगे XPS दस्तावेज़ में Java का उपयोग करके। इस ट्यूटोरियल में आप सीखेंगे कि क्षैतिज ग्रेडिएंट कैसे जोड़ें, यह दृश्य परिष्कार के लिए क्यों महत्वपूर्ण है, और **ग्रेडिएंट स्टॉप्स** को सटीक रंग नियंत्रण के लिए कैसे **कस्टमाइज़** करें। Aspose.Page for Java XPS (XML Paper Specification) दस्तावेज़ों के साथ काम करना आसान बनाता है, जिससे आप डिज़ाइन पर ध्यान केंद्रित कर सकते हैं न कि लो‑लेवल फ़ाइल हैंडलिंग पर।

## Quick Answers
- **कौनसी लाइब्रेरी चाहिए?** Aspose.Page for Java  
- **कौनसा Java संस्करण काम करता है?** कोई भी Java 8+ रनटाइम  
- **क्या लाइसेंस चाहिए?** विकास के लिए मुफ्त ट्रायल चलती है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है  
- **क्या मैं ग्रेडिएंट की दिशा बदल सकता हूँ?** हाँ – केवल लीनियर ब्रश के प्रारंभ/समाप्त बिंदुओं को बदलें  
- **क्या कई ग्रेडिएंट जोड़ना संभव है?** बिल्कुल – विभिन्न ब्रश के साथ पाथ निर्माण चरणों को दोहराएँ  

## What is a Horizontal Gradient in XPS?
एक क्षैतिज ग्रेडिएंट का अर्थ है रंगों का बाएँ से दाएँ तक स्मूथ ट्रांज़िशन किसी आकार के भीतर। XPS में इसे लीनियर ग्रेडिएंट ब्रश द्वारा दर्शाया जाता है जो परिभाषित **ग्रेडिएंट स्टॉप्स** के बीच इंटरपोलेशन करता है। यह दृश्य प्रभाव आमतौर पर बैनर, बटन और बैकग्राउंड फ़िल्स में उपयोग किया जाता है।

## Why Use Aspose.Page for Java?
- **पूर्ण XPS समर्थन** – थर्ड‑पार्टी टूल्स के बिना बनाएं, संपादित करें और रेंडर करें।  
- **सरल API** – `XpsDocument`, `XpsPath`, और `XpsGradientBrush` जैसे हाई‑लेवल ऑब्जेक्ट्स XML जटिलता को छुपाते हैं।  
- **प्रदर्शन** – बड़े दस्तावेज़ों और बैच प्रोसेसिंग के लिए अनुकूलित।  

## Prerequisites
शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

1. **Java Development Environment** – नवीनतम JDK को [java.com](https://www.java.com) से इंस्टॉल करें।  
2. **Aspose.Page for Java Library** – JAR को [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) से डाउनलोड करें।  

## Import Packages
आवश्यक क्लासेज़ को इम्पोर्ट करके शुरू करें। ये इम्पोर्ट्स आपको दस्तावेज़ निर्माण, ग्रेडिएंट हैंडलिंग और बेसिक जियोमेट्री तक पहुँच प्रदान करते हैं।

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
एक नया `XpsDocument` इंस्टेंस बनाएँ और उस फ़ोल्डर को निर्दिष्ट करें जहाँ आप परिणाम सहेजना चाहते हैं।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Step 2: Create Horizontal Gradient
एक **ग्रेडिएंट स्टॉप्स** की सूची परिभाषित करें जो प्रत्येक ट्रांज़िशन पॉइंट के रंग और स्थिति को नियंत्रित करती है। नीचे दिया गया उदाहरण एक जीवंत इंद्रधनुष‑समान ग्रेडिएंट बनाता है।

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
- **Color** – किसी भी ARGB मान को सेट करने के लिए `doc.createColor(alpha, red, green, blue)` का उपयोग करें।  
- **Position** – दूसरा आर्गुमेंट (`0` और `1` के बीच `float`) निर्धारित करता है कि स्टॉप ग्रेडिएंट लाइन पर कहाँ दिखेगा। इन मानों को बदलकर रंगों को बाएँ या दाएँ शिफ्ट करें।

## Step 3: Add Path with Gradient
एक आयताकार पाथ बनाएँ, आवश्यकता अनुसार ट्रांसफ़ॉर्म लागू करें, और उसे लीनियर ग्रेडिएंट ब्रश से भरें। ब्रश दो बिंदुओं (`(10,0)` से `(228,0)`) का उपयोग करके क्षैतिज प्रभाव उत्पन्न करता है।

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Pro tip:** कई पाथ्स के लिए वही `stops` सूची पुन: उपयोग करने से प्रदर्शन बेहतर हो सकता है, लेकिन नई स्टॉप्स जोड़ने से पहले `clear()` करना न भूलें।

## Step 4: Save the Document
XPS फ़ाइल को डिस्क पर सहेजें। अब आप इसे किसी भी XPS व्यूअर में खोलकर क्षैतिज ग्रेडिएंट को देख सकते हैं।

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Common Issues & Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| Gradient appears solid | No gradient stops added or brush not set | Ensure `path.setFill(...)` uses a `LinearGradientBrush` and that stops are added via `getGradientStops().addAll(stops)`. |
| Colors look muted | Incorrect alpha value (first parameter) | Use `255` for fully opaque colors unless transparency is desired. |
| Path size is off | Transform matrix values are wrong | Adjust the matrix parameters (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Frequently Asked Questions

**Q: Can I apply multiple gradients in a single XPS document?**  
A: Yes, you can add multiple paths, each with its own gradient brush, to create complex layered designs.

**Q: Is Aspose.Page compatible with the latest Java versions?**  
A: Aspose.Page for Java is regularly updated and works with Java 8 and newer releases.

**Q: Are there other gradient types available in Aspose.Page?**  
A: Besides linear gradients, Aspose.Page also supports radial gradients for circular color transitions.

**Q: Can I customize the colors and positions of gradient stops?**  
A: Absolutely! You have full control over each stop’s ARGB color and its relative position (0‑1 range).

**Q: Is there a community forum for Aspose.Page where I can seek help?**  
A: Yes, you can visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to connect with the community and get assistance.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}