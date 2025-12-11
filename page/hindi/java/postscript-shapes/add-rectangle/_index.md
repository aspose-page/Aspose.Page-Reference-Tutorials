---
date: 2025-12-11
description: Aspose.Page का उपयोग करके Java PostScript में आयताकार आकार कैसे बनाएं,
  सीखें। यह चरण‑दर‑चरण मार्गदर्शिका दिखाती है कि पेंट कैसे सेट करें, जावा में आयत
  का रंग कैसे सेट करें, और जीवंत ग्राफिक्स कैसे बनाएं।
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page के साथ Java PostScript में आयत कैसे बनाएं
url: /hi/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript में Aspose.Page के साथ आयत कैसे बनाएं

## Introduction
यदि आपको एक Java PostScript फ़ाइल के अंदर **आयत कैसे बनाएं** आकारों की आवश्यकता है, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम Aspose.Page for Java का उपयोग करके रंगीन आयतें जोड़ना, उनके फ़िल और स्ट्रोक को नियंत्रित करना, और परिणाम को एक PostScript दस्तावेज़ के रूप में सहेजना दिखाएंगे। आप बिल्कुल **पेंट कैसे सेट करें**, आयत की ज्योमेट्री कैसे परिभाषित करें, और क्यों यह तरीका प्रोग्रामेटिक रूप से प्रिंटेबल ग्राफिक्स उत्पन्न करने के लिए आदर्श है, देखेंगे।

## Quick Answers
- **क्या लाइब्रेरी आवश्यक है?** Aspose.Page for Java  
- **क्या मैं आयत के रंग बदल सकता हूँ?** Yes – use `setPaint` with any `java.awt.Color`  
- **क्या विकास के लिए लाइसेंस चाहिए?** A free trial works for testing; a license is required for production  
- **उदाहरण में कौन सा पेज आकार उपयोग किया गया है?** A4 (default `PsSaveOptions`)  
- **क्या कोड Java 8+ के साथ संगत है?** Absolutely – it uses standard AWT classes  

## Prerequisites
ट्यूटोरियल में प्रवेश करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ मौजूद हैं:
- Java प्रोग्रामिंग की बुनियादी समझ।  
- Aspose.Page for Java लाइब्रेरी स्थापित हो। यदि नहीं, तो इसे [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) से डाउनलोड करें।  
- आपके मशीन पर Java विकास पर्यावरण सेट अप हो।  

## Import Packages
अपने Java प्रोजेक्ट में, आवश्यक पैकेज इम्पोर्ट करके शुरू करें:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## How to Draw Rectangle in Java PostScript
नीचे पूरा कार्यप्रवाह स्पष्ट चरणों में विभाजित किया गया है। प्रत्येक चरण में एक छोटा विवरण और उसके बाद मूल कोड ब्लॉक (अपरिवर्तित) शामिल है।

### Step 1: Set Paint for Filling Rectangle  
**पेंट कैसे सेट करें** – हम पहले आयत के लिए नारंगी भराव रंग चुनते हैं।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Step 2: Set Paint for Stroking Rectangle  
**जावा में आयत का रंग सेट करें** – अब हम पेंट को लाल में बदलते हैं और स्ट्रोक की चौड़ाई निर्धारित करते हैं।

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Step 3: Close Current Page and Save Document  
ड्रॉ करने के बाद, हम पेज बंद करते हैं और फ़ाइल को सहेजते हैं।

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Why Use Aspose.Page for Rectangle Graphics?
- **Cross‑platform**: मानक PostScript उत्पन्न करता है जो किसी भी प्रिंटर पर काम करता है।  
- **Fine‑grained control**: आप भराव रंग, स्ट्रोक रंग, और लाइन की चौड़ाई स्वतंत्र रूप से सेट कर सकते हैं।  
- **No external dependencies**: केवल बिल्ट‑इन AWT ज्योमेट्री क्लासेज़ का उपयोग करता है।  

## Common Issues & Tips
- **File path errors** – सुनिश्चित करें कि `dataDir` फ़ाइल विभाजक (`/` या `\\`) के साथ समाप्त हो।  
- **License exceptions** – ट्रायल संस्करण वॉटरमार्क जोड़ता है; उत्पादन उपयोग के लिए पूर्ण लाइसेंस प्राप्त करें।  
- **Color visibility** – कुछ प्रिंटर कुछ RGB मानों को अलग ढंग से व्याख्या कर सकते हैं; पहले एक साधारण काली आयत के साथ परीक्षण करें।  

## Conclusion
इस गाइड में हमने Java PostScript दस्तावेज़ में **आयत कैसे बनाएं** आकृतियों को प्रदर्शित किया, **पेंट कैसे सेट करें** को कवर किया, और Aspose.Page का उपयोग करके **जावा में आयत का रंग सेट करें** दिखाया। विभिन्न आकारों, रंगों और लाइन शैलियों के साथ प्रयोग करने में संकोच न करें ताकि रिपोर्ट, इनवॉइस या कस्टम प्रिंट के लिए समृद्ध प्रिंटेबल ग्राफिक्स बना सकें।

## Frequently Asked Questions

### Can I use Aspose.Page for Java with other programming languages?
क्या मैं Aspose.Page for Java को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?  
Aspose.Page मुख्यतः Java को सपोर्ट करता है, लेकिन अन्य भाषाओं के लिए समान लाइब्रेरी उपलब्ध हैं।

### Is there a trial version of Aspose.Page for Java available?
क्या Aspose.Page for Java का ट्रायल संस्करण उपलब्ध है?  
हाँ, आप Aspose.Page for Java की सुविधाओं को [free trial version](https://releases.aspose.com/) के साथ देख सकते हैं।

### Where can I find additional help and discussions?
मैं अतिरिक्त सहायता और चर्चा कहाँ पा सकता हूँ?  
समुदाय से जुड़ने और सहायता पाने के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) पर जाएँ।

### How can I obtain a temporary license for Aspose.Page for Java?
मैं Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?  
अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) प्राप्त करें।

### Where can I purchase a licensed version of Aspose.Page for Java?
मैं Aspose.Page for Java का लाइसेंस प्राप्त संस्करण कहाँ खरीद सकता हूँ?  
लाइसेंस प्राप्त संस्करण [यहाँ](https://purchase.aspose.com/buy) खरीदें।

**Additional Q&A**

**Q:** *क्या मैं आयत का आकार गतिशील रूप से बदल सकता हूँ?*  
**A:** Yes – `fill` या `draw` कॉल करने से पहले `Rectangle2D.Float(x, y, width, height)` पैरामीटर को सरलता से बदलें।

**Q:** *क्या आयत के अंदर टेक्स्ट जोड़ना संभव है?*  
**A:** बिल्कुल। आयत ड्रॉ करने के बाद, इच्छित फ़ॉन्ट और स्थिति के साथ `document.drawString(...)` का उपयोग करें।

**Q:** *क्या Aspose.Page वृत्त या बहुभुज जैसी अन्य आकृतियों का समर्थन करता है?*  
**A:** हाँ, API विभिन्न वेक्टर ग्राफिक्स के लिए `drawEllipse` और `drawPolygon` जैसी विधियाँ प्रदान करता है।

---

**अंतिम अपडेट:** 2025-12-11  
**परीक्षित संस्करण:** Aspose.Page for Java 24.12 (latest)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}