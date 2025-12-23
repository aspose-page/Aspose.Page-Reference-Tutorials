---
date: 2025-12-23
description: Aspose.Page Java के साथ XPS को TIFF में आसानी से बदलें। सहज एकीकरण के
  लिए हमारे चरण‑दर‑चरण गाइड का पालन करें। अभी डाउनलोड करें!
linktitle: Convert XSP to TIFF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Aspose.Page Java का उपयोग करके Java में XSP को TIFF में परिवर्तित करें
url: /hi/java/xps-conversion/to-tiff/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java का उपयोग करके Java में XSP को TIFF में बदलें

आज के तेज़ गति वाले सॉफ़्टवेयर परिदृश्य में, **aspose page java** Java दस्तावेज़ रूपांतरण को सरल और विश्वसनीय बनाता है। चाहे आपको अभिलेखीय, प्रिंटिंग या बैच प्रोसेसिंग के लिए **convert XPS to TIFF** करने की आवश्यकता हो, यह ट्यूटोरियल आपको सटीक चरणों के माध्यम से ले जाता है, प्रत्येक क्रिया के पीछे “क्यों” को समझाता है, और तुरंत लागू करने योग्य व्यावहारिक टिप्स प्रदान करता है।

## त्वरित उत्तर
- **XPS‑to‑TIFF रूपांतरण को कौनसी लाइब्रेरी संभालती है?** Aspose.Page Java.  
- **उत्पादन के लिए मुझे लाइसेंस चाहिए?** हाँ, एक वैध Aspose.Page Java लाइसेंस आवश्यक है।  
- **कौनसा Java संस्करण समर्थित है?** JDK 8 या उससे ऊपर।  
- **क्या मैं एक साथ कई XPS फ़ाइलें बदल सकता हूँ?** हाँ – आप उसी कोड के आसपास एक बैच XPS रूपांतरण लूप बना सकते हैं।  
- **प्रिंट‑तैयार TIFFs के लिए कौनसा रिज़ॉल्यूशन सबसे अच्छा है?** 300 DPI एक सामान्य विकल्प है, लेकिन आप इसे TiffSaveOptions के माध्यम से समायोजित कर सकते हैं।

## Aspose.Page Java क्या है?
Aspose.Page Java एक शक्तिशाली API है जो **java document conversion** को XPS (XML Paper Specification) से विभिन्न रास्टर और वेक्टर फ़ॉर्मैट्स, जिसमें TIFF शामिल है, में सक्षम बनाता है। यह जटिल पेज लेआउट, फ़ॉन्ट और ग्राफ़िक्स को Microsoft XPS Document Writer की आवश्यकता के बिना संभालता है।

## XPS से TIFF रूपांतरण के लिए Aspose.Page Java का उपयोग क्यों करें?
- **उच्च सटीकता:** वेक्टर डेटा और टेक्स्ट रेंडरिंग को संरक्षित करता है।  
- **प्रदर्शन:** बड़े फ़ाइलों और बैच XPS रूपांतरण परिदृश्यों के लिए अनुकूलित।  
- **लचीलापन:** `tiff save options` जैसे रिज़ॉल्यूशन, संपीड़न, और पेज चयन के साथ आउटपुट को सूक्ष्म‑समायोजित करें।  
- **क्रॉस‑प्लेटफ़ॉर्म:** किसी भी OS पर काम करता है जो Java का समर्थन करता है, जिससे यह सर्वर‑साइड प्रोसेसिंग के लिए आदर्श बनता है।

## पूर्वापेक्षाएँ
Before diving into the conversion process, ensure you have:

- अपने मशीन पर Java Development Kit (JDK) स्थापित हो।  
- Aspose.Page for Java लाइब्रेरी। आप इसे [here](https://releases.aspose.com/page/java/) से डाउनलोड कर सकते हैं।  
- Aspose.Page for Java के लिए एक वैध लाइसेंस। आप एक अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं, या पूर्ण लाइसेंस [here](https://purchase.aspose.com/buy) खरीद सकते हैं।

## पैकेज आयात करें
अपने Java प्रोजेक्ट में आवश्यक पैकेज आयात करके शुरू करें। सुनिश्चित करें कि Aspose.Page for Java JAR आपके बिल्ड पाथ में जोड़ा गया है।

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## चरण 1: दस्तावेज़ डायरेक्टरी सेट करें
उस फ़ोल्डर का पथ निर्धारित करें जिसमें आपका स्रोत XPS फ़ाइल स्थित है।

```java
String dataDir = "Your Document Directory";
```

## चरण 2: XPS दस्तावेज़ लोड करें
`XpsDocument` का एक इंस्टेंस बनाएं जो इनपुट फ़ाइल की ओर संकेत करता हो।

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

## चरण 3: TiffSaveOptions को प्रारंभ करें
**tiff save options** को कॉन्फ़िगर करें जो इमेज क्वालिटी, रिज़ॉल्यूशन, और निर्यात करने वाले पेजों को नियंत्रित करता है।

```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

## चरण 4: रेंडरिंग डिवाइस बनाएं
`ImageDevice` का एक इंस्टेंस बनाएं जो पेजों को TIFF इमेज में रेंडर करेगा।

```java
ImageDevice device = new ImageDevice();
```

## चरण 5: दस्तावेज़ को TIFF में सहेजें
डिवाइस और पहले परिभाषित विकल्पों का उपयोग करके XPS दस्तावेज़ को रेंडर करें।

```java
document.save(device, options);
```

## चरण 6: इटररेट करें और TIFF इमेज सहेजें
रेंडर किए गए इमेज बफ़र्स के माध्यम से लूप करें और प्रत्येक पेज को एक अलग TIFF फ़ाइल में लिखें।

```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

बधाई हो! आपने Java में **aspose page java** का उपयोग करके सफलतापूर्वक **convert XPS to TIFF** कर लिया है। लाइब्रेरी की अधिक सुविधाओं और कार्यात्मकताओं का अन्वेषण करने के लिए [documentation](https://reference.aspose.com/page/java/) देखें।

## निष्कर्ष
इस ट्यूटोरियल में हमने XPS से TIFF तक **java document conversion** करने के लिए आवश्यक सभी जानकारी को कवर किया, पर्यावरण सेटअप से लेकर `tiff save options` को सूक्ष्म‑समायोजित करने तक। Aspose.Page Java के साथ आप **batch XPS conversion** पाइपलाइन भी बना सकते हैं जो दर्जनों या सैकड़ों फ़ाइलों को स्वचालित रूप से प्रोसेस करती हैं।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Page for Java को बिना लाइसेंस के उपयोग कर सकता हूँ?
हालांकि आप मूल्यांकन के लिए अस्थायी लाइसेंस प्राप्त कर सकते हैं, उत्पादन उपयोग के लिए वैध लाइसेंस आवश्यक है। अपना लाइसेंस [here](https://purchase.aspose.com/buy) से प्राप्त करें।

### क्या XPS फ़ाइलों के आकार पर कोई सीमाएँ हैं?
Aspose.Page for Java विभिन्न आकारों के दस्तावेज़ों को संभालता है, लेकिन यह सलाह दी जाती है कि आप अपने विशिष्ट वातावरण में बड़े फ़ाइलों के साथ परीक्षण करें।

### मैं Aspose.Page for Java के बारे में समर्थन कैसे प्राप्त कर सकता हूँ या प्रश्न पूछ सकता हूँ?
समुदाय समर्थन और चर्चा के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) पर जाएँ।

### क्या Aspose.Page for Java के लिए मुफ्त ट्रायल उपलब्ध है?
हाँ, आप लाइब्रेरी को मुफ्त ट्रायल के साथ एक्सप्लोर कर सकते हैं। इसे [here](https://releases.aspose.com/) से डाउनलोड करें।

### इस रूपांतरण में TIFF इमेज के लिए अनुशंसित रिज़ॉल्यूशन क्या है?
उदाहरण में 300 DPI का रिज़ॉल्यूशन उपयोग किया गया है, लेकिन आप इसे अपनी विशिष्ट आवश्यकताओं के आधार पर समायोजित कर सकते हैं।

---

**अंतिम अपडेट:** 2025-12-23  
**परीक्षण किया गया:** Aspose.Page Java 24.11 (लेखन के समय नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}