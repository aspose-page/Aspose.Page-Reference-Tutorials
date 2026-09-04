---
date: 2026-09-04
description: Java PostScript में Aspose.Page Java के साथ gradient जोड़ना सीखें, LinearGradientPaint
  का उपयोग करके diagonal रंग परिवर्तन बनाकर जीवंत दस्तावेज़ बनाएं।
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'कैसे जोड़ें gradient: diagonal gradient in Java PostScript using Aspose.Page
  Java'
og_description: Java PostScript में Aspose.Page Java का उपयोग करके gradient जोड़ना
  सीखें। यह गाइड आपको कुछ ही चरणों में LinearGradientPaint के साथ diagonal gradient
  बनाने का तरीका दिखाता है।
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: Java PostScript में Aspose.Page Java के साथ gradient कैसे जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'कैसे जोड़ें gradient: diagonal gradient in Java PostScript using Aspose.Page
  Java'
url: /hi/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java का उपयोग करके Java PostScript में विकर्ण ग्रेडिएंट जोड़ें

## परिचय
यदि आप PostScript फ़ाइल को एक सुगम विकर्ण रंग संक्रमण से समृद्ध करना चाहते हैं, तो **Aspose.Page Java** इसे आश्चर्यजनक रूप से आसान बनाता है। इस ट्यूटोरियल में आप **ग्रेडिएंट जोड़ने** की प्रक्रिया चरण‑दर‑चरण सीखेंगे, Java 2D की `LinearGradientPaint` क्लास का उपयोग करके। अंत तक आपके पास एक तैयार‑चलाने योग्य स्निपेट होगा जो एक जीवंत विकर्ण ग्रेडिएंट के साथ PostScript दस्तावेज़ बनाता है, और आप समझेंगे कि यह दृष्टिकोण कच्चे PostScript कमांड्स को हाथ से लिखने की तुलना में अधिक रखरखाव योग्य क्यों है।

## Java PostScript में ग्रेडिएंट कैसे जोड़ें
ग्रेडिएंट जोड़ना ग्राफ़िक्स‑केवल कार्य जैसा लग सकता है, लेकिन Aspose.Page के साथ आप शुद्ध Java में रहते हुए मूल PostScript कमांड्स पर पूर्ण नियंत्रण प्राप्त करते हैं। यह अनुभाग समझाता है कि यह दृष्टिकोण क्यों काम करता है और हाथ से लिखे कच्चे PostScript की तुलना में आपको क्या लाभ मिलता है।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java.  
- **कौन सी क्लास ग्रेडिएंट बनाती है?** `LinearGradientPaint`.  
- **क्या मैं रंग बदल सकता हूँ?** हाँ – `Color[]` एरे को संशोधित करें।  
- **उत्पादन के लिए लाइसेंस चाहिए?** एक व्यावसायिक लाइसेंस आवश्यक है; एक मुफ्त ट्रायल उपलब्ध है।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** एक बुनियादी ग्रेडिएंट के लिए लगभग 10 मिनट।

## Aspose.Page Java क्या है?
Aspose.Page Java एक पूर्ण‑विशेषताओं वाला API है जो डेवलपर्स को किसी भी बाहरी सॉफ़्टवेयर के बिना PostScript और PDF फ़ाइलें उत्पन्न, संपादित और परिवर्तित करने देता है। यह लाइब्रेरी **50+ इनपुट और आउटपुट फ़ॉर्मेट** का समर्थन करती है और **500+ पृष्ठ** वाले दस्तावेज़ों को 100 MB से कम मेमोरी उपयोग के साथ प्रोसेस कर सकती है।

## विकर्ण ग्रेडिएंट क्यों उपयोग करें?
विकर्ण ग्रेडिएंट चार्ट, बैनर या किसी भी ग्राफ़िक तत्व में गहराई और दृश्य आकर्षण जोड़ता है जिसे आधुनिक लुक चाहिए। क्योंकि ग्रेडिएंट एक कोने से opposite कोने तक चलता है, यह बैकग्राउंड, बटन स्किन और सजावटी आकारों के लिए उपयुक्त है, जिससे अतिरिक्त इमेज एसेट्स के बिना पेशेवर फिनिश मिलता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

- Java Development Kit (JDK) 8 या उससे ऊपर।  
- Eclipse, IntelliJ IDEA, या VS Code जैसा IDE।  
- **Aspose.Page for Java** लाइब्रेरी – नवीनतम संस्करण [आधिकारिक डाउनलोड पृष्ठ](https://releases.aspose.com/page/java/) से डाउनलोड करें।

## पैकेज आयात करें
`java.awt` पैकेज कोर ग्राफ़िक्स क्लासेस प्रदान करता है, जबकि `com.aspose.page` पैकेज आपको PostScript‑विशिष्ट API तक पहुंच देता है।

`LinearGradientPaint` क्लास Aspose.Page का Java 2D ग्रेडिएंट कार्यक्षमता के साथ पुल है।  
`AffineTransform` ग्रेडिएंट को घुमाने और स्केल करने में सक्षम बनाता है ताकि वह विकर्ण रूप से संरेखित हो सके।

```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## चरण 1: PostScript दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
पहले, फ़ोल्डर निर्धारित करें जहाँ फ़ाइल सहेजी जाएगी और एक `FileOutputStream` खोलें। यह स्ट्रीम उत्पन्न PostScript डेटा प्राप्त करता है।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## चरण 2: A4 आकार के साथ सेव ऑप्शन बनाएं
`PsSaveOptions` आपको पेज आकार, रिज़ॉल्यूशन और अन्य आउटपुट सेटिंग्स निर्दिष्ट करने देता है। यहाँ हम डिफ़ॉल्ट A4 आकार का उपयोग करते हैं, जो 595 × 842 पॉइंट्स पर 72 dpi है।

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## चरण 3: नया PS दस्तावेज़ बनाएं
`PsDocument` क्लास PostScript दस्तावेज़ का प्रतिनिधित्व करती है और पेज बनाने तथा ग्राफ़िक्स ड्रॉ करने के मेथड प्रदान करती है।  
`PsDocument` को आउटपुट स्ट्रीम और सेव ऑप्शन के साथ इंस्टैंशिएट करें। `false` फ़्लैग कंस्ट्रक्टर को स्वचालित रूप से नया पेज खोलने से रोकता है – हम बाद में यह करेंगे।

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## चरण 4: एक आयत बनाएं
ऐसी आयत परिभाषित करें जो ग्रेडिएंट फ़िल प्राप्त करेगी। आयत की स्थिति (200, 100) और आकार (200 × 100) इस तरह चुना गया है कि ग्रेडिएंट स्पष्ट रूप से दिखाई दे।

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## चरण 5: ग्रेडिएंट ट्रांसफ़ॉर्म बनाएं
`AffineTransform` हमें ग्रेडिएंट को घुमाने, स्केल करने और ट्रांसलेट करने देता है ताकि वह आयत के पार विकर्ण रूप से चले। नीचे दिया गया गणित हाइपोटेन्यूस की गणना करता है और स्केलिंग अनुपात को उसी अनुसार समायोजित करता है।

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## चरण 6: विकर्ण रैखिक ग्रेडिएंट पेंट बनाएं
`LinearGradientPaint` वह मुख्य क्लास है जो रंग संक्रमण उत्पन्न करती है। यह आयत के ऊपर‑बाएँ से नीचे‑दाएँ तक फैली होती है, पहले परिभाषित ट्रांसफ़ॉर्म का उपयोग करते हुए। `MultipleGradientPaint.CycleMethod.NO_CYCLE` सुनिश्चित करता है कि ग्रेडिएंट दोहराया न जाए।

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## चरण 7: पेंट सेट करें और आयत को भरें
ग्रेडिएंट पेंट को दस्तावेज़ पर लागू करें और आयत आकार को भरें। यह चरण विकर्ण रंग संक्रमण को PostScript पेज पर रेंडर करता है।

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## चरण 8: वर्तमान पेज बंद करें और दस्तावेज़ सहेजें
अंत में, पेज बंद करें, स्ट्रीम को फ्लश करें, और फ़ाइल सहेजें। परिणामी `DiagonalGradient_outPS.ps` फ़ाइल को किसी भी PostScript व्यूअर से खोला जा सकता है।

```java
// Close current page and save the document
document.closePage();
document.save();
```

## सामान्य समस्याएँ एवं टिप्स
- **ग्रेडिएंट सपाट दिखता है** – घुमाव कोण को दोबारा जांचें; 45° का घुमाव एक वास्तविक विकर्ण बनाता है।  
- **रंग धुंधले दिखते हैं** – सटीक रंग रेंडरिंग के लिए `MultipleGradientPaint.ColorSpaceType.SRGB` का उपयोग सुनिश्चित करें।  
- **फ़ाइल नहीं मिली त्रुटि** – सुनिश्चित करें कि `dataDir` मौजूदा फ़ोल्डर की ओर इशारा करता है और एप्लिकेशन के पास लिखने की अनुमति है।  
- **बड़े दस्तावेज़ों से मेमोरी स्पाइक** – मेमोरी फुटप्रिंट कम करने के लिए `PsSaveOptions.setCompress(true)` का उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या मैं इस लाइब्रेरी का उपयोग Java में अन्य ग्राफ़िक ऑपरेशनों के लिए कर सकता हूँ?**  
उ: हाँ, Aspose.Page for Java ड्राइंग प्रिमिटिव्स, टेक्स्ट रेंडरिंग और इमेज हैंडलिंग क्षमताओं का पूर्ण सेट प्रदान करता है।

**प्र: क्या Aspose.Page Java के लिए कोई मुफ्त ट्रायल उपलब्ध है?**  
उ: बिल्कुल। आप पूरी तरह कार्यात्मक ट्रायल [Aspose मुफ्त ट्रायल पृष्ठ](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

**प्र: Aspose.Page Java के लिए दस्तावेज़ीकरण कहाँ मिल सकता है?**  
उ: आधिकारिक API संदर्भ यहाँ उपलब्ध है: [Aspose.Page Java API reference](https://reference.aspose.com/page/java/)।

**प्र: Aspose.Page Java के लिए लाइसेंस कैसे खरीदें?**  
उ: लाइसेंस सीधे [Aspose खरीद पोर्टल](https://purchase.aspose.com/buy) से खरीदा जा सकता है।

**प्र: सहायता चाहिए या प्रश्न हैं?**  
उ: मदद के लिए समुदाय‑चलित [Aspose.Page फ़ोरम](https://forum.aspose.com/c/page/39) पर जाएँ, जहाँ Aspose इंजीनियर और अन्य डेवलपर्स मदद करते हैं।

---

**अंतिम अपडेट:** 2026-09-04  
**परीक्षित संस्करण:** Aspose.Page for Java 24.12 (नवीनतम)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Page for Java के साथ PostScript में रेडियल ग्रेडिएंट बनाएं](/page/java/postscript-gradient-addition/)
- [Linear Gradient Paint के साथ Java PostScript में ग्रेडिएंट कैसे जोड़ें](/page/java/postscript-gradient-addition/horizontal/)
- [Java में PostScript ग्रेडिएंट बनाएं – वर्टिकल ग्रेडिएंट जोड़ें](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}