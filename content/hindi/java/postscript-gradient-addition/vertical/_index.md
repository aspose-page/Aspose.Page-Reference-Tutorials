---
title: जावा पोस्टस्क्रिप्ट में वर्टिकल ग्रेडिएंट जोड़ें
linktitle: जावा पोस्टस्क्रिप्ट में वर्टिकल ग्रेडिएंट जोड़ें
second_title: Aspose.Page जावा एपीआई
description: जावा के लिए Aspose.Page के साथ जावा पोस्टस्क्रिप्ट में वर्टिकल ग्रेडिएंट जोड़ने के लिए चरण-दर-चरण मार्गदर्शिका देखें। जीवंत दृश्यों के साथ अपने दस्तावेज़ों को सहजता से बढ़ाएं।
type: docs
weight: 14
url: /hi/java/postscript-gradient-addition/vertical/
---
## परिचय
जावा के लिए Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट में वर्टिकल ग्रेडिएंट जोड़ने पर इस चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। यदि आप अपने दस्तावेज़ को आकर्षक ग्रेडिएंट्स के साथ बढ़ाना चाहते हैं, तो यह ट्यूटोरियल आपके लिए है। जावा के लिए Aspose.Page पोस्टस्क्रिप्ट दस्तावेज़ों में निर्बाध रूप से हेरफेर करने के लिए शक्तिशाली उपकरण प्रदान करता है।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- आपकी मशीन पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Page। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में, आरंभ करने के लिए आवश्यक पैकेज आयात करें:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
अब, आइए जावा पोस्टस्क्रिप्ट में वर्टिकल ग्रेडिएंट जोड़ने की प्रक्रिया को कई चरणों में विभाजित करें।
## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
```
## चरण 2: पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
```java
// पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## चरण 3: A4 आकार के साथ सेव विकल्प बनाएं
```java
// A4 आकार के साथ सेव विकल्प बनाएं
PsSaveOptions options = new PsSaveOptions();
```
## चरण 4: एक नया पीएस दस्तावेज़ बनाएँ
```java
// पेज खुलने पर नया PS दस्तावेज़ बनाएँ
PsDocument document = new PsDocument(outPsStream, options, false);
```
## चरण 5: एक आयत बनाएं
```java
//एक आयत बनाएं
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## चरण 6: ग्रेडिएंट के लिए रंग और भिन्न सेट करें
```java
// ग्रेडिएंट के लिए रंगों और भिन्नों की सारणी बनाएं।
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## चरण 7: ग्रेडिएंट ट्रांसफ़ॉर्म बनाएं
```java
// ग्रेडिएंट ट्रांसफ़ॉर्म बनाएं. परिवर्तन में स्केल घटक आयत की चौड़ाई और ऊंचाई के बराबर होने चाहिए।
// अनुवाद घटक आयत के ऑफसेट हैं।
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// मूल बिंदु के चारों ओर ग्रेडिएंट को 90 डिग्री पर घुमाएँ
transform.rotate(90 * (Math.PI / 180));
```
## चरण 8: वर्टिकल लीनियर ग्रेडिएंट पेंट बनाएं
```java
// वर्टिकल लीनियर ग्रेडिएंट पेंट बनाएं।
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## चरण 9: पेंट सेट करें और आयत भरें
```java
// पेंट सेट करें
document.setPaint(paint);
// आयत भरें
document.fill(rectangle);
```
## चरण 10: वर्तमान पृष्ठ बंद करें और दस्तावेज़ सहेजें
```java
// वर्तमान पृष्ठ बंद करें
document.closePage();
// दस्तावेज़ सहेजें
document.save();
```
बधाई हो! आपने जावा के लिए Aspose.Page का उपयोग करके अपने जावा पोस्टस्क्रिप्ट दस्तावेज़ में सफलतापूर्वक एक लंबवत ग्रेडिएंट जोड़ा है।
## निष्कर्ष
इस ट्यूटोरियल में, हमने जावा के लिए Aspose.Page का उपयोग करके जीवंत वर्टिकल ग्रेडिएंट्स के साथ आपके दस्तावेज़ों को बढ़ाने की प्रक्रिया का पता लगाया। अब, आप आश्चर्यजनक दृश्यों को शामिल करके अपने दस्तावेज़ हेरफेर को अगले स्तर पर ले जा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं अन्य जावा लाइब्रेरीज़ के साथ जावा के लिए Aspose.Page का उपयोग कर सकता हूँ?
हां, जावा के लिए Aspose.Page को अन्य जावा लाइब्रेरीज़ के साथ सहजता से काम करने के लिए डिज़ाइन किया गया है।
### क्या जावा के लिए Aspose.Page के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मुझे अतिरिक्त दस्तावेज कहां मिल सकते हैं?
 विस्तृत दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/page/java/).
### मैं जावा के लिए Aspose.Page कैसे खरीद सकता हूँ?
 आप जावा के लिए Aspose.Page खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### क्या Aspose.Page चर्चा के लिए कोई मंच है?
 हाँ, आप सामुदायिक मंच में शामिल हो सकते हैं[यहाँ](https://forum.aspose.com/c/page/39).