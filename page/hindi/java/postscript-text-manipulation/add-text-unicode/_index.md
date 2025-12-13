---
date: 2025-12-13
description: जावा में ASP पेज पर टेक्स्ट कैसे जोड़ें, जावा में फ़ॉन्ट स्टाइल कैसे
  सेट करें, और Aspose.Page का उपयोग करके यूनिकोड टेक्स्ट कैसे जोड़ें, यह सीखें। हमारी
  चरण‑दर‑चरण गाइड का पालन करें।
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: ASP पेज में टेक्स्ट जोड़ें – जावा पोस्टस्क्रिप्ट में यूनिकोड
url: /hi/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – जावा पोस्टस्क्रिप्ट में यूनिकोड

## Introduction
यदि आपको जावा पोस्टस्क्रिप्ट वर्कफ़्लो में **asp page add text** करने की आवश्यकता है और यूनिकोड अक्षरों को संरक्षित रखना है, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम यूनिकोड टेक्स्ट जोड़ने, फ़ॉन्ट स्टाइल सेट करने, और **Aspose.Page for Java** का उपयोग करके परिणाम सहेजने की प्रक्रिया को समझेंगे। अंत तक आप समझ जाएंगे कि फ़ॉन्ट स्टाइल java कैसे सेट करें और अपने प्रोजेक्ट्स में यूनिकोड टेक्स्ट को प्रभावी ढंग से कैसे जोड़ें।

## Quick Answers
- **जावा पोस्टस्क्रिप्ट में यूनिकोड टेक्स्ट जोड़ने के लिए कौन सी लाइब्रेरी उपयोग की जा सकती है?** Aspose.Page for Java.  
- **टेक्स्ट जोड़ने की प्रमुख मेथड कौन सी है?** `doc.addGlyphs(...)` साथ में `XpsGlyphs` ऑब्जेक्ट.  
- **क्या यूनिकोड के लिए विशेष फ़ॉन्ट चाहिए?** कोई भी TrueType/OpenType फ़ॉन्ट जो आवश्यक कोड पॉइंट्स को सपोर्ट करता हो (जैसे, Arial).  
- **क्या फ़ॉन्ट स्टाइल बदल सकते हैं?** हाँ, `XpsFontStyle` (Regular, Bold, Italic, आदि) का उपयोग करके.  
- **प्रोडक्शन में लाइसेंस आवश्यक है?** हाँ, गैर‑ट्रायल उपयोग के लिए एक वैध Aspose.Page लाइसेंस चाहिए.

## What is asp page add text?
`asp page add text` वह प्रक्रिया है जिसमें Aspose.Page API का उपयोग करके पोस्टस्क्रिप्ट या XPS दस्तावेज़ में टेक्स्ट स्ट्रिंग्स डाली जाती हैं। यह API लो‑लेवल पोस्टस्क्रिप्ट कमांड्स को एब्स्ट्रैक्ट करती है, जिससे आप `XpsGlyphs` जैसे हाई‑लेवल ऑब्जेक्ट्स के साथ काम कर सकते हैं।

## Why use Aspose.Page to set font style java and add Unicode text?
- **पूर्ण यूनिकोड सपोर्ट** – राइट‑टू‑लेफ्ट स्क्रिप्ट्स और जटिल ग्लिफ़्स को संभालता है.  
- **सरल API** – टेक्स्ट जोड़ने और स्टाइल लागू करने के लिए एक‑लाइन कॉल्स.  
- **क्रॉस‑प्लैटफ़ॉर्म** – किसी भी जावा‑कम्पैटिबल वातावरण में काम करता है.  
- **कोई बाहरी डिपेंडेंसी नहीं** – अतिरिक्त रेंडरिंग इंजन की आवश्यकता नहीं.

## Prerequisites
ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित प्री‑रिक्विज़िट्स मौजूद हैं:

1. **Java Development Kit (JDK)** – सुनिश्चित करें कि आपके मशीन पर जावा इंस्टॉल है.  
2. **Aspose.Page for Java** – Aspose.Page लाइब्रेरी को [download link](https://releases.aspose.com/page/java/) से डाउनलोड और इंस्टॉल करें.  
3. **Integrated Development Environment (IDE)** – अपना पसंदीदा जावा IDE चुनें, जैसे IntelliJ IDEA या Eclipse.

## Import Packages
अपने जावा प्रोजेक्ट में Aspose.Page के आवश्यक पैकेज इम्पोर्ट करें. अपने कोड में निम्नलाइनों को जोड़ें:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Step 1: Set Up Your Project
अपने IDE में एक नया जावा प्रोजेक्ट बनाएं और प्रोजेक्ट स्ट्रक्चर सेट करें. प्रोजेक्ट डिपेंडेंसीज़ में Aspose.Page लाइब्रेरी को शामिल करना न भूलें.

## Step 2: Initialize XPS Document
प्रोजेक्ट के भीतर एक नया XPS दस्तावेज़ इनिशियलाइज़ करके शुरू करें:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Step 3: Add Unicode Text
अब, Aspose.Page लाइब्रेरी का उपयोग करके अपने XPS दस्तावेज़ में यूनिकोड टेक्स्ट जोड़ें. नीचे दिया गया कोड स्निपेट उपयोग करें:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

यह कोड सेगमेंट यूनिकोड टेक्स्ट **"AVAJ rof SPX.esopsA"** को XPS दस्तावेज़ में (400, 200) निर्देशांक पर निर्दिष्ट फ़ॉन्ट और स्टाइल के साथ जोड़ता है. देखें कि `setBidiLevel(1)` कॉल राइट‑टू‑लेफ्ट रेंडरिंग को सक्षम करके सही यूनिकोड डिस्प्ले कैसे प्रदान करता है.

## Step 4: Save the Document
निम्नलिखित कोड का उपयोग करके परिणामी XPS दस्तावेज़ सहेजें:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## Conclusion
बधाई हो! आपने सफलतापूर्वक **asp page add text** किया और जावा पोस्टस्क्रिप्ट परिदृश्य में Aspose.Page का उपयोग करके फ़ॉन्ट स्टाइल सेट किया। यह विधि आपको यूनिकोड रेंडरिंग और स्टाइलिंग पर सूक्ष्म नियंत्रण देती है, जिससे अंतर्राष्ट्रीय रिपोर्ट, इनवॉइस, और ग्राफ़िक्स बनाना आसान हो जाता है।

Aspose.Page की अधिक सुविधाएँ और क्षमताएँ [documentation](https://reference.aspose.com/page/java/) में देखें.

## Frequently Asked Questions

**Q:** क्या मैं Aspose.Page for Java को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?  
**A:** Aspose.Page मुख्यतः जावा के लिए डिज़ाइन किया गया है, लेकिन Aspose विभिन्न प्रोग्रामिंग भाषाओं के लिए लाइब्रेरीज़ प्रदान करता है.

**Q:** क्या कोई फ्री ट्रायल उपलब्ध है?  
**A:** हाँ, आप Aspose.Page का फ्री ट्रायल [here](https://releases.aspose.com/) से एक्सेस कर सकते हैं.

**Q:** Aspose.Page के बारे में सपोर्ट और डिस्कशन कहाँ मिल सकते हैं?  
**A:** सपोर्ट और डिस्कशन के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) पर जाएँ.

**Q:** Aspose.Page के लिए टेम्पररी लाइसेंस कैसे प्राप्त करूँ?  
**A:** आप टेम्पररी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से ले सकते हैं.

**Q:** Aspose.Page में उपलब्ध फ़ॉन्ट स्टाइल कौन‑से हैं?  
**A:** Aspose.Page Regular, Bold, Italic, और BoldItalic जैसे फ़ॉन्ट स्टाइल्स को सपोर्ट करता है.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-13  
**Tested With:** Aspose.Page for Java (latest)  
**Author:** Aspose  

---