---
title: जावा पोस्टस्क्रिप्ट में टेक्सचर टाइलिंग पैटर्न जोड़ें
linktitle: जावा पोस्टस्क्रिप्ट में टेक्सचर टाइलिंग पैटर्न जोड़ें
second_title: Aspose.Page जावा एपीआई
description: जावा के लिए Aspose.Page के साथ पोस्टस्क्रिप्ट दस्तावेज़ों में आसानी से टेक्सचर टाइलिंग पैटर्न जोड़ें। रचनात्मक संभावनाओं के लिए हमारी निर्बाध एकीकरण मार्गदर्शिका का अन्वेषण करें।
type: docs
weight: 10
url: /hi/java/postscript-texture-patterns/add-texture-tiling-pattern/
---
## परिचय
जावा विकास के क्षेत्र में, पोस्टस्क्रिप्ट दस्तावेज़ों में जटिल पैटर्न और बनावट बनाना एक सामान्य आवश्यकता है। जावा के लिए Aspose.Page इस कार्य को सहजता से पूरा करने में एक मूल्यवान उपकरण साबित होता है। इस ट्यूटोरियल में, हम Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट दस्तावेज़ में टेक्सचर टाइलिंग पैटर्न जोड़ने की प्रक्रिया में आपका मार्गदर्शन करेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- जावा प्रोग्रामिंग भाषा की बुनियादी समझ।
- पोस्टस्क्रिप्ट दस्तावेज़ संरचना से परिचित होना।
-  जावा लाइब्रेरी के लिए Aspose.Page स्थापित किया गया। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
## पैकेज आयात करें
अपने जावा प्रोजेक्ट के लिए आवश्यक पैकेज आयात करके प्रारंभ करें:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## चरण 1: एक पोस्टस्क्रिप्ट दस्तावेज़ बनाएँ
एक नया पोस्टस्क्रिप्ट दस्तावेज़ बनाकर, आउटपुट स्ट्रीम और सेव विकल्पों को निर्दिष्ट करके शुरुआत करें। सुनिश्चित करें कि आपके पास आवश्यक पथ कॉन्फ़िगर हैं।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// A4 आकार के साथ सेव विकल्प बनाएं
PsSaveOptions options = new PsSaveOptions();
// पेज खुलने पर नया PS दस्तावेज़ बनाएँ
PsDocument document = new PsDocument(outPsStream, options, false);
// पेज खुलने पर नया PS दस्तावेज़ बनाएँ
PsDocument document = new PsDocument(outPsStream, options, false);
```
## चरण 2: ग्राफ़िक्स वातावरण सेट करें
मूल का अनुवाद करके और बनावट छवि फ़ाइल से बफ़र्डइमेज बनाकर ग्राफ़िक्स वातावरण सेट करें।
```java
document.writeGraphicsSave();
document.translate(200, 100);
// छवि फ़ाइल से एक बफ़र्डइमेज ऑब्जेक्ट बनाएं
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```
## चरण 3: टेक्सचर ब्रश बनाएं
छवि से बनावट ब्रश को परिभाषित करें, बनावट द्वारा कवर किए जाने वाले क्षेत्र को निर्दिष्ट करें।
```java
// छवि क्षेत्र को चौड़ाई में दोगुना करें
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// छवि से बनावट ब्रश बनाएं
TexturePaint paint = new TexturePaint(image, imageArea);
```
## चरण 4: आकृतियाँ बनाएं और भरें
एक आयत बनाएं और इसे परिभाषित बनावट वाले ब्रश से भरें। इसके अतिरिक्त, दृश्य अपील के लिए आकृति बनाएं और रूपरेखा बनाएं।
```java
// आयत बनाएं
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// इस टेक्सचर ब्रश को वर्तमान पेंट के रूप में सेट करें
document.setPaint(paint);
// आयत भरें
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```
## चरण 5: बनावट पैटर्न के साथ टेक्स्ट जोड़ें
दस्तावेज़ में टेक्स्ट जोड़ें और उसे बनावट पैटर्न से भरें/स्ट्रोक करें। आवश्यकतानुसार फ़ॉन्ट, स्थिति और अन्य पैरामीटर अनुकूलित करें।
```java
// टेक्स्ट को टेक्सचर पैटर्न से भरें
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// बनावट पैटर्न के साथ पाठ को रेखांकित करें
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## चरण 6: सहेजें और बंद करें
वर्तमान पृष्ठ को बंद करके, दस्तावेज़ को सहेजकर और निर्बाध निष्पादन सुनिश्चित करके प्रक्रिया समाप्त करें।
```java
// वर्तमान पृष्ठ बंद करें
document.closePage();
// दस्तावेज़ सहेजें
document.save();
```
## निष्कर्ष
बधाई हो! आपने जावा के लिए Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट दस्तावेज़ में एक बनावट टाइलिंग पैटर्न सफलतापूर्वक जोड़ा है। आगे के अनुकूलन विकल्पों का पता लगाने और इस शक्तिशाली लाइब्रेरी की पूरी क्षमता का उपयोग करने के लिए स्वतंत्र महसूस करें।

## अक्सर पूछे जाने वाले प्रश्न
### क्या जावा के लिए Aspose.Page शुरुआती लोगों के लिए उपयुक्त है?
बिल्कुल! जावा के लिए Aspose.Page व्यापक दस्तावेज़ीकरण प्रदान करता है, जो इसे सभी कौशल स्तरों के डेवलपर्स के लिए सुलभ बनाता है।
### क्या मैं जावा के लिए Aspose.Page को अपने मौजूदा जावा प्रोजेक्ट में एकीकृत कर सकता हूँ?
 हां, आप दिए गए दस्तावेज़ का पालन करके आसानी से जावा के लिए Aspose.Page को अपने प्रोजेक्ट में एकीकृत कर सकते हैं[यहाँ](https://reference.aspose.com/page/java/).
### मुझे समर्थन कहां मिल सकता है या Aspose.Page से संबंधित प्रश्नों पर चर्चा कहां हो सकती है?
 दौरा करना[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) समुदाय के साथ जुड़ना और सहायता प्राप्त करना।
### क्या जावा के लिए Aspose.Page के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप नि:शुल्क परीक्षण का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं जावा के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 मिलने जाना[इस लिंक](https://purchase.aspose.com/temporary-license/) अस्थायी लाइसेंस प्राप्त करने के लिए.