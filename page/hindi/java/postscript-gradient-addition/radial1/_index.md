---
title: Aspose.Page के साथ जावा पोस्टस्क्रिप्ट में रेडियल ग्रेडिएंट्स में महारत हासिल करना
linktitle: जावा में रेडियल ग्रेजुएट्स में महारत हासिल करना
second_title: Aspose.Page जावा एपीआई
description: जावा के लिए Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट में आश्चर्यजनक रेडियल ग्रेडिएंट जोड़ने का तरीका जानें। इस चरण-दर-चरण मार्गदर्शिका के साथ अपने पोस्टस्क्रिप्ट दस्तावेज़ों को उन्नत बनाएं।
weight: 12
url: /hi/java/postscript-gradient-addition/radial1/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ जावा पोस्टस्क्रिप्ट में रेडियल ग्रेडिएंट्स में महारत हासिल करना

## परिचय
Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट में रेडियल ग्रेडिएंट कैसे जोड़ें, इस पर हमारी चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। इस ट्यूटोरियल में, हम आपको एक सुंदर रेडियल ग्रेडिएंट के साथ एक पोस्टस्क्रिप्ट दस्तावेज़ बनाने की प्रक्रिया के बारे में बताएंगे। जावा के लिए Aspose.Page एक शक्तिशाली लाइब्रेरी है जो आपको पोस्टस्क्रिप्ट फ़ाइलों के साथ निर्बाध रूप से काम करने की अनुमति देती है।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है।
-  जावा के लिए Aspose.Page: Aspose.Page लाइब्रेरी को यहां से डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/page/java/).
- एकीकृत विकास पर्यावरण (आईडीई): अपना पसंदीदा जावा आईडीई चुनें, जैसे कि एक्लिप्स या इंटेलीजे।
## पैकेज आयात करें
अपने जावा पोस्टस्क्रिप्ट प्रोजेक्ट के साथ आरंभ करने के लिए आवश्यक पैकेज आयात करके शुरुआत करें:
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## चरण 1: एक आयत बनाएं
आइए अपने पोस्टस्क्रिप्ट दस्तावेज़ में एक आयत बनाकर शुरुआत करें:
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// A4 आकार के साथ सेव विकल्प बनाएं
PsSaveOptions options = new PsSaveOptions();
// पेज खुलने पर नया PS दस्तावेज़ बनाएँ
PsDocument document = new PsDocument(outPsStream, options, false);
//एक आयत बनाएं
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```
## चरण 2: रंग और भिन्न को परिभाषित करें
रेडियल ग्रेडिएंट के लिए रंगों और अंशों की सरणियाँ परिभाषित करें:
```java
// ग्रेडिएंट के लिए रंगों और भिन्नों की सारणी बनाएं
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```
## चरण 3: रेडियल ग्रेडिएंट पेंट बनाएं
आयत के लिए रेडियल ग्रेडिएंट पेंट बनाएं:
```java
// रेडियल ग्रेडिएंट पेंट बनाएं
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(300, 200), 100, new Point2D.Float(300, 200),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## चरण 4: पेंट सेट करें और आयत भरें
पेंट सेट करें और आयत को रेडियल ग्रेडिएंट से भरें:
```java
// पेंट सेट करें
document.setPaint(paint);
// आयत भरें
document.fill(rectangle);
```
## चरण 5: बंद करें और सहेजें
अंत में, वर्तमान पृष्ठ को बंद करें और दस्तावेज़ को सहेजें:
```java
// वर्तमान पृष्ठ बंद करें
document.closePage();
// दस्तावेज़ सहेजें
document.save();
```
यह Aspose.Page का उपयोग करके आपके जावा पोस्टस्क्रिप्ट दस्तावेज़ में रेडियल ग्रेडिएंट जोड़ने की प्रक्रिया पूरी करता है।
## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक सीख लिया है कि जावा के लिए Aspose.Page का उपयोग करके अपने पोस्टस्क्रिप्ट दस्तावेज़ों को रेडियल ग्रेडिएंट्स के साथ कैसे बढ़ाया जाए। आश्चर्यजनक दृश्य प्रभाव बनाने के लिए विभिन्न रंगों और विन्यासों के साथ प्रयोग करें।
## पूछे जाने वाले प्रश्न
### क्या मैं व्यावसायिक परियोजनाओं में जावा के लिए Aspose.Page का उपयोग कर सकता हूँ?
 हां, आप वाणिज्यिक परियोजनाओं में जावा के लिए Aspose.Page का उपयोग कर सकते हैं। लाइसेंसिंग विवरण के लिए, यहां जाएं[यहाँ](https://purchase.aspose.com/buy).
### मैं जावा के लिए Aspose.Page के लिए दस्तावेज़ कहाँ पा सकता हूँ?
 दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/page/java/).
### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मुझे अस्थायी लाइसेंस कैसे मिल सकता है?
 एक अस्थायी लाइसेंस प्राप्त करें[यहाँ](https://purchase.aspose.com/temporary-license/).
### सामुदायिक समर्थन की आवश्यकता है?
 Aspose.Page समुदाय में शामिल हों[मंच](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
