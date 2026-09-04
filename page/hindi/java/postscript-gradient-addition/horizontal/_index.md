---
date: 2026-09-04
description: Aspose.Page for Java के साथ Linear Gradient Paint Java का उपयोग करके
  PostScript फ़ाइल में horizontal gradient java कैसे बनाएं, सीखें। चरण‑दर‑चरण कोड,
  सामान्य समस्याएँ, और अक्सर पूछे जाने वाले प्रश्न।
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: Aspose का उपयोग करके PostScript में horizontal gradient java बनाएं
og_description: Linear Gradient Paint Java के साथ PostScript में horizontal gradient
  java बनाएं। यह Aspose.Page ट्यूटोरियल आपको सटीक चरण, आवश्यकताएँ, और 15 मिनट से कम
  समय में समस्या निवारण सुझाव दिखाता है।
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: Aspose का उपयोग करके PostScript में horizontal gradient java बनाएं
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: Aspose का उपयोग करके PostScript में horizontal gradient java बनाएं
url: /hi/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript में Linear Gradient Paint का उपयोग करके क्षैतिज ग्रेडिएंट कैसे जोड़ें

## परिचय
इस व्यापक ट्यूटोरियल में आप **कैसे बनाएं क्षैतिज ग्रेडिएंट जावा** सीखेंगे, जो Aspose.Page for Java के साथ आने वाली **Linear Gradient Paint Java** क्लास का उपयोग करके PostScript दस्तावेज़ में किया जाता है। हम हर चरण को विस्तार से बताएँगे—प्रोजेक्ट सेटअप से लेकर आकार और टेक्स्ट दोनों पर ग्रेडिएंट रेंडर करने तक—ताकि आप कुछ ही मिनटों में परिष्कृत, प्रिंट‑तैयार ग्राफ़िक्स बना सकें। चाहे आप रिपोर्टिंग इंजन, डिज़ाइन‑ऑटोमेशन टूल, या कस्टम प्रिंटर ड्राइवर बना रहे हों, यह गाइड आपको आवश्यक सटीक कोड प्रदान करता है।

## त्वरित उत्तर
- **कौनसी लाइब्रेरी आवश्यक है?** Aspose.Page for Java (में Linear Gradient Paint Java शामिल है)।  
- **इम्प्लीमेंटेशन में कितना समय लगता है?** बुनियादी क्षैतिज ग्रेडिएंट के लिए लगभग 10‑15 मिनट।  
- **क्या मुझे लाइसेंस चाहिए?** प्रोडक्शन उपयोग के लिए अस्थायी या पूर्ण लाइसेंस आवश्यक है।  
- **कौनसा JDK संस्करण काम करता है?** Java 8 या उससे नया।  
- **क्या मैं ग्रेडिएंट को दोनों आकार और टेक्स्ट पर उपयोग कर सकता हूँ?** हाँ – वही `LinearGradientPaint` इंस्टेंस आकारों को भर सकता है और टेक्स्ट स्ट्रोक या फ़िल में लागू किया जा सकता है।

## क्षैतिज ग्रेडिएंट क्या है और इसे क्यों उपयोग करें?
एक क्षैतिज ग्रेडिएंट वस्तु के बाएँ किनारे से दाएँ किनारे तक रंगों को मिलाता है, जिससे एक सुगम संक्रमण बनता है जो गहराई और दृश्य आकर्षण जोड़ता है। यह आधुनिक UI घटकों, हाइलाइटेड हेडिंग्स, या PDF या PostScript रिपोर्ट में सूक्ष्म बैकग्राउंड शेडिंग के लिए आदर्श है। **Linear Gradient Paint Java** का उपयोग करके आप प्रारंभ‑और‑अंत रंग, अपारदर्शिता, और स्केलिंग को सटीक रूप से नियंत्रित कर सकते हैं, जिससे परिणाम किसी भी डिवाइस या प्रिंटर पर स्पष्ट दिखे।

## पूर्वापेक्षाएँ
कोड में डुबकी लगाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- Java Development Kit (JDK) आपके मशीन पर स्थापित हो।  
- Aspose.Page for Java लाइब्रेरी। आप इसे [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) से डाउनलोड कर सकते हैं।

## पैकेज इम्पोर्ट करें
अपने Java प्रोजेक्ट में आवश्यक पैकेज इम्पोर्ट करके शुरू करें। ये इम्पोर्ट्स आपको ग्राफ़िक्स प्रिमिटिव्स, ग्रेडिएंट हैंडलिंग, और Aspose.Page API तक पहुँच प्रदान करते हैं।

`PsDocument` क्लास एक PostScript दस्तावेज़ का प्रतिनिधित्व करता है जिस पर आप ग्राफ़िक्स ड्रॉ कर सकते हैं।  

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

## चरण 1: एक आयत बनाएं
पहले, आउटपुट स्ट्रीम, दस्तावेज़, और एक आयत सेट करें जो ग्रेडिएंट को होस्ट करेगा।

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

## चरण 2: क्षैतिज रैखिक ग्रेडिएंट पेंट बनाएं
`LinearGradientPaint` वह मुख्य क्लास है जो रैखिक रंग संक्रमण को परिभाषित करता है।  
`LinearGradientPaint` क्लास एक पेंट ऑब्जेक्ट का प्रतिनिधित्व करता है जो सीधी रेखा के साथ ग्रेडिएंट रेंडर करता है; आप प्रारंभ/अंत बिंदु, रंग स्टॉप, और वैकल्पिक `AffineTransform` को अपने आकार के अनुसार स्केल कर सकते हैं।

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

## चरण 3: आयत को भरें
अब हम अभी परिभाषित किए गए ग्रेडिएंट से आयत को भरते हैं।

```java
// Fill the rectangle
document.fill(rectangle);
```

## चरण 4: ग्रेडिएंट के साथ टेक्स्ट भरें
आप वही ग्रेडिएंट टेक्स्ट पर भी लागू कर सकते हैं, जिससे एक प्रभावशाली दृश्य प्रभाव बनता है।

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## चरण 5: ग्रेडिएंट के साथ टेक्स्ट को स्ट्रोक करें
अंत में, ग्रेडिएंट को स्ट्रोक रंग के रूप में उपयोग करके टेक्स्ट को आउटलाइन करें।

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## सामान्य समस्याएँ और समाधान
| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| ग्रेडिएंट खिंचा हुआ दिखता है | गलत `AffineTransform` स्केलिंग | सुनिश्चित करें कि ट्रांसफ़ॉर्म की चौड़ाई और ऊँचाई आयत के आयामों (उदाहरण में 200 × 100) के बराबर हों। |
| रंग फीके दिखते हैं | अल्फा मान बहुत कम सेट किया गया है | `new Color(r,g,b,alpha)` में अल्फा घटक (चौथा मान) बढ़ाएँ। |
| टेक्स्ट दिखाई नहीं दे रहा है | टेक्स्ट ड्रॉ करने से पहले पेंट सेट नहीं किया गया | `document.setPaint(paint)` को किसी भी `fillAndStrokeText` या `outlineText` कॉल से **पहले** कॉल करें। |

## अक्सर पूछे जाने वाले प्रश्न
**Q:** क्या मैं Aspose.Page for Java को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?  
**A:** हाँ, Aspose.Page for Java को व्यावसायिक प्रोजेक्ट्स में उपयोग किया जा सकता है। लाइसेंसिंग विवरण के लिए, [Aspose.Purchase](https://purchase.aspose.com/buy) पेज देखें।

**Q:** क्या कोई मुफ्त ट्रायल उपलब्ध है?  
**A:** हाँ, आप Aspose.Page for Java का मुफ्त ट्रायल [Aspose.Page for Java free trial](https://releases.aspose.com/) पेज पर प्राप्त कर सकते हैं।

**Q:** अतिरिक्त दस्तावेज़ीकरण और समर्थन कहाँ मिल सकता है?  
**A:** व्यापक संसाधनों के लिए [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) देखें। समुदाय सहायता के लिए, [Aspose.Page forum](https://forum.aspose.com/c/page/39) देखें।

**Q:** मैं अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?  
**A:** आप अस्थायी लाइसेंस [Aspose.Purchase temporary license page](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

**Q:** Aspose.Page for Java की सिस्टम आवश्यकताएँ क्या हैं?  
**A:** विस्तृत सिस्टम आवश्यकताओं के लिए [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) देखें।

**अंतिम अपडेट:** 2026-09-04  
**परीक्षण किया गया:** Aspose.Page for Java 24.11  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Java में PostScript ग्रेडिएंट बनाएं – वर्टिकल ग्रेडिएंट जोड़ें](/page/java/postscript-gradient-addition/vertical/)
- [कैसे जोड़ें ग्रेडिएंट: Java PostScript में डायगोनल ग्रेडिएंट Aspose.Page Java का उपयोग करके](/page/java/postscript-gradient-addition/diagonal/)
- [PostScript ग्रेडिएंट बनाएं – Java में रेडियल ग्रेडिएंट](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}