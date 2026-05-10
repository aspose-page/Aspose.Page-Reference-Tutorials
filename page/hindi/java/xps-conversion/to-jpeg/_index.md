---
date: 2026-03-13
description: Aspose.Page Java के साथ Java में XPS को JPEG में कैसे बदलें, सीखें। यह
  चरण‑दर‑चरण गाइड आपको Aspose.Page Java लाइब्रेरी का उपयोग करके XPS को JPEG में कुशलतापूर्वक
  बदलने का तरीका दिखाता है।
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: Aspose.Page Java का उपयोग करके Java में XPS को JPEG में कैसे परिवर्तित करें
url: /hi/java/xps-conversion/to-jpeg/
weight: 11
---

top-button >}}

Make sure to keep them unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में Aspose.Page Java का उपयोग करके XPS को JPEG में कैसे बदलें

## Aspose.Page Java का परिचय
इस ट्यूटोरियल में आप **Aspose.Page Java** लाइब्रेरी का उपयोग करके XPS को JPEG में कैसे बदलना है, सीखेंगे। XPS फ़ाइलों को JPEG छवियों में बदलना अक्सर आवश्यक होता है जब आपको दस्तावेज़ पृष्ठों को वेब पोर्टलों, डेस्कटॉप व्यूअर्स, या ईमेल अटैचमेंट्स में रास्टर ग्राफ़िक्स के रूप में प्रदर्शित करना हो। हम कोड की हर पंक्ति को समझेंगे, प्रत्येक सेटिंग क्यों महत्वपूर्ण है यह बताएँगे, और व्यावहारिक टिप्स साझा करेंगे ताकि आप इस रूपांतरण पाइपलाइन को अपने Java एप्लिकेशन में आत्मविश्वास के साथ एम्बेड कर सकें।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी रूपांतरण संभालती है?** Aspose.Page Java  
- **क्या मैं विशिष्ट पृष्ठ चुन सकता हूँ?** हाँ – `JpegSaveOptions` में `setPageNumbers` का उपयोग करें  
- **मैं कौन सी इमेज क्वालिटी नियंत्रित कर सकता हूँ?** स्मूदिंग मोड, रिज़ॉल्यूशन, और JPEG क्वालिटी सेटिंग्स  
- **उत्पादन के लिए लाइसेंस चाहिए?** हाँ, एक व्यावसायिक लाइसेंस आवश्यक है (एक मुफ्त ट्रायल उपलब्ध है)  
- **क्या कोड Java 8 के साथ संगत है?** बिल्कुल – API Java 8 और उसके बाद के संस्करणों के साथ काम करती है  

## XPS क्या है और XPS को JPEG में क्यों बदलें?
XPS (XML Paper Specification) एक स्थिर‑लेआउट दस्तावेज़ फ़ॉर्मेट है जो PDF के समान है। XPS को JPEG में बदलना उपयोगी होता है जब आपको थंबनेल, ईमेल अटैचमेंट्स, या उन सिस्टमों के साथ एकीकरण के लिए रास्टर छवियों की आवश्यकता होती है जो केवल इमेज फ़ाइलें स्वीकार करते हैं। JPEG दृश्य गुणवत्ता और फ़ाइल आकार के बीच अच्छा संतुलन प्रदान करता है, जिससे यह वेब‑आधारित प्रीव्यू के लिए आदर्श बनता है।

## पूर्वापेक्षाएँ
कोड में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- **Java विकास वातावरण** – JDK 8 या बाद का स्थापित और कॉन्फ़िगर किया हुआ।  
- **Aspose.Page for Java** – आधिकारिक साइट से नवीनतम लाइब्रेरी डाउनलोड करें [here](https://releases.aspose.com/page/java/).  
- **नमूना XPS दस्तावेज़** – एक XPS फ़ाइल जिसे आप JPEG छवियों में बदलना चाहते हैं।  

## पैकेज आयात करें
अपने Java स्रोत फ़ाइल में आवश्यक क्लासेस को आयात करके शुरू करें:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## चरण 1: पाथ्स को इनिशियलाइज़ करें और XPS दस्तावेज़ लोड करें
उस डायरेक्टरी को सेट करें जिसमें आपका स्रोत XPS फ़ाइल हो और एक `XpsDocument` इंस्टेंस बनाएं:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **प्रो टिप:** प्लेटफ़ॉर्म‑स्वतंत्र पाथ हैंडलिंग के लिए `java.nio.file` से `Paths.get()` का उपयोग करें।

## चरण 2: JPEG सेव विकल्प कॉन्फ़िगर करें
परिभाषित करें कि JPEG छवियों को कैसे रेंडर किया जाना चाहिए—रिज़ॉल्यूशन, स्मूदिंग, और कौन से पृष्ठ निर्यात किए जाएँ:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` प्रिंटिंग के लिए उपयुक्त हाई‑रिज़ॉल्यूशन आउटपुट उत्पन्न करता है।  
- `setPageNumbers` आपको केवल आवश्यक पृष्ठ चुनने देता है, जिससे समय और मेमोरी बचती है।

## चरण 3: रेंडरिंग डिवाइस बनाएं
`ImageDevice` रेंडर किए गए पृष्ठों को बाइट एरे के रूप में कैप्चर करता है:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## चरण 4: XPS दस्तावेज़ को JPEG में रेंडर करें
`save` मेथड को कॉल करें, डिवाइस और आपने जो विकल्प कॉन्फ़िगर किए हैं उन्हें पास करें:

```java
document.save(device, options);
```

इस चरण पर `device` में एक दो‑आयामी एरे होता है जहाँ प्रत्येक तत्व एक JPEG‑एन्कोडेड पृष्ठ को दर्शाता है।

## चरण 5: परिणाम के माध्यम से इटरेट करें और फ़ाइलें लिखें
रेंडर किए गए पृष्ठों पर लूप चलाएँ और प्रत्येक बाइट एरे को अलग JPEG फ़ाइल में लिखें:

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

प्रत्येक फ़ाइल का नाम `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg` होगा, जिससे स्रोत दस्तावेज़ और पृष्ठ संख्या की पहचान आसान हो जाएगी।

## सामान्य उपयोग केस
- **डॉक्यूमेंट मैनेजमेंट सिस्टम** के लिए थंबनेल बनाना।  
- उन वेब एप्लिकेशनों में पृष्ठ प्रीव्यू एम्बेड करना जहाँ केवल इमेज फ़ॉर्मेट समर्थित हैं।  
- बड़े XPS आर्काइव्स को JPEG में बैच‑प्रोसेस करना ताकि आर्काइविंग या रिपोर्टिंग उद्देश्यों के लिए उपयोग किया जा सके।  

## सामान्य समस्याएँ और ट्रबलशूटिंग
| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| **खाली JPEG फ़ाइलें** | आउटपुट स्ट्रीम सही ढंग से फ्लश या बंद नहीं किया गया है | सुनिश्चित करें कि `imageStream.close()` को अंदरूनी लूप के भीतर कॉल किया गया है (जैसा दिखाया गया है)। |
| **Out‑of‑memory errors** बड़े XPS फ़ाइलों पर | सभी पृष्ठों को एक साथ रेंडर करने से बहुत अधिक RAM उपयोग होता है | पृष्ठों को छोटे बैच में प्रोसेस करें या JVM हीप (`-Xmx`) बढ़ाएँ। |
| **गुम पृष्ठ** | `setPageNumbers` इच्छित पृष्ठ को शामिल नहीं करता है | पृष्ठ संख्या एरे को वास्तविक XPS पृष्ठ इंडेक्स (1‑आधारित) से मिलान करें। |

## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न: क्या Aspose.Page व्यावसायिक प्रोजेक्ट्स के लिए उपयुक्त है?
A: हाँ, Aspose.Page एक व्यावसायिक उत्पाद है जिसमें लाइसेंस विकल्प उपलब्ध हैं। विवरण के लिए [here](https://purchase.aspose.com/buy) देखें।

### प्रश्न: क्या मैं खरीदने से पहले Aspose.Page आज़मा सकता हूँ?
A: हाँ, आप एक मुफ्त ट्रायल [here](https://releases.aspose.com/) प्राप्त कर सकते हैं।

### प्रश्न: मैं Aspose.Page दस्तावेज़ीकरण कहाँ पा सकता हूँ?
A: दस्तावेज़ीकरण उपलब्ध है [here](https://reference.aspose.com/page/java/)।

### प्रश्न: मैं Aspose.Page के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
A: समुदाय‑आधारित समर्थन के लिए [Aspose.Page Forum](https://forum.aspose.com/c/page/39) पर जाएँ।

### प्रश्न: परीक्षण के लिए क्या मुझे अस्थायी लाइसेंस चाहिए?
A: हाँ, आप एक अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) प्राप्त कर सकते हैं।

## निष्कर्ष
अब आप **Aspose.Page Java** का उपयोग करके **XPS को JPEG में कैसे बदलें** में निपुण हो गए हैं। चरण‑दर‑चरण गाइड का पालन करके, आप इस रूपांतरण पाइपलाइन को किसी भी Java एप्लिकेशन में एकीकृत कर सकते हैं—चाहे वह डेस्कटॉप टूल हो, वेब सेवा, या बैच‑प्रोसेसिंग यूटिलिटी। विभिन्न रिज़ॉल्यूशन, पृष्ठ चयन, और इमेज फ़ॉर्मेट के साथ प्रयोग करने में संकोच न करें ताकि आपके प्रोजेक्ट की आवश्यकताओं को पूरा किया जा सके।

---

**अंतिम अपडेट:** 2026-03-13  
**परीक्षित संस्करण:** Aspose.Page 24.11 for Java (latest at time of writing)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}