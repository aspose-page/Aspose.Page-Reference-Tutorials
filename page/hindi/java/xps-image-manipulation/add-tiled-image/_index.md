---
date: 2025-12-28
description: Aspose.Page का उपयोग करके जावा में XPS दस्तावेज़ बनाना सीखें और इस चरण‑दर‑चरण
  गाइड के साथ टाइल्ड इमेज को आसानी से जोड़ें।
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: जावा में टाइल्ड इमेज के साथ XPS दस्तावेज़ कैसे बनाएं
url: /hi/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS दस्तावेज़ बनाएं और जावा में टाइल्ड इमेज जोड़ें

## परिचय
आधुनिक जावा विकास में, **XPS दस्तावेज़** फ़ाइलों को प्रोग्रामेटिक रूप से बनाना एक मूल्यवान कौशल है, विशेषकर जब आपको उन्हें टाइल्ड इमेज जैसी ग्राफ़िक्स से समृद्ध करना हो। Aspose.Page for Java इस प्रक्रिया को सरल बनाता है, जिससे आप लो‑लेवल फ़ाइल हैंडलिंग के बजाय विज़ुअल डिज़ाइन पर ध्यान केंद्रित कर सकते हैं। इस ट्यूटोरियल में आप सीखेंगे कि कैसे XPS दस्तावेज़ बनाएं, **टाइल्ड इमेज जोड़ें**, और परिणाम को सहेजें, सभी स्पष्ट, चरण‑दर‑चरण कोड उदाहरणों के साथ।

## त्वरित उत्तर
- **Aspose.Page क्या करता है?** यह जावा में XPS दस्तावेज़ उत्पन्न करने और उन्हें नियंत्रित करने के लिए एक उच्च‑स्तरीय API प्रदान करता है।  
- **क्या मैं इमेज को टाइल कर सकता हूँ?** हाँ – `XpsImageBrush` को `XpsTileMode.Tile` के साथ उपयोग करें।  
- **क्या मुझे लाइसेंस चाहिए?** उत्पादन उपयोग के लिए एक अस्थायी या व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन सा जावा संस्करण समर्थित है?** कोई भी JDK 8+ संगत है।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बेसिक टाइल्ड‑इमेज परिदृश्य के लिए लगभग 10–15 मिनट।

## “XPS दस्तावेज़ बनाना” क्या है?
XPS (XML Paper Specification) फ़ाइल एक फिक्स्ड‑लेआउट दस्तावेज़ फ़ॉर्मेट है जो PDF के समान है। प्रोग्रामेटिक रूप से XPS दस्तावेज़ बनाना आपको जावा कोड से सीधे प्रिंटेबल, डिवाइस‑इंडिपेंडेंट फ़ाइलें उत्पन्न करने की सुविधा देता है।

## टाइल्ड इमेज क्यों जोड़ें?
इमेज को टाइल करने से ग्राफ़िक एक निर्धारित क्षेत्र में दोहराया जाता है, जो बैकग्राउंड, वॉटरमार्क या पैटर्न फ़िल्स के लिए आदर्श है। Aspose.Page के `XpsTileMode.Tile` का उपयोग करके आप यह कुछ ही लाइनों के कोड से हासिल कर सकते हैं।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

1. **Java Development Kit (JDK)** – JDK 8 या नया स्थापित हो।  
2. **Aspose.Page for Java** – [वेबसाइट](https://releases.aspose.com/page/java/) से डाउनलोड करें।  
3. **एक लिखने योग्य डायरेक्टरी** – जहाँ उत्पन्न XPS फ़ाइल सहेजी जाएगी।

## पैकेज आयात करें
अपने जावा प्रोजेक्ट में आवश्यक क्लासेस आयात करें:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## चरण‑दर‑चरण गाइड

### चरण 1: अपना प्रोजेक्ट सेट अप करें
Aspose.Page JAR फ़ाइलों को अपने प्रोजेक्ट की क्लासपाथ में जोड़ें और आयात स्टेटमेंट्स को बिना त्रुटि के कंपाइल होने की पुष्टि करें।

### चरण 2: XPS दस्तावेज़ बनाएं
एक नया `XpsDocument` ऑब्जेक्ट इंस्टैंशिएट करें। यह मुख्य कंटेनर है जो सभी पेज, पाथ और रिसोर्सेज़ को रखेगा।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### चरण 3: टाइल्ड इमेज पाथ निर्धारित करें
जिस इमेज को आप टाइल करना चाहते हैं (उदा., `R08LN_NN.jpg`) उसे `dataDir` द्वारा संदर्भित डायरेक्टरी में रखें। यह इमेज ब्रश पैटर्न के रूप में उपयोग होगी।

### चरण 4: टाइल्ड इमेज जोड़ें
एक आयताकार पाथ बनाएं और उसे `XpsImageBrush` से भरें। टाइल मोड को `Tile` सेट करने पर इमेज आयत के भीतर दोहराई जाएगी।

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### चरण 5: दस्तावेज़ सहेजें
XPS फ़ाइल को डिस्क पर स्थायी रूप से लिखें। आउटपुट फ़ाइल में वह टाइल्ड इमेज होगी जिसे आपने अभी परिभाषित किया है।

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

इन चरणों को तब दोहराएँ जब भी आपको समान XPS दस्तावेज़ के अन्य पेज या शैप्स में **टाइल्ड इमेज जोड़नी** हो।

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| इमेज नहीं दिख रही है | फ़ाइल पाथ (`dataDir + "R08LN_NN.jpg"`) सही है और इमेज एक्सेसिबल है, यह सुनिश्चित करें। |
| टाइल पैटर्न खिंचा हुआ दिख रहा है | टाइल आकार को नियंत्रित करने के लिए स्रोत और गंतव्य `Rectangle2D` मानों को समायोजित करें। |
| अपारदर्शिता प्रभाव नहीं डाल रही | टाइल मोड कॉन्फ़िगरेशन के **बाद** ब्रश की अपारदर्शिता सेट करें। |

## अक्सर पूछे जाने वाले प्रश्न

### क्या Aspose.Page सभी जावा संस्करणों के साथ संगत है?
Aspose.Page विभिन्न जावा संस्करणों के साथ काम करने के लिए डिज़ाइन किया गया है। संगतता के बारे में विवरण के लिए दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/page/java/) देखें।

### क्या मैं Aspose.Page को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?
हाँ, Aspose.Page व्यावसायिक लाइसेंस प्रदान करता है। इन्हें [यहाँ](https://purchase.aspose.com/buy) खरीदें।

### क्या कोई मुफ्त ट्रायल उपलब्ध है?
हाँ, आप Aspose.Page की सुविधाओं को एक मुफ्त ट्रायल के साथ [यहाँ](https://releases.aspose.com/) एक्सप्लोर कर सकते हैं।

### समुदाय समर्थन और चर्चा कहाँ मिल सकती है?
Aspose.Page समुदाय से जुड़ें [फ़ोरम](https://forum.aspose.com/c/page/39) पर।

### Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त करें?
अस्थायी लाइसेंस प्राप्त करने के लिए [यहाँ](https://purchase.aspose.com/temporary-license/) जाएँ।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2025-12-28  
**परीक्षित संस्करण:** Aspose.Page for Java 24.12 (नवीनतम)  
**लेखक:** Aspose  

---