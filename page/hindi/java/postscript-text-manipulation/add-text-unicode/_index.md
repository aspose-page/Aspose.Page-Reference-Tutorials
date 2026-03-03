---
date: 2025-12-17
description: Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट में यूनिकोड टेक्स्ट कैसे
  जोड़ें, सीखें – यूनिकोड स्ट्रिंग्स को आसानी से जोड़ने के लिए चरण‑दर‑चरण मार्गदर्शिका।
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page के साथ जावा पोस्टस्क्रिप्ट में यूनिकोड टेक्स्ट कैसे जोड़ें
url: /hi/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा पोस्टस्क्रिप्ट में Unicode टेक्स्ट कैसे जोड़ें Aspose.Page के साथ

## परिचय
यदि आप **Unicode** अक्षरों को जावा‑आधारित पोस्टस्क्रिप्ट (या XPS) वर्कफ़्लो में कैसे जोड़ें, इस बारे में सोच रहे हैं, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम Aspose.Page लाइब्रेरी फॉर जावा का उपयोग करके Unicode स्ट्रिंग्स को एम्बेड करने के सटीक चरणों को दिखाएंगे। गाइड के अंत तक आप किसी भी भाषा‑विशिष्ट टेक्स्ट—अरबी, चीनी, इमोजी, जो भी हो—को सीधे अपने पोस्टस्क्रिप्ट आउटपुट में डाल सकेंगे।

## त्वरित उत्तर
- **कौनसी लाइब्रेरी चाहिए?** Aspose.Page for Java  
- **क्या मैं दाएँ‑से‑बाएँ स्क्रिप्ट जोड़ सकता हूँ?** हाँ, कोड में दिखाए अनुसार Bidi लेवल सेट करें  
- **क्या विकास के लिए लाइसेंस चाहिए?** परीक्षण के लिए मुफ्त ट्रायल काम करता है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है  
- **कौनसा IDE सबसे अच्छा है?** कोई भी Java IDE (IntelliJ IDEA, Eclipse, NetBeans)  
- **क्या कोड क्रॉस‑प्लेटफ़ॉर्म है?** बिल्कुल—Windows, macOS, या Linux पर चलाएँ  

## पोस्टस्क्रिप्ट के संदर्भ में “Unicode कैसे जोड़ें” क्या है?
Unicode जोड़ना मतलब ऐसे अक्षर डालना है जो बेसिक ASCII रेंज से परे कोड पॉइंट्स द्वारा प्रतिनिधित्व होते हैं। Aspose.Page लो‑लेवल एन्कोडिंग विवरणों को एब्स्ट्रैक्ट करता है, जिससे आप टेक्स्ट कंटेंट और उसकी विज़ुअल प्लेसमेंट पर ध्यान केंद्रित कर सकते हैं।

## Unicode टेक्स्ट के लिए Aspose.Page क्यों उपयोग करें?
- **पूर्ण Unicode समर्थन** – जटिल स्क्रिप्ट, लिगेचर, और दाएँ‑से‑बाएँ भाषाओं को संभालता है।  
- **कोई बाहरी निर्भरताएँ नहीं** – फ़ॉन्ट फ़ाइलों को मैन्युअल रूप से प्रबंधित करने की आवश्यकता नहीं; API सिस्टम फ़ॉन्ट के साथ काम करता है।  
- **सरल API** – बहुभाषी टेक्स्ट रेंडर करने के लिए कुछ मेथड कॉल पर्याप्त हैं।  

## पूर्वापेक्षाएँ
पहले सुनिश्चित करें कि आपके पास निम्नलिखित चीज़ें तैयार हैं:

1. **Java Development Kit (JDK)** – कोई भी नवीनतम संस्करण (8 या उससे नया)।  
2. **Aspose.Page for Java** – लाइब्रेरी को [download link](https://releases.aspose.com/page/java/) से डाउनलोड और इंस्टॉल करें।  
3. **आपके पसंद का IDE** – IntelliJ IDEA, Eclipse, या कोई भी अन्य Java IDE जो आप पसंद करते हैं।  

## पैकेज आयात करें
अपने Java सोर्स फ़ाइल में आवश्यक Aspose.Page क्लासेज़ जोड़ें:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## चरण 1: अपना प्रोजेक्ट सेट अप करें
एक नया Java प्रोजेक्ट बनाएं, Aspose.Page JAR को प्रोजेक्ट के बिल्ड पाथ में जोड़ें, और एक फ़ोल्डर बनाएं जहाँ जेनरेटेड XPS फ़ाइल सहेजी जाएगी। इस फ़ोल्डर को बाद में `dataDir` के रूप में संदर्भित किया जाएगा।

## चरण 2: XPS दस्तावेज़ प्रारंभ करें
एक खाली XPS दस्तावेज़ बनाएं जो कंटेंट रखेगा:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## चरण 3: Unicode टेक्स्ट जोड़ें
अब हम वास्तव में Unicode स्ट्रिंग जोड़ेंगे। नीचे दिया गया उदाहरण उल्टा वाक्य “AVAJ rof SPX.esopsA” लिखता है, जिसमें केवल ASCII अक्षर हैं, लेकिन आप इसे किसी भी Unicode टेक्स्ट (जैसे अरबी “مرحبا” या चीनी “你好”) से बदल सकते हैं।

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **प्रो टिप:** दाएँ‑से‑बाएँ भाषाओं को सही ढंग से रेंडर करने के लिए `glyphs.setBidiLevel(1);` सेट करें। बाएँ‑से‑दाएँ स्क्रिप्ट के लिए आप इस लाइन को छोड़ सकते हैं।

## चरण 4: दस्तावेज़ सहेजें
XPS फ़ाइल को डिस्क पर सहेजें:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

प्रोग्राम चलाने के बाद, किसी भी XPS व्यूअर से जेनरेटेड `AddEncodingText_out.xps` खोलें और निर्दिष्ट कॉर्डिनेट्स पर Unicode टेक्स्ट रेंडर होते देखें।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|--------|-------|----------|
| टेक्स्ट वर्गों के रूप में दिखता है | फ़ॉन्ट नहीं मिला या अक्षरों को सपोर्ट नहीं करता | ऐसे फ़ॉन्ट का उपयोग करें जिसमें आवश्यक ग्लिफ़ हों (जैसे “Arial Unicode MS”) |
| दाएँ‑से‑बाएँ टेक्स्ट बाएँ‑से‑दाएँ दिखता है | Bidi level सेट नहीं है | `glyphs.setBidiLevel(1);` कॉल करें |
| फ़ाइल सहेजी नहीं गई | `dataDir` पथ अमान्य या लिखने की अनुमति नहीं | डायरेक्टरी मौजूद है और एप्लिकेशन के पास लिखने की अनुमति है, यह सुनिश्चित करें |

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Page for Java को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?
Aspose.Page मुख्यतः जावा के लिए डिज़ाइन किया गया है, लेकिन Aspose विभिन्न प्रोग्रामिंग भाषाओं के लिए लाइब्रेरी प्रदान करता है।

### क्या मुफ्त ट्रायल उपलब्ध है?
हाँ, आप Aspose.Page का मुफ्त ट्रायल [यहाँ](https://releases.aspose.com/) से एक्सेस कर सकते हैं।

### Aspose.Page के समर्थन और चर्चा कहाँ मिल सकती है?
समर्थन और चर्चाओं के लिए [Aspose.Page फ़ोरम](https://forum.aspose.com/c/page/39) देखें।

### Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त करें?
आप अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

### Aspose.Page में उपलब्ध फ़ॉन्ट शैलियाँ क्या हैं?
Aspose.Page Regular, Bold, Italic, और BoldItalic जैसी फ़ॉन्ट शैलियों को सपोर्ट करता है।

## निष्कर्ष
आपने अब **Unicode टेक्स्ट को जावा पोस्टस्क्रिप्ट (XPS) दस्तावेज़ में Aspose.Page के साथ जोड़ना** सीख लिया है। यह क्षमता मल्टीभाषी रिपोर्टिंग, अंतर्राष्ट्रीय इनवॉइस, और किसी भी ऐसी स्थिति में द्वार खोलती है जहाँ गैर‑ASCII अक्षर आवश्यक हों। टेक्स्ट रोटेशन, क्लिपिंग पाथ, या कस्टम फ़ॉन्ट एम्बेड करने जैसी अतिरिक्त सुविधाओं का पता लगाने के लिए आधिकारिक [डॉक्यूमेंटेशन](https://reference.aspose.com/page/java/) देखें।

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
