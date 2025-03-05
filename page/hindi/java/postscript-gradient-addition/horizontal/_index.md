---
title: जावा पोस्टस्क्रिप्ट में क्षैतिज ग्रेडिएंट जोड़ें
linktitle: जावा पोस्टस्क्रिप्ट में क्षैतिज ग्रेडिएंट जोड़ें
second_title: Aspose.Page जावा एपीआई
description: जावा के लिए Aspose.Page के साथ जावा पोस्टस्क्रिप्ट में क्षैतिज ग्रेडिएंट जोड़ने का तरीका जानें। सहजता से दृश्यात्मक रूप से आश्चर्यजनक दस्तावेज़ बनाएं।
type: docs
weight: 11
url: /hi/java/postscript-gradient-addition/horizontal/
---
## परिचय
जावा के लिए Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट में एक क्षैतिज ग्रेडिएंट जोड़ने पर इस व्यापक ट्यूटोरियल में आपका स्वागत है। Aspose.Page एक शक्तिशाली जावा लाइब्रेरी है जो डेवलपर्स को पोस्टस्क्रिप्ट और अन्य दस्तावेज़ प्रारूपों के साथ काम करने की अनुमति देती है। इस ट्यूटोरियल में, हम चरण-दर-चरण उदाहरणों का उपयोग करके क्षैतिज ग्रेडिएंट के साथ एक पोस्टस्क्रिप्ट दस्तावेज़ बनाने की प्रक्रिया में आपका मार्गदर्शन करेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- आपकी मशीन पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
- जावा लाइब्रेरी के लिए Aspose.Page। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose.Page जावा दस्तावेज़ीकरण](https://reference.aspose.com/page/java/).
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करके शुरुआत करें। Aspose.Page के साथ काम करने के लिए ये पैकेज महत्वपूर्ण हैं।
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## चरण 1: एक आयत बनाएं
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// A4 आकार के साथ सेव विकल्प बनाएं
PsSaveOptions options = new PsSaveOptions();
// पेज खुलने पर नया PS दस्तावेज़ बनाएँ
PsDocument document = new PsDocument(outPsStream, options, false);
//एक आयत बनाएं
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## चरण 2: क्षैतिज रैखिक ढाल पेंट बनाएं
```java
// क्षैतिज रैखिक ढाल पेंट बनाएं। परिवर्तन में स्केल घटक आयत की चौड़ाई और ऊंचाई के बराबर होने चाहिए।
// अनुवाद घटक आयत के ऑफसेट हैं।
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// पेंट सेट करें
document.setPaint(paint);
```
## चरण 3: आयत भरें
```java
// आयत भरें
document.fill(rectangle);
```
## चरण 4: ग्रेडिएंट के साथ एक टेक्स्ट भरें
```java
// किसी टेक्स्ट को ग्रेडिएंट से भरें
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## चरण 5: ग्रेडिएंट के साथ टेक्स्ट को स्ट्रोक करें
```java
// किसी टेक्स्ट को ग्रेडिएंट से स्ट्रोक करें
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## निष्कर्ष
बधाई हो! आपने जावा के लिए Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट में एक क्षैतिज ग्रेडिएंट सफलतापूर्वक जोड़ा है। इस ट्यूटोरियल ने आपको आकर्षक पोस्टस्क्रिप्ट दस्तावेज़ बनाने में मदद करने के लिए एक विस्तृत चरण-दर-चरण मार्गदर्शिका प्रदान की है।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं व्यावसायिक परियोजनाओं में जावा के लिए Aspose.Page का उपयोग कर सकता हूँ?
हां, जावा के लिए Aspose.Page का उपयोग व्यावसायिक परियोजनाओं में किया जा सकता है। लाइसेंसिंग विवरण के लिए, यहां जाएं[Aspose.खरीद](https://purchase.aspose.com/buy).
### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप Java के लिए Aspose.Page का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मुझे अतिरिक्त दस्तावेज और सहायता कहां मिल सकती है?
 दौरा करना[Aspose.Page जावा दस्तावेज़ीकरण](https://reference.aspose.com/page/java/) व्यापक संसाधनों के लिए. सामुदायिक समर्थन के लिए, जाँच करें[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39).
### मैं अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
 आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[Aspose.खरीद](https://purchase.aspose.com/temporary-license/).
### जावा के लिए Aspose.Page के लिए सिस्टम आवश्यकताएँ क्या हैं?
 को देखें[प्रलेखन](https://reference.aspose.com/page/java/) विस्तृत सिस्टम आवश्यकताओं के लिए.