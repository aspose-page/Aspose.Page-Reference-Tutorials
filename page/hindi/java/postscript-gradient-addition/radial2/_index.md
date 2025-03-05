---
title: Aspose.Page के साथ जावा पोस्टस्क्रिप्ट रेडियल ग्रेडिएंट
linktitle: Aspose.Page के साथ जावा पोस्टस्क्रिप्ट रेडियल ग्रेडिएंट
second_title: Aspose.Page जावा एपीआई
description: अपने जावा अनुप्रयोगों में आश्चर्यजनक ग्राफिक्स के लिए Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट में रेडियल ग्रेडिएंट जोड़ने के लिए चरण-दर-चरण मार्गदर्शिका देखें।
type: docs
weight: 13
url: /hi/java/postscript-gradient-addition/radial2/
---
## परिचय
जावा के लिए Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट में रेडियल ग्रेडिएंट 2 जोड़ने पर हमारी चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। यह ट्यूटोरियल आपको एक सुंदर रेडियल ग्रेडिएंट के साथ एक पोस्टस्क्रिप्ट दस्तावेज़ बनाने की प्रक्रिया के बारे में बताएगा, जो आपके जावा अनुप्रयोगों को आकर्षक ग्राफिक्स के साथ बढ़ाएगा।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- जावा प्रोग्रामिंग का कार्यसाधक ज्ञान।
- आपकी मशीन पर जावा डेवलपमेंट किट (जेडीके) स्थापित किया गया।
-  जावा लाइब्रेरी के लिए Aspose.Page, जिसे आप यहां से डाउनलोड कर सकते हैं[Aspose.Page जावा दस्तावेज़ीकरण](https://reference.aspose.com/page/java/).
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में, Aspose.Page के लिए आवश्यक पैकेज आयात करें:
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
अपनी दस्तावेज़ निर्देशिका का पथ परिभाषित करें:
```java
String dataDir = "Your Document Directory";
```
## चरण 2: आउटपुट स्ट्रीम बनाएं
पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं:
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## चरण 3: सहेजें विकल्प बनाएं
A4 आकार के साथ सेव विकल्प बनाएं:
```java
PsSaveOptions options = new PsSaveOptions();
```
## चरण 4: पीएस दस्तावेज़ बनाएं
खोले गए पृष्ठ के साथ एक नया PS दस्तावेज़ बनाएँ:
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## चरण 5: एक वृत्त बनाएं
Ellipse2D.Float वर्ग का उपयोग करके एक वृत्त को परिभाषित करें:
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## चरण 6: ग्रेडिएंट रंगों को परिभाषित करें
रेडियल ग्रेडिएंट के लिए रंगों और अंशों की सारणी बनाएं:
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## चरण 7: एफ़िनट्रांसफ़ॉर्म बनाएं
रेडियल ग्रेडिएंट के लिए एक एफ़िनट्रांसफॉर्म बनाएं:
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## चरण 8: रेडियल ग्रेडिएंट पेंट बनाएं
निर्दिष्ट मापदंडों के साथ एक रेडियलग्रेडिएंटपेंट बनाएं:
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## चरण 9: पेंट सेट करें और सर्कल भरें
पेंट सेट करें और सर्कल को रेडियल ग्रेडिएंट से भरें:
```java
document.setPaint(paint);
document.fill(circle);
```
## चरण 10: पृष्ठ बंद करें और दस्तावेज़ सहेजें
वर्तमान पृष्ठ बंद करें और दस्तावेज़ सहेजें:
```java
document.closePage();
document.save();
```
बधाई हो! आपने जावा के लिए Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट में रेडियल ग्रेडिएंट 2 को सफलतापूर्वक जोड़ा है।
## निष्कर्ष
इस ट्यूटोरियल में, हमने पता लगाया कि पोस्टस्क्रिप्ट दस्तावेजों में रेडियल ग्रेडिएंट्स के साथ अपने जावा अनुप्रयोगों को कैसे बढ़ाया जाए। जावा के लिए Aspose.Page आश्चर्यजनक ग्राफिक्स बनाने के लिए टूल का एक शक्तिशाली सेट प्रदान करता है, जिससे आप अपने जावा प्रोजेक्ट्स को अगले स्तर पर ले जा सकते हैं।
## पूछे जाने वाले प्रश्न
### प्रश्न: मैं जावा के लिए Aspose.Page के लिए दस्तावेज़ कहां पा सकता हूं?
 उत्तर: दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/page/java/).
### प्रश्न: मैं जावा के लिए Aspose.Page कैसे डाउनलोड कर सकता हूं?
 उत्तर: आप इसे यहां से डाउनलोड कर सकते हैं[पृष्ठ जारी करता है](https://releases.aspose.com/page/java/).
### प्रश्न: क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हाँ, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: क्या मुझे जावा के लिए Aspose.Page का अस्थायी लाइसेंस मिल सकता है?
 उत्तर: हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: मैं सामुदायिक समर्थन कहां प्राप्त कर सकता हूं और चर्चाओं में भाग ले सकता हूं?
 ए: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39).