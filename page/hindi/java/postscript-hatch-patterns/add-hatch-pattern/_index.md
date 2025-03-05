---
title: जावा पोस्टस्क्रिप्ट में हैच पैटर्न जोड़ें
linktitle: जावा पोस्टस्क्रिप्ट में हैच पैटर्न जोड़ें
second_title: Aspose.Page जावा एपीआई
description: Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट दस्तावेज़ों में आकर्षक हैच पैटर्न जोड़ने का तरीका जानें। अपनी दृश्य सामग्री को सहजता से उन्नत करें।
type: docs
weight: 10
url: /hi/java/postscript-hatch-patterns/add-hatch-pattern/
---
## परिचय
जावा प्रोग्रामिंग की दुनिया में, विज़ुअल तत्वों को बढ़ाना डेवलपर्स के लिए एक सामान्य आवश्यकता है। एक दिलचस्प दृश्य वृद्धि पोस्टस्क्रिप्ट दस्तावेज़ों में हैच पैटर्न को जोड़ना है। यह ट्यूटोरियल जावा के लिए Aspose.Page का उपयोग करके हैच पैटर्न जोड़ने की प्रक्रिया में आपका मार्गदर्शन करेगा।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित सेटअप है:
- जावा विकास वातावरण: सुनिश्चित करें कि आपके पास जावा विकास वातावरण तैयार है।
-  जावा लाइब्रेरी के लिए Aspose.Page: जावा लाइब्रेरी के लिए Aspose.Page को डाउनलोड और इंस्टॉल करें। आप आवश्यक फ़ाइलें पा सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें। निम्नलिखित कोड स्निपेट का उपयोग करें:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## चरण 1: प्रारंभिक पैरामीटर सेट करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// A4 आकार के साथ सेव विकल्प बनाएं
PsSaveOptions options = new PsSaveOptions();
// पेज खुलने पर नया PS दस्तावेज़ बनाएँ
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```
## चरण 2: ग्राफ़िक्स स्थिति सहेजें और अनुवाद करें
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```
## चरण 3: प्रत्येक पैटर्न के लिए वर्ग बनाएं
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```
## चरण 4: पैटर्न स्क्वायर आउटलाइन के लिए पेन सेट करें
```java
BasicStroke stroke = new BasicStroke(2);
```
## चरण 5: हैच पैटर्न के माध्यम से पुनरावृत्त करें
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (प्रदान किए गए कोड के साथ जारी रखें)
}
```
## चरण 6: ग्राफ़िक्स स्थिति पुनर्स्थापित करें
```java
document.writeGraphicsRestore();
```
## चरण 7: टेक्स्ट को हैच पैटर्न से भरें
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```
## चरण 8: हैच पैटर्न के साथ पाठ की रूपरेखा तैयार करें
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```
## चरण 9: दस्तावेज़ को बंद करें और सहेजें
```java
document.closePage();
document.save();
```
इन चरणों का पालन करें, और आप Aspose.Page का उपयोग करके अपने जावा पोस्टस्क्रिप्ट दस्तावेज़ में सफलतापूर्वक हैच पैटर्न जोड़ देंगे।
## निष्कर्ष
हैच पैटर्न जैसे दृश्य तत्वों को शामिल करने से आपके जावा अनुप्रयोगों की अपील में काफी वृद्धि हो सकती है। जावा के लिए Aspose.Page इस प्रक्रिया को निर्बाध बनाता है, जिससे आप आसानी से आश्चर्यजनक पोस्टस्क्रिप्ट दस्तावेज़ बना सकते हैं।
## पूछे जाने वाले प्रश्न
### क्या मैं अन्य जावा फ्रेमवर्क के साथ जावा के लिए Aspose.Page का उपयोग कर सकता हूँ?
हां, जावा के लिए Aspose.Page को विभिन्न जावा फ्रेमवर्क के साथ सहजता से एकीकृत करने के लिए डिज़ाइन किया गया है।
### क्या जावा के लिए Aspose.Page के लिए एक परीक्षण संस्करण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं जावा के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### जावा के लिए Aspose.Page के लिए मुझे और अधिक ट्यूटोरियल और समर्थन कहां मिल सकता है?
 पता लगाएं[जावा फोरम के लिए Aspose.Page](https://forum.aspose.com/c/page/39) ट्यूटोरियल और सामुदायिक सहायता के लिए।
### क्या जावा के लिए Aspose.Page के लिए कोई व्यापक दस्तावेज़ीकरण संसाधन है?
 हाँ, दस्तावेज़ देखें[यहाँ](https://reference.aspose.com/page/java/).