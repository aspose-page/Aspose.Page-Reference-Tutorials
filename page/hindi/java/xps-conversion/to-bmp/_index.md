---
title: जावा में XPS को BMP में कनवर्ट करें
linktitle: जावा में XPS को BMP में कनवर्ट करें
second_title: Aspose.Page जावा एपीआई
description: Aspose.Page के साथ जानें कि जावा में XPS को BMP में कैसे बदलें। कुशल और उच्च गुणवत्ता वाले दस्तावेज़ रूपांतरण के लिए हमारी आसान मार्गदर्शिका का पालन करें।
weight: 10
url: /hi/java/xps-conversion/to-bmp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में XPS को BMP में कनवर्ट करें

## परिचय
Aspose.Page का उपयोग करके जावा में XPS (XML पेपर विशिष्टता) फ़ाइलों को BMP (बिटमैप) प्रारूप में परिवर्तित करने पर इस चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। जावा के लिए Aspose.Page एक शक्तिशाली लाइब्रेरी है जो XPS दस्तावेज़ों के साथ काम करने के लिए व्यापक सुविधाएँ प्रदान करती है। इस ट्यूटोरियल में, हम आपको XPS फ़ाइलों को BMP छवियों में आसानी से परिवर्तित करने की प्रक्रिया के बारे में बताएंगे।
## आवश्यक शर्तें
रूपांतरण प्रक्रिया में उतरने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- जावा विकास पर्यावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Page: जावा लाइब्रेरी के लिए Aspose.Page को डाउनलोड करें और अपने प्रोजेक्ट में शामिल करें। आप पुस्तकालय पा सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
- नमूना XPS फ़ाइल: एक नमूना XPS दस्तावेज़ तैयार करें जिसे आप BMP में कनवर्ट करना चाहते हैं।
## पैकेज आयात करें
अपने जावा कोड में आवश्यक Aspose.Page पैकेज शामिल करें:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
आइए रूपांतरण प्रक्रिया को पालन करने में आसान चरणों में विभाजित करें:
## चरण 1: एक्सपीएस दस्तावेज़ लोड करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक्सपीएस दस्तावेज़ लोड करें
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## चरण 2: विकल्पों को आरंभ करें
```java
// आवश्यक मापदंडों के साथ विकल्प ऑब्जेक्ट को आरंभ करें।
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[]{1, 2, 6});
```
## चरण 3: रेंडरिंग डिवाइस बनाएं
```java
// बीएमपी प्रारूप के लिए रेंडरिंग डिवाइस बनाएं
ImageDevice device = new ImageDevice();
```
## चरण 4: दस्तावेज़ सहेजें
```java
// विकल्पों और डिवाइस का उपयोग करके XPS दस्तावेज़ को BMP में सहेजें
document.save(device, options);
```
## चरण 5: छवियों को पुनरावृत्त करें और सहेजें
```java
// दस्तावेज़ विभाजन के माध्यम से पुनरावृति करें
for (int i = 0; i < device.getResult().length; i++) {
    // विभाजन पृष्ठों के माध्यम से पुनरावृति करें
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // छवि आउटपुट स्ट्रीम प्रारंभ करें
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // छवि लिखें
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```
रूपांतरण प्रक्रिया में आपको किसी भी अतिरिक्त अनुकूलन या संशोधन की आवश्यकता हो सकती है, इसके लिए इन चरणों को दोहराएं।
## निष्कर्ष
बधाई हो! आपने Aspose.Page का उपयोग करके जावा में XPS फ़ाइलों को BMP में परिवर्तित करना सफलतापूर्वक सीख लिया है। Aspose.Page द्वारा प्रदान किया गया लचीलापन और उपयोग में आसानी इसे दस्तावेज़ रूपांतरण कार्यों को संभालने के लिए एक मूल्यवान उपकरण बनाती है।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या मैं बीएमपी छवियों के रिज़ॉल्यूशन को अनुकूलित कर सकता हूं?
 उत्तर: हां, आप रिज़ॉल्यूशन को संशोधित करके समायोजित कर सकते हैं`options.setResolution()`कोड में पैरामीटर.
### प्रश्न: क्या Aspose.Page विभिन्न जावा संस्करणों के साथ संगत है?
उत्तर: हां, Aspose.Page जावा संस्करणों की एक विस्तृत श्रृंखला का समर्थन करता है। सुनिश्चित करें कि आपके पास एक संगत संस्करण स्थापित है।
### प्रश्न: मैं एक विशिष्ट पृष्ठ श्रेणी से XPS फ़ाइलों को कैसे परिवर्तित कर सकता हूँ?
 ए: का प्रयोग करें`options.setPageNumbers()` उन पृष्ठ संख्याओं को निर्दिष्ट करने की विधि जिन्हें आप कनवर्ट करना चाहते हैं।
### प्रश्न: क्या Aspose.Page द्वारा समर्थित अन्य आउटपुट प्रारूप हैं?
उत्तर: हाँ, Aspose.Page विभिन्न आउटपुट स्वरूपों का समर्थन करता है। विस्तृत सूची के लिए दस्तावेज़ देखें।
### प्रश्न: मुझे अतिरिक्त सहायता या समर्थन कहां मिल सकता है?
 ए: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक समर्थन और चर्चा के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
