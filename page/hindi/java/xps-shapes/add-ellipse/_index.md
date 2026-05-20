---
date: 2026-04-24
description: जानेँ कि कैसे जावा में रेडियल ग्रेडिएंट एलिप्स के साथ XPS दस्तावेज़ बनाएं।
  यह चरण‑दर‑चरण गाइड दिखाता है कि Aspose.Page का उपयोग करके स्ट्रोक की मोटाई कैसे
  सेट करें और पाथ जियोमेट्री को कैसे परिभाषित करें।
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: जावा XPS में एलिप्स जोड़ें
second_title: Aspose.Page Java API
title: XPS दस्तावेज़ जावा बनाएं – रेडियल ग्रेडिएंट एलिप्स जोड़ें
url: /hi/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# रैडियल ग्रेडिएंट एलिप्स जोड़ें Aspose.Page के साथ

## परिचय
इस ट्यूटोरियल में, आप **create XPS document Java** को Aspose.Page for Java का उपयोग करके एक सुंदर रैडियल ग्रेडिएंट स्ट्रोक वाले एलिप्स के साथ बनाने के बारे में सीखेंगे। Aspose.Page एक मजबूत लाइब्रेरी है जो लो‑लेवल XPS विवरणों को एब्स्ट्रैक्ट करती है, जिससे आप फ़ाइल फ़ॉर्मेट की जटिलताओं के बजाय डिज़ाइन पर ध्यान केंद्रित कर सकते हैं। इस गाइड के अंत तक आपके पास एक तैयार‑to‑use XPS फ़ाइल होगी जिसे आप रिपोर्ट, इनवॉइस या किसी भी दस्तावेज़‑जनरेशन वर्कफ़्लो में एम्बेड कर सकते हैं।

## त्वरित उत्तर
- **यह कोड क्या उत्पन्न करता है?** एकल‑पृष्ठ XPS फ़ाइल जिसमें बहु‑रंग रैडियल ग्रेडिएंट के साथ स्ट्रोक किया गया एलिप्स शामिल है।  
- **कौन सा मुख्य API उपयोग किया गया है?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, आदि)।  
- **क्या मुझे नमूना चलाने के लिए लाइसेंस चाहिए?** एक अस्थायी लाइसेंस मूल्यांकन के लिए काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **हम कौन सी मुख्य गुण सेट करते हैं?** स्ट्रोक ब्रश (रैडियल ग्रेडिएंट), स्प्रेड मेथड, ग्रेडिएंट स्टॉप्स, और स्ट्रोक मोटाई।  
- **क्या मैं एलिप्स का आकार बदल सकता हूँ?** हाँ – पाथ जियोमेट्री स्ट्रिंग या ग्रेडिएंट ब्रश निर्देशांक को संशोधित करें।

## “create XPS document Java” क्या है?
Java में XPS दस्तावेज़ बनाना मतलब प्रोग्रामेटिक रूप से XML Paper Specification (XPS) फ़ाइल—एक फिक्स्ड‑लेआउट दस्तावेज़ फ़ॉर्मेट जो PDF के समान है—को सीधे Java कोड से जनरेट करना। Aspose.Page एक हाई‑लेवल ऑब्जेक्ट मॉडल (`XpsDocument`, `XpsCanvas`, आदि) प्रदान करता है जो XML मार्कअप को एब्स्ट्रैक्ट करता है, जिससे प्रक्रिया मानक Java ऑब्जेक्ट्स के साथ काम करने जितनी सरल हो जाती है।

## रैडियल ग्रेडिएंट एलिप्स का उपयोग क्यों करें?
रैडियल ग्रेडिएंट एक त्रि‑आयामी एहसास देता है, जो रिपोर्ट में विज़ुअल हाइलाइट्स, लोगो या सजावटी तत्वों के लिए उपयुक्त है। सॉलिड‑कलर स्ट्रोक की तुलना में, ग्रेडिएंट गहराई जोड़ता है बिना फ़ाइल आकार को काफी बढ़ाए, और XPS फ़ॉर्मेट किसी भी स्केलिंग के लिए वेक्टर क्वालिटी को संरक्षित रखता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- आपके मशीन पर Java Development Kit (JDK) स्थापित हो।  
- Aspose.Page for Java लाइब्रेरी डाउनलोड की गई। आप इसे [यहाँ](https://releases.aspose.com/page/java/) प्राप्त कर सकते हैं।  
- आपकी पसंद का कोड एडिटर (Eclipse, IntelliJ, आदि) Java कोड लिखने और चलाने के लिए।

## पैकेज आयात करें
Aspose.Page का उपयोग करने के लिए सुनिश्चित करें कि आपके Java प्रोजेक्ट में आवश्यक पैकेज आयात किए गए हैं। अपने Java फ़ाइल के शीर्ष पर निम्नलिखित इम्पोर्ट स्टेटमेंट जोड़ें:

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
उस पाथ को परिभाषित करें जहाँ XPS दस्तावेज़ सहेजा जाएगा:

```java
String dataDir = "Your Document Directory";
```

## चरण 2: XPS दस्तावेज़ बनाएं
निम्नलिखित कोड का उपयोग करके एक नया XPS दस्तावेज़ इनिशियलाइज़ करें:

```java
XpsDocument doc = new XpsDocument();
```

## चरण 3: रैडियल ग्रेडिएंट स्टॉप्स परिभाषित करें
रैडियल ग्रेडिएंट स्ट्रोक वाले एलिप्स के लिए ग्रेडिएंट स्टॉप्स की सूची बनाएं:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## चरण 4: पाथ जियोमेट्री बनाएं
पाथ जियोमेट्री का उपयोग करके रैडियल ग्रेडिएंट स्ट्रोक वाला एलिप्स परिभाषित करें:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## चरण 5: कैनवास और पाथ जोड़ें
दस्तावेज़ में एक नया कैनवास जोड़ें और परिभाषित जियोमेट्री के साथ पाथ को अपेंड करें:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## चरण 6: स्ट्रोक और ग्रेडिएंट सेट करें
रैडियल ग्रेडिएंट ब्रश के साथ पाथ का स्ट्रोक कॉन्फ़िगर करें:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## चरण 7: स्ट्रोक मोटाई सेट करें
पाथ की **set stroke thickness** निर्दिष्ट करें:

```java
path.setStrokeThickness(12f);
```

## चरण 8: दस्तावेज़ सहेजें
परिणामी XPS दस्तावेज़ सहेजें:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

बधाई हो! आपने Aspose.Page के साथ **create XPS document Java** बनाते हुए सफलतापूर्वक रैडियल ग्रेडिएंट स्ट्रोक वाला एलिप्स जोड़ दिया है।

## सामान्य समस्याएँ और समाधान
| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| **एलिप्स सपाट दिखता है** | `XpsSpreadMethod.Pad` का उपयोग `Reflect` के बजाय किया गया है। | `XpsSpreadMethod.Reflect` में स्प्रेड मेथड बदलें जैसा कि चरण 6 में दिखाया गया है। |
| **कोई आउटपुट फ़ाइल नहीं** | `dataDir` एक गैर‑मौजूद फ़ोल्डर की ओर इशारा करता है। | सुनिश्चित करें कि निर्देशिका मौजूद है या पूर्ण पथ (absolute path) का उपयोग करें। |
| **ग्रेडिएंट रंग गलत दिख रहे हैं** | ग्रेडिएंट स्टॉप्स का क्रम गलत है। | `offset` मानों (0 → 1) को क्रमबद्ध रूप से बढ़ते हुए जांचें। |
| **संकलन त्रुटियाँ** | क्लासपाथ पर Aspose.Page JAR फ़ाइलें अनुपलब्ध हैं। | अपने प्रोजेक्ट निर्भरताओं में `aspose-page-xx.jar` जोड़ें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ सहजता से एकीकृत किया जा सकता है।

**Q: क्या Aspose.Page बड़े‑पैमाने पर दस्तावेज़ प्रोसेसिंग के लिए उपयुक्त है?**  
A: बिल्कुल! Aspose.Page को बड़े‑पैमाने पर दस्तावेज़ प्रोसेसिंग को कुशलता से संभालने के लिए डिज़ाइन किया गया है।

**Q: मैं Aspose.Page for Java के लिए अधिक ट्यूटोरियल और उदाहरण कहाँ पा सकता हूँ?**  
A: व्यापक ट्यूटोरियल और उदाहरणों के लिए [Aspose.Page for Java दस्तावेज़ीकरण](https://reference.aspose.com/page/java/) देखें।

**Q: मैं Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?**  
A: आप एक अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) प्राप्त कर सकते हैं।

**Q: क्या Aspose.Page चर्चा के लिए कोई समुदाय फ़ोरम हैं?**  
A: हाँ, अन्य डेवलपर्स के साथ जुड़ने और सहायता प्राप्त करने के लिए [Aspose.Page समुदाय फ़ोरम](https://forum.aspose.com/c/page/39) में शामिल हों।

---

**अंतिम अपडेट:** 2026-04-24  
**परीक्षित संस्करण:** Aspose.Page for Java 24.11 (लेखन समय पर नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}