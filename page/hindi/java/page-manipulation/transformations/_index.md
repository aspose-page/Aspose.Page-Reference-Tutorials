---
date: 2026-02-07
description: Aspose.Page for Java के साथ आयत को स्केल करना, आकार को ट्रांसलेट करना,
  और पोस्टस्क्रिप्ट दस्तावेज़ बनाने के लिए अफ़ाइन ट्रांसफ़ॉर्म लागू करना सीखें।
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Aspose.Page for Java के साथ आयत को कैसे स्केल करें
url: /hi/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for Java के साथ आयत को स्केल करने का तरीका

## परिचय
Aspose.Page for Java की शक्तिशाली विशेषताओं का उपयोग करके विभिन्न पृष्ठ रूपांतरण करने के लिए एक व्यापक गाइड में आपका स्वागत है। इस ट्यूटोरियल में आप **how to scale rectangle** सीखेंगे, आकारों को ट्रांसलेट करेंगे, वस्तुओं को घुमाएंगे, और **apply affine transform** तकनीकों को **PostScript document** बनाते समय लागू करेंगे। ये क्षमताएँ आपको लो‑लेवल रेंडरिंग कोड से निपटे बिना समृद्ध, ग्राफ़िक्स‑इंटेंसिव Java एप्लिकेशन बनाने की अनुमति देती हैं।

## त्वरित उत्तर
- **Java में Aspose.Page के साथ आयत को कैसे स्केल करें?** Use the `document.scale()` method before drawing the shape.  
- **क्या मैं किसी आकार को (translate) अन्य ग्राफ़िक्स को प्रभावित किए बिना हिला सकता हूँ?** Yes—save the graphics state, call `document.translate(x, y)`, draw, then restore the state.  
- **कौन सा क्लास PostScript फ़ाइल बनाता है?** `PsDocument` together with `PsSaveOptions`.  
- **क्या उत्पादन उपयोग के लिए मुझे लाइसेंस चाहिए?** A valid Aspose.Page license is required for commercial deployments.  
- **कौन सा Java संस्करण समर्थित है?** Aspose.Page works with Java 8 and later.

## पूर्वापेक्षाएँ
स्टेप‑बाय‑स्टेप गाइड में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- Java प्रोग्रामिंग का बुनियादी ज्ञान।  
- Aspose.Page for Java लाइब्रेरी स्थापित है। आप इसे [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) से डाउनलोड कर सकते हैं।  
- आपके मशीन पर Java Integrated Development Environment (IDE) सेटअप हो।  

## पैकेज आयात करें
अपने Java प्रोजेक्ट में, Aspose.Page for Java का उपयोग करने के लिए आवश्यक पैकेज आयात करें:

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
आयत को स्केल करने से उसका आकार X और Y अक्षों के साथ बदलता है जबकि उसका रूप बना रहता है। Aspose.Page `scale(float sx, float sy)` मेथड प्रदान करता है, जो वर्तमान ग्राफ़िक्स स्टेट पर **affine transform** लागू करता है। यह **how to scale rectangle** कीवर्ड के पीछे की मुख्य तकनीक है।

## Aspose.Page के साथ आकार को ट्रांसलेट कैसे करें
ट्रांसलेशन एक आकार को उसके आयाम बदले बिना नई जगह पर ले जाता है। यह **how to translate shape** का सार है। ग्राफ़िक्स स्टेट को सहेजकर, `translate(dx, dy)` लागू करके, ड्रॉ करके और फिर स्टेट को पुनर्स्थापित करके, आप अन्य वस्तुओं को अप्रभावित रख सकते हैं।

## उदाहरण 1: कोई रूपांतरण नहीं
पहला उदाहरण बिना किसी रूपांतरण के एक साधारण आयत ड्रॉ करता है। यह बाद के उदाहरणों के साथ तुलना के लिए एक बेसलाइन के रूप में कार्य करता है।

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
यहाँ हम **how to translate shape** को दर्शाते हैं, जहाँ हम दूसरे आयत को ड्रॉ करने से पहले ग्राफ़िक्स कॉन्टेक्स्ट को 250 यूनिट दाईं ओर ले जाते हैं।

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
यह उदाहरण मुख्य प्रश्न **how to scale rectangle** का उत्तर देता है। हम आयत को उसकी मूल चौड़ाई के 50 % और ऊँचाई के 75 % तक छोटा करते हैं।

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
रोटेशन एक और सामान्य affine ऑपरेशन है। जबकि रोटेशन के कोड स्निपेट संक्षिप्तता के लिए छोड़ दिए गए हैं, पैटर्न समान है: ग्राफ़िक्स स्टेट को सहेजें, `document.rotate(angle)` कॉल करें, आकार को ड्रॉ करें, फिर पुनर्स्थापित करें। यह व्यावहारिक रूप से **rotate shape java** और **how to rotate rectangle** को दर्शाता है।

## यह क्यों महत्वपूर्ण है – वास्तविक‑दुनिया के लाभ
- **Device‑independent output** – एक बार लिखें और प्लेटफ़ॉर्म‑विशिष्ट संशोधनों के बिना PostScript या XPS उत्पन्न करें।  
- **Fine‑grained control** – सटीक लेआउट आवश्यकताओं को पूरा करने के लिए ट्रांसलेशन, स्केलिंग, शीयरिंग और रोटेशन को संयोजित करें।  
- **Performance‑oriented** – बड़े‑पैमाने के दस्तावेज़ों के बैच प्रोसेसिंग के लिए लो‑ओवरहेड API आदर्श है।  

## सामान्य उपयोग केस
- प्रिंटेबल इनवॉइस बनाना – उदाहरण के लिए, एक **printable invoice java** समाधान जो लोगो और बारकोड को सटीक रूप से रखता है।  
- तकनीकी आरेख बनाना जहाँ सटीक स्केलिंग और पोजिशनिंग आवश्यक है।  
- PostScript फ़ॉर्मेट में मल्टी‑पेज रिपोर्टों का उत्पादन स्वचालित करना।

## सामान्य समस्याएँ और समाधान
- **Transformation not resetting** – अनचाहे कैरी‑ओवर प्रभावों से बचने के लिए हमेशा `document.writeGraphicsSave()` को `document.writeGraphicsRestore()` के साथ जोड़े।  
- **Unexpected colors** – प्रत्येक रूपांतरण के बाद पेंट सेट करना सुनिश्चित करें; ग्राफ़िक्स स्टेट पुनर्स्थापना के बाद पिछले रंग सेटिंग्स को नहीं रखता।  
- **File size too large** – रास्टर ग्राफ़िक्स एम्बेड करने पर संपीड़न सक्षम करने या इमेज रेज़ोल्यूशन कम करने के लिए `PsSaveOptions` का उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Page for Java को अन्य दस्तावेज़ फ़ॉर्मेट्स के लिए उपयोग कर सकता हूँ?
Aspose.Page मुख्य रूप से PostScript और XPS फ़ॉर्मेट्स के पेज मैनिपुलेशन पर केंद्रित है।

### मैं Aspose.Page for Java के लिए अधिक उदाहरण और दस्तावेज़ कहाँ पा सकता हूँ?
व्यापक जानकारी के लिए [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) देखें।

### क्या Aspose.Page for Java के लिए कोई मुफ्त ट्रायल उपलब्ध है?
हाँ, आप एक मुफ्त ट्रायल [यहाँ](https://releases.aspose.com/) से प्राप्त कर सकते हैं।

### मैं Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?
अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) प्राप्त करें।

### मैं Aspose.Page for Java के बारे में समुदाय समर्थन या प्रश्न कहाँ पूछ सकता हूँ?
[Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) पर समुदाय चर्चा के लिए जाएँ।

## अक्सर पूछे जाने वाले प्रश्न

**Q: `translate` और `scale` में क्या अंतर है?**  
A: `translate` कॉर्डिनेट सिस्टम के मूल बिंदु को स्थानांतरित करता है, जबकि `scale` X और/या Y अक्षों के साथ ड्रॉ किए गए वस्तुओं का आकार बदलता है।

**Q: क्या मैं एक ही ग्राफ़िक्स स्टेट में कई रूपांतरणों को संयोजित कर सकता हूँ?**  
A: हाँ—ड्रॉ करने से पहले क्रमिक रूप से `translate`, `scale`, `rotate`, या `shear` कॉल करके, आप एक संयुक्त affine ट्रांसफ़ॉर्मेशन बनाते हैं।

**Q: आकार ड्रॉ करने के बाद मैं रूपांतरणों को कैसे रीसेट करूँ?**  
A: पहले सहेजे गए ग्राफ़िक्स स्टेट पर लौटने के लिए `document.writeGraphicsRestore()` का उपयोग करें।

**Q: क्या आयत को उसके केंद्र के आसपास घुमाना संभव है?**  
A: बिल्कुल। आयत को मूल बिंदु पर ले जाएँ, `rotate(angle)` लागू करें, फिर ड्रॉ करने से पहले उसे वापस ले आएँ।

**Q: क्या Aspose.Page स्मूथ ग्राफ़िक्स के लिए एंटी‑एलियासिंग का समर्थन करता है?**  
A: हाँ—एंटी‑एलियासिंग सक्षम करने के लिए `PsSaveOptions` में उपयुक्त रेंडरिंग विकल्प सेट करें।

---

**अंतिम अपडेट:** 2026-02-07  
**परीक्षित संस्करण:** Aspose.Page for Java 24.12  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}