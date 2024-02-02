---
title: Aspose.Page के साथ रेडियल ग्रेडिएंट एलिप्स जोड़ें
linktitle: जावा एक्सपीएस में एलिप्से जोड़ें
second_title: Aspose.Page जावा एपीआई
description: जावा के लिए Aspose.Page का उपयोग करके जावा XPS में रेडियल ग्रेडिएंट स्ट्रोक्ड एलिप्स जोड़ने पर चरण-दर-चरण मार्गदर्शिका देखें। अपने दस्तावेज़ निर्माण को सहजता से बढ़ाएं।
type: docs
weight: 10
url: /hi/java/xps-shapes/add-ellipse/
---
## परिचय
जावा के लिए Aspose.Page का उपयोग करके जावा XPS में एक दीर्घवृत्त जोड़ने पर हमारी चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। Aspose.Page एक शक्तिशाली जावा लाइब्रेरी है जो डेवलपर्स को XPS दस्तावेज़ों के साथ सहजता से काम करने की अनुमति देती है। इस ट्यूटोरियल में, हम आपको रेडियल ग्रेडिएंट स्ट्रोक्ड एलिप्स बनाने और इसे XPS दस्तावेज़ के रूप में सहेजने की प्रक्रिया के बारे में बताएंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- आपकी मशीन पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Page डाउनलोड किया गया। आप ये पा सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
- जावा कोड लिखने और निष्पादित करने के लिए आपकी पसंद का एक कोड संपादक (एक्लिप्स, इंटेलीजे, आदि)।
## पैकेज आयात करें
सुनिश्चित करें कि Aspose.Page का उपयोग करने के लिए आपके जावा प्रोजेक्ट में आवश्यक पैकेज आयातित हैं। अपनी जावा फ़ाइल के शीर्ष पर निम्नलिखित आयात विवरण जोड़ें:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
अपनी दस्तावेज़ निर्देशिका का पथ परिभाषित करें जहाँ XPS दस्तावेज़ सहेजा जाएगा:
```java
String dataDir = "Your Document Directory";
```
## चरण 2: एक्सपीएस दस्तावेज़ बनाएं
निम्नलिखित कोड का उपयोग करके एक नया XPS दस्तावेज़ प्रारंभ करें:
```java
XpsDocument doc = new XpsDocument();
```
## चरण 3: रेडियल ग्रेडिएंट स्टॉप्स को परिभाषित करें
रेडियल ग्रेडिएंट स्ट्रोक्ड दीर्घवृत्त के लिए ग्रेडिएंट स्टॉप की एक सूची बनाएं:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## चरण 4: पथ ज्यामिति बनाएं
पथ ज्यामिति का उपयोग करके रेडियल ग्रेडिएंट स्ट्रोक वाले दीर्घवृत्त को परिभाषित करें:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## चरण 5: कैनवास और पथ जोड़ें
दस्तावेज़ में एक नया कैनवास जोड़ें और परिभाषित ज्यामिति के साथ पथ जोड़ें:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## चरण 6: स्ट्रोक और ग्रेडिएंट सेट करें
रेडियल ग्रेडिएंट ब्रश से पथ के स्ट्रोक को कॉन्फ़िगर करें:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## चरण 7: स्ट्रोक की मोटाई सेट करें
पथ की स्ट्रोक मोटाई निर्दिष्ट करें:
```java
path.setStrokeThickness(12f);
```
## चरण 8: दस्तावेज़ सहेजें
परिणामी XPS दस्तावेज़ सहेजें:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
बधाई हो! आपने Java के लिए Aspose.Page का उपयोग करके Java XPS में रेडियल ग्रेडिएंट स्ट्रोक्ड एलिप्स को सफलतापूर्वक जोड़ा है।
## निष्कर्ष
इस ट्यूटोरियल में, हमने एक आकर्षक रेडियल ग्रेडिएंट स्ट्रोक्ड एलिप्स के साथ एक एक्सपीएस दस्तावेज़ बनाने के चरणों का पता लगाया। जावा के लिए Aspose.Page XPS दस्तावेज़ हेरफेर को सरल बनाता है, डेवलपर्स को एक शक्तिशाली टूलसेट प्रदान करता है।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं अन्य जावा लाइब्रेरीज़ के साथ जावा के लिए Aspose.Page का उपयोग कर सकता हूँ?
हां, जावा के लिए Aspose.Page को अन्य जावा लाइब्रेरी के साथ सहजता से एकीकृत किया जा सकता है।
### क्या Aspose.Page बड़े पैमाने पर दस्तावेज़ प्रसंस्करण के लिए उपयुक्त है?
बिल्कुल! Aspose.Page को बड़े पैमाने पर दस्तावेज़ प्रसंस्करण को कुशलतापूर्वक संभालने के लिए डिज़ाइन किया गया है।
### जावा के लिए Aspose.Page के लिए मुझे और अधिक ट्यूटोरियल और उदाहरण कहां मिल सकते हैं?
 दौरा करना[जावा दस्तावेज़ीकरण के लिए Aspose.Page](https://reference.aspose.com/page/java/)व्यापक ट्यूटोरियल और उदाहरणों के लिए।
### मैं जावा के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आपको अस्थायी लाइसेंस मिल सकता है[यहाँ](https://purchase.aspose.com/temporary-license/).
### क्या Aspose.Page चर्चाओं के लिए सामुदायिक मंच हैं?
 हाँ, शामिल हों[Aspose.Page सामुदायिक मंच](https://forum.aspose.com/c/page/39) अन्य डेवलपर्स के साथ जुड़ने और सहायता प्राप्त करने के लिए।