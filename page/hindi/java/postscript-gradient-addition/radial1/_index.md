---
date: 2026-09-09
description: Aspose.Page का उपयोग करके Java PostScript में radial gradient कैसे बनाएं,
  सीखें। यह चरण‑दर‑चरण गाइड आपको दिखाता है कि कैसे color stops gradient जोड़ें, radii
  सेट करें, और जल्दी से एक PS file जनरेट करें।
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Java में radial gradients में महारत हासिल करें
og_description: Aspose.Page का उपयोग करके Java PostScript में radial gradient कैसे
  बनाएं, सीखें। यह गाइड बताता है कि कैसे color stops gradient जोड़ें, radii सेट करें,
  और मिनटों में एक PS file जनरेट करें।
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Java PostScript में radial gradient कैसे बनाएं
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Java PostScript में radial gradient कैसे बनाएं
url: /hi/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript में Aspose.Page के साथ रेडियल ग्रेडिएंट कैसे बनाएं

## परिचय
यदि आपको PostScript फ़ाइल के अंदर **रेडियल ग्रेडिएंट बनाना** है, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम हर चरण को समझाएंगे जो एक स्मूथ रेडियल ग्रेडिएंट वाले PostScript दस्तावेज़ को उत्पन्न करने के लिए आवश्यक है, **Aspose.Page for Java** का उपयोग करके। अंत तक आप API को समझेंगे, एक पूर्ण चलाने योग्य उदाहरण देखेंगे, और किसी भी डिज़ाइन परिदृश्य के लिए रंग, स्थितियों और त्रिज्या को कैसे समायोजित किया जाए, यह जानेंगे।

## त्वरित उत्तर
- **PostScript में रेडियल ग्रेडिएंट बनाने वाली लाइब्रेरी कौन सी है?** Aspose.Page for Java।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बुनियादी उदाहरण के लिए लगभग 10‑15 मिनट।  
- **कोड चलाने के लिए लाइसेंस चाहिए?** विकास के लिए फ्री ट्रायल काम करता है; उत्पादन के लिए वाणिज्यिक लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** Java 8 या उससे ऊपर।  
- **क्या मैं ग्रेडिएंट का आकार बदल सकता हूँ?** हाँ – `RadialGradientPaint` कंस्ट्रक्टर में त्रिज्या और केंद्र बिंदु को समायोजित करें।

## Java में रेडियल ग्रेडिएंट कैसे बनाएं

अपने Java प्रोजेक्ट को लोड करें, आवश्यक क्लासेस इम्पोर्ट करें, और नीचे दिए गए चरण‑दर‑चरण मार्गदर्शक का पालन करें। मुख्य उत्तर यह है कि आप `RadialGradientPaint` को अपने कलर स्टॉप्स के साथ इंस्टैंशिएट करते हैं और फिर इसे `PsDocument` पर ड्रॉ किए गए एक आयत पर लागू करते हैं। यह दो‑ऑब्जेक्ट दृष्टिकोण सभी लो‑लेवल PostScript कमांड्स को आपके लिए संभालता है।

## रेडियल ग्रेडिएंट क्या है?
`RadialGradientPaint` एक Java AWT क्लास है जो केंद्रीय बिंदु से बाहर की ओर एक गोलाकार रंग संक्रमण को परिभाषित करती है। यह कई कलर स्टॉप्स का स्मूथ मिश्रण बनाता है, जिससे यह स्पॉटलाइट, सॉफ्ट बैकग्राउंड या किसी भी प्रभाव के लिए आदर्श है जहाँ रंग एक फोकल पॉइंट से फैलते हैं।

## रेडियल ग्रेडिएंट के लिए Aspose.Page क्यों उपयोग करें?
Aspose.Page आपको PostScript आउटपुट पर पूर्ण प्रोग्रामेटिक नियंत्रण देता है जबकि लो‑लेवल PS सिंटैक्स की भारी मेहनत को संभालता है। यह **50+ इनपुट और आउटपुट फ़ॉर्मैट** को सपोर्ट करता है, मेमोरी में पूरी फ़ाइल लोड किए बिना सैकड़ों‑पृष्ठ दस्तावेज़ रेंडर कर सकता है, और किसी भी ऑपरेटिंग सिस्टम पर चलता है जो Java 8+ को सपोर्ट करता है। यह मात्रात्मक क्षमता इसे एंटरप्राइज़‑ग्रेड ग्राफ़िक्स जेनरेशन के लिए भरोसेमंद विकल्प बनाती है।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK) 8+** – `java -version` से सत्यापित करें।  
- **Aspose.Page for Java** – आधिकारिक [Aspose.Page डाउनलोड पेज](https://releases.aspose.com/page/java/) से नवीनतम JAR डाउनलोड करें।  
- **आपका पसंदीदा IDE** – Eclipse, IntelliJ IDEA, या Java एक्सटेंशन वाले VS Code।  
- **एक लिखने योग्य फ़ोल्डर** – जहाँ उत्पन्न `.ps` फ़ाइल सहेजी जाएगी।

## पैकेज इम्पोर्ट करें
पहले, उन क्लासेस को इम्पोर्ट करें जिनकी हमें आवश्यकता होगी। `java.awt` पैकेज ग्रेडिएंट पेंट ऑब्जेक्ट्स प्रदान करता है, जबकि `com.aspose.eps` में PostScript दस्तावेज़ संभालने वाली क्लासेस होती हैं।

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

## चरण‑दर‑चरण मार्गदर्शिका

### चरण 1: एक आयत बनाएं और PS दस्तावेज़ खोलें
`PsDocument` Aspose.Page की क्लास है जो एक PostScript दस्तावेज़ का प्रतिनिधित्व करती है और आकार, टेक्स्ट और इमेज ड्रॉ करने के मेथड्स प्रदान करती है। हम एक आउटपुट स्ट्रीम बनाते हैं, पेज आकार (डिफ़ॉल्ट रूप से A4) कॉन्फ़िगर करते हैं, और एक आयत परिभाषित करते हैं जो ग्रेडिएंट को होस्ट करेगा।

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

> **प्रो टिप:** आयत के निर्देशांक (`200, 100, 200, 200`) को समायोजित करके ग्रेडिएंट को पेज पर कहीं भी रख सकते हैं।

### चरण 2: रंग और फ्रैक्शन परिभाषित करें
एक रेडियल ग्रेडिएंट *कलर स्टॉप्स* (रंग) और *फ्रैक्शन* (उन स्टॉप्स की सापेक्ष स्थितियों) से बनता है। यहाँ हम छह रंगों और उनके संबंधित फ्रैक्शन की एक एरे बनाते हैं।

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **यह क्यों महत्वपूर्ण है:** `fractions` को बदलकर आप रंगों के परिवर्तन की गति को नियंत्रित करते हैं, जिससे सूक्ष्म या **नाटकीय** प्रभाव प्राप्त होते हैं।

### चरण 3: रेडियल ग्रेडिएंट पेंट बनाएं
`RadialGradientPaint` वह कोर क्लास है जो रेडियल कलर ग्रेडिएंट का वर्णन करती है, जिसमें केंद्र बिंदु, त्रिज्या, फोकस पॉइंट, फ्रैक्शन, रंग, साइक्ल मेथड और कलर स्पेस शामिल हैं। अब हम ऊपर परिभाषित एरेज़ का उपयोग करके `RadialGradientPaint` ऑब्जेक्ट बनाते हैं।

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

> **नोट:** `transform` को `null` रखा जा सकता है यदि आपको अतिरिक्त स्केलिंग या रोटेशन की आवश्यकता नहीं है। `AffineTransform` के साथ प्रयोग करके विकृत ग्रेडिएंट बना सकते हैं।

### चरण 4: पेंट सेट करें और आयत को भरें
पेंट तैयार होने पर, हम `PsDocument` को इसे उपयोग करने के लिए बताते हैं और फिर पहले परिभाषित आयत को भरते हैं।

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

इस बिंदु पर PostScript पेज में एक आयत स्मूथली रेडियल ग्रेडिएंट से भरी हुई होगी।

### चरण 5: दस्तावेज़ को बंद करें और सहेजें
अंत में, वर्तमान पेज को बंद करें और फ़ाइल को डिस्क पर लिखें।

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

`RadialGradient1_outPS.ps` को किसी भी PostScript व्यूअर (जैसे Ghostscript) में खोलें और आप देखेंगे कि ग्रेडिएंट ठीक उसी तरह रेंडर हुआ है जैसा परिभाषित किया गया था।

## सामान्य समस्याएँ और समाधान
| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| ग्रेडिएंट एकसमान रंग जैसा दिख रहा है | `fractions` एरे `0.0f` से शुरू नहीं होता या `1.0f` पर समाप्त नहीं होता | सुनिश्चित करें कि पहला फ्रैक्शन `0.0f` और अंतिम `1.0f` हो। |
| रंग फीके दिख रहे हैं | गलत `ColorSpaceType` उपयोग किया गया है | अधिक जीवंत आउटपुट के लिए `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` पर स्विच करें। |
| आउटपुट फ़ाइल नहीं बन रही | `FileOutputStream` पाथ अमान्य या लिखने योग्य नहीं है | जांचें कि `dataDir` मौजूद है और एप्लिकेशन के पास लिखने की अनुमति है। |

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या मैं Aspose.Page for Java को वाणिज्यिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?**  
उ: हाँ। उत्पादन उपयोग के लिए वाणिज्यिक लाइसेंस आवश्यक है। आप इसे [Aspose लाइसेंसिंग पेज](https://purchase.aspose.com/buy) से खरीद सकते हैं।

**प्र: आधिकारिक API रेफ़रेंस कहाँ मिल सकता है?**  
उ: पूरी डॉक्यूमेंटेशन उपलब्ध है [Aspose.Page Java API रेफ़रेंस](https://reference.aspose.com/page/java/) पर।

**प्र: क्या परीक्षण के लिए फ्री ट्रायल उपलब्ध है?**  
उ: बिल्कुल। ट्रायल संस्करण [Aspose.Page रिलीज़ पेज](https://releases.aspose.com/) से डाउनलोड करें।

**प्र: मूल्यांकन के लिए अस्थायी लाइसेंस कैसे प्राप्त करें?**  
उ: अस्थायी लाइसेंस के लिए आप [अस्थायी लाइसेंस अनुरोध पेज](https://purchase.aspose.com/temporary-license/) पर अनुरोध कर सकते हैं।

**प्र: समुदाय समर्थन कहाँ मिल सकता है?**  
उ: Aspose.Page कम्युनिटी फ़ोरम में शामिल हों: [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39)।

## निष्कर्ष
अब आप **Java PostScript दस्तावेज़ में रेडियल ग्रेडिएंट** बनाने के लिए Aspose.Page का उपयोग करना जानते हैं। आयत का आकार, कलर स्टॉप्स और ग्रेडिएंट की त्रिज्या को समायोजित करके आप अनगिनत विज़ुअल इफ़ेक्ट बना सकते हैं—सूक्ष्म बैकग्राउंड फ़िल से लेकर बोल्ड स्पॉटलाइट ग्राफ़िक्स तक। विभिन्न `AffineTransform` मानों के साथ प्रयोग करके ग्रेडिएंट को घुमा या तिरछा कर सकते हैं, और इस तकनीक को टेक्स्ट और इमेज के साथ मिलाकर richer PDF या EPS आउटपुट बना सकते हैं।

---

**अंतिम अपडेट:** 2026-09-09  
**टेस्टेड विथ:** Aspose.Page for Java latest (लेखन समय)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Fill Shape with Gradient: Java PostScript Radial Example](/page/java/postscript-gradient-addition/radial2/)
- [Create PostScript Gradient in Java – Add Vertical Gradient](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page Transparency Tutorial – Add Transparency in Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}