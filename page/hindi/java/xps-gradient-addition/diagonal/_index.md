---
title: जावा एक्सपीएस में डायगोनल ग्रेडिएंट जोड़ें
linktitle: जावा एक्सपीएस में डायगोनल ग्रेडिएंट जोड़ें
second_title: Aspose.Page जावा एपीआई
description: Aspose.Page का उपयोग करके जावा में अपने XPS दस्तावेज़ों में एक आश्चर्यजनक विकर्ण ग्रेडिएंट जोड़ने का तरीका जानें। अपनी दृश्य प्रस्तुति को सहजता से उन्नत करें।
weight: 10
url: /hi/java/xps-gradient-addition/diagonal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा एक्सपीएस में डायगोनल ग्रेडिएंट जोड़ें

## परिचय
जावा विकास की निरंतर विकसित हो रही दुनिया में, आपके XPS दस्तावेज़ों की दृश्य अपील को बढ़ाना महत्वपूर्ण है। इसे प्राप्त करने का एक प्रभावी तरीका विकर्ण ग्रेडिएंट्स को शामिल करना है। यह ट्यूटोरियल आपको जावा के लिए Aspose.Page का उपयोग करने की प्रक्रिया में मार्गदर्शन करेगा, चरण-दर-चरण निर्देश और कोड स्निपेट प्रदान करेगा।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- जावा प्रोग्रामिंग की बुनियादी समझ.
- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित किया गया।
-  जावा लाइब्रेरी के लिए Aspose.Page। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
- एक कोड संपादक जैसे IntelliJ IDEA या Eclipse।
## पैकेज आयात करें
अपने जावा प्रोजेक्ट के लिए आवश्यक पैकेज आयात करके शुरुआत करें। अपने कोड में, आप निम्नलिखित आयात जोड़ सकते हैं:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपने पसंदीदा इंटीग्रेटेड डेवलपमेंट एनवायरनमेंट (आईडीई) में एक नया जावा प्रोजेक्ट बनाएं और अपने प्रोजेक्ट निर्भरता में Aspose.Page लाइब्रेरी को शामिल करें।
## चरण 2: दस्तावेज़ निर्देशिका को परिभाषित करें
अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करें जहां XPS फ़ाइल सहेजी जाएगी:
```java
String dataDir = "Your Document Directory";
```
## चरण 3: एक्सपीएस दस्तावेज़ बनाएं
एक नया XpsDocument ऑब्जेक्ट प्रारंभ करें:
```java
XpsDocument doc = new XpsDocument();
```
## चरण 4: विकर्ण ढाल पथ जोड़ें
XPS दस्तावेज़ में विकर्ण ढाल के साथ एक पथ जोड़ें:
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```
## चरण 5: लीनियर ग्रेडिएंट स्टॉप्स को परिभाषित करें
विशिष्ट रंगों और स्थितियों के साथ रैखिक ग्रेडिएंट स्टॉप सेट करें:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... अन्य रंगों और स्थितियों के लिए दोहराएं
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```
## चरण 6: पथ पर रेखीय ढाल लागू करें
पहले से परिभाषित पथ पर रैखिक ढाल लागू करें:
```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## चरण 7: दस्तावेज़ सहेजें
अतिरिक्त विकर्ण ग्रेडिएंट के साथ XPS दस्तावेज़ सहेजें:
```java
doc.save(dataDir + "LinearGradient.xps");
```
## निष्कर्ष
बधाई हो! आपने जावा के लिए Aspose.Page का उपयोग करके अपने XPS दस्तावेज़ में सफलतापूर्वक एक विकर्ण ढाल जोड़ लिया है। यह देखने में आकर्षक सुविधा आपके दस्तावेज़ों की समग्र प्रस्तुति को बेहतर बना सकती है।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या मैं अन्य जावा फ्रेमवर्क के साथ जावा के लिए Aspose.Page का उपयोग कर सकता हूं?
Aspose.Page को विभिन्न जावा फ्रेमवर्क के साथ सहजता से एकीकृत करने के लिए डिज़ाइन किया गया है, जो इसे आपकी परियोजनाओं के लिए एक बहुमुखी विकल्प बनाता है।
### प्रश्न: क्या Aspose.Page के लिए कोई लाइसेंस संबंधी विचार हैं?
 हां, इस पर लाइसेंसिंग विवरण की समीक्षा करना सुनिश्चित करें[Aspose.पेज खरीद पृष्ठ](https://purchase.aspose.com/buy).
### प्रश्न: क्या मैं खरीदने से पहले जावा के लिए Aspose.Page आज़मा सकता हूँ?
 बिल्कुल! आप एक खोज कर सकते हैं[निःशुल्क परीक्षण संस्करण यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं Aspose समुदाय से समर्थन कैसे प्राप्त कर सकता हूं या उससे कैसे जुड़ सकता हूं?
 दौरा करना[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) समुदाय के साथ जुड़ना और सहायता प्राप्त करना।
### प्रश्न: क्या अस्थायी लाइसेंस का प्रावधान है?
 हाँ, आप प्राप्त कर सकते हैं[यहां अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
