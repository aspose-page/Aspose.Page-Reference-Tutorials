---
title: जावा में XPS को JPEG में कनवर्ट करें
linktitle: जावा में XPS को JPEG में कनवर्ट करें
second_title: Aspose.Page जावा एपीआई
description: Aspose.Page का उपयोग करके जावा में XPS को JPEG में बदलने का तरीका जानें। निर्बाध एकीकरण के लिए चरण-दर-चरण निर्देशों के साथ एक व्यापक मार्गदर्शिका।
weight: 11
url: /hi/java/xps-conversion/to-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में XPS को JPEG में कनवर्ट करें

## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Page का उपयोग करके XPS (XML पेपर विशिष्टता) फ़ाइलों को JPEG छवियों में परिवर्तित करने का तरीका जानेंगे। Aspose.Page एक शक्तिशाली जावा लाइब्रेरी है जो डेवलपर्स को XPS और अन्य दस्तावेज़ प्रारूपों के साथ निर्बाध रूप से काम करने की अनुमति देती है। यह चरण-दर-चरण मार्गदर्शिका आपको प्रक्रिया को समझने और इसे अपने जावा अनुप्रयोगों में लागू करने में मदद करेगी।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- जावा विकास वातावरण: सुनिश्चित करें कि आपकी मशीन पर जावा विकास वातावरण स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Page: जावा लाइब्रेरी के लिए Aspose.Page को डाउनलोड और इंस्टॉल करें। आप पुस्तकालय पा सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
- नमूना XPS दस्तावेज़: एक नमूना XPS दस्तावेज़ रखें जिसे आप JPEG में कनवर्ट करना चाहते हैं।
## पैकेज आयात करें
अपने जावा क्लास में आवश्यक पैकेज आयात करके शुरुआत करें:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## चरण 1: पथ और XPS दस्तावेज़ प्रारंभ करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// XPS इनपुट स्ट्रीम प्रारंभ करें
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## चरण 2: JpegSaveOptions सेट करें
```java
// आवश्यक मापदंडों के साथ विकल्प ऑब्जेक्ट को आरंभ करें।
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## चरण 3: रेंडरिंग डिवाइस बनाएं
```java
// पीडीएफ प्रारूप के लिए रेंडरिंग डिवाइस बनाएं
ImageDevice device = new ImageDevice();
```
## चरण 4: XPS को JPEG के रूप में सहेजें
```java
document.save(device, options);
```
## चरण 5: JPEG पेजों को पुनरावृत्त करें और सहेजें
```java
//दस्तावेज़ विभाजन के माध्यम से पुनरावृति (निश्चित दस्तावेज़, XPS शब्दों में)
for (int i = 0; i < device.getResult().length; i++) {
    // विभाजन पृष्ठों के माध्यम से पुनरावृति करें
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // छवि आउटपुट स्ट्रीम प्रारंभ करें
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // छवि लिखें
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //स्ट्रीम बंद करें
        imageStream.close();
    }
}
```
चरणों की यह श्रृंखला प्रभावी रूप से आपके XPS दस्तावेज़ को JPEG छवियों में परिवर्तित कर देगी, जिनमें से प्रत्येक को अलग से सहेजा जाएगा।
## निष्कर्ष
बधाई हो! आपने Aspose.Page का उपयोग करके जावा में XPS को JPEG में परिवर्तित करने का तरीका सफलतापूर्वक सीख लिया है। जावा अनुप्रयोगों में दस्तावेज़ रूपांतरण के साथ काम करने वाले डेवलपर्स के लिए यह प्रक्रिया अमूल्य है।
## अक्सर पूछे जाने वाले प्रश्नों

### प्रश्न: क्या Aspose.Page व्यावसायिक परियोजनाओं के लिए उपयुक्त है?
 उत्तर: हाँ, Aspose.Page एक व्यावसायिक उत्पाद है जिसके पास लाइसेंसिंग विकल्प उपलब्ध हैं। जाँच करना[यहाँ](https://purchase.aspose.com/buy) जानकारी के लिए।
### प्रश्न: क्या मैं खरीदने से पहले Aspose.Page आज़मा सकता हूँ?
 उत्तर: हाँ, आप निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मुझे Aspose.Page दस्तावेज़ कहां मिल सकता है?
 उत्तर: दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/page/java/).
### प्रश्न: मैं Aspose.Page के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 ए: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) समुदाय-आधारित समर्थन के लिए.
### प्रश्न: क्या मुझे परीक्षण के लिए अस्थायी लाइसेंस की आवश्यकता है?
 उत्तर: हाँ, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
