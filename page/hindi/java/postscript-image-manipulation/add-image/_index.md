---
title: जावा पोस्टस्क्रिप्ट में छवि जोड़ें
linktitle: जावा पोस्टस्क्रिप्ट में छवि जोड़ें
second_title: Aspose.Page जावा एपीआई
description: पोस्टस्क्रिप्ट दस्तावेज़ों में छवियां जोड़ने पर इस ट्यूटोरियल में Aspose.Page Java के सहज एकीकरण का अन्वेषण करें। अपनी दस्तावेज़ हेरफेर क्षमताओं को बढ़ाएँ।
weight: 10
url: /hi/java/postscript-image-manipulation/add-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा पोस्टस्क्रिप्ट में छवि जोड़ें

## परिचय
इस ट्यूटोरियल में, हम यह पता लगाएंगे कि जावा लाइब्रेरी के लिए Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट दस्तावेज़ में छवियां कैसे जोड़ें। Aspose.Page एक शक्तिशाली लाइब्रेरी है जो पोस्टस्क्रिप्ट फ़ाइलों के साथ काम करने के लिए विभिन्न सुविधाएँ प्रदान करती है, जिससे डेवलपर्स को अपने दस्तावेज़ों में निर्बाध रूप से हेरफेर करने और बढ़ाने की अनुमति मिलती है।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Page। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
- जावा प्रोग्रामिंग की बुनियादी समझ।
## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें। संदर्भ के रूप में निम्नलिखित कोड स्निपेट का उपयोग करें:
```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## चरण 1: ग्राफ़िक्स सेव लिखें
पहले चरण में दस्तावेज़ में ग्राफ़िक्स सेव लिखना शामिल है। यह सुनिश्चित करता है कि बाद में किए गए किसी भी परिवर्तन या संशोधन को जरूरत पड़ने पर वापस लिया जा सकता है।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// A4 आकार के साथ सेव विकल्प बनाएं
PsSaveOptions options = new PsSaveOptions();
// पेज खुलने पर नया PS दस्तावेज़ बनाएँ
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```
## चरण 2: अनुवाद करें और रूपांतरित करें
इसके बाद, दस्तावेज़ का अनुवाद करें और छवि फ़ाइल से एक बफ़र्डइमेज ऑब्जेक्ट बनाएं। एफ़िनट्रांसफ़ॉर्म का उपयोग करके स्केलिंग और रोटेशन जैसे परिवर्तनों की एक श्रृंखला लागू करें।
```java
document.translate(100, 100);
// छवि फ़ाइल से एक बफ़रेडइमेज ऑब्जेक्ट बनाएं
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// छवि परिवर्तन बनाएँ
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```
## चरण 3: दस्तावेज़ में छवि जोड़ें
अब, परिवर्तित छवि को दस्तावेज़ में जोड़ें।
```java
document.drawImage(image, transform, null);
```
## चरण 4: ग्राफ़िक्स रिस्टोर लिखें
छवि जोड़ने के बाद, किए गए परिवर्तनों को अंतिम रूप देने के लिए ग्राफ़िक्स रिस्टोर लिखें।
```java
document.writeGraphicsRestore();
```
## चरण 5: वर्तमान पृष्ठ बंद करें और सहेजें
वर्तमान पृष्ठ बंद करें और दस्तावेज़ सहेजें।
```java
document.closePage();
document.save();
```
एकाधिक छवियां जोड़ने या अपनी आवश्यकताओं के आधार पर परिवर्तनों को अनुकूलित करने के लिए इन चरणों को दोहराएं।
## निष्कर्ष
 बधाई हो! आपने जावा के लिए Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट दस्तावेज़ में छवियां जोड़ने का तरीका सफलतापूर्वक सीख लिया है। पता लगाएं[प्रलेखन](https://reference.aspose.com/page/java/) अधिक उन्नत सुविधाओं और कार्यक्षमताओं के लिए।
## पूछे जाने वाले प्रश्न
### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ जावा के लिए Aspose.Page का उपयोग कर सकता हूँ?
Aspose.Page मुख्य रूप से जावा का समर्थन करता है, लेकिन अन्य प्रोग्रामिंग भाषाओं के लिए भी संस्करण उपलब्ध हैं।
### क्या जावा के लिए Aspose.Page के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं जावा के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आपको अस्थायी लाइसेंस मिल सकता है[यहाँ](https://purchase.aspose.com/temporary-license/).
### मुझे Java के लिए Aspose.Page से संबंधित सामुदायिक समर्थन और चर्चाएँ कहाँ मिल सकती हैं?
 दौरा करना[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक समर्थन के लिए.
### क्या जावा के लिए Aspose.Page खरीदने के लिए कोई अतिरिक्त संसाधन हैं?
 आप लाइब्रेरी खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
