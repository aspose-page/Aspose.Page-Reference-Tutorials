---
title: जावा पोस्टस्क्रिप्ट में विकर्ण ग्रेडिएंट जोड़ें
linktitle: जावा पोस्टस्क्रिप्ट में विकर्ण ग्रेडिएंट जोड़ें
second_title: Aspose.Page जावा एपीआई
description: जावा के लिए Aspose.Page का उपयोग करके अपने जावा पोस्टस्क्रिप्ट दस्तावेज़ों को विकर्ण ग्रेडिएंट के साथ बढ़ाएं। सहजता से जीवंत रंग परिवर्तन जोड़ने के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 10
url: /hi/java/postscript-gradient-addition/diagonal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा पोस्टस्क्रिप्ट में विकर्ण ग्रेडिएंट जोड़ें

## परिचय
जावा के लिए Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट में एक विकर्ण ढाल जोड़ने पर हमारी चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। इस ट्यूटोरियल में, हम प्रत्येक उदाहरण को कई चरणों में विभाजित करते हुए, आपको प्रक्रिया के बारे में बताएंगे। एक कुशल एसईओ लेखक के रूप में, मैं यह सुनिश्चित करूँगा कि सामग्री न केवल जानकारीपूर्ण हो बल्कि खोज इंजनों के लिए भी अनुकूलित हो, जिससे डेवलपर्स और उत्साही लोगों के लिए इसका अनुसरण करना आसान हो जाए।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
- एकीकृत विकास पर्यावरण (आईडीई) जैसे एक्लिप्स या इंटेलीजे।
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
## चरण 1: पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```
## चरण 2: A4 आकार के साथ सेव विकल्प बनाएं
```java
// A4 आकार के साथ सेव विकल्प बनाएं
PsSaveOptions options = new PsSaveOptions();
```
## चरण 3: नया पीएस दस्तावेज़ बनाएं
```java
// पेज खुलने पर नया PS दस्तावेज़ बनाएँ
PsDocument document = new PsDocument(outPsStream, options, false);
```
## चरण 4: एक आयत बनाएं
```java
//एक आयत बनाएं
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## चरण 5: ग्रेडिएंट ट्रांसफ़ॉर्म बनाएं
```java
//ग्रेडिएंट ट्रांसफ़ॉर्म बनाएं. स्केल घटक आयत की चौड़ाई और ऊंचाई के बराबर होने चाहिए।
// अनुवाद घटक आयत के ऑफसेट हैं।
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// दृश्यमान रंग परिवर्तन के लिए ग्रेडिएंट घुमाएँ, फिर स्केल करें और अनुवाद करें
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```
## चरण 6: डायगोनल लीनियर ग्रेडिएंट पेंट बनाएं
```java
// विकर्ण रैखिक ढाल पेंट बनाएं
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```
## चरण 7: पेंट सेट करें और आयत भरें
```java
// पेंट सेट करें और आयत भरें
document.setPaint(paint);
document.fill(rectangle);
```
## चरण 8: वर्तमान पृष्ठ बंद करें और दस्तावेज़ सहेजें
```java
// वर्तमान पृष्ठ बंद करें और दस्तावेज़ सहेजें
document.closePage();
document.save();
```
इन चरणों का पालन करके, आप जावा के लिए Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट में सफलतापूर्वक एक विकर्ण ग्रेडिएंट जोड़ देंगे।
## निष्कर्ष
बधाई हो! आपने सीखा है कि जावा के लिए Aspose.Page का उपयोग करके अपने जावा पोस्टस्क्रिप्ट दस्तावेज़ों को विकर्ण ग्रेडिएंट के साथ कैसे बढ़ाया जाए। अद्वितीय दृश्य प्रभाव प्राप्त करने के लिए विभिन्न मापदंडों के साथ प्रयोग करें।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या मैं इस लाइब्रेरी का उपयोग जावा में अन्य ग्राफ़िक संचालन के लिए कर सकता हूँ?
उत्तर: हाँ, जावा के लिए Aspose.Page पोस्टस्क्रिप्ट और अन्य ग्राफ़िक तत्वों के साथ काम करने के लिए कई सुविधाएँ प्रदान करता है।
### प्रश्न: क्या जावा के लिए Aspose.Page के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हाँ, आप निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं जावा के लिए Aspose.Page के लिए दस्तावेज़ कहां पा सकता हूं?
 उत्तर: दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/page/java/).
### प्रश्न: मैं जावा के लिए Aspose.Page का लाइसेंस कैसे खरीद सकता हूं?
 उत्तर: आप लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### प्रश्न: सहायता चाहिए या कोई प्रश्न हैं?
 ए: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
