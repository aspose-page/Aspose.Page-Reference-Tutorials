---
title: जावा एक्सपीएस में वर्टिकल ग्रेडिएंट जोड़ें
linktitle: जावा एक्सपीएस में वर्टिकल ग्रेडिएंट जोड़ें
second_title: Aspose.Page जावा एपीआई
description: Aspose.Page के साथ Java XPS दस्तावेज़ों में वर्टिकल ग्रेडिएंट जोड़ने का तरीका जानें। दृश्य अपील को सहजता से बढ़ाएँ। अंदर चरण-दर-चरण मार्गदर्शिका.
weight: 12
url: /hi/java/xps-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा एक्सपीएस में वर्टिकल ग्रेडिएंट जोड़ें

## परिचय
इस ट्यूटोरियल में, हम यह पता लगाएंगे कि Java के लिए Aspose.Page का उपयोग करके Java XPS में वर्टिकल ग्रेडिएंट कैसे जोड़ा जाए। अपने XPS दस्तावेज़ों में ग्रेडिएंट जोड़ने से आपकी सामग्री की दृश्य अपील बढ़ सकती है, जिससे यह अधिक आकर्षक और सौंदर्यपूर्ण रूप से मनभावन हो सकती है।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- एक कार्यशील जावा विकास वातावरण।
-  जावा लाइब्रेरी के लिए Aspose.Page। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
- जावा प्रोग्रामिंग की बुनियादी समझ।
## पैकेज आयात करें
अपने जावा प्रोजेक्ट के लिए आवश्यक पैकेज आयात करके प्रारंभ करें। सुनिश्चित करें कि आपने अपने प्रोजेक्ट निर्भरता में जावा लाइब्रेरी के लिए Aspose.Page को शामिल किया है।
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
        
// जावा के लिए Aspose.Page आयात करें
```
## चरण 1: दस्तावेज़ को प्रारंभ करें
XPS दस्तावेज़ को प्रारंभ करके प्रारंभ करें। यह आपके दस्तावेज़ में पथ और ग्रेडिएंट जैसे तत्वों को जोड़ने के लिए आधार तैयार करता है।
```java
// दस्तावेज़ आरंभ करें
XpsDocument doc = new XpsDocument();
```
## चरण 2: वर्टिकल ग्रेडिएंट के साथ एक पथ बनाएं
अब, आइए एक ऊर्ध्वाधर ढाल के साथ एक पथ बनाएं। इसमें पथ ज्यामिति को परिभाषित करना और ग्रेडिएंट स्टॉप निर्दिष्ट करना शामिल है।
```java
// ज्यामिति के साथ एक पथ बनाएं
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// ऊर्ध्वाधर ढाल स्टॉप को परिभाषित करें
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//पथ पर लंबवत ढाल लागू करें
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## चरण 3: दस्तावेज़ सहेजें
अंत में, XPS दस्तावेज़ को अपनी वांछित निर्देशिका में जोड़े गए वर्टिकल ग्रेडिएंट के साथ सहेजें।
```java
// दस्तावेज़ सहेजें
doc.save(dataDir + "VerticalGradient.xps");
```
बधाई हो! आपने Aspose.Page का उपयोग करके अपने Java XPS दस्तावेज़ में सफलतापूर्वक एक लंबवत ग्रेडिएंट जोड़ा है।
## निष्कर्ष
अपने XPS दस्तावेज़ों को ग्रेडिएंट्स के साथ बढ़ाने से उनकी दृश्य अपील में काफी सुधार हो सकता है। जावा के लिए Aspose.Page इस प्रक्रिया को सरल बनाता है, जिससे आप आसानी से शानदार दस्तावेज़ बना सकते हैं।

### पूछे जाने वाले प्रश्न
### क्या मैं व्यावसायिक परियोजनाओं में जावा के लिए Aspose.Page का उपयोग कर सकता हूँ?
 हां, जावा के लिए Aspose.Page व्यावसायिक उपयोग के लिए उपलब्ध है। आप इसे खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### क्या जावा के लिए Aspose.Page के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप निःशुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं जावा के लिए Aspose.Page के लिए दस्तावेज़ कहाँ पा सकता हूँ?
 दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/page/java/).
### मैं जावा के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 एक अस्थायी लाइसेंस प्राप्त करें[यहाँ](https://purchase.aspose.com/temporary-license/).
### क्या मदद की ज़रूरत है या कोई सवाल है?
 Aspose.Page समुदाय पर जाएँ[मंच](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
