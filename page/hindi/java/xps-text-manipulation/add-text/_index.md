---
date: 2026-04-24
description: Aspose.Page का उपयोग करके जावा में XPS टेक्स्ट कैसे जोड़ें, सीखें – XPS
  दस्तावेज़ बनाने, टेक्स्ट जोड़ने और आसानी से XPS फ़ाइलें सहेजने के लिए चरण‑दर‑चरण
  मार्गदर्शिका।
keywords:
- how to add xps
- create xps document
- aspose.page add text
linktitle: Java XPS में टेक्स्ट जोड़ें
second_title: Aspose.Page Java API
title: जावा में XPS टेक्स्ट कैसे जोड़ें – Aspose.Page ट्यूटोरियल
url: /hi/java/xps-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में XPS टेक्स्ट कैसे जोड़ें – Aspose.Page ट्यूटोरियल

## परिचय
यदि आपको प्रोग्रामेटिक रूप से **how to add XPS** टेक्स्ट जोड़ना है, तो Aspose.Page for Java आपको XPS (XML Paper Specification) फ़ाइलों के साथ काम करने के लिए एक साफ़, उच्च‑प्रदर्शन API प्रदान करता है। इस ट्यूटोरियल में हम XPS दस्तावेज़ बनाना, स्टाइल्ड टेक्स्ट डालना, और परिणाम को सहेजना — सभी संक्षिप्त, आसान‑से‑फ़ॉलो कोड के साथ — दिखाएंगे। चाहे आप रिपोर्टिंग इंजन बना रहे हों, इनवॉइस जेनरेट कर रहे हों, या सिर्फ़ पेज पर टेक्स्ट ओवरले करना चाहते हों, ये कदम आपको जल्दी से शुरू करने में मदद करेंगे।

## त्वरित उत्तर
- **Java में XPS हेरफेर के लिए सबसे अच्छा लाइब्रेरी कौन सा है?** Aspose.Page for Java.  
- **क्या मैं बिना लाइसेंस के XPS फ़ाइलें बना और सहेज सकता हूँ?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है.  
- **कौन से IDE समर्थित हैं?** IntelliJ IDEA, Eclipse, NetBeans, या कोई भी IDE जो Java को सपोर्ट करता है.  
- **सरल टेक्स्ट जोड़ने के लिए कितनी पंक्तियों का कोड चाहिए?** लगभग 10 पंक्तियों के साथ सेटअप.  
- **फ़ॉन्ट स्टाइलिंग संभव है?** हाँ – आप फ़ॉन्ट फ़ैमिली, आकार, शैली, और रंग सेट कर सकते हैं.

## XPS क्या है और टेक्स्ट क्यों जोड़ें?
XPS (XML Paper Specification) माइक्रोसॉफ्ट का फिक्स्ड‑लेआउट दस्तावेज़ फ़ॉर्मेट है, जो PDF के समान है लेकिन XML पर आधारित है। XPS फ़ाइल में टेक्स्ट जोड़ना आम है जब आपको सटीक प्लेसमेंट चाहिए, जैसे लेबल, वॉटरमार्क, या रिपोर्ट में डायनामिक डेटा। Aspose.Page का उपयोग करके आप XML की लो‑लेवल संरचनाओं से निपटे बिना XPS को मैनीपुलेट कर सकते हैं।

## XPS टेक्स्ट जोड़ने के लिए Aspose.Page क्यों उपयोग करें?
- **पूर्ण नियंत्रण** glyph पोजिशनिंग, फ़ॉन्ट शैलियों, और ब्रशेज़ पर।  
- **कोई बाहरी निर्भरताएँ नहीं** – शुद्ध Java API।  
- **उच्च सटीकता** रेंडरिंग जो प्लेटफ़ॉर्म्स के बीच लेआउट को संरक्षित रखती है।  
- **व्यापक दस्तावेज़ीकरण** और तेज़ ऑनबोर्डिंग के लिए सैंपल कोड।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK)** – एक नवीनतम संस्करण (8 या उससे ऊपर) स्थापित हो।  
- **Aspose.Page for Java** – आधिकारिक साइट से लाइब्रेरी डाउनलोड करें [here](https://releases.aspose.com/page/java/).  
- **एक Java IDE** – IntelliJ IDEA, Eclipse, या कोई भी एडिटर जो आप पसंद करते हैं।

## पैकेज आयात करें
XPS मैनीपुलेशन के लिए आवश्यक क्लासेज़ को आयात करके शुरू करें:

```java
import java.awt.Color;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
```

## चरण 1: दस्तावेज़ डायरेक्टरी सेट करें (create xps file)
परिभाषित करें कि जेनरेट की गई XPS फ़ाइल कहाँ संग्रहीत होगी:

```java
String dataDir = "Your Document Directory";
```

## चरण 2: XPS दस्तावेज़ बनाएं (create xps document)
एक नया, खाली XPS दस्तावेज़ इंस्टैंशिएट करें:

```java
XpsDocument doc = new XpsDocument();
```

## चरण 3: टेक्स्ट स्टाइलिंग के लिए ब्रश बनाएं
एक सॉलिड‑कलर ब्रश टेक्स्ट का रंग निर्धारित करता है। यहाँ हम काला उपयोग करते हैं:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
```

## चरण 4: Glyphs जोड़ें – वास्तविक टेक्स्ट (aspose.page add text)
वह टेक्स्ट जोड़ें जिसे आप दस्तावेज़ में दिखाना चाहते हैं। `addGlyphs` मेथड आपको फ़ॉन्ट, आकार, शैली, और सटीक कॉर्डिनेट्स निर्दिष्ट करने देता है:

```java
XpsGlyphs glyphs = doc.addGlyphs("Arial", 12, XpsFontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.setFill(textFill);
```

## चरण 5: परिणामी XPS दस्तावेज़ सहेजें (save xps file)
अंत में, दस्तावेज़ को डिस्क पर लिखें:

```java
doc.save(dataDir + "AddText_out.xps");
```

आवश्यकतानुसार अतिरिक्त पंक्तियों को सम्मिलित करने, फ़ॉन्ट बदलने, या स्थितियों को समायोजित करने के लिए **Add Glyphs** चरण को दोहराएँ।

## सामान्य समस्याएँ और प्रो टिप्स
- **गलत निर्देशांक:** XPS बिंदुओं (1/72 इंच) में मापी गई कोऑर्डिनेट सिस्टम का उपयोग करता है। टेक्स्ट को सटीक रूप से स्थित करने के लिए `x` और `y` मानों को समायोजित करें।  
- **फ़ॉन्ट नहीं मिला:** सुनिश्चित करें कि फ़ॉन्ट नाम (जैसे “Arial”) कोड चलाने वाले मशीन पर स्थापित है।  
- **लाइसेंस अपवाद:** वैध लाइसेंस के बिना, उत्पन्न XPS में वॉटरमार्क हो सकता है। इसे रोकने के लिए एप्लिकेशन में जल्दी लाइसेंस लागू करें।

## अक्सर पूछे जाने वाले प्रश्न

### क्या Aspose.Page सभी Java IDEs के साथ संगत है?
हाँ, Aspose.Page लोकप्रिय Java IDEs जैसे IntelliJ IDEA और Eclipse के साथ काम करता है।

### क्या मैं जोड़े गए टेक्स्ट पर विभिन्न फ़ॉन्ट शैलियाँ लागू कर सकता हूँ?
बिल्कुल! `addGlyphs` कॉल करते समय `XpsFontStyle.Bold`, `Italic` या शैलियों को मिलाकर उपयोग करें।

### Aspose.Page के अतिरिक्त उदाहरण और दस्तावेज़ीकरण कहाँ मिल सकते हैं?
व्यापक दस्तावेज़ीकरण यहाँ देखें [here](https://reference.aspose.com/page/java/).

### क्या Aspose.Page के लिए मुफ्त ट्रायल उपलब्ध है?
हाँ, आप मुफ्त ट्रायल यहाँ प्राप्त कर सकते हैं [here](https://releases.aspose.com/).

### मैं Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?
अस्थायी लाइसेंस यहाँ प्राप्त करें [here](https://purchase.aspose.com/temporary-license/).

**Q: क्या मैं टेक्स्ट के साथ इमेजेज़ एम्बेड कर सकता हूँ?**  
A: हाँ – `XpsImage` ऑब्जेक्ट्स को glyphs के साथ उपयोग करके रिच लेआउट बना सकते हैं।

**Q: क्या Aspose.Page Unicode कैरेक्टर्स को सपोर्ट करता है?**  
A: यह पूरी तरह से Unicode को सपोर्ट करता है, जिससे आप किसी भी भाषा में टेक्स्ट जोड़ सकते हैं।

**Q: परीक्षण के लिए कौन सा Aspose.Page संस्करण उपयोग किया गया था?**  
A: कोड को Aspose.Page 23.12 for Java के साथ परीक्षण किया गया था।

---

**अंतिम अपडेट:** 2026-04-24  
**परीक्षण किया गया:** Aspose.Page 23.12 for Java  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}