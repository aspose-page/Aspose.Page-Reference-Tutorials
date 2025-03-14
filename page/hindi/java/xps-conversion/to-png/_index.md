---
title: जावा में XPS को PNG में कनवर्ट करें
linktitle: जावा में XPS को PNG में कनवर्ट करें
second_title: Aspose.Page जावा एपीआई
description: Aspose.Page का उपयोग करके जावा में आसानी से XPS को PNG में बदलें। इस विश्वसनीय और डेवलपर-अनुकूल समाधान के साथ दस्तावेज़ कार्यों को सुव्यवस्थित करें।
weight: 13
url: /hi/java/xps-conversion/to-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में XPS को PNG में कनवर्ट करें

## परिचय
सॉफ़्टवेयर विकास की गतिशील दुनिया में, XPS (XML पेपर विशिष्टता) दस्तावेज़ों को PNG (पोर्टेबल नेटवर्क ग्राफ़िक्स) छवियों में परिवर्तित करने की आवश्यकता अक्सर उठती रहती है। जावा में इस कार्य को निर्बाध रूप से पूरा करने के लिए, Aspose.Page एक शक्तिशाली समाधान प्रदान करता है। इस ट्यूटोरियल में, हम जावा के लिए Aspose.Page का उपयोग करके XPS को PNG में परिवर्तित करने की प्रक्रिया के बारे में जानेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ स्थापित हैं:
1. जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जेडीके स्थापित है।
2.  जावा के लिए Aspose.Page: Aspose.Page लाइब्रेरी डाउनलोड और इंस्टॉल करें। आप डाउनलोड लिंक पा सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
3. एकीकृत विकास पर्यावरण (आईडीई): IntelliJ IDEA या Eclipse जैसी जावा-संगत आईडीई चुनें।
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में, Aspose.Page कार्यक्षमताओं का उपयोग करने के लिए आवश्यक पैकेज आयात करें। अपनी जावा फ़ाइल की शुरुआत में निम्नलिखित आयात विवरण जोड़ें:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
```
## चरण 2: एक्सपीएस दस्तावेज़ लोड करें
```java
// एक्सपीएस दस्तावेज़ लोड करें
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## चरण 3: विकल्पों को आरंभ करें
```java
// आवश्यक मापदंडों के साथ विकल्प ऑब्जेक्ट को आरंभ करें।
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## चरण 4: रेंडरिंग डिवाइस बनाएं
```java
// पीडीएफ प्रारूप के लिए रेंडरिंग डिवाइस बनाएं
ImageDevice device = new ImageDevice();
```
## चरण 5: सहेजें और पुनरावृत्त करें
```java
// विकल्पों और डिवाइस का उपयोग करके XPS दस्तावेज़ को PNG में सहेजें
document.save(device, options);
//दस्तावेज़ विभाजन के माध्यम से पुनरावृति (निश्चित दस्तावेज़, XPS शब्दों में)
for (int i = 0; i < device.getResult().length; i++) {
    // विभाजन पृष्ठों के माध्यम से पुनरावृति करें
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // छवि आउटपुट स्ट्रीम प्रारंभ करें
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // छवि लिखें
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // स्ट्रीम बंद करें
        imageStream.close();
    }
}
```
इन चरणों का पालन करके, आप जावा के लिए Aspose.Page का उपयोग करके आसानी से XPS दस्तावेज़ों को PNG छवियों में परिवर्तित कर सकते हैं।
## निष्कर्ष
अंत में, जावा के लिए Aspose.Page XPS से PNG रूपांतरण प्रक्रिया को सरल बनाता है, डेवलपर्स को एक विश्वसनीय और कुशल टूल प्रदान करता है। दस्तावेज़ हेरफेर कार्यों को सुव्यवस्थित करने के लिए इस लाइब्रेरी को अपने जावा प्रोजेक्ट्स में शामिल करें।
## पूछे जाने वाले प्रश्न
### क्या मैं व्यावसायिक परियोजनाओं में जावा के लिए Aspose.Page का उपयोग कर सकता हूँ?
 हाँ, Aspose.Page एक व्यावसायिक उत्पाद है। आप लाइसेंस संबंधी जानकारी पा सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप नि:शुल्क परीक्षण का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं जावा के लिए Aspose.Page के लिए दस्तावेज़ कहाँ पा सकता हूँ?
 व्यापक दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/page/java/).
### मैं परीक्षण प्रयोजनों के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
 आपको अस्थायी लाइसेंस मिल सकता है[यहाँ](https://purchase.aspose.com/temporary-license/).
### क्या Aspose.Page चर्चाओं के लिए सामुदायिक मंच हैं?
 हाँ, सामुदायिक मंचों पर जाएँ[यहाँ](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
