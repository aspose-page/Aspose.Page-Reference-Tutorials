---
date: 2026-10-20
description: Aspose.Page for Java के साथ आयत को स्केल करना, आकार को ट्रांसलेट करना,
  और PostScript दस्तावेज़ बनाने के लिए affine transform लागू करना सीखें।
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Java पेज मैनिपुलेशन में Transformations
og_description: Aspose.Page for Java का उपयोग करके आयत को स्केल करना, आकार को ट्रांसलेट
  करना, और affine transform लागू करके PostScript फ़ाइलें कुशलता से जनरेट करना सीखें।
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Aspise.Page for Java के साथ आयत को स्केल करने का तरीका – चरण-दर-चरण गाइड
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Aspose.Page for Java के साथ आयत को स्केल करने का तरीका
url: /hi/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for Java के साथ आयत को स्केल करना

## परिचय
इस गाइड में आप Aspose.Page for Java का उपयोग करके **how to scale rectangle** ऑब्जेक्ट्स को स्केल करना सीखेंगे, साथ ही आकार की स्थितियों को ट्रांसलेट करना, ग्राफ़िक्स को घुमाना, और उच्च‑गुणवत्ता वाले PostScript आउटपुट के लिए अफाइन ट्रांसफ़ॉर्म ऑपरेशन्स लागू करना सीखेंगे। ये तकनीकें आपको लो‑लेवल रेंडरिंग कोड लिखे बिना जटिल, डिवाइस‑इंडिपेंडेंट ग्राफ़िक्स बनाने देती हैं, जिससे आपके Java एप्लिकेशन अधिक शक्तिशाली और मेंटेन करने योग्य बनते हैं।

## त्वरित उत्तर
`scale(sx, sy)` ग्राफ़िक्स कॉन्टेक्स्ट को दिए गए क्षैतिज और ऊर्ध्वाधर फैक्टर्स द्वारा स्केल करता है।  

- **मैं Java में Aspose.Page के साथ आयत को कैसे स्केल करूँ?** आयत को ड्रॉ करने से पहले ग्राफ़िक्स कॉन्टेक्स्ट पर `scale(sx, sy)` मेथड को कॉल करें।  
- **क्या मैं किसी आकार को (ट्रांसलेट) अन्य ग्राफ़िक्स को प्रभावित किए बिना हिला सकता हूँ?** हाँ—ट्रांसलेशन को `writeGraphicsSave()` और `writeGraphicsRestore()` कॉल्स के बीच रैप करें।  
- **कौन सा क्लास PostScript फ़ाइल बनाता है?** `PsDocument` को `PsSaveOptions` के साथ उपयोग करें।  
- **क्या उत्पादन उपयोग के लिए मुझे लाइसेंस चाहिए?** व्यावसायिक डिप्लॉयमेंट के लिए एक वैध Aspose.Page लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** Aspose.Page Java 8 और उसके बाद के संस्करणों के साथ काम करता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:

- कोर Java सिंटैक्स और ऑब्जेक्ट‑ओरिएंटेड कॉन्सेप्ट्स की ठोस समझ।  
- Aspose.Page for Java लाइब्रेरी स्थापित हो। आप इसे [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) से डाउनलोड कर सकते हैं।  
- एक Java IDE (IntelliJ IDEA, Eclipse, या VS Code) जो लाइब्रेरी की JAR फ़ाइलों को क्लासपाथ पर कॉन्फ़िगर किया गया हो।

## पैकेज इम्पोर्ट करें
`PsDocument` वह मुख्य क्लास है जिसका उपयोग PostScript दस्तावेज़ बनाने के लिए किया जाता है, और `PsSaveOptions` दस्तावेज़ को कैसे सहेजा जाए, इसे कॉन्फ़िगर करता है।  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Aspose.Page में “how to scale rectangle” क्या है?
`scale(float sx, float sy)` मेथड वर्तमान ग्राफ़िक्स स्टेट पर एक अफाइन स्केलिंग ट्रांसफ़ॉर्म लागू करता है, जिससे बाद के ड्रॉइंग्स को `sx` (क्षैतिज) और `sy` (ऊर्ध्वाधर) फैक्टर्स द्वारा आकार बदल दिया जाता है। यह **how to scale rectangle** कीवर्ड के पीछे का मुख्य ऑपरेशन है। इस ट्रांसफ़ॉर्म को ड्रॉ करने से पहले लागू करने पर, आयत जैसी कोई भी बाद की आकृतियाँ नई आयामों के साथ रेंडर होंगी जबकि उनके अनुपात संरक्षित रहेंगे।

## Aspose.Page के साथ आकार को ट्रांसलेट कैसे करें
`writeGraphicsSave()` वर्तमान ग्राफ़िक्स स्टेट को सहेजता है और `writeGraphicsRestore()` उसे पुनर्स्थापित करता है, जिससे ट्रांसफ़ॉर्मेशन केवल इच्छित आकार को प्रभावित करें। ट्रांसलेशन कोऑर्डिनेट सिस्टम के मूल बिंदु को पुनः स्थित करता है बिना ऑब्जेक्ट के आयाम बदले। `translate(dx, dy)` को `writeGraphicsSave()` / `writeGraphicsRestore()` के बीच रखकर, आप सुनिश्चित करते हैं कि केवल इच्छित आकार ही हिले जबकि अन्य ग्राफ़िक्स अपरिवर्तित रहें, जिससे व्यक्तिगत तत्वों पर सटीक नियंत्रण मिलता है।

## उदाहरण 1: कोई ट्रांसफ़ॉर्मेशन नहीं
पहला उदाहरण कोई भी ट्रांसफ़ॉर्मेशन किए बिना एक आयत ड्रॉ करता है, जिससे बाद के उदाहरणों के साथ दृश्य तुलना के लिए एक बेसलाइन स्थापित होती है।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## उदाहरण 2: ट्रांसलेशन
इस नमूने में हम ग्राफ़िक्स कॉन्टेक्स्ट को दूसरे आयत को ड्रॉ करने से पहले 250 यूनिट दाईं ओर ले जाते हैं, जिससे **how to translate shape** दर्शाया जाता है।

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## उदाहरण 3: स्केलिंग
यहाँ हम मुख्य प्रश्न **how to scale rectangle** का उत्तर देते हैं। आयत को `scale(0.5f, 0.75f)` कॉल का उपयोग करके उसकी मूल चौड़ाई का 50 % और मूल ऊँचाई का 75 % तक घटाया गया है।

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Java में आकार को घुमाना (rotate shape java)
`rotate(angle)` निर्दिष्ट डिग्री में कोऑर्डिनेट सिस्टम को घुमाता है। अपना `PsDocument` लोड करें, ग्राफ़िक्स स्टेट पर `rotate(angle)` कॉल करें, आकार ड्रॉ करें, फिर पिछले स्टेट को पुनर्स्थापित करें। यह पैटर्न **rotate shape java** और **how to rotate rectangle** को एक ही पुन: उपयोग योग्य ब्लॉक में लागू करता है, जिससे आप ग्राफ़िक्स को अपनी पसंद के किसी भी बिंदु के चारों ओर घुमा सकते हैं।

## यह क्यों महत्वपूर्ण है – वास्तविक‑दुनिया के लाभ
- **डिवाइस‑इंडिपेंडेंट आउटपुट** – Aspose.Page PostScript और XPS फ़ाइलें जनरेट कर सकता है जो किसी भी प्रिंटर या व्यूअर पर समान रूप से रेंडर होती हैं, जिससे प्लेटफ़ॉर्म‑स्पेसिफिक ट्यूनिंग समाप्त हो जाती है।  
- **सूक्ष्म‑स्तरीय नियंत्रण** – ट्रांसलेशन, स्केलिंग, शीयरिंग और रोटेशन को मिलाकर सटीक लेआउट स्पेसिफिकेशन को पूरा करें; API प्रति पृष्ठ 20 से अधिक ट्रांसफ़ॉर्मेशन संयोजनों का समर्थन करता है।  
- **परफ़ॉर्मेंस‑उन्मुख प्रोसेसिंग** – लाइब्रेरी सामान्य 100‑पेज रिपोर्टों के लिए 10 MB से कम मेमोरी फ़ुटप्रिंट के साथ दस्तावेज़ प्रोसेस करती है, जिससे बैच जॉब तेज़ और स्केलेबल बनते हैं।

## सामान्य उपयोग केस
- **प्रिंटेबल इनवॉइस** – स्केलिंग और ट्रांसलेशन का उपयोग करके लोगो, बारकोड और टेबल को सटीक रूप से रखें ताकि कॉर्पोरेट ब्रांडिंग गाइडलाइन के साथ मेल खाए।  
- **टेक्निकल डायग्राम** – ऐसे स्कीमैटिक जनरेट करें जहाँ प्रत्येक कंपोनेंट को अनुपातिक रूप से री‑साइज़ और पोज़िशन करना आवश्यक हो।  
- **ऑटोमेटेड मल्टी‑पेज रिपोर्ट्स** – PostScript रिपोर्ट्स बनाएं जिनमें पेजों के बीच लगातार स्केलिंग की आवश्यकता हो, जैसे इंजीनियरिंग स्पेसिफिकेशन।

## सामान्य समस्याएँ और समाधान
- **ट्रांसफ़ॉर्मेशन रीसेट नहीं हो रहा** – हमेशा `writeGraphicsSave()` को `writeGraphicsRestore()` के साथ जोड़े; अन्यथा बाद के ड्रॉइंग्स अनचाहे ट्रांसफ़ॉर्म को विरासत में ले लेते हैं।  
- **अप्रत्याशित रंग** – प्रत्येक ट्रांसफ़ॉर्मेशन के बाद पेंट (रंग) सेट करें क्योंकि ग्राफ़िक्स स्टेट रिस्टोर के बाद रंग जानकारी को संरक्षित नहीं करता।  
- **फ़ाइल आकार बहुत बड़ा** – `PsSaveOptions` में कंप्रेशन सक्षम करें और एम्बेडेड रास्टर इमेज रिज़ॉल्यूशन को सीमित करें ताकि सामान्य 50‑पेज दस्तावेज़ों के लिए अंतिम फ़ाइल 5 MB से कम रहे।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं Aspose.Page for Java को अन्य दस्तावेज़ फ़ॉर्मेट्स के लिए उपयोग कर सकता हूँ?
Aspose.Page मुख्यतः PostScript और XPS फ़ॉर्मेट्स के लिए पेज मैनिपुलेशन पर केंद्रित है, लेकिन यह सीमित PDF एक्सपोर्ट क्षमताएँ भी प्रदान करता है।

### मैं Aspose.Page for Java के लिए अधिक उदाहरण और दस्तावेज़ कहाँ पा सकता हूँ?
व्यापक गाइड, API रेफ़रेंसेज़, और सैंपल प्रोजेक्ट्स के लिए [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) पर जाएँ।

### क्या Aspose.Page for Java के लिए कोई फ्री ट्रायल उपलब्ध है?
हाँ, आप **Aspose free trial download** पेज के माध्यम से फ्री ट्रायल एक्सेस कर सकते हैं: [Aspose free trial download](https://releases.aspose.com/)।

### मैं Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?
आप **temporary license request page** के माध्यम से अस्थायी लाइसेंस प्राप्त कर सकते हैं: [temporary license request page](https://purchase.aspose.com/temporary-license/)।

### मैं Aspose.Page for Java के बारे में समुदाय समर्थन या प्रश्न कहाँ पूछ सकता हूँ?
समुदाय चर्चा, कोड स्निपेट्स, और ट्रबलशूटिंग टिप्स के लिए [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) पर जाएँ।

## अक्सर पूछे जाने वाले प्रश्न

**प्र: `translate` और `scale` में क्या अंतर है?**  
**उ:** `translate` कोऑर्डिनेट सिस्टम के मूल बिंदु को स्थानांतरित करता है, जबकि `scale` X और/या Y अक्षों के साथ ड्रॉ किए गए ऑब्जेक्ट्स का आकार बदलता है।

**प्र: क्या मैं एक ही ग्राफ़िक्स स्टेट में कई ट्रांसफ़ॉर्मेशन को संयोजित कर सकता हूँ?**  
**उ:** हाँ—ड्रॉ करने से पहले क्रमवार `translate`, `scale`, `rotate`, या `shear` कॉल करके आप एक संयुक्त अफाइन ट्रांसफ़ॉर्मेशन बनाते हैं।

**प्र: आकार ड्रॉ करने के बाद मैं ट्रांसफ़ॉर्मेशन को कैसे रीसेट करूँ?**  
**उ:** `writeGraphicsRestore()` का उपयोग करके पहले सहेजे गए ग्राफ़िक्स स्टेट पर लौटें।

**प्र: क्या आयत को उसके केंद्र के चारों ओर घुमाना संभव है?**  
**उ:** बिल्कुल। आयत को मूल बिंदु पर ट्रांसलेट करें, `rotate(angle)` लागू करें, फिर ड्रॉ करने से पहले इसे वापस ट्रांसलेट करें।

**प्र: क्या Aspose.Page स्मूद ग्राफ़िक्स के लिए एंटी‑एलियासिंग का समर्थन करता है?**  
**उ:** हाँ—`PsSaveOptions` में उपयुक्त रेंडरिंग विकल्प सेट करके एंटी‑एलियासिंग को सक्षम करें।

---

**अंतिम अपडेट:** 2026-10-20  
**परीक्षित संस्करण:** Aspose.Page for Java 24.12  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Page के साथ Java PostScript में आयत कैसे ड्रॉ करें](/page/java/postscript-shapes/add-rectangle/)
- [Aspose.Page for Java के साथ PostScript में रेडियल ग्रेडिएंट बनाएं](/page/java/postscript-gradient-addition/)
- [PostScript पेज मैनिपुलेशन](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}