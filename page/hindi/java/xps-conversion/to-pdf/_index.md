---
date: 2025-12-23
description: Aspose.Page का उपयोग करके जावा में XPS को PDF में कैसे बदलें, सीखें।
  यह गाइड चरण‑दर‑चरण रूपांतरण, XPS से PDF रेंडर करने और PDF पृष्ठ संख्याएँ निर्दिष्ट
  करने का प्रदर्शन करता है।
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: जावा में XPS को PDF में कैसे बदलें
url: /hi/java/xps-conversion/to-pdf/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में XPS को PDF में कैसे बदलें

## Java में XPS को PDF में कैसे बदलें
Java विकास के क्षेत्र में, **XPS को PDF में कैसे बदलें** एक अक्सर पूछा जाने वाला प्रश्न है। चाहे आप एक दस्तावेज़‑प्रबंधन प्रणाली बना रहे हों या प्रिंट करने योग्य रिपोर्ट उत्पन्न करनी हों, XPS फ़ाइलों को विश्वसनीय रूप से बदलना एक गेम‑चेंजर हो सकता है। सौभाग्य से, Aspose.Page for Java केवल कुछ लाइनों के कोड के साथ **XPS से PDF रेंडर** करना आसान बनाता है।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी परिवर्तन को संभालती है?** Aspose.Page for Java।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बुनियादी सेटअप के लिए लगभग 10‑15 मिनट।  
- **क्या लाइसेंस की आवश्यकता है?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है।  
- **क्या मैं केवल चयनित पृष्ठों को बदल सकता हूँ?** हाँ – *specify PDF page numbers* विकल्प का उपयोग करें।  
- **क्या परिवर्तन बिना हानि के होता है?** लाइब्रेरी वेक्टर ग्राफ़िक्स और टेक्स्ट की सटीकता को बनाए रखती है।

## XPS से PDF परिवर्तन क्या है?
XPS (XML Paper Specification) माइक्रोसॉफ्ट का फिक्स्ड‑लेआउट दस्तावेज़ फ़ॉर्मेट है। इसे PDF में बदलने से आप दस्तावेज़ों को सार्वभौमिक रूप से स्वीकृत PDF मानक का उपयोग करके साझा, प्रिंट या संग्रहित कर सकते हैं।

## Aspose.Page for Java से XPS से PDF रेंडर करने के फायदे
- **उच्च सटीकता** – वेक्टर ग्राफ़िक्स, फ़ॉन्ट और लेआउट को बरकरार रखता है।  
- **सूक्ष्म नियंत्रण** – आप इमेज क्वालिटी, कंप्रेशन सेट कर सकते हैं और यहाँ तक कि विशिष्ट पृष्ठ भी चुन सकते हैं।  
- **कोई बाहरी निर्भरताएँ नहीं** – शुद्ध Java, किसी भी प्लेटफ़ॉर्म पर काम करता है जो JDK को सपोर्ट करता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

- **Java Development Kit (JDK)** – कोई भी हालिया संस्करण (8+ अनुशंसित)।  
- **Aspose.Page for Java** – आधिकारिक [documentation](https://reference.aspose.com/page/java/) से लाइब्रेरी डाउनलोड करें।  
- वह XPS फ़ाइल जिसे आप बदलना चाहते हैं।

## पैकेज इम्पोर्ट करें
अपने Java प्रोजेक्ट में Aspose.Page for Java के साथ काम करने के लिए आवश्यक पैकेज इम्पोर्ट करें। यह चरण XPS से PDF परिवर्तन के लिए आवश्यक कार्यक्षमताओं तक पहुँचने के लिए महत्वपूर्ण है।

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## चरण‑दर‑चरण गाइड

### चरण 1: दस्तावेज़ डायरेक्टरी सेट करें
उस फ़ोल्डर का पाथ परिभाषित करें जिसमें आपका स्रोत XPS फ़ाइल मौजूद है।

```java
String dataDir = "Your Document Directory";
```

### चरण 2: PDF आउटपुट स्ट्रीम इनिशियलाइज़ करें
एक `FileOutputStream` बनाएं जो उत्पन्न PDF को प्राप्त करेगा।

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

### चरण 3: XPS दस्तावेज़ लोड करें
Aspose.Page का उपयोग करके XPS फ़ाइल लोड करें।

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### चरण 4: PDF सेव ऑप्शन इनिशियलाइज़ करें  
परिवर्तन के लिए विकल्प बनाएं। यहाँ आप **specify PDF page numbers** कर सकते हैं, इमेज क्वालिटी समायोजित कर सकते हैं, और कंप्रेशन सेट कर सकते हैं।

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### चरण 5: PDF रेंडरिंग डिवाइस बनाएं  
एक रेंडरिंग डिवाइस सेट करें जो PDF आउटपुट लिखेगा।

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### चरण 6: दस्तावेज़ को सेव करें  
अंत में, कॉन्फ़िगर किए गए विकल्प और डिवाइस का उपयोग करके XPS दस्तावेज़ को PDF के रूप में सेव करें।

```java
document.save(device, options);
```

इन चरणों को दोहराएँ, फ़ाइल पाथ और विकल्पों को अपनी विशिष्ट स्थिति के अनुसार समायोजित करें।

## XPS बदलते समय PDF पेज नंबर कैसे निर्दिष्ट करें
यदि आपको मूल XPS से केवल कुछ पृष्ठ चाहिए, तो `setPageNumbers` एरे को इच्छित पृष्ठ सूचकांकों (1 से शुरू) से भरें। यह फ़ाइल आकार और प्रोसेसिंग समय को कम करने में मदद करता है।

## सामान्य समस्याएँ एवं ट्रबलशूटिंग
- **FileNotFoundException** – सुनिश्चित करें कि `dataDir` सही फ़ोल्डर की ओर इशारा कर रहा है और XPS फ़ाइल का नाम मेल खाता है।  
- **LicenseException** – उत्पादन उपयोग के लिए वैध Aspose.Page लाइसेंस आवश्यक है; अन्यथा लाइब्रेरी मूल्यांकन मोड में वॉटरमार्क के साथ चलती है।  
- **कम इमेज क्वालिटी** – आवश्यकतानुसार `setJpegQualityLevel` बढ़ाएँ या लॉसलेस कंप्रेशन पर स्विच करें।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Page for Java से मल्टी‑पेज XPS फ़ाइल को बदल सकता हूँ?
हाँ, आप `PdfSaveOptions` में **specify PDF page numbers** (देखें चरण 4) का उपयोग करके आवश्यक पृष्ठ शामिल कर सकते हैं।

### अतिरिक्त समर्थन या Aspose.Page‑संबंधित प्रश्नों के लिए कहाँ जा सकता हूँ?
समुदाय समर्थन और चर्चा के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) देखें।

### क्या Aspose.Page for Java के लिए एक मुफ्त ट्रायल उपलब्ध है?
हाँ, आप एक [free trial](https://releases.aspose.com/) के साथ फीचर का अन्वेषण कर सकते हैं।

### Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करें?
अस्थायी लाइसेंस विवरण के लिए [इस लिंक](https://purchase.aspose.com/temporary-license/) पर जाएँ।

### Aspose.Page for Java लाइसेंस कहाँ खरीदें?
आप लाइसेंस [यहाँ](https://purchase.aspose.com/buy) खरीद सकते हैं।

---

**अंतिम अपडेट:** 2025-12-23  
**टेस्टेड विथ:** Aspose.Page for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}