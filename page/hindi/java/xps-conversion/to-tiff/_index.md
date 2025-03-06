---
title: जावा में XSP को TIFF में बदलें
linktitle: जावा में XSP को TIFF में बदलें
second_title: Aspose.Page जावा एपीआई
description: जावा के लिए Aspose.Page के साथ आसानी से XPS को TIFF में बदलें। निर्बाध एकीकरण के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें। अब डाउनलोड करो!
weight: 14
url: /hi/java/xps-conversion/to-tiff/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में XSP को TIFF में बदलें

आज के डिजिटल युग में, दस्तावेज़ रूपांतरण विभिन्न अनुप्रयोगों में महत्वपूर्ण भूमिका निभाता है। यदि आप एक जावा डेवलपर हैं जो एक्सपीएस (एक्सएमएल पेपर विशिष्टता) दस्तावेजों को टीआईएफएफ (टैग की गई छवि फ़ाइल प्रारूप) में परिवर्तित करने के लिए एक मजबूत समाधान ढूंढ रहे हैं, तो जावा के लिए Aspose.Page आपकी पसंदीदा लाइब्रेरी है। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको प्रक्रिया के बारे में बताएंगे, यह सुनिश्चित करते हुए कि आपको विस्तृत स्पष्टीकरण और कोड स्निपेट के साथ एक सहज अनुभव होगा।
## आवश्यक शर्तें
रूपांतरण प्रक्रिया में उतरने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- आपकी मशीन पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Page। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
-  जावा के लिए Aspose.Page के लिए एक वैध लाइसेंस। आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/) , या पूर्ण लाइसेंस खरीदें[यहाँ](https://purchase.aspose.com/buy).
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करके शुरुआत करें। सुनिश्चित करें कि आपके प्रोजेक्ट में जावा लाइब्रेरी के लिए Aspose.Page जोड़ा गया है।
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
अपनी दस्तावेज़ निर्देशिका का पथ परिभाषित करें जहां इनपुट XPS फ़ाइल स्थित है।
```java
String dataDir = "Your Document Directory";
```
## चरण 2: एक्सपीएस दस्तावेज़ लोड करें
Aspose.Page लाइब्रेरी का उपयोग करके XPS दस्तावेज़ लोड करें।
```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## चरण 3: TiffSaveOptions को आरंभ करें
स्मूथिंग मोड, रिज़ॉल्यूशन और विशिष्ट पेज नंबर जैसे आवश्यक पैरामीटर के साथ TiffSaveOptions ऑब्जेक्ट को प्रारंभ करें।
```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## चरण 4: रेंडरिंग डिवाइस बनाएं
ImageDevice क्लास का उपयोग करके TIFF प्रारूप के लिए एक रेंडरिंग डिवाइस बनाएं।
```java
ImageDevice device = new ImageDevice();
```
## चरण 5: दस्तावेज़ को TIFF में सहेजें
निर्दिष्ट विकल्पों और रेंडरिंग डिवाइस का उपयोग करके XPS दस्तावेज़ को TIFF प्रारूप में सहेजें।
```java
document.save(device, options);
```
## चरण 6: TIFF छवियों को पुनरावृत्त करें और सहेजें
दस्तावेज़ विभाजन और पृष्ठों के माध्यम से पुनरावृति करें, छवि आउटपुट स्ट्रीम प्रारंभ करें और TIFF छवियों को सहेजें।
```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```
 बधाई हो! आपने Aspose.Page का उपयोग करके जावा में XPS को TIFF में सफलतापूर्वक परिवर्तित कर लिया है। लाइब्रेरी की अधिक सुविधाओं और कार्यात्मकताओं का पता लगाने के लिए स्वतंत्र महसूस करें[प्रलेखन](https://reference.aspose.com/page/java/).
## निष्कर्ष
इस ट्यूटोरियल में, हमने Aspose.Page का उपयोग करके जावा में XPS को TIFF में बदलने के लिए आवश्यक चरणों को कवर किया है। दस्तावेज़ रूपांतरण अब आपकी उंगलियों पर है, जिससे आप बहुमुखी फ़ाइल प्रारूप समर्थन के साथ अपने एप्लिकेशन को बढ़ा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं बिना लाइसेंस के जावा के लिए Aspose.Page का उपयोग कर सकता हूँ?
 जबकि आप मूल्यांकन के लिए एक अस्थायी लाइसेंस प्राप्त कर सकते हैं, उत्पादन उपयोग के लिए एक वैध लाइसेंस की आवश्यकता होती है। अपना लाइसेंस प्राप्त करें[यहाँ](https://purchase.aspose.com/buy).
### क्या रूपांतरण के लिए XPS फ़ाइलों के आकार पर कोई सीमाएँ हैं?
जावा के लिए Aspose.Page विभिन्न आकारों के दस्तावेज़ों को संभालता है, लेकिन आपके विशिष्ट वातावरण में बड़ी फ़ाइलों के साथ परीक्षण करना उचित है।
### मैं Java के लिए Aspose.Page के बारे में समर्थन कैसे प्राप्त कर सकता हूँ या प्रश्न कैसे पूछ सकता हूँ?
 दौरा करना[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक समर्थन और चर्चा के लिए।
### क्या जावा के लिए Aspose.Page के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण के साथ पुस्तकालय का अन्वेषण कर सकते हैं। इसे डाउनलोड करें[यहाँ](https://releases.aspose.com/).
### इस रूपांतरण में TIFF छवियों के लिए अनुशंसित रिज़ॉल्यूशन क्या है?
प्रदान किया गया उदाहरण 300 डीपीआई के रिज़ॉल्यूशन का उपयोग करता है, लेकिन आप इसे अपनी विशिष्ट आवश्यकताओं के आधार पर समायोजित कर सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
