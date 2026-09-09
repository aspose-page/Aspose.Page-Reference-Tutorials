---
date: 2026-09-09
description: Java PostScript में gradient बनाना और Aspose.Page का उपयोग करके shape
  में gradient जोड़ना सीखें। कोड और टिप्स के साथ इस step‑by‑step गाइड का पालन करें।
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Java PostScript Radial Gradient के साथ Aspose.Page
og_description: Java PostScript में gradient बनाना और Aspose.Page का उपयोग करके shape
  में gradient जोड़ना सीखें। कोड और टिप्स के साथ इस step‑by‑step गाइड का पालन करें।
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Java PostScript में radial fill के साथ gradient कैसे बनाएं
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Java PostScript में radial fill के साथ gradient कैसे बनाएं
url: /hi/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript में रेडियल फ़िल के साथ ग्रेडिएंट कैसे बनाएं

## परिचय
इस ट्यूटोरियल में आप Java और Aspose.Page का उपयोग करके PostScript दस्तावेज़ में **how to create gradient** ग्राफ़िक्स बनाना सीखेंगे। हम हर चरण को विस्तार से बताएँगे—प्रोजेक्ट सेटअप से लेकर एक स्मूथ रेडियल ग्रेडिएंट से भरे हुए सर्कल को रेंडर करने तक—ताकि आप तुरंत **add gradient to shape** ऑब्जेक्ट्स जोड़ सकें और अपने Java एप्लिकेशन्स की दृश्य गुणवत्ता को बढ़ा सकें।

## त्वरित उत्तर
- **What does this tutorial create?** एक PostScript फ़ाइल (`.ps`) जिसमें रेडियल ग्रेडिएंट से भरा सर्कल होता है।  
- **Which library is required?** Aspose.Page for Java (latest version).  
- **How long does implementation take?** लगभग 10‑15 मिनट एक कार्यशील उदाहरण के लिए।  
- **Do I need a license?** प्रोडक्शन उपयोग के लिए एक टेम्पररी या फुल लाइसेंस आवश्यक है; विकास के लिए एक फ्री ट्रायल काम करता है।  
- **Can I reuse the code for PDF or SVG?** हाँ—Aspose.Page न्यूनतम बदलावों के साथ कई आउटपुट फ़ॉर्मैट्स को सपोर्ट करता है।

## PostScript में ग्रेडिएंट के साथ शैप को कैसे भरें
आप `PsDocument` बनाकर, `RadialGradientPaint` परिभाषित करके, इसे लक्ष्य शैप पर लागू करके और अंत में दस्तावेज़ को सहेजकर PostScript में एक शैप को रेडियल ग्रेडिएंट से भर सकते हैं। यह संक्षिप्त वर्कफ़्लो आपको रास्टर इमेज़ के बिना प्रोफ़ेशनल‑लुकिंग वेक्टर ग्राफ़िक्स बनाने देता है, और वही कोड PDF या SVG आउटपुट के लिए भी पुन: उपयोग किया जा सकता है। प्रक्रिया सीधी है और सभी समर्थित फ़ॉर्मैट्स में लगातार काम करती है।

## रेडियल ग्रेडिएंट क्या है?
एक रेडियल ग्रेडिएंट केंद्र बिंदु से बाहर की ओर रंगों को ट्रांज़िशन करता है, जिससे एक स्मूथ, सर्कुलर मिश्रण बनता है। यह हाइलाइट्स, बटन बैकग्राउंड, या किसी भी विज़ुअल के लिए आदर्श है जिसे प्राकृतिक “ग्लो” इफ़ेक्ट चाहिए। रंग स्टॉप्स और रेडियस को बदलकर आप लाइटिंग, डेप्थ, और मैटेरियल प्रॉपर्टीज़ को शुद्ध वेक्टर रूप में सिमुलेट कर सकते हैं।

## रेडियल ग्रेडिएंट्स के लिए Aspose.Page क्यों उपयोग करें?
Aspose.Page आपको एक ही Java API के साथ डिवाइस‑इंडिपेंडेंट वेक्टर ग्राफ़िक्स जनरेट करने देता है। यह 50 से अधिक इनपुट और आउटपुट फ़ॉर्मैट्स—जिसमें PostScript, PDF, और SVG शामिल हैं—को सपोर्ट करता है, जबकि हाई‑रेज़ोल्यूशन आउटपुट के लिए रंग की सटीकता और एंटी‑एलियासिंग को बनाए रखता है। लाइब्रेरी आसान‑से‑उपयोग ग्रेडिएंट क्लासेज़ भी प्रदान करती है, जिससे जटिल विज़ुअल इफ़ेक्ट्स को लागू करना सरल हो जाता है।

## पूर्वापेक्षाएँ
- Java प्रोग्रामिंग की बुनियादी परिचितता।  
- आपके मशीन पर JDK 8 या नया स्थापित हो।  
- Aspose.Page for Java लाइब्रेरी (डाउनलोड करें [Aspose.Page Java documentation](https://reference.aspose.com/page/java/))।

## पैकेज इम्पोर्ट करें
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

## चरण 1: दस्तावेज़ डायरेक्टरी सेट अप करें
उस फ़ोल्डर को परिभाषित करें जहाँ जनरेट किया गया PostScript फ़ाइल सहेजा जाएगा। प्लेसहोल्डर को आपके सिस्टम पर वास्तविक पाथ से बदलें।

```java
String dataDir = "Your Document Directory";
```

## चरण 2: आउटपुट स्ट्रीम बनाएं
FileOutputStream फ़ाइल में रॉ बाइट्स लिखता है, जिससे बाइनरी डेटा सहेजा जा सकता है। `.ps` फ़ाइल को टार्गेट करने वाला एक खोलना Aspose.Page को जनरेट किया गया PostScript डेटा सीधे डिस्क पर स्ट्रीम करने देता है।

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## चरण 3: सेव ऑप्शन्स बनाएं
PsSaveOptions यह निर्धारित करता है कि PostScript फ़ाइल कैसे सहेजी जाए, जिसमें पेज साइज और कॉम्प्रेशन शामिल हैं। आप इन सेटिंग्स को कस्टमाइज़ कर सकते हैं, लेकिन इस उदाहरण के लिए डिफ़ॉल्ट ठीक हैं।

```java
PsSaveOptions options = new PsSaveOptions();
```

## चरण 4: ps दस्तावेज़ बनाएं
PsDocument मेमोरी में एक PostScript दस्तावेज़ का प्रतिनिधित्व करता है और पेज और ग्राफ़िक्स जोड़ने के मेथड्स प्रदान करता है।

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## चरण 5: एक सर्कल बनाएं
`Ellipse2D.Float` एक एलिप्स शैप को वर्णित करता है; जब चौड़ाई = ऊँचाई होती है तो यह एक परिपूर्ण सर्कल बन जाता है। यह ऑब्जेक्ट हमारे ग्रेडिएंट फ़िल के लिए कैनवास के रूप में काम करेगा।

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## ग्रेडिएंट के साथ सर्कल कैसे ड्रॉ करें
रेडियल ग्रेडिएंट के साथ सर्कल ड्रॉ करने के लिए, आप `RadialGradientPaint` को ग्राफ़िक्स कॉन्टेक्स्ट में लोड करते हैं और फिर पहले परिभाषित एलिप्स को भरते हैं। यह एकल ऑपरेशन शैप को केंद्र से बाहर की ओर एक स्मूथ रंग ट्रांज़िशन के साथ पेंट करता है, जिससे एक दृश्य रूप से आकर्षक इफ़ेक्ट बनता है।

## चरण 6: ग्रेडिएंट रंग निर्धारित करें
दो एरे तैयार करें: एक ग्रेडिएंट में दिखाई देने वाले रंगों के लिए और दूसरा संबंधित फ्रैक्शनल पोजीशन्स (0 = केंद्र, 1 = किनारा) के लिए।

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## चरण 7: affinetransform बनाएं
AffineTransform एक मैट्रिक्स है जो ग्राफ़िक्स ऑब्जेक्ट्स को ट्रांसलेट, रोटेट, स्केल या शियर कर सकता है। यहाँ यह ग्रेडिएंट को स्केल और ट्रांसलेट करता है ताकि यह सर्कल के अंदर ठीक फिट हो सके।

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## चरण 8: रेडियल ग्रेडिएंट पेंट बनाएं
RadialGradientPaint एक केंद्र बिंदु, रेडियस, और रंग स्टॉप्स के आधार पर रेडियल कलर ग्रेडिएंट बनाता है।

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

## चरण 9: पेंट सेट करें और सर्कल भरें
ग्रेडिएंट पेंट को दस्तावेज़ पर लागू करें और पहले परिभाषित सर्कल को भरें। यह हमारे **radial gradient example** का मुख्य भाग है और दिखाता है कि **fill shape with gradient** कैसे किया जाता है।

```java
document.setPaint(paint);
document.fill(circle);
```

## चरण 10: पेज बंद करें और दस्तावेज़ सहेजें
पेज को फाइनलाइज़ करें, सामग्री को डिस्क पर लिखें, और स्ट्रीम को बंद करें। आपका PostScript फ़ाइल अब किसी भी PS व्यूअर के साथ देखने के लिए तैयार है।

```java
document.closePage();
document.save();
```

बधाई हो! आपने Aspose.Page का उपयोग करके Java PostScript में सफलतापूर्वक एक रेडियल ग्रेडिएंट उदाहरण बनाया है। अब आपके पास **fill shape with gradient** के लिए एक पुन: उपयोग योग्य पैटर्न है जिसे अन्य शैप्स और आउटपुट फ़ॉर्मैट्स के लिए अनुकूलित किया जा सकता है।

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|---------|----------|
| **FileNotFoundException** जब आउटपुट स्ट्रीम खोल रहे हों | सुनिश्चित करें कि `dataDir` एक मौजूदा फ़ोल्डर की ओर इशारा करता है और आपके पास लिखने की अनुमति है। |
| ग्रेडिएंट सपाट या गायब दिख रहा है | सुनिश्चित करें कि `fractions` एरे `colors` एरे की लंबाई से मेल खाता है और `AffineTransform` सही ढंग से स्केल हो रहा है। |
| रंग उलटे दिख रहे हैं | `colors` एरे में रंगों का क्रम बदलें या `focus` पॉइंट कोऑर्डिनेट्स को समायोजित करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: Where can I find the documentation for Aspose.Page for Java?**  
A: पूर्ण API रेफ़रेंस [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/) में उपलब्ध है।

**Q: How can I download Aspose.Page for Java?**  
A: नवीनतम JAR [releases page](https://releases.aspose.com/page/java/) से प्राप्त करें।

**Q: Is there a free trial available?**  
A: हाँ—ट्रायल संस्करण [Aspose free trial download page](https://releases.aspose.com/) से डाउनलोड करें।

**Q: Can I obtain a temporary license for testing?**  
A: बिल्कुल, आप इसे [temporary license page](https://purchase.aspose.com/temporary-license/) से अनुरोध कर सकते हैं।

**Q: Where can I get community support?**  
A: चर्चा में शामिल हों [Aspose.Page forum](https://forum.aspose.com/c/page/39) पर।

## निष्कर्ष
इस गाइड में हमने Aspose.Page for Java का उपयोग करके एक PostScript दस्तावेज़ के लिए पूर्ण **radial gradient example** बनाया। चरणों का पालन करके अब आपके पास **fill shape with gradient** के लिए एक पुन: उपयोग योग्य पैटर्न है, जिसे आप PDF, SVG, या Aspose.Page द्वारा समर्थित किसी भी अन्य फ़ॉर्मैट में अनुकूलित कर सकते हैं। विभिन्न रंगों, रेडियस, और शैप्स के साथ प्रयोग करें ताकि आपके Java ग्राफ़िक्स प्रोजेक्ट्स समृद्ध हों।

---

**अंतिम अपडेट:** 2026-09-09  
**परीक्षित संस्करण:** Aspose.Page for Java 24.11 (latest at time of writing)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Java में PostScript ग्रेडिएंट बनाएं – वर्टिकल ग्रेडिएंट जोड़ें](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page for Java के साथ PostScript में टेक्सचर पैटर्न बनाएं](/page/java/postscript-texture-patterns/)
- [Aspose.Page ट्रांसपेरेंसी ट्यूटोरियल – Java PostScript में ट्रांसपेरेंसी जोड़ें](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}