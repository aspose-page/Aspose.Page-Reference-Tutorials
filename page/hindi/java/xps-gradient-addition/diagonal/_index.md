---
date: 2026-05-25
description: जावा में Aspose.Page का उपयोग करके XPS दस्तावेज़ों में ग्रेडिएंट जोड़ना
  सीखें। यह चरण‑दर‑चरण गाइड दिखाता है कि कैसे Diagonal Gradient जोड़ें, linear gradient
  brushes लागू करें, और पेशेवर XPS फ़ाइलें बनाएं।
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: जावा XPS में Diagonal Gradient जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'ग्रेडिएंट कैसे जोड़ें: Diagonal Gradient in Java XPS'
url: /hi/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ग्रेडिएंट कैसे जोड़ें: जावा XPS में तिरछा ग्रेडिएंट

## परिचय
आधुनिक जावा विकास में, XPS दस्तावेज़ों में **how to add gradient** को मास्टर करना आपके रिपोर्टों को एक परिष्कृत, आकर्षक रूप देता है जो अलग दिखता है। यह ट्यूटोरियल आपको शून्य से XPS फ़ाइल बनाने, तिरछा ग्रेडिएंट जोड़ने, और परिणाम को सहेजने की प्रक्रिया दिखाता है—सभी Aspose.Page for Java के साथ। आप समझेंगे कि ग्रेडिएंट क्यों महत्वपूर्ण हैं, सटीक API कॉल देखेंगे, और सामान्य pitfalls से बचने के लिए व्यावहारिक टिप्स प्राप्त करेंगे।

## त्वरित उत्तर
- **What is the primary library?** Aspose.Page for Java  
- **Which method adds the gradient?** `createLinearGradientBrush` with gradient stops  
- **Do I need a license?** A trial works for development; a commercial license is required for production  
- **How long does implementation take?** About 10‑15 minutes for a basic diagonal gradient  
- **Can I use this with other Java frameworks?** Yes, the API is framework‑agnostic  

## XPS दस्तावेज़ में तिरछा ग्रेडिएंट क्या है?
एक तिरछा ग्रेडिएंट एक स्मूथ रंग परिवर्तन है जो किसी आकृति के एक कोने से विपरीत कोने तक चलता है, जिससे एक तिरछा दृश्य प्रभाव बनता है। XPS में, यह प्रभाव एक लीनियर ग्रेडिएंट ब्रश द्वारा परिभाषित किया जाता है जिसमें क्रमबद्ध ग्रेडिएंट स्टॉप्स होते हैं जो रंगों और तिरछी रेखा के साथ सापेक्ष स्थितियों को निर्दिष्ट करते हैं।

## Aspose.Page के साथ तिरछा ग्रेडिएंट क्यों जोड़ें?
Aspose.Page **100 % रेंडरिंग फिडेलिटी** प्रदान करता है ग्रेडिएंट्स के लिए, 20 से अधिक XPS व्यूअर्स में, और यह **30+ XPS फीचर्स** जैसे टेक्स्ट, इमेजेज, और वेक्टर शैप्स को सपोर्ट करता है। API जटिल XPS मार्कअप को एब्स्ट्रैक्ट करती है, जिससे आप डिज़ाइन पर ध्यान केंद्रित कर सकते हैं जबकि यह सुनिश्चित करता है कि वही फ़ाइल Windows, macOS, और Linux प्लेटफ़ॉर्म पर समान दिखे।

## पूर्वापेक्षाएँ
- बेसिक जावा प्रोग्रामिंग ज्ञान।  
- आपके मशीन पर JDK स्थापित है।  
- Aspose.Page for Java लाइब्रेरी – इसे **[here](https://releases.aspose.com/page/java/)** से डाउनलोड करें।  
- IntelliJ IDEA या Eclipse जैसे IDE।  

## पैकेज आयात करें
शुरू करने के लिए उन क्लासेज़ को इम्पोर्ट करें जिनकी आपको आवश्यकता होगी। ये इम्पोर्ट्स आपको जियोमेट्री, ग्रेडिएंट हैंडलिंग, और XPS दस्तावेज़ निर्माण तक पहुँच प्रदान करते हैं।

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## चरण 1: अपना प्रोजेक्ट सेट अप करें
अपने पसंदीदा IDE में एक नया जावा प्रोजेक्ट बनाएं और Aspose.Page JAR फ़ाइलों को प्रोजेक्ट के बिल्ड पाथ में जोड़ें।

## चरण 2: दस्तावेज़ निर्देशिका निर्धारित करें
निर्दिष्ट करें कि उत्पन्न XPS फ़ाइल कहाँ सहेजी जाएगी।

```java
String dataDir = "Your Document Directory";
```

## चरण 3: XPS दस्तावेज़ बनाएं
`XpsDocument` वह कोर ऑब्जेक्ट है जो मेमोरी में XPS फ़ाइल का प्रतिनिधित्व करता है। इसे इंस्टैंशिएट करने से आपको पेज, शैप्स, और ब्रशेज़ जोड़ने के लिए एक कैनवास मिलता है।

```java
XpsDocument doc = new XpsDocument();
```

## चरण 4: तिरछा ग्रेडिएंट पाथ जोड़ें
एक आयताकार पाथ बनाएं जो ग्रेडिएंट प्राप्त करेगा। पाथ जियोमेट्री एक सरल move‑line‑close कमांड का उपयोग करती है।  
XpsPath XPS दस्तावेज़ में एक वेक्टर शैप को परिभाषित करता है, जैसे आयत या कस्टम जियोमेट्री।

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## चरण 5: रैखिक ग्रेडिएंट स्टॉप्स निर्धारित करें
रंगों और उनकी स्थितियों को सेट करें। प्रत्येक स्टॉप ग्रेडिएंट में एक बिंदु को परिभाषित करता है जहाँ एक विशिष्ट रंग दिखाई देता है।  
XpsGradientStop ग्रेडिएंट में एकल रंग स्टॉप का प्रतिनिधित्व करता है, जो रंग और उसके ऑफ़सेट को निर्दिष्ट करता है।

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## चरण 6: पाथ पर रैखिक ग्रेडिएंट लागू करें
`XpsLinearGradientBrush` Aspose.Page का ब्रश प्रकार है रैखिक रंग संक्रमणों के लिए। यह दो बिंदु लेता है जो ग्रेडिएंट दिशा को परिभाषित करते हैं और ग्रेडिएंट स्टॉप्स का एक संग्रह जो उस रेखा के साथ रंगों को निर्धारित करता है।

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## चरण 7: दस्तावेज़ सहेजें
XPS फ़ाइल को डिस्क पर स्थायी रूप से सहेजें। फ़ाइल में वह आयत होगा जो आपने परिभाषित तिरछा ग्रेडिएंट से भरा होगा।

```java
doc.save(dataDir + "LinearGradient.xps");
```

## जावा XPS में ग्रेडिएंट कैसे जोड़ें?
`XpsDocument` लोड करें, एक `XpsLinearGradientBrush` बनाएं जिसमें प्रारंभ बिंदु `(0,0)` और समाप्ति बिंदु `(width,height)` हो, ग्रेडिएंट स्टॉप्स संलग्न करें, ब्रश को शैप के `Fill` प्रॉपर्टी को असाइन करें, और अंत में `save` कॉल करें। यह संक्षिप्त प्रवाह आपको केवल कुछ API कॉल्स में तिरछा ग्रेडिएंट एम्बेड करने देता है, जिससे आपका कोड साफ़ और रखरखाव योग्य रहता है।

## सामान्य समस्याएँ और टिप्स
- **Gradient direction** – सुनिश्चित करें कि ब्रश के प्रारंभ और समाप्ति बिंदु उस तिरछे दिशा को दर्शाते हों जिसे आप चाहते हैं; उन्हें बदलने से ग्रेडिएंट उलट जाएगा।  
- **Color precision** – Aspose ARGB का उपयोग करता है; यदि आपको ट्रांसपेरेंसी चाहिए तो अल्फा चैनल शामिल करें।  
- **File path** – हमेशा एक एब्सॉल्यूट पाथ उपयोग करें या यह सत्यापित करें कि रिलेटिव पाथ मौजूद लिखने योग्य डायरेक्टरी की ओर इशारा करता है।

## अतिरिक्त FAQ

**Q: मैं एक मौजूदा XPS शेप में **how to add gradient** कैसे जोड़ूँ?**  
A: एक `XpsLinearGradientBrush` बनाएं, ग्रेडिएंट स्टॉप्स निर्धारित करें, और इसे शैप की `Fill` प्रॉपर्टी को असाइन करें जैसा कि चरण 6 में दिखाया गया है।

**Q: **apply linear gradient** वास्तव में पर्दे के पीछे क्या करता है?**  
A: यह XPS पैकेज में एक ब्रश परिभाषा उत्पन्न करता है जो प्रारंभ/समाप्ति बिंदुओं और ग्रेडिएंट स्टॉप्स के संग्रह को संदर्भित करता है, जिसे व्यूअर एक स्मूथ रंग संक्रमण के रूप में रेंडर करता है।

**Q: अन्य XPS फीचर्स के लिए **how to use aspose** का कोई तेज़ तरीका है?**  
A: हाँ, Aspose.Page API में इमेजेज, टेक्स्ट, और कस्टम शैप्स जोड़ने के लिए मेथड्स शामिल हैं—सिर्फ `XpsDocument` क्लास को एक्सप्लोर करें अतिरिक्त हेल्पर्स के लिए।

**Q: क्या मैं **add gradient path** को गैर‑आयताकार शैप्स में जोड़ सकता हूँ?**  
A: बिल्कुल। `createPathGeometry` का उपयोग करके कोई भी जियोमेट्री परिभाषित करें और फिर उसके `Fill` को एक ग्रेडिएंट ब्रश असाइन करें।

**Q: क्या ग्रेडिएंट फ़ाइल आकार को उल्लेखनीय रूप से प्रभावित करता है?**  
A: केवल मामूली रूप से; ग्रेडिएंट परिभाषाएँ XPS पैकेज के भीतर हल्की XML एंट्रीज़ होती हैं।

---

**अंतिम अपडेट:** 2026-05-25  
**परीक्षण किया गया:** Aspose.Page for Java 24.11  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose Page XPS Gradient Addition](/page/java/xps-gradient-addition/)
- [Java XPS Text Addition - Aspose.Page Tutorial](/page/java/xps-text-manipulation/add-text/)
- [How to Add Image to Java XPS Documents – A Simple Guide with Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}