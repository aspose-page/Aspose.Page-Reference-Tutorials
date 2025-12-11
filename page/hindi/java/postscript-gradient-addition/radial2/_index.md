---
date: 2025-12-08
description: Aspose.Page का उपयोग करके Java PostScript में रेडियल ग्रेडिएंट उदाहरण
  कैसे बनाएं, सीखें। पूर्ण कोड और समस्या निवारण के साथ चरण‑दर‑चरण गाइड।
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'रेडियल ग्रेडिएंट उदाहरण: Aspose.Page के साथ जावा पोस्टस्क्रिप्ट'
url: /hi/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Radial Gradient Example: Java PostScript with Aspose.Page

## Introduction
इस ट्यूटोरियल में आप Aspose.Page for Java का उपयोग करके एक PostScript दस्तावेज़ के लिए **रेडियल ग्रेडिएंट उदाहरण** बनाएँगे। हम प्रोजेक्ट सेट‑अप से लेकर एक सर्कल को स्मूथ रेडियल ग्रेडिएंट से भरने तक हर कदम को विस्तार से बताएँगे—ताकि आप अपने Java एप्लिकेशन में तुरंत आकर्षक ग्राफ़िक्स जोड़ सकें।

## Quick Answers
- **यह ट्यूटोरियल क्या बनाता है?** एक PostScript फ़ाइल (`.ps`) जिसमें रेडियल ग्रेडिएंट से भरा हुआ सर्कल होता है।  
- **कौन‑सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java (नवीनतम संस्करण)।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** लगभग 10‑15 मिनट एक कार्यशील उदाहरण के लिए।  
- **क्या लाइसेंस चाहिए?** प्रोडक्शन उपयोग के लिए एक टेम्पररी या फुल लाइसेंस आवश्यक है; विकास के लिए फ्री ट्रायल काम करता है।  
- **क्या कोड को PDF या SVG के लिए पुनः उपयोग किया जा सकता है?** हाँ—Aspose.Page न्यूनतम बदलावों के साथ कई आउटपुट फ़ॉर्मेट्स को सपोर्ट करता है।

## What Is a Radial Gradient?
रेडियल ग्रेडिएंट केंद्र बिंदु से बाहर की ओर रंगों को ट्रांज़िशन करता है, जिससे एक स्मूथ, सर्कुलर ब्लेंड बनता है। यह हाइलाइट्स, बटन बैकग्राउंड, या किसी भी विज़ुअल के लिए आदर्श है जिसे प्राकृतिक “ग्लो” इफ़ेक्ट चाहिए।

## Why Use Aspose.Page for Radial Gradients?
- **डिवाइस‑इंडिपेंडेंट रेंडरिंग** – PostScript, PDF, SVG, आदि पर समान रूप से काम करता है।  
- **पूर्ण Java इंटीग्रेशन** – कोई नेटिव कोड नहीं, सिर्फ साधारण Java APIs।  
- **हाई‑क्वालिटी आउटपुट** – एंटी‑एलियासिंग और कलर‑स्पेस कंट्रोल को सपोर्ट करता है।

## Prerequisites
शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

- Java प्रोग्रामिंग की बेसिक समझ।  
- आपके मशीन पर JDK 8 या नया इंस्टॉल हो।  
- Aspose.Page for Java लाइब्रेरी (डाउनलोड करें [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) से)।  

## Import Packages
सबसे पहले, उन क्लासेज़ को इम्पोर्ट करें जिनकी हमें आवश्यकता होगी। इनमें स्टैंडर्ड AWT ग्राफ़िक्स टाइप्स और Aspose.Page API शामिल हैं।

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Set Up Document Directory
उस फ़ोल्डर को परिभाषित करें जहाँ जेनरेट की गई PostScript फ़ाइल सेव होगी। प्लेसहोल्डर को अपने सिस्टम के वास्तविक पाथ से बदलें।

```java
String dataDir = "Your Document Directory";
```

## Step 2: Create Output Stream
एक `FileOutputStream` खोलें जो टार्गेट `.ps` फ़ाइल की ओर इशारा करता हो। यह स्ट्रीम Aspose.Page द्वारा जेनरेट किए गए बाइनरी डेटा को फीड करता है।

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Step 3: Create Save Options
`PsSaveOptions` का एक इंस्टेंस बनाएँ। आप पेज साइज, कम्प्रेशन आदि को कस्टमाइज़ कर सकते हैं, लेकिन इस उदाहरण के लिए डिफ़ॉल्ट ठीक हैं।

```java
PsSaveOptions options = new PsSaveOptions();
```

## Step 4: Create PS Document
`PsDocument` ऑब्जेक्ट बनाएँ, आउटपुट स्ट्रीम और सेव ऑप्शन्स पास करें। `false` फ्लैग Aspose.Page को ऑटोमैटिकली पेज खोलने से रोकता है (हम इसे मैन्युअली करेंगे)।

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 5: Create a Circle
हम `Ellipse2D.Float` का उपयोग करके एक सर्कल ड्रॉ करेंगे। पैरामीटर्स हैं `(x, y, width, height)`। `width = height` सेट करने से परफेक्ट सर्कल बनता है।

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Step 6: Define Gradient Colors
दो एरे तैयार करें: एक ग्रेडिएंट में दिखने वाले रंगों के लिए और दूसरा उनके संबंधित फ्रैक्शनल पोज़िशन (0 = सेंटर, 1 = एज) के लिए।

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Step 7: Create AffineTransform
`AffineTransform` ग्रेडिएंट को हमारे सर्कल में फिट करने के लिए स्केल और ट्रांसलेट करता है। मैट्रिक्स `(scaleX, 0, 0, scaleY, translateX, translateY)` यही काम करता है।

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Step 8: Create Radial Gradient Paint
अब हम `RadialGradientPaint` ऑब्जेक्ट बनाते हैं। यह सेंटर पॉइंट, रेडियस, फोकस पॉइंट, कलर फ्रैक्शन्स, कलर एरे, साइक्ल मेथड, कलर स्पेस और ऊपर परिभाषित ट्रांसफ़ॉर्म को लेता है।

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Step 9: Set Paint and Fill Circle
डॉक्यूमेंट पर ग्रेडिएंट पेंट लागू करें और पहले परिभाषित सर्कल को फ़िल करें। यह हमारे **रेडियल ग्रेडिएंट उदाहरण** का मुख्य भाग है।

```java
document.setPaint(paint);
document.fill(circle);
```

## Step 10: Close Page and Save Document
पेज को फाइनलाइज़ करें, कंटेंट को डिस्क पर लिखें, और स्ट्रीम को बंद करें। आपकी PostScript फ़ाइल अब किसी भी PS व्यूअर से देखी जा सकती है।

```java
document.closePage();
document.save();
```

Congratulations! You have successfully created a radial gradient example in Java PostScript using Aspose.Page.

## Common Issues and Solutions
| Problem | Solution |
|---------|----------|
| **FileNotFoundException** when opening the output stream | Verify that `dataDir` points to an existing folder and you have write permissions. |
| Gradient looks flat or missing | Ensure the `fractions` array matches the `colors` array length and that the `AffineTransform` scales correctly. |
| Colors appear inverted | Swap the order of colors in the `colors` array or adjust the `focus` point coordinates. |

## Frequently Asked Questions

**Q: Where can I find the documentation for Aspose.Page for Java?**  
A: The full API reference is available [here](https://reference.aspose.com/page/java/).

**Q: How can I download Aspose.Page for Java?**  
A: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).

**Q: Is there a free trial available?**  
A: Yes—download a trial version [here](https://releases.aspose.com/).

**Q: Can I obtain a temporary license for testing?**  
A: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Where can I get community support?**  
A: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

## Conclusion
इस गाइड में हमने Aspose.Page for Java का उपयोग करके एक PostScript दस्तावेज़ के लिए पूर्ण **रेडियल ग्रेडिएंट उदाहरण** बनाया। चरणों का पालन करके अब आपके पास जटिल ग्रेडिएंट बनाने का एक पुन: उपयोग योग्य पैटर्न है, जिसे आप PDF, SVG या अन्य सपोर्टेड फ़ॉर्मेट्स में भी एडेप्ट कर सकते हैं। विभिन्न रंगों, रेडियस और आकारों के साथ प्रयोग करें और अपने Java ग्राफ़िक्स प्रोजेक्ट्स को समृद्ध बनाएं।

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}