---
date: 2025-12-23
description: जावा में XPS को JPEG में कैसे बदलें सीखें और Aspose.Page का उपयोग करके
  XPS फ़ाइलों को प्रभावी ढंग से कैसे बदलें, यह जानें। सहज एकीकरण के लिए चरण‑दर‑चरण
  निर्देशों के साथ एक व्यापक गाइड।
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: जावा में XPS को JPEG में कैसे बदलें
url: /hi/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में XPS को JPEG में कैसे बदलें

## परिचय
इस ट्यूटोरियल में, **आप सीखेंगे कि Aspose.Page लाइब्रेरी for Java का उपयोग करके XPS को JPEG में कैसे बदलें**। XPS फ़ाइलों को इमेज फ़ॉर्मेट में बदलना एक सामान्य आवश्यकता है जब आपको वेब या डेस्कटॉप एप्लिकेशन में दस्तावेज़ पृष्ठों को प्रदर्शित, प्रीव्यू या आगे प्रोसेस करना हो। हम प्रत्येक चरण को विस्तार से बताएँगे, यह समझाएँगे कि प्रत्येक लाइन क्यों महत्वपूर्ण है, और व्यावहारिक टिप्स देंगे ताकि आप इस रूपांतरण लॉजिक को अपने प्रोजेक्ट में आत्मविश्वास के साथ इंटीग्रेट कर सकें।

## त्वरित उत्तर
- **कौन सा लाइब्रेरी रूपांतरण को संभालती है?** Aspose.Page for Java  
- **क्या मैं विशिष्ट पृष्ठ चुन सकता हूँ?** हाँ – `JpegSaveOptions` में `setPageNumbers` का उपयोग करें  
- **मैं कौन सी इमेज क्वालिटी नियंत्रित कर सकता हूँ?** स्मूदिंग मोड, रिज़ॉल्यूशन, और JPEG क्वालिटी सेटिंग्स  
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** हाँ, एक व्यावसायिक लाइसेंस आवश्यक है (एक मुफ्त ट्रायल उपलब्ध है)  
- **क्या कोड Java 8 के साथ संगत है?** बिल्कुल – API Java 8 और उसके बाद के संस्करणों के साथ काम करती है  

## XPS क्या है और इसे JPEG में क्यों बदलें?
XPS (XML Paper Specification) एक फिक्स्ड‑लेआउट दस्तावेज़ फ़ॉर्मेट है जो PDF के समान है। XPS को JPEG में बदलना उपयोगी होता है जब आपको थंबनेल, ई‑मेल अटैचमेंट या उन सिस्टमों के साथ इंटीग्रेशन के लिए रास्टर इमेज चाहिए जो केवल इमेज फ़ाइलें स्वीकार करते हैं। JPEG दृश्य गुणवत्ता और फ़ाइल आकार के बीच अच्छा संतुलन प्रदान करता है, जिससे यह वेब‑आधारित प्रीव्यू के लिए आदर्श है।

## पूर्वापेक्षाएँ
कोड में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- **Java विकास पर्यावरण** – JDK 8 या उसके बाद का स्थापित और कॉन्फ़िगर किया हुआ।  
- **Aspose.Page for Java** – आधिकारिक साइट [here](https://releases.aspose.com/page/java/) से नवीनतम लाइब्रेरी डाउनलोड करें।  
- **Sample XPS Document** – वह XPS फ़ाइल जिसे आप JPEG इमेज में बदलना चाहते हैं।  

## पैकेज आयात करें
अपने Java स्रोत फ़ाइल में आवश्यक क्लासेज़ को इम्पोर्ट करके शुरू करें:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## चरण 1: पाथ्स को इनिशियलाइज़ करें और XPS दस्तावेज़ लोड करें
उस डायरेक्टरी को सेट करें जिसमें आपका स्रोत XPS फ़ाइल है और एक `XpsDocument` इंस्टेंस बनाएं:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **Pro tip:** प्लेटफ़ॉर्म‑स्वतंत्र पाथ हैंडलिंग के लिए `java.nio.file` से `Paths.get()` का उपयोग करें।

## चरण 2: JPEG सहेजने के विकल्प कॉन्फ़िगर करें
निर्धारित करें कि JPEG इमेज कैसे रेंडर की जाएँ—रिज़ॉल्यूशन, स्मूदिंग, और कौन से पृष्ठ एक्सपोर्ट किए जाएँ:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` उच्च‑रिज़ॉल्यूशन आउटपुट उत्पन्न करता है जो प्रिंटिंग के लिए उपयुक्त है।  
- `setPageNumbers` आपको केवल आवश्यक पृष्ठ चुनने की अनुमति देता है, जिससे समय और मेमोरी बचती है।

## चरण 3: रेंडरिंग डिवाइस बनाएं
`ImageDevice` रेंडर किए गए पृष्ठों को बाइट एरे के रूप में कैप्चर करता है:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## चरण 4: XPS दस्तावेज़ को JPEG में रेंडर करें
`save` मेथड को कॉल करें, जिसमें डिवाइस और आपने कॉन्फ़िगर किए हुए विकल्प पास करें:

```java
document.save(device, options);
```

इस बिंदु पर `device` दो‑आयामी एरे रखता है जहाँ प्रत्येक तत्व एक JPEG‑एन्कोडेड पृष्ठ का प्रतिनिधित्व करता है।

## चरण 5: परिणाम के माध्यम से इटरेट करें और फ़ाइलें लिखें
रेंडर किए गए पृष्ठों पर लूप चलाएँ और प्रत्येक बाइट एरे को अलग‑अलग JPEG फ़ाइल में लिखें:

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

प्रत्येक फ़ाइल का नाम `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg` होगा, जिससे स्रोत दस्तावेज़ और पृष्ठ संख्या की पहचान आसान हो जाती है।

## सामान्य समस्याएँ और ट्रबलशूटिंग
| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| **Blank JPEG files** | आउटपुट स्ट्रीम सही से फ्लश या क्लोज नहीं हुई | सुनिश्चित करें कि `imageStream.close()` आंतरिक लूप के भीतर कॉल किया गया है (जैसा दिखाया गया है)। |
| **Out‑of‑memory errors** on large XPS files | सभी पृष्ठों को एक साथ रेंडर करने से बहुत अधिक RAM उपयोग होता है | पृष्ठों को छोटे बैच में प्रोसेस करें या JVM हीप (`-Xmx`) बढ़ाएँ। |
| **Missing pages** | `setPageNumbers` में इच्छित पृष्ठ शामिल नहीं है | पृष्ठ संख्या एरे को वास्तविक XPS पृष्ठ इंडेक्स (1‑आधारित) से मिलाएँ। |

## अक्सर पूछे जाने वाले प्रश्न

### Q: क्या Aspose.Page व्यावसायिक प्रोजेक्ट्स के लिए उपयुक्त है?
A: हाँ, Aspose.Page एक व्यावसायिक उत्पाद है जिसमें लाइसेंसिंग विकल्प उपलब्ध हैं। विवरण के लिए [here](https://purchase.aspose.com/buy) देखें।

### Q: क्या मैं खरीदने से पहले Aspose.Page आज़मा सकता हूँ?
A: हाँ, आप एक मुफ्त ट्रायल [here](https://releases.aspose.com/) प्राप्त कर सकते हैं।

### Q: मैं Aspose.Page दस्तावेज़ीकरण कहाँ पा सकता हूँ?
A: दस्तावेज़ीकरण उपलब्ध है [here](https://reference.aspose.com/page/java/)।

### Q: मैं Aspose.Page के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
A: समुदाय‑आधारित समर्थन के लिए [Aspose.Page Forum](https://forum.aspose.com/c/page/39) पर जाएँ।

### Q: क्या परीक्षण के लिए मुझे एक अस्थायी लाइसेंस चाहिए?
A: हाँ, आप एक अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) प्राप्त कर सकते हैं।

## निष्कर्ष
आपने अब **Java के लिए Aspose.Page का उपयोग करके XPS को JPEG में कैसे बदलें** में महारत हासिल कर ली है। चरण‑दर‑चरण गाइड का पालन करके आप इस रूपांतरण पाइपलाइन को किसी भी Java एप्लिकेशन—चाहे वह डेस्कटॉप टूल हो, वेब सर्विस हो, या बैच‑प्रोसेसिंग यूटिलिटी—में इंटीग्रेट कर सकते हैं। विभिन्न रिज़ॉल्यूशन, पृष्ठ चयन, और इमेज फ़ॉर्मेट के साथ प्रयोग करने में संकोच न करें ताकि आपके प्रोजेक्ट की आवश्यकताओं के अनुसार अनुकूलित किया जा सके।

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Page 24.11 for Java (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}