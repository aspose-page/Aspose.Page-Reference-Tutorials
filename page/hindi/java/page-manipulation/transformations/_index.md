---
date: 2025-12-07
description: जावा में Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट दस्तावेज़ बनाने के
  लिए आयत को स्केल करना, आकार को ट्रांसलेट करना और अफाइन ट्रांसफ़ॉर्म लागू करना सीखें।
language: hi
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Aspose.Page के साथ आयत को स्केल करना और ट्रांसफ़ॉर्मेशन लागू करना
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ आयत को स्केल करने और ट्रांसफ़ॉर्मेशन लागू करने का तरीका

## परिचय
Aspose.Page for Java की शक्तिशाली सुविधाओं का उपयोग करके विभिन्न पेज ट्रांसफ़ॉर्मेशन करने के लिए इस व्यापक गाइड में आपका स्वागत है। इस ट्यूटोरियल में आप **how to scale rectangle**, आकारों को ट्रांसलेट करना, ऑब्जेक्ट्स को घुमाना, और **apply affine transform** तकनीकों को **PostScript document** बनाते समय सीखेंगे। ये क्षमताएँ आपको लो‑लेवल रेंडरिंग कोड से निपटे बिना समृद्ध, ग्राफ़िक्स‑इंटेंसिव Java एप्लिकेशन बनाने में मदद करती हैं।

## त्वरित उत्तर
- **How do I scale a rectangle in Java with Aspose.Page?** आकृति को ड्रॉ करने से पहले `document.scale()` मेथड का उपयोग करें।  
- **Can I move (translate) a shape without affecting other graphics?** हाँ—ग्राफ़िक्स स्टेट को सेव करें, `document.translate(x, y)` कॉल करें, ड्रॉ करें, फिर स्टेट को रीस्टोर करें।  
- **What class creates a PostScript file?** `PsDocument` को `PsSaveOptions` के साथ उपयोग किया जाता है।  
- **Do I need a license for production use?** व्यावसायिक डिप्लॉयमेंट के लिए एक वैध Aspose.Page लाइसेंस आवश्यक है।  
- **Which Java version is supported?** Aspose.Page Java 8 और उसके बाद के संस्करणों के साथ काम करता है।

## पूर्वापेक्षाएँ
स्टेप‑बाय‑स्टेप गाइड में प्रवेश करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- Java प्रोग्रामिंग का बुनियादी ज्ञान।
- Aspose.Page for Java लाइब्रेरी स्थापित है। आप इसे [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) से डाउनलोड कर सकते हैं।
- आपके मशीन पर Java Integrated Development Environment (IDE) सेटअप हो।

## पैकेज इम्पोर्ट करें
अपने Java प्रोजेक्ट में, Aspose.Page for Java का उपयोग करने के लिए आवश्यक पैकेज इम्पोर्ट करें:

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
आयत को स्केल करने से उसका आकार X और Y अक्षों के साथ बदलता है जबकि उसकी आकृति बनी रहती है। Aspose.Page `scale(float sx, float sy)` मेथड प्रदान करता है, जो वर्तमान ग्राफ़िक्स स्टेट पर **affine transform** लागू करता है। यह **how to scale rectangle** कीवर्ड के पीछे की मुख्य तकनीक है।

## Aspose.Page के साथ आकार को ट्रांसलेट करने का तरीका
ट्रांसलेशन एक आकार को नई जगह पर ले जाता है बिना उसके आयाम बदले। यह **how to translate shape** का सार है। ग्राफ़िक्स स्टेट को सेव करके, `translate(dx, dy)` लागू करके, ड्रॉ करके और फिर स्टेट को रीस्टोर करके, आप अन्य ऑब्जेक्ट्स को अप्रभावित रख सकते हैं।

## उदाहरण 1: कोई ट्रांसफ़ॉर्मेशन नहीं
पहला उदाहरण बिना किसी ट्रांसफ़ॉर्मेशन के एक साधारण आयत ड्रॉ करता है। यह बाद के उदाहरणों के साथ तुलना के लिए बेसलाइन के रूप में काम करता है।

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
यह उदाहरण मुख्य प्रश्न **how to scale rectangle** का उत्तर देता है। हम आयत को उसकी मूल चौड़ाई के 50 % और ऊँचाई के 75 % तक छोटा कर देते हैं।

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

## Java में आकार को घुमाने का तरीका (rotate shape java)
रोटेशन एक और सामान्य affine ऑपरेशन है। जबकि रोटेशन के कोड स्निपेट संक्षिप्तता के लिए छोड़े गए हैं, पैटर्न समान है: ग्राफ़िक्स स्टेट को सेव करें, `document.rotate(angle)` कॉल करें, आकार को ड्रॉ करें, फिर रीस्टोर करें। यह व्यावहारिक रूप से **rotate shape java** और **how to rotate rectangle** को दर्शाता है।

## इन ट्रांसफ़ॉर्मेशन्स के लिए Aspose.Page क्यों उपयोग करें?
- **Device‑independent**: एक बार लिखें, प्लेटफ़ॉर्म‑विशिष्ट कोड के बिना PostScript या XPS जनरेट करें।  
- **Fine‑grained control**: ग्राफ़िक्स स्टेट तक सीधा एक्सेस आपको ट्रांसलेशन, स्केलिंग, शीयरिंग और रोटेशन को संयोजित करने देता है।  
- **Performance**: कम ओवरहेड वाला API जो बड़े दस्तावेज़ों की बैच प्रोसेसिंग के लिए उपयुक्त है।  

## सामान्य उपयोग केस
- डायनामिक बारकोड और लोगो के साथ प्रिंटेबल इनवॉइस बनाना।  
- तकनीकी डायग्राम बनाना जहाँ सटीक स्केलिंग और पोजिशनिंग आवश्यक है।  
- PostScript फ़ॉर्मेट में मल्टी‑पेज रिपोर्ट्स का उत्पादन स्वचालित करना।

## निष्कर्ष
इस ट्यूटोरियल में, हमने Aspose.Page for Java का उपयोग करके Java पेज मैनिपुलेशन में विभिन्न ट्रांसफ़ॉर्मेशन्स का अध्ययन किया, विशेष रूप से **how to scale rectangle**, **how to translate shape**, और अन्य affine ऑपरेशन्स पर ध्यान केंद्रित किया। इन उदाहरणों का पालन करके आप अपने Java एप्लिकेशन को उन्नत पेज मैनिपुलेशन क्षमताओं से सशक्त बना सकते हैं और **create PostScript document** आउटपुट बना सकते हैं जो पेशेवर प्रकाशन मानकों को पूरा करते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Page for Java को अन्य दस्तावेज़ फ़ॉर्मेट्स के लिए उपयोग कर सकता हूँ?
Aspose.Page मुख्यतः PostScript और XPS फ़ॉर्मेट्स के पेज मैनिपुलेशन पर केंद्रित है।

### Aspose.Page for Java के लिए अधिक उदाहरण और दस्तावेज़ीकरण कहाँ मिल सकते हैं?
विस्तृत जानकारी के लिए [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) देखें।

### क्या Aspose.Page for Java के लिए मुफ्त ट्रायल उपलब्ध है?
हाँ, आप एक मुफ्त ट्रायल [यहाँ](https://releases.aspose.com/) से एक्सेस कर सकते हैं।

### Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?
एक अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) प्राप्त करें।

### Aspose.Page for Java के बारे में समुदाय समर्थन या प्रश्न कहाँ पूछ सकते हैं?
समुदाय चर्चा के लिए [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) देखें।

## अक्सर पूछे जाने वाले प्रश्न
**प्रश्न: `translate` और `scale` में क्या अंतर है?**  
**उत्तर:** `translate` कॉर्डिनेट सिस्टम के मूल बिंदु को ले जाता है, जबकि `scale` X और/या Y अक्षों के साथ ड्रॉ किए गए ऑब्जेक्ट्स का आकार बदलता है।

**प्रश्न: क्या मैं एक ही ग्राफ़िक्स स्टेट में कई ट्रांसफ़ॉर्मेशन को संयोजित कर सकता हूँ?**  
**उत्तर:** हाँ—ड्रॉ करने से पहले क्रमशः `translate`, `scale`, `rotate`, या `shear` कॉल करके आप एक संयुक्त affine ट्रांसफ़ॉर्मेशन बना सकते हैं।

**प्रश्न: आकार ड्रॉ करने के बाद ट्रांसफ़ॉर्मेशन को कैसे रीसेट करूँ?**  
**उत्तर:** पहले सेव किए गए ग्राफ़िक्स स्टेट पर लौटने के लिए `document.writeGraphicsRestore()` का उपयोग करें।

**प्रश्न: क्या आयत को उसके केंद्र के चारों ओर घुमाना संभव है?**  
**उत्तर:** बिल्कुल। आयत को मूल बिंदु पर ले जाएँ, `rotate(angle)` लागू करें, फिर ड्रॉ करने से पहले उसे वापस ले आएँ।

**प्रश्न: क्या Aspose.Page स्मूथ ग्राफ़िक्स के लिए एंटी‑एलियासिंग सपोर्ट करता है?**  
**उत्तर:** हाँ—एंटी‑एलियासिंग सक्षम करने के लिए `PsSaveOptions` में उपयुक्त रेंडरिंग विकल्प सेट करें।

---

**अंतिम अपडेट:** 2025-12-07  
**परीक्षित संस्करण:** Aspose.Page for Java 24.12  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}