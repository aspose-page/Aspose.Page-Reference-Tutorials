---
title: जावा एक्सपीएस में क्षैतिज ग्रेडिएंट जोड़ें
linktitle: जावा एक्सपीएस में क्षैतिज ग्रेडिएंट जोड़ें
second_title: Aspose.Page जावा एपीआई
description: Aspose.Page का उपयोग करके जावा में XPS दस्तावेज़ों में एक आश्चर्यजनक क्षैतिज ग्रेडिएंट जोड़ने का तरीका जानें। निर्बाध एकीकरण के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 11
url: /hi/java/xps-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा एक्सपीएस में क्षैतिज ग्रेडिएंट जोड़ें

## परिचय
जावा के लिए Aspose.Page का उपयोग करके Java XPS में एक क्षैतिज ग्रेडिएंट जोड़ने पर इस चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। जावा के लिए Aspose.Page एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को XPS (XML पेपर स्पेसिफिकेशन) दस्तावेज़ों के साथ निर्बाध रूप से काम करने की अनुमति देती है।
इस ट्यूटोरियल में, हम आपको XPS दस्तावेज़ में क्षैतिज ग्रेडिएंट जोड़ने के लिए जावा एप्लिकेशन बनाने की प्रक्रिया के बारे में बताएंगे। इसे आसानी से प्राप्त करने के लिए नीचे दिए गए चरणों का पालन करें।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1. जावा विकास पर्यावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है। यदि नहीं, तो जावा का नवीनतम संस्करण डाउनलोड और इंस्टॉल करें[java.com](https://www.java.com).
2.  जावा लाइब्रेरी के लिए Aspose.Page: जावा लाइब्रेरी के लिए आपके पास Aspose.Page होना आवश्यक है। आप इसे यहां से डाउनलोड कर सकते हैं[जावा दस्तावेज़ीकरण के लिए Aspose.Page](https://reference.aspose.com/page/java/).
## पैकेज आयात करें
अपने जावा एप्लिकेशन के लिए आवश्यक पैकेज आयात करके प्रारंभ करें। अपने प्रोजेक्ट में जावा लाइब्रेरी के लिए Aspose.Page शामिल करें। आप कोड की निम्नलिखित पंक्तियाँ जोड़कर ऐसा कर सकते हैं:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## चरण 1: दस्तावेज़ आरंभ करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
//दस्तावेज़ आरंभ करें
XpsDocument doc = new XpsDocument();
```
## चरण 2: क्षैतिज ग्रेडिएंट बनाएं
```java
// क्षैतिज ढाल
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## चरण 3: ग्रेडिएंट के साथ पथ जोड़ें
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## चरण 4: दस्तावेज़ सहेजें
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
अपनी विशिष्ट आवश्यकताओं के आधार पर मापदंडों को समायोजित करते हुए, आवश्यकतानुसार इन चरणों को दोहराएं।
## निष्कर्ष
बधाई हो! आपने Java के लिए Aspose.Page का उपयोग करके XPS दस्तावेज़ में एक क्षैतिज ग्रेडिएंट सफलतापूर्वक जोड़ दिया है। इस ट्यूटोरियल ने उन डेवलपर्स के लिए एक व्यापक मार्गदर्शिका प्रदान की जो अपने जावा अनुप्रयोगों को ग्रेडिएंट प्रभावों के साथ बढ़ाना चाहते हैं।
## पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं एक ही XPS दस्तावेज़ में एकाधिक ग्रेडिएंट लागू कर सकता हूँ?
हाँ, आप जटिल डिज़ाइन बनाने के लिए विभिन्न ग्रेडिएंट के साथ कई पथ जोड़ सकते हैं।
### प्रश्न: क्या Aspose.Page नवीनतम जावा संस्करणों के साथ संगत है?
नवीनतम जावा रिलीज़ के साथ संगतता सुनिश्चित करने के लिए जावा के लिए Aspose.Page को नियमित रूप से अपडेट किया जाता है।
### प्रश्न: क्या Aspose.Page में अन्य ग्रेडिएंट प्रकार उपलब्ध हैं?
हां, रैखिक ग्रेडिएंट्स के अलावा, Aspose.Page अधिक विविध प्रभावों के लिए रेडियल ग्रेडिएंट्स का समर्थन करता है।
### प्रश्न: क्या मैं ग्रेडिएंट स्टॉप के रंग और स्थिति को अनुकूलित कर सकता हूँ?
बिल्कुल! प्रत्येक ग्रेडिएंट स्टॉप के रंग और स्थिति पर आपका पूर्ण नियंत्रण होता है।
### प्रश्न: क्या Aspose.Page के लिए कोई सामुदायिक मंच है जहां मैं मदद मांग सकता हूं?
 हां, आप यहां जा सकते हैं[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) समुदाय से जुड़ने और सहायता प्राप्त करने के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
