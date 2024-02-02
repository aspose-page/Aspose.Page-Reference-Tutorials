---
title: Aspose.Page Java के साथ सहज मीटरयुक्त लाइसेंस एकीकरण
linktitle: जावा में मीटर्ड लाइसेंस सेट करें
second_title: Aspose.Page जावा एपीआई
description: Java के साथ Aspose.Page के निर्बाध एकीकरण का अन्वेषण करें। आसानी से मीटर्ड लाइसेंस सेट करें और अपनी दस्तावेज़ प्रसंस्करण क्षमताओं को बढ़ाएं।
type: docs
weight: 10
url: /hi/java/license-management/set-metered-license/
---
## परिचय
Aspose.Page का उपयोग करके जावा में मीटर्ड लाइसेंस स्थापित करने पर हमारी व्यापक मार्गदर्शिका में आपका स्वागत है। यदि आप अपनी दस्तावेज़ प्रसंस्करण क्षमताओं को बढ़ाना चाहते हैं और Aspose.Page के साथ निर्बाध एकीकरण सुनिश्चित करना चाहते हैं, तो आप सही जगह पर हैं। इस ट्यूटोरियल में, हम आपको प्रक्रिया के बारे में बताएंगे, प्रत्येक चरण को आसानी से पचने योग्य टुकड़ों में तोड़ देंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान।
-  Aspose.Page लाइब्रेरी स्थापित की गई। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
- मीटरयुक्त सार्वजनिक और निजी कुंजियाँ, जिन्हें आप अपने Aspose खाते के माध्यम से प्राप्त कर सकते हैं।
## पैकेज आयात करें
आइए अपने जावा प्रोग्राम के लिए आवश्यक पैकेज आयात करके शुरुआत करें। सुनिश्चित करें कि आपके पास Aspose.Page लाइब्रेरी आपके प्रोजेक्ट में एकीकृत है।
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## चरण 1: दस्तावेज़ और छवि प्रारूप प्रारंभ करें
पहला कदम दस्तावेज़ को सेट करना और वांछित छवि प्रारूप को परिभाषित करना है।
```java
// मीटरयुक्त सार्वजनिक और निजी कुंजियाँ सेट करें
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// setMeteredKey प्रॉपर्टी तक पहुंचें और सार्वजनिक और निजी कुंजियों को पैरामीटर के रूप में पास करें
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## चरण 2: पोस्टस्क्रिप्ट इनपुट स्ट्रीम प्रारंभ करें
इस चरण में, हम प्रोसेसिंग के लिए पोस्टस्क्रिप्ट इनपुट स्ट्रीम को आरंभ करते हैं।
```java
// पोस्टस्क्रिप्ट इनपुट स्ट्रीम प्रारंभ करें
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## चरण 3: दस्तावेज़ लाइसेंस की जाँच करें
आगे बढ़ने से पहले, यह सत्यापित करना महत्वपूर्ण है कि दस्तावेज़ उचित रूप से लाइसेंसीकृत है या नहीं।
```java
// जाँचें कि दस्तावेज़ लाइसेंसीकृत है या नहीं
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## चरण 4: विकल्प और छवि डिवाइस प्रारंभ करें
अब, डिफ़ॉल्ट मापदंडों के साथ विकल्पों और छवि डिवाइस को आरंभ करते हैं।
```java
// डिफ़ॉल्ट पैरामीटर के साथ विकल्प ऑब्जेक्ट को प्रारंभ करें।
ImageSaveOptions options = new ImageSaveOptions();
// डिफ़ॉल्ट पैरामीटर के साथ ImageDevice ऑब्जेक्ट को प्रारंभ करें।
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## चरण 5: ईपीएस फ़ाइल को छवि के रूप में सहेजें
परिभाषित विकल्पों और डिवाइस का उपयोग करके ईपीएस फ़ाइल को एक छवि के रूप में सहेजें।
```java
// ईपीएस फ़ाइल को छवि के रूप में सहेजें
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## चरण 6: छवि बाइट्स प्राप्त करें और सहेजें
छवि बाइट्स पुनर्प्राप्त करें और उन्हें एक फ़ाइल में सहेजें।
```java
// छवियाँ बाइट्स प्राप्त करें. एक पृष्ठ के लिए एक बाइट्स सरणी। हमारे मामले में, हमारे पास एक पृष्ठ है।
byte[][] imagesBytes = device.getImagesBytes();
// फ़ाइल में छवि बाइट्स सहेजें
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## निष्कर्ष
बधाई हो! आपने Aspose.Page का उपयोग करके जावा में सफलतापूर्वक मीटर्ड लाइसेंस स्थापित कर लिया है। इस ट्यूटोरियल ने सुचारू एकीकरण प्रक्रिया सुनिश्चित करने के लिए चरण-दर-चरण मार्गदर्शिका प्रदान की है।
## पूछे जाने वाले प्रश्न
### प्रश्न: मैं मीटर वाली सार्वजनिक और निजी कुंजी कैसे प्राप्त कर सकता हूं?
आप इन चाबियों को अपने Aspose खाते के माध्यम से प्राप्त कर सकते हैं।
### प्रश्न: क्या Aspose.Page लाइब्रेरी निःशुल्क है?
 Aspose.Page नि:शुल्क परीक्षण और सशुल्क संस्करण दोनों प्रदान करता है। मिलने जाना[यहाँ](https://releases.aspose.com/) निःशुल्क परीक्षण के लिए.
### प्रश्न: क्या मैं व्यावसायिक परियोजनाओं के लिए Aspose.Page का उपयोग कर सकता हूँ?
 हाँ, Aspose.Page वाणिज्यिक लाइसेंस प्रदान करता है। आप उन्हें खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### प्रश्न: मुझे अतिरिक्त दस्तावेज कहां मिल सकते हैं?
 दस्तावेज़ देखें[यहाँ](https://reference.aspose.com/page/java/).
### प्रश्न: मैं अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 अस्थायी लाइसेंस प्राप्त किया जा सकता है[यहाँ](https://purchase.aspose.com/temporary-license/).