---
date: 2026-05-05
description: Aspose.Page for Java का उपयोग करके EPS फ़ाइलों में XMP नामित मान कैसे
  जोड़ें, सीखें – कोड उदाहरणों के साथ चरण‑दर‑चरण मार्गदर्शिका।
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
linktitle: जावा का उपयोग करके XMP में नामित मान जोड़ें
second_title: Aspose.Page Java API
title: जावा का उपयोग करके EPS फ़ाइलों में XMP नामित मान कैसे जोड़ें
url: /hi/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP मेटाडेटा में नामित मान जोड़ें Java का उपयोग करके

## परिचय
आधुनिक Java विकास में, EPS फ़ाइलों के भीतर **XMP** मेटाडेटा कैसे जोड़ें सीखना दस्तावेज़ की उत्पत्ति को संरक्षित करने और खोजयोग्यता में सुधार के लिए आवश्यक है। **asp** (Aspose.Page for Java) के साथ, आप कस्टम नामित मानों को XMP पैकेट में आसानी से सम्मिलित कर सकते हैं। यह ट्यूटोरियल आपको सटीक चरणों के माध्यम से ले जाता है—कोड स्निपेट्स सहित—ताकि आप आज ही अपने EPS दस्तावेज़ों में XMP मेटाडेटा जोड़ना शुरू कर सकें।

## त्वरित उत्तर
- **कौनसी लाइब्रेरी आवश्यक है?** Aspose.Page for Java (asp)  
- **कौनसी फ़ाइल प्रकार लक्षित है?** EPS files containing XMP metadata  
- **मुख्य उपयोग मामला?** Add custom named values (e.g., page size limits) to XMP  
- **पूर्वापेक्षाएँ?** JDK 8+ and the Aspose.Page for Java library  
- **सामान्य कार्यान्वयन समय?** 5–10 minutes once the library is set up  

## asp क्या है?
*asp* **Aspose** का संक्षिप्त रूप है, जो .NET और Java APIs का एक समूह है जो दस्तावेज़ प्रसंस्करण को सरल बनाता है। Aspose.Page for Java घटक आपको PostScript और EPS फ़ाइलें बनाने, संपादित करने और बदलने की अनुमति देता है, साथ ही उनके मेटाडेटा, जिसमें XMP शामिल है, तक पूर्ण प्रोग्रामेटिक पहुंच प्रदान करता है।

## XMP मेटाडेटा में नामित मान क्यों जोड़ें?
- **सर्च इंजन मित्रता:** कस्टम टैग खोज योग्यता को बढ़ाते हैं।  
- **वर्कफ़्लो ऑटोमेशन:** डाउनस्ट्रीम टूल आपके कस्टम मानों को पढ़कर निर्णय ले सकते हैं।  
- **अनुपालन:** नियामक जानकारी को सीधे दस्तावेज़ पैकेज में एम्बेड करें।  

## यह क्यों महत्वपूर्ण है
XMP में नामित मान जोड़ने से आप मनमाने कुंजी‑मान जोड़े संग्रहीत कर सकते हैं जिन्हें पूरे EPS फ़ाइल को पार्स किए बिना पढ़ा जा सकता है। यह क्षमता स्वचालित प्रकाशन पाइपलाइन, डिजिटल एसेट मैनेजमेंट सिस्टम, और अनुपालन‑आधारित वर्कफ़्लो में विशेष रूप से मूल्यवान है जहाँ मेटाडेटा डाउनस्ट्रीम कार्यों को संचालित करता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- **Java Development Kit (JDK):** आपके मशीन पर स्थापित नवीनतम JDK (8 या उससे ऊपर)।  
- **Aspose.Page for Java लाइब्रेरी:** इसे आधिकारिक [डाउनलोड लिंक](https://releases.aspose.com/page/java/) से डाउनलोड करें। JAR को अपने प्रोजेक्ट के क्लासपाथ में जोड़ें।  
- **एक EPS फ़ाइल** जिसमें पहले से XMP मेटाडेटा हो या जो स्वचालित रूप से उत्पन्न हो जाएगा।  

## पैकेज आयात करें
आवश्यक Java पैकेज आयात करके शुरू करें। ये इम्पोर्ट आपको फ़ाइल स्ट्रीम, EPS दस्तावेज़ मॉडल, और XMP हैंडलिंग क्लासेज़ तक पहुंच प्रदान करते हैं।

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Java का उपयोग करके EPS फ़ाइलों में XMP नामित मान कैसे जोड़ें
नीचे एक संक्षिप्त, क्रमांकित चरण-दर-चरण मार्गदर्शिका है जो बिल्कुल **XMP** नामित मानों को EPS दस्तावेज़ में कैसे जोड़ें दिखाती है।

### चरण 1: इनपुट EPS फ़ाइल स्ट्रीम को प्रारंभ करें
`FileInputStream` में स्रोत EPS फ़ाइल लोड करें। यह स्ट्रीम दस्तावेज़ को Aspose के API में भेजती है।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **प्रो टिप:** `dataDir` वेरिएबल को कॉन्फ़िगर करने योग्य रखें ताकि समान कोड विभिन्न वातावरणों में काम करे।

### चरण 2: XMP मेटाडेटा प्राप्त करें
मौजूदा XMP पैकेट प्राप्त करें। यदि EPS फ़ाइल में यह नहीं है, तो Aspose PS टिप्पणी से भरकर एक नया XMP ऑब्जेक्ट बनाता है।

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### चरण 3: नामित मान जोड़ें
XMP संरचना में एक कस्टम नामित मान डालें। इस उदाहरण में हम `xmpTPg:MaxPageSize` नेमस्पेस के तहत एक नई कुंजी जोड़ते हैं।

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **यह क्यों महत्वपूर्ण है:** नामित मान आपको मनमाने कुंजी‑मान जोड़े संग्रहीत करने देते हैं जिन्हें डाउनस्ट्रीम एप्लिकेशन पूरे दस्तावेज़ को पार्स किए बिना पढ़ सकते हैं।

### चरण 4: आउटपुट EPS फ़ाइल स्ट्रीम को प्रारंभ करें
एक `FileOutputStream` तैयार करें जहाँ संशोधित EPS सहेजा जाएगा।

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### चरण 5: दस्तावेज़ सहेजें
परिवर्तनों को स्थायी बनाएं। `save` कॉल अपडेटेड XMP पैकेट को EPS फ़ाइल में वापस लिखता है।

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### चरण 6: इनपुट EPS स्ट्रीम बंद करें
संसाधन लीक से बचने के लिए मूल फ़ाइल हैंडल को रिलीज़ करें।

```java
psStream.close();
```

इन छह चरणों का पालन करके, आपने सफलतापूर्वक **asp** (Aspose.Page for Java) का उपयोग करके **XMP मेटाडेटा में नामित मान जोड़ा** है।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|-----|
| `xmp` पर `NullPointerException` | EPS फ़ाइल में XMP नहीं है और Aspose इसे उत्पन्न करने में विफल रहा | सुनिश्चित करें कि EPS में कम से कम एक PS टिप्पणी हो या मैन्युअली नया `XmpMetadata` इंस्टेंस बनाएं। |
| आउटपुट फ़ाइल खाली है | आउटपुट स्ट्रीम फ़्लश/क्लोज नहीं किया गया | जाँचें कि `outPsStream.close()` को `finally` ब्लॉक में कॉल किया गया है (जैसा दिखाया गया है)। |
| डुप्लिकेट कुंजी त्रुटि | एक ही नामित मान दो बार जोड़ा गया | `xmp.containsNamedValue(...)` के साथ जांचें कि कुंजी पहले से मौजूद है या नहीं, फिर जोड़ें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न:** क्या मैं Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?  
**उत्तर:** हाँ, Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ सहजता से काम करने के लिए डिज़ाइन किया गया है, जिससे आपके विकास वातावरण में लचीलापन मिलता है।

**प्रश्न:** क्या Aspose.Page for Java के लिए मुफ्त ट्रायल उपलब्ध है?  
**उत्तर:** हाँ, आप Aspose.Page for Java का मुफ्त ट्रायल [यहाँ](https://releases.aspose.com/) से प्राप्त कर सकते हैं।

**प्रश्न:** मैं Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?  
**उत्तर:** Aspose.Page for Java के लिए अस्थायी लाइसेंस प्राप्त करने हेतु [इस लिंक](https://purchase.aspose.com/temporary-license/) पर जाएँ।

**प्रश्न:** Aspose.Page for Java के लिए अधिक ट्यूटोरियल और उदाहरण कहाँ मिलेंगे?  
**उत्तर:** व्यापक ट्यूटोरियल और उदाहरणों के लिए [डॉक्यूमेंटेशन](https://reference.aspose.com/page/java/) देखें।

**प्रश्न:** क्या Aspose.Page for Java बड़े‑पैमाने के प्रोजेक्ट्स के लिए उपयुक्त है?  
**उत्तर:** बिल्कुल, Aspose.Page for Java को बड़े‑पैमाने के प्रोजेक्ट्स को कुशलतापूर्वक संभालने के लिए डिज़ाइन किया गया है, जो मजबूत दस्तावेज़ हेरफेर क्षमताएँ प्रदान करता है।

## निष्कर्ष
इस गाइड में हमने दिखाया कि **asp** (Aspose.Page for Java) कैसे EPS फ़ाइलों में **XMP मेटाडेटा में नामित मान जोड़ना** सरल बनाता है। उपरोक्त चरणों के साथ, आप अपने दस्तावेज़ों को कस्टम मेटाडेटा से समृद्ध कर सकते हैं, खोजयोग्यता में सुधार कर सकते हैं, और अधिक स्मार्ट डाउनस्ट्रीम प्रोसेसिंग सक्षम कर सकते हैं।

---

**अंतिम अपडेट:** 2026-05-05  
**परीक्षित संस्करण:** Aspose.Page for Java 24.12 (latest at time of writing)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}