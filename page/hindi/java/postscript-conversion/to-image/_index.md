---
title: जावा में पोस्टस्क्रिप्ट को छवि में बदलें
linktitle: जावा में पोस्टस्क्रिप्ट को छवि में बदलें
second_title: Aspose.Page जावा एपीआई
description: Aspose.Page का उपयोग करके जावा में पोस्टस्क्रिप्ट को छवियों में परिवर्तित करने पर एक व्यापक ट्यूटोरियल खोजें। चरण-दर-चरण मार्गदर्शिका, अक्सर पूछे जाने वाले प्रश्न और आवश्यक शर्तें शामिल हैं।
weight: 10
url: /hi/java/postscript-conversion/to-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में पोस्टस्क्रिप्ट को छवि में बदलें

## परिचय
सॉफ़्टवेयर विकास के निरंतर विकसित होते परिदृश्य में, कुशल दस्तावेज़ हेरफेर महत्वपूर्ण है। जावा के लिए Aspose.Page एक शक्तिशाली उपकरण के रूप में उभरता है, जो डेवलपर्स को पोस्टस्क्रिप्ट फ़ाइलों को छवियों में निर्बाध रूप से परिवर्तित करने की अनुमति देता है। इस ट्यूटोरियल में, हम चरण दर चरण प्रक्रिया से गुजरेंगे, यह सुनिश्चित करते हुए कि आप प्रत्येक पहलू को व्यापक रूप से समझ सकें।
## आवश्यक शर्तें
रूपांतरण प्रक्रिया में उतरने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
-  जावा लाइब्रेरी के लिए Aspose.Page: सुनिश्चित करें कि आपके पास जावा लाइब्रेरी के लिए Aspose.Page आपके प्रोजेक्ट में एकीकृत है। यदि नहीं, तो आप इसे यहां से डाउनलोड कर सकते हैं[पृष्ठ जारी करता है](https://releases.aspose.com/page/java/).
- दस्तावेज़ निर्देशिका: अपनी दस्तावेज़ निर्देशिका में एक पोस्टस्क्रिप्ट फ़ाइल (.ps एक्सटेंशन के साथ) तैयार रखें, क्योंकि हम इसे रूपांतरण के लिए इनपुट के रूप में उपयोग करेंगे।
## पैकेज आयात करें
अपने जावा एप्लिकेशन में आवश्यक पैकेज आयात करके शुरुआत करें। नीचे एक उदाहरण स्निपेट है:
## चरण 1: आवश्यक पैकेज आयात करें
अपने जावा एप्लिकेशन में, निर्बाध एकीकरण को सक्षम करने के लिए जावा पैकेज के लिए आवश्यक Aspose.Page आयात करें।
```java
// आवश्यक पैकेज आयात करें
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
import com.aspose.page.ImageFormat;

```
## चरण 2: दस्तावेज़ निर्देशिका और छवि प्रारूप सेट करें
अपनी दस्तावेज़ निर्देशिका के लिए पथ निर्दिष्ट करें और अपने इच्छित छवि प्रारूप को प्रारंभ करें (उदाहरण के लिए, पीएनजी)।
```java
// दस्तावेज़ निर्देशिका के लिए पथ सेट करें
String dataDir = "Your Document Directory";
// छवि प्रारूप आरंभ करें
ImageFormat imageFormat = ImageFormat.PNG;
```
## चरण 3: पोस्टस्क्रिप्ट इनपुट स्ट्रीम प्रारंभ करें
निर्दिष्ट दस्तावेज़ निर्देशिका के भीतर अपनी पोस्टस्क्रिप्ट फ़ाइल के लिए FileInputStream खोलें।
```java
// पोस्टस्क्रिप्ट इनपुट स्ट्रीम प्रारंभ करें
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## चरण 4: रूपांतरण विकल्प सेट करें
रूपांतरण विकल्पों को कॉन्फ़िगर करें, जिसमें यह भी शामिल है कि रूपांतरण के दौरान छोटी त्रुटियों को दबाया जाए या नहीं।
```java
// रूपांतरण विकल्प सेट करें
boolean suppressErrors = true;
ImageSaveOptions options = new ImageSaveOptions(suppressErrors);
```
## चरण 5: इमेज डिवाइस बनाएं
रूपांतरण प्रक्रिया को संभालने के लिए ImageDevice को प्रारंभ करें।
```java
// इमेजडिवाइस बनाएं
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## चरण 6: रूपांतरण करें
सेव विधि का उपयोग करके रूपांतरण प्रक्रिया निष्पादित करें और किसी भी अपवाद को संभालें।
```java
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## चरण 7: परिवर्तित छवियाँ सहेजें
परिवर्तित छवियों को निर्दिष्ट निर्देशिका में सहेजें।
```java
byte[][] imagesBytes = device.getImagesBytes();
int i = 0;
for (byte [] imageBytes : imagesBytes) {
    String imagePath = dataDir + "PSToImage" + i + "." + imageFormat.toString().toLowerCase();
    FileOutputStream fs = new FileOutputStream(imagePath);
    try {
        fs.write(imageBytes, 0, imageBytes.length);
    } catch (IOException ex) {
        System.out.println(ex.getMessage());
    } finally {
        fs.close();
    }
    i++;
}
```
## चरण 8: त्रुटियों की समीक्षा करें (वैकल्पिक)
यदि त्रुटियों का दमन सक्षम है, तो रूपांतरण के दौरान हुए किसी भी अपवाद की समीक्षा करें।
```java
if (suppressErrors) {
    for (Exception ex : options.getExceptions()) {
        System.out.println(ex.getMessage());
    }
}
```
## निष्कर्ष
इस ट्यूटोरियल में, हमने जावा के लिए Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट फ़ाइलों को छवियों में परिवर्तित करने की चरण-दर-चरण प्रक्रिया का पता लगाया। इन निर्देशों का पालन करके, आप कुशल दस्तावेज़ हेरफेर सुनिश्चित करते हुए, इस कार्यक्षमता को अपने जावा अनुप्रयोगों में निर्बाध रूप से एकीकृत कर सकते हैं।
## पूछे जाने वाले प्रश्न
### क्या मैं जावा के लिए Aspose.Page का उपयोग करके छोटी त्रुटियों वाली पोस्टस्क्रिप्ट फ़ाइलों को परिवर्तित कर सकता हूँ?
 हाँ, आप सेट कर सकते हैं`suppressErrors` मामूली त्रुटियों के बावजूद रूपांतरण को आगे बढ़ाने के लिए रूपांतरण विकल्पों में सत्य पर ध्वजांकित करें।
### मैं रूपांतरण प्रक्रिया के दौरान अतिरिक्त फ़ॉन्ट कैसे संभाल सकता हूं?
 उपयोग`setAdditionalFontsFolders` अतिरिक्त फ़ोल्डर निर्दिष्ट करने के लिए विकल्प ऑब्जेक्ट में विधि जहां फ़ॉन्ट संग्रहीत हैं।
### रूपांतरण के लिए डिफ़ॉल्ट छवि प्रारूप क्या है?
डिफ़ॉल्ट छवि प्रारूप पीएनजी है, लेकिन यदि आवश्यक हो तो आप एक अलग प्रारूप निर्दिष्ट कर सकते हैं।
### क्या ImageDevice में छवि का आकार सेट करना अनिवार्य है?
नहीं, यह अनिवार्य नहीं है. डिफ़ॉल्ट छवि का आकार 595x842 है, लेकिन यदि विशिष्ट आयामों की आवश्यकता हो तो आप इसे सेट कर सकते हैं।
### मुझे अधिक जानकारी और सहायता कहां मिल सकती है?
 पता लगाएं[प्रलेखन](https://reference.aspose.com/page/java/) और विजिट करें[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक समर्थन के लिए.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
