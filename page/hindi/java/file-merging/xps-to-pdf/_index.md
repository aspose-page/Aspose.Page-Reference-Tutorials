---
date: 2025-11-29
description: Aspose.Page Java के साथ जावा में XPS को PDF के रूप में कैसे सहेजें, सीखें।
  कुशल XPS‑से‑PDF रूपांतरण और PDF संपीड़न सेटिंग्स के लिए हमारी चरण‑दर‑चरण गाइड का
  पालन करें।
linktitle: Convert XPS to PDF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Aspose.Page Java का उपयोग करके Java में XPS को PDF में बदलें
url: /hi/java/file-merging/xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में Aspose.Page Java का उपयोग करके XPS को PDF में बदलें

## परिचय
इस ट्यूटोरियल में, आप **जावा में Aspose.Page Java का उपयोग करके XPS को PDF में कैसे बदलें** सीखेंगे, जो जावा दस्तावेज़ रूपांतरण के लिए एक मजबूत लाइब्रेरी है। चाहे आपको इनवॉइस को बैच‑प्रोसेस करना हो, प्रिंटेबल रिपोर्ट बनानी हों, या केवल लेगेसी XPS फ़ाइलों को माइग्रेट करना हो, Aspose.Page Java काम को तेज़, भरोसेमंद और पूरी तरह कॉन्फ़िगर करने योग्य बनाता है।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी XPS से PDF रूपांतरण संभालती है?** Aspose.Page Java  
- **एक बुनियादी रूपांतरण में कितना समय लगता है?** आमतौर पर एक‑पृष्ठ XPS फ़ाइल के लिए एक सेकंड से कम।  
- **क्या विकास के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है।  
- **क्या मैं PDF संपीड़न को नियंत्रित कर सकता हूँ?** हाँ – `PdfSaveOptions` का उपयोग करके इमेज और टेक्स्ट संपीड़न सेट करें।  
- **कौन सा जावा संस्करण आवश्यक है?** जावा 8 या बाद का (JDK 11+ की सिफ़ारिश की जाती है)।

## Aspose.Page Java क्या है?
Aspose.Page Java एक **उच्च‑प्रदर्शन API** है जो डेवलपर्स को प्रोग्रामेटिक रूप से XPS दस्तावेज़ बनाने, संपादित करने और रूपांतरित करने की सुविधा देती है। यह XPS को PDF, PNG, JPEG और अन्य फ़ॉर्मेट में रेंडर करने का समर्थन करता है, साथ ही **PDF संपीड़न सेट करने** जैसी आउटपुट सेटिंग्स पर सूक्ष्म नियंत्रण प्रदान करता है।

## XPS‑to‑PDF रूपांतरण के लिए Aspose.Page Java क्यों उपयोग करें?
- **शून्य‑निर्भरता रेंडरिंग** – कोई नेटिव लाइब्रेरी या बाहरी टूल नहीं।  
- **सटीक लेआउट संरक्षण** – PDF आउटपुट मूल XPS की उपस्थिति को प्रतिबिंबित करता है।  
- **PDF आउटपुट पर पूर्ण नियंत्रण** – आप इमेज क्वालिटी समायोजित कर सकते हैं, संपीड़न एल्गोरिदम चुन सकते हैं, और विशिष्ट पृष्ठों को रेंडर करने का चयन कर सकते हैं।  
- **क्रॉस‑प्लेटफ़ॉर्म** – विंडोज, लिनक्स और macOS पर किसी भी मानक JDK के साथ काम करता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:

1. **जावा डेवलपमेंट किट (JDK) 8+** – बेहतर प्रदर्शन और सुरक्षा के लिए नवीनतम JDK की सिफ़ारिश की जाती है।  
2. **Aspose.Page for Java लाइब्रेरी** – आधिकारिक [Aspose.Page Java दस्तावेज़ीकरण](https://reference.aspose.com/page/java/) से JAR डाउनलोड करें।  
3. एक **IDE** (IntelliJ IDEA, Eclipse, VS Code) या साधारण टेक्स्ट एडिटर प्लस कमांड‑लाइन बिल्ड टूल्स (Maven/Gradle)।

## पैकेज आयात करें
अपनी जावा क्लास में आवश्यक इम्पोर्ट जोड़ें ताकि आप XPS दस्तावेज़ और PDF आउटपुट के साथ काम कर सकें।

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.rendering.pdf.PdfDevice;
import com.aspose.xps.rendering.pdf.PdfSaveOptions;
import com.aspose.xps.rendering.pdf.PdfImageCompression;
import com.aspose.xps.rendering.pdf.PdfTextCompression;
import java.io.FileOutputStream;
```

## चरण‑दर‑चरण गाइड

### चरण 1: दस्तावेज़ निर्देशिका पथ सेट करें
उस फ़ोल्डर को परिभाषित करें जिसमें आपका स्रोत XPS फ़ाइल है और जहाँ PDF सहेजा जाएगा।

```java
String dataDir = "C:/MyDocuments/XpsFiles/";   // <-- replace with your actual path
```

### चरण 2: PDF आउटपुट स्ट्रीम प्रारंभ करें
एक `FileOutputStream` बनाएँ जो गंतव्य PDF फ़ाइल की ओर इशारा करता हो।

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

> **प्रो टिप:** `try‑with‑resources` का उपयोग करके स्ट्रीम को स्वचालित रूप से बंद करें और संसाधन लीक से बचें।

### चरण 3: XPS दस्तावेज़ लोड करें
स्रोत XPS फ़ाइल को लोड करके एक `XpsDocument` ऑब्जेक्ट बनाएं।

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### चरण 4: PDF सहेजने के विकल्प प्रारंभ करें (PDF संपीड़न सेट करें)
निर्धारित करें कि PDF कैसे संपीड़ित किया जाना चाहिए। यह चरण आपको इमेज और टेक्स्ट के लिए **PDF संपीड़न सेट** करने की अनुमति देता है, जिससे फ़ाइल आकार गुणवत्ता से समझौता किए बिना घटता है।

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);                         // maximum JPEG quality
options.setImageCompression(PdfImageCompression.Jpeg);   // compress images as JPEG
options.setTextCompression(PdfTextCompression.Flate);    // compress text streams
options.setPageNumbers(new int[] { 1, 2, 6 });            // optional: export only selected pages
```

> **यह क्यों महत्वपूर्ण है:** JPEG क्वालिटी और संपीड़न प्रकार को समायोजित करने से 10 MB PDF को 2 MB से कम में घटाया जा सकता है, जबकि दृश्य गुणवत्ता बनी रहती है।

### चरण 5: PDF फ़ॉर्मेट के लिए रेंडरिंग डिवाइस बनाएं
`PdfDevice` रेंडर किए गए पृष्ठों को PDF आउटपुट स्ट्रीम में स्ट्रीम करता है।

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### चरण 6: दस्तावेज़ सहेजें
कॉन्फ़िगर किए गए विकल्पों का उपयोग करके XPS सामग्री को PDF में रेंडर करें।

```java
document.save(device, options);
```

> **परिणाम:** निष्पादन के बाद, `XPStoPDF.pdf` `dataDir` फ़ोल्डर में दिखाई देगा, जिसमें आपके द्वारा निर्दिष्ट संपीड़न सेटिंग्स के साथ रूपांतरित पृष्ठ होंगे।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|----------|
| **`FileNotFoundException`** | गलत `dataDir` पथ | सुनिश्चित करें कि निर्देशिका मौजूद है और एप्लिकेशन के पास पढ़ने/लिखने की अनुमति है। |
| **खाली PDF पृष्ठ** | `PdfDevice` प्रारंभ नहीं किया गया | सुनिश्चित करें कि `PdfDevice` उसी `FileOutputStream` के साथ बनाया गया है जिसका उपयोग आउटपुट के लिए किया गया है। |
| **बड़ी PDF आकार** | डिफ़ॉल्ट संपीड़न कम है | `setJpegQualityLevel` बढ़ाएँ या `PdfImageCompression.Jpeg` को कम क्वालिटी स्तर के साथ उपयोग करें। |
| **केवल कुछ पृष्ठ दिखाई देते हैं** | `setPageNumbers` फ़िल्टर पृष्ठों को बाहर रखता है | सभी आवश्यक पृष्ठ संख्याएँ शामिल करने के लिए एरे को समायोजित करें या सभी पृष्ठों को निर्यात करने के लिए कॉल हटाएँ। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या Aspose.Page Java विभिन्न जावा संस्करणों के साथ संगत है?**  
उत्तर: हाँ, Aspose.Page Java जावा 8 से लेकर जावा 21 तक का समर्थन करता है, जिसमें Oracle और OpenJDK दोनों वितरण शामिल हैं।

**प्रश्न: क्या मैं रूपांतरित PDF के लिए संपीड़न सेटिंग्स को अनुकूलित कर सकता हूँ?**  
उत्तर: बिल्कुल। चरण 4 में दिखाए अनुसार `PdfSaveOptions` का उपयोग करके JPEG क्वालिटी, इमेज संपीड़न प्रकार और टेक्स्ट संपीड़न सेट कर सकते हैं।

**प्रश्न: अतिरिक्त समर्थन या समुदाय चर्चा कहाँ मिल सकती है?**  
उत्तर: समुदाय सहायता, कोड नमूने और समस्या निवारण टिप्स के लिए [Aspose.Page फ़ोरम](https://forum.aspose.com/c/page/39) देखें।

**प्रश्न: क्या Aspose.Page के लिए कोई मुफ्त ट्रायल उपलब्ध है?**  
उत्तर: हाँ, आप [Aspose डाउनलोड पेज](https://releases.aspose.com/) से पूरी कार्यात्मक ट्रायल डाउनलोड कर सकते हैं।

**प्रश्न: Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
उत्तर: एक अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) अनुरोध किया जा सकता है।

## निष्कर्ष
**Aspose.Page Java** का उपयोग करके आप आसानी से **XPS को PDF के रूप में सहेज** सकते हैं और आउटपुट के हर पहलू को नियंत्रित कर सकते हैं, पृष्ठ चयन से लेकर संपीड़न तक। इस ट्यूटोरियल में वह सब कुछ कवर किया गया है जिसकी आपको अपनी जावा एप्लिकेशन में XPS‑to‑PDF रूपांतरण को एक‑बार उपयोगिता या बड़े‑पैमाने पर दस्तावेज़ प्रोसेसिंग पाइपलाइन में एकीकृत करने के लिए आवश्यकता है।

---

**अंतिम अपडेट:** 2025-11-29  
**परीक्षित संस्करण:** Aspose.Page for Java 24.10  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}