---
date: 2025-12-21
description: Aspose.Page का उपयोग करके जावा में XPS को BMP में बदलते समय रिज़ॉल्यूशन
  कैसे सेट करें, सीखें। यह जावा इमेज कन्वर्ज़न गाइड उच्च‑गुणवत्ता वाले परिणाम सुनिश्चित
  करता है।
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: जावा में XPS को BMP में बदलते समय रिज़ॉल्यूशन कैसे सेट करें
url: /hi/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS को BMP में Java के साथ परिवर्तित करें

## परिचय
Aspose.Page का उपयोग करके Java में XPS (XML Paper Specification) फ़ाइलों को BMP (Bitmap) फ़ॉर्मेट में परिवर्तित करते समय **रिज़ॉल्यूशन कैसे सेट करें** पर इस चरण‑दर‑चरण गाइड में आपका स्वागत है। Aspose.Page for Java एक शक्तिशाली लाइब्रेरी है जो XPS दस्तावेज़ों के साथ काम करने के लिए व्यापक सुविधाएँ प्रदान करती है। इस ट्यूटोरियल में, हम आपको XPS फ़ाइलों को BMP छवियों में आसानी से परिवर्तित करने की प्रक्रिया के माध्यम से ले जाएंगे।

## त्वरित उत्तर
- **मैं कौन सी लाइब्रेरी उपयोग करूँ?** Aspose.Page for Java सबसे पूर्ण XPS → BMP रूपांतरण सुविधाएँ प्रदान करता है।  
- **क्या मैं इमेज क्वालिटी को नियंत्रित कर सकता हूँ?** हाँ – रिज़ॉल्यूशन और स्मूदिंग मोड सेट करने के लिए `BmpSaveOptions` का उपयोग करें।  
- **क्या मुझे केवल विशिष्ट पृष्ठों को ही परिवर्तित करना है?** बिल्कुल, `options.setPageNumbers()` आपको सटीक पृष्ठ चुनने की अनुमति देता है।  
- **क्या यह वास्तविक Java इमेज रूपांतरण है?** API XPS पृष्ठों को सीधे बिटमैप डेटा में रेंडर करता है, इसलिए कोई मध्यवर्ती फ़ॉर्मेट आवश्यक नहीं है।  
- **कौन सा Java संस्करण समर्थित है?** सभी आधुनिक Java संस्करण (8 और उससे ऊपर) संगत हैं।

## रिज़ॉल्यूशन सेट करने का उद्देश्य क्या है?
रिज़ॉल्यूशन उत्पन्न BMP छवि में प्रति इंच डॉट्स (DPI) की संख्या निर्धारित करता है। उच्च DPI अधिक स्पष्ट छवियां प्रदान करता है, जो प्रिंटिंग या विस्तृत ग्राफिक कार्य के लिए आवश्यक है। रिज़ॉल्यूशन को समायोजित करने से आपको अपने **java convert xps** कार्यप्रवाह की आउटपुट क्वालिटी पर पूर्ण नियंत्रण मिलता है।

## XPS → BMP रूपांतरण के लिए Aspose.Page का उपयोग क्यों करें?
- **उच्च सटीकता** – मूल XPS की वेक्टर गुणवत्ता को बनाए रखता है।  
- **सूक्ष्म नियंत्रण** – आप DPI, स्मूदिंग सेट कर सकते हैं, और यहाँ तक कि परिवर्तित करने के लिए विशिष्ट पृष्ठ भी चुन सकते हैं।  
- **कोई बाहरी निर्भरताएँ नहीं** – शुद्ध Java, कोई नेटिव लाइब्रेरी आवश्यक नहीं।  
- **स्केलेबल** – एकल‑पृष्ठ दस्तावेज़ों के साथ-साथ बड़े बहु‑पृष्ठ XPS फ़ाइलों के लिए भी काम करता है।

## पूर्वापेक्षाएँ
रूपांतरण प्रक्रिया में डुबकी लगाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

- **Java विकास वातावरण** – आपके मशीन पर Java 8 या उससे नया स्थापित हो।  
- **Aspose.Page for Java लाइब्रेरी** – Aspose.Page for Java लाइब्रेरी को डाउनलोड करके अपने प्रोजेक्ट में शामिल करें। आप लाइब्रेरी [यहाँ](https://releases.aspose.com/page/java/) पा सकते हैं।  
- **नमूना XPS फ़ाइल** – एक नमूना XPS दस्तावेज़ तैयार करें जिसे आप BMP में परिवर्तित करना चाहते हैं।

## पैकेज आयात करें
अपने Java कोड में आवश्यक Aspose.Page पैकेज शामिल करें:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## XPS को BMP रूपांतरण के लिए रिज़ॉल्यूशन कैसे सेट करें
नीचे एक संक्षिप्त, क्रमांकित चरण-दर-चरण मार्गदर्शिका है जो दिखाती है कि रिज़ॉल्यूशन कहाँ और कैसे सेट करें, साथ ही **विशिष्ट पृष्ठों को परिवर्तित करने** का तरीका।

### चरण 1: XPS दस्तावेज़ लोड करें
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### चरण 2: विकल्प प्रारंभ करें (रिज़ॉल्यूशन और पृष्ठ चयन)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### चरण 3: रेंडरिंग डिवाइस बनाएं
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### चरण 4: विकल्पों का उपयोग करके दस्तावेज़ सहेजें
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### चरण 5: रेंडर की गई छवियों के माध्यम से इटररेट करें और फ़ाइलें लिखें
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

रूपांतरण प्रक्रिया में किसी भी अतिरिक्त अनुकूलन या संशोधन के लिए इन चरणों को दोहराएँ।

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **कम‑गुणवत्ता वाला BMP आउटपुट** | `options.setResolution()` को मान ≥ 300 DPI पर सेट किया गया है, यह सुनिश्चित करें। |
| **केवल दस्तावेज़ का हिस्सा ही परिवर्तित हो रहा है** | सुनिश्चित करें कि `options.setPageNumbers()` सभी इच्छित पृष्ठ सूचकांक शामिल करता है। |
| **बड़े XPS फ़ाइलों पर OutOfMemoryError** | दस्तावेज़ को छोटे भागों में प्रोसेस करें या JVM हीप आकार (`-Xmx`) बढ़ाएँ। |
| **फ़ाइल नहीं मिली** | `dataDir` पथ और इनपुट XPS फ़ाइल के अस्तित्व को दोबारा जांचें। |

## अक्सर पूछे जाने वाले प्रश्न
### प्र: क्या मैं BMP छवियों का रिज़ॉल्यूशन कस्टमाइज़ कर सकता हूँ?
उ: हाँ, आप कोड में `options.setResolution()` पैरामीटर को बदलकर रिज़ॉल्यूशन समायोजित कर सकते हैं।

### प्र: क्या Aspose.Page विभिन्न Java संस्करणों के साथ संगत है?
उ: हाँ, Aspose.Page विभिन्न Java संस्करणों का समर्थन करता है। सुनिश्चित करें कि आपके पास संगत संस्करण स्थापित है।

### प्र: मैं XPS फ़ाइलों को विशिष्ट पृष्ठ रेंज से कैसे परिवर्तित कर सकता हूँ?
उ: आप `options.setPageNumbers()` मेथड का उपयोग करके उन पृष्ठ संख्याओं को निर्दिष्ट कर सकते हैं जिन्हें आप परिवर्तित करना चाहते हैं।

### प्र: क्या Aspose.Page द्वारा समर्थित अन्य आउटपुट फ़ॉर्मेट हैं?
उ: हाँ, Aspose.Page विभिन्न आउटपुट फ़ॉर्मेट का समर्थन करता है। विस्तृत सूची के लिए दस्तावेज़ देखें।

### प्र: अतिरिक्त सहायता या समर्थन कहाँ प्राप्त कर सकता हूँ?
उ: समुदाय समर्थन और चर्चाओं के लिए [Aspose.Page Forum](https://forum.aspose.com/c/page/39) पर जाएँ।

---

**अंतिम अपडेट:** 2025-12-21  
**परीक्षण किया गया:** Aspose.Page for Java 24.12  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}