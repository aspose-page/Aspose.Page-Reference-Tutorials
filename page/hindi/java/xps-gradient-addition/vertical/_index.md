---
date: 2025-12-25
description: Aspose.Page का उपयोग करके Java XPS में वर्टिकल ग्रेडिएंट कैसे जोड़ें,
  सीखें। अपने दस्तावेज़ की दृश्य आकर्षण को बढ़ाने के लिए इस चरण‑दर‑चरण गाइड का पालन
  करें।
linktitle: How to Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
title: जावा XPS में वर्टिकल ग्रेडिएंट कैसे जोड़ें
url: /hi/java/xps-gradient-addition/vertical/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS में वर्टिकल ग्रेडिएंट कैसे जोड़ें

## परिचय
इस ट्यूटोरियल में आप Java के साथ काम करते समय XPS दस्तावेज़ों में **वर्टिकल ग्रेडिएंट कैसे जोड़ें** जानेंगे। वर्टिकल ग्रेडिएंट लागू करने से आपके रिपोर्ट, इनवॉइस या किसी भी प्रिंटेबल कंटेंट की दृश्य प्रभावशीलता में काफी सुधार हो सकता है। हम प्रत्येक चरण को विस्तार से बताएँगे, प्रोजेक्ट सेटअप से लेकर अंतिम XPS फ़ाइल को सहेजने तक, शक्तिशाली Aspose.Page for Java लाइब्रेरी का उपयोग करके।

## त्वरित उत्तर
- **वर्टिकल ग्रेडिएंट क्या करता है?** यह किसी आकार के शीर्ष से नीचे तक एक सुगम रंग परिवर्तन बनाता है।  
- **कौनसी लाइब्रेरी आवश्यक है?** Aspose.Page for Java (आधिकारिक साइट से डाउनलोड किया जा सकता है)।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या यह Java 8+ के साथ संगत है?** हाँ, API Java 8 और बाद के संस्करणों को सपोर्ट करता है।  
- **इम्प्लीमेंटेशन में कितना समय लगता है?** पर्यावरण सेटअप हो जाने के बाद आमतौर पर 10 मिनट से कम।

## पूर्वापेक्षाएँ
कोड में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- एक कार्यशील Java विकास पर्यावरण (JDK 8 या नया)।  
- Aspose.Page for Java लाइब्रेरी। आप इसे [here](https://releases.aspose.com/page/java/) से डाउनलोड कर सकते हैं।  
- Java प्रोग्रामिंग अवधारणाओं की बुनियादी समझ।  

## पैकेज आयात करें
अपने Java प्रोजेक्ट के लिए आवश्यक पैकेज आयात करके शुरू करें। सुनिश्चित करें कि Aspose.Page for Java लाइब्रेरी आपके प्रोजेक्ट के क्लासपाथ में जोड़ी गई है।

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```

## चरण 1: दस्तावेज़ को इनिशियलाइज़ करें
एक नया XPS दस्तावेज़ बनाकर शुरू करें। यह ऑब्जेक्ट बाद में आप जो भी ड्रॉइंग एलिमेंट्स जोड़ेंगे, उन्हें रखेगा।

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

## चरण 2: वर्टिकल ग्रेडिएंट के साथ एक पाथ बनाएं
अगले चरण में, एक आयताकार पाथ परिभाषित करें और उस पर वर्टिकल लीनियर ग्रेडिएंट लागू करें। ग्रेडिएंट स्टॉप्स रंगों और उनके वर्टिकल अक्ष पर स्थितियों को निर्धारित करते हैं।

```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## चरण 3: दस्तावेज़ को सहेजें
अंत में, XPS फ़ाइल को डिस्क पर लिखें। परिणामी फ़ाइल में वह आयताकार होगा जो आपने परिभाषित वर्टिकल ग्रेडिएंट से भरा होगा।

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

बधाई हो! आपने Aspose.Page का उपयोग करके Java XPS दस्तावेज़ में **वर्टिकल ग्रेडिएंट कैसे जोड़ें** सफलतापूर्वक सीख लिया है।

## वर्टिकल ग्रेडिएंट क्यों उपयोग करें?
- **बेहतर सौंदर्यशास्त्र:** ग्रेडिएंट स्थिर आकारों में गहराई और आधुनिक लुक जोड़ते हैं।  
- **ब्रांड स्थिरता:** पृष्ठों में कॉर्पोरेट रंगों को सुगमता से मिलाएं।  
- **आसान कस्टमाइज़ेशन:** ग्राफ़िक्स को पुनः डिज़ाइन किए बिना रंग या स्टॉप पोज़िशन बदलें।

## सामान्य समस्याएँ और ट्रबलशूटिंग
- **ग्रेडिएंट दिखाई नहीं रहा:** सुनिश्चित करें कि `LinearGradientBrush` के प्रारंभ और अंत बिंदु वर्टिकल अभिविन्यास के लिए सही ढंग से सेट हैं।  
- **फ़ाइल सहेजी नहीं गई:** सुनिश्चित करें कि `dataDir` लिखने योग्य फ़ोल्डर की ओर इशारा कर रहा है और आपके पास फ़ाइलें लिखने की अनुमति है।  
- **लाइब्रेरी नहीं मिली:** दोबारा जांचें कि Aspose.Page JAR आपके प्रोजेक्ट के बिल्ड पाथ में शामिल है।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Page for Java को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?**  
उत्तर: हाँ, Aspose.Page for Java व्यावसायिक उपयोग के लिए उपलब्ध है। आप इसे [here](https://purchase.aspose.com/buy) से खरीद सकते हैं।

**प्रश्न: क्या Aspose.Page for Java के लिए कोई मुफ्त ट्रायल उपलब्ध है?**  
उत्तर: हाँ, आप मुफ्त ट्रायल [here](https://releases.aspose.com/) से प्राप्त कर सकते हैं।

**प्रश्न: Aspose.Page for Java की दस्तावेज़ीकरण कहाँ मिल सकती है?**  
उत्तर: दस्तावेज़ीकरण [here](https://reference.aspose.com/page/java/) पर उपलब्ध है।

**प्रश्न: Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
उत्तर: अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त करें।

**प्रश्न: सहायता चाहिए या कोई प्रश्न हैं?**  
उत्तर: Aspose.Page समुदाय के [forum](https://forum.aspose.com/c/page/39) पर जाएँ।

---

**अंतिम अपडेट:** 2025-12-25  
**परीक्षण किया गया:** Aspose.Page for Java 24.12 (लेखन के समय नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}