---
title: Aspose.Page जावा टेक्स्ट मैनिपुलेशन
linktitle: जावा पोस्टस्क्रिप्ट में टेक्स्ट जोड़ें
second_title: Aspose.Page जावा एपीआई
description: पोस्टस्क्रिप्ट दस्तावेज़ों में टेक्स्ट जोड़ने पर हमारे ट्यूटोरियल में जावा के लिए Aspose.Page की शक्ति का अन्वेषण करें। सिस्टम और कस्टम फ़ॉन्ट का आसानी से उपयोग करना सीखें।
type: docs
weight: 10
url: /hi/java/postscript-text-manipulation/add-text/
---
## परिचय
जावा के लिए Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट में टेक्स्ट जोड़ने पर हमारी चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। जावा के लिए Aspose.Page एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को पोस्टस्क्रिप्ट दस्तावेज़ों में आसानी से हेरफेर करने की अनुमति देती है। इस ट्यूटोरियल में, हम आपको टेक्स्ट जोड़ने, सिस्टम और कस्टम फ़ॉन्ट का उपयोग करने, टेक्स्ट को रेखांकित करने और एक आकर्षक परिणाम के लिए स्ट्रोक्स को शामिल करने की प्रक्रिया के बारे में बताएंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान।
-  जावा लाइब्रेरी के लिए Aspose.Page स्थापित किया गया। आप इसे यहां से डाउनलोड कर सकते हैं[जावा डाउनलोड पेज के लिए Aspose.Page](https://releases.aspose.com/page/java/).
-  निर्दिष्ट फ़ोल्डर में आवश्यक फ़ॉन्ट उपलब्ध हैं. आप अतिरिक्त जानकारी इसमें पा सकते हैं[जावा दस्तावेज़ीकरण के लिए Aspose.Page](https://reference.aspose.com/page/java/).
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में, जावा के लिए Aspose.Page के लिए आवश्यक पैकेज आयात करें:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## चरण 1: दस्तावेज़ सेट करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// A4 आकार के साथ सेव विकल्प बनाएं
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// पीएस फ़ाइल में लिखने के लिए एक पाठ
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// नया 1-पृष्ठ वाला PS दस्तावेज़ बनाएँ
PsDocument document = new PsDocument(outPsStream, options, false);
```
## चरण 2: टेक्स्ट भरने के लिए सिस्टम फ़ॉन्ट का उपयोग करना
```java
// टेक्स्ट भरने के लिए सिस्टम फ़ॉन्ट का उपयोग करना
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// टेक्स्ट को डिफ़ॉल्ट या पहले से परिभाषित रंग (काला) से भरें
document.fillText(str, font, 50, 100);
// टेक्स्ट को नीले रंग से भरें
document.fillText(str, font, 50, 150, Color.BLUE);
```
## चरण 3: टेक्स्ट भरने के लिए कस्टम फ़ॉन्ट का उपयोग करना
```java
// टेक्स्ट भरने के लिए कस्टम फ़ॉन्ट का उपयोग करना
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// टेक्स्ट को डिफ़ॉल्ट या पहले से परिभाषित रंग (काला) से भरें
document.fillText(str, drFont, 50, 200);
// टेक्स्ट को नीले रंग से भरें
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## चरण 4: सिस्टम फॉन्ट के साथ टेक्स्ट की रूपरेखा तैयार करना
```java
// पाठ की रूपरेखा तैयार करने के लिए सिस्टम फ़ॉन्ट का उपयोग करना
document.outlineText(str, font, 50, 300);
// नीले-बैंगनी रंग के 2-बिंदु चौड़ाई वाले पेन से पाठ की रूपरेखा बनाएं
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// टेक्स्ट को नारंगी रंग से भरें और नीले रंग के 2-पॉइंट चौड़ाई वाले पेन से स्ट्रोक करें
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## चरण 5: कस्टम फ़ॉन्ट के साथ टेक्स्ट को रेखांकित करना
```java
// पाठ की रूपरेखा के लिए कस्टम फ़ॉन्ट का उपयोग करना
document.outlineText(str, drFont, 50, 450);
// नीले-बैंगनी रंग के 2-बिंदु चौड़ाई वाले पेन से पाठ की रूपरेखा बनाएं
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// टेक्स्ट को नारंगी रंग से भरें और नीले रंग के 2-पॉइंट चौड़ाई वाले पेन से स्ट्रोक करें
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## चरण 6: दस्तावेज़ सहेजें
```java
// वर्तमान पृष्ठ बंद करें
document.closePage();
// दस्तावेज़ सहेजें
document.save();
```
## निष्कर्ष
बधाई हो! आपने जावा के लिए Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट में टेक्स्ट जोड़ने का तरीका सफलतापूर्वक सीख लिया है। अपने दस्तावेज़ को और बेहतर बनाने के लिए विभिन्न फ़ॉन्ट, रंग और रूपरेखा विकल्पों के साथ प्रयोग करें।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं जावा के लिए Aspose.Page के साथ अपने स्वयं के कस्टम फ़ॉन्ट का उपयोग कर सकता हूँ?
 हां, आप फ़ॉन्ट नाम और आकार निर्दिष्ट करके कस्टम फ़ॉन्ट का उपयोग कर सकते हैं`DrFont` कक्षा।
### मैं टेक्स्ट का रंग कैसे बदल सकता हूँ?
 आप इसका उपयोग करके वांछित रंग सेट कर सकते हैं`Color` पाठ को भरते या रेखांकित करते समय कक्षा।
### क्या पोस्टस्क्रिप्ट दस्तावेज़ में एकाधिक पृष्ठ जोड़ना संभव है?
बिल्कुल! आप दस्तावेज़ निर्माण और सहेजने के चरणों को दोहराकर कई पेज बना सकते हैं।
###  का उद्देश्य क्या है`ExternalFontCache` class?
`ExternalFontCache` कस्टम फ़ॉन्ट लाने के लिए उपयोग किया जाता है, यह सुनिश्चित करते हुए कि वे टेक्स्ट हेरफेर के लिए उपलब्ध हैं।
### क्या मैं उल्लिखित पाठ पर अलग-अलग स्ट्रोक लगा सकता हूँ?
 हाँ, आप इसका उपयोग करके स्ट्रोक की चौड़ाई और रंग को अनुकूलित कर सकते हैं`Stroke` कक्षा और`Color` कक्षा, क्रमशः.