---
date: 2025-12-25
description: जावा में Aspose.Page का उपयोग करके XPS दस्तावेज़ों में ग्रेडिएंट कैसे
  जोड़ें और शानदार क्षैतिज प्रभावों के लिए ग्रेडिएंट स्टॉप्स को कैसे कस्टमाइज़ करें,
  यह सीखें।
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: जावा XPS में ग्रेडिएंट कैसे जोड़ें – क्षैतिज ग्रेडिएंट
url: /hi/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS में ग्रेडिएंट – हॉरिजॉन्टल ग्रेडिएंट कैसे जोड़ें

## परिचय
इस स्टेप-दर-चरण गाइड में आपका स्वागत है, जहाँ आप **ग्रेडिएंट जोड़कर** XPS डॉक्यूमेंट में Java का इस्तेमाल करके सिखाते हैं। इस ट्यूटोरियल में आप सिखाते हैं कि ग्रेडिएंट कैसे जोड़ें, यह व्यू परिष्कार के लिए क्यों ज़रूरी है, और **ग्रेडिएंट स्टॉप्स** को सटीक रंग कंट्रोल के लिए कैसे **कस्टमाइज़** करें। Aspose.Page for Java XPS (XML Paper Specification) डॉक्यूमेंट्स के साथ काम करना आसान बनाता है, जिससे आप डिज़ाइन पर ध्यान केंद्रित कर सकते हैं न कि लो-लेवल फ़ाइल हैंडलिंग पर।

## क्विक आंसर्स
- **कौन सी लाइब्रेरी चाहिए?** Aspose.Page for Java
- **कौन सा Java एडिशन काम करता है?** कोई भी Java8+ रनटाइम
- **क्या लाइसेंस चाहिए?** डेवलपमेंट के लिए फ्री ट्रायल चलती है; प्रोडक्शन के लिए प्रोफेशनल लाइसेंस ज़रूरी है
- **क्या मैं ग्रेडिएंट की दिशा बदल सकता हूँ?** हाँ – केवल लीनियर ब्रश के शुरू/समाप्त बिंदुओं को बदलें
- **क्या कई ग्रेडिएंट जोड़ना मुमकिन है?** बिल्कुल – अलग-अलग ब्रश के साथ पथ निर्माण चरणों को दोहराएँ

## XPS में हॉरिजॉन्टल ग्रेडिएंट क्या है?

एक क्षैतिज ग्रेडिएंट का मतलब है रंगों का बाएँ से दाएँ तक स्मूथ ट्रांज़िशन किसी आकार के अंदर। XPS में इसे लीनियर ग्रेडिएंट ब्रश द्वारा दिखाया जाता है जो परिभाषित **ग्रेडिएंट स्टॉप्स** के बीच इंटरपोलेशन करता है। यह व्यू इफ़ेक्ट आमतौर पर बैनर, बटन और बैकग्राउंड फ़िल्स में इस्तेमाल किया जाता है।

## Java के लिए Aspose.Page का इस्तेमाल क्यों करें?
- **पूर्ण XPS सपोर्ट** – थर्ड-पार्टी टूल्स के बिना बनाएँ, एडिट करें और रेंडर करें।
- **सरल API** – `XpsDocument`, `XpsPath`, और `XpsGradientBrush` जैसे हाई-लेवल ऑब्जेक्ट्स XML एन्कोडिंग को छिपाते हैं।

- **प्रदर्शन** – बड़े डॉक्यूमेंट्स और बैच प्रोसेसिंग के लिए सेटअप।

## प्रीरिक्विजिट्स
शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

1. **Java Development Environment** – नवीनतम JDK को [java.com](https://www.java.com) से इंस्टॉल करें।
2. **Aspose.Page for Java Library** – JAR को [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) से डाउनलोड करें।

## पैकेज इंपोर्ट करें
आवश्यक क्लासेज़ को इम्पोर्ट करके शुरू करें। ये इम्पोर्ट्स आपको दस्तावेज़ निर्माण, ग्रेडिएंट हैंडलिंग और बेसिक जियोमेट्री तक पहुँच प्रदान करते हैं।

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## स्टेप 1: XPS डॉक्यूमेंट को इनिशियलाइज़ करें
एक नया `XpsDocument` इंस्टेंस बनाएँ और उस फ़ोल्डर को निर्दिष्ट करें जहाँ आप परिणाम सहेजना चाहते हैं।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## स्टेप 2: हॉरिजॉन्टल ग्रेडिएंट बनाएं
एक **ग्रेडिएंट स्टॉप्स** की सूची परिभाषित करें जो प्रत्येक ट्रांज़िशन पॉइंट के रंग और स्थिति को नियंत्रित करती है। नीचे दिया गया उदाहरण एक जीवंत इंद्रधनुष‑समान ग्रेडिएंट बनाता है।

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### ग्रेडिएंट स्टॉप को कस्टमाइज़ कैसे करें
- **Color** – किसी भी ARGB मान को सेट करने के लिए `doc.createColor(alpha, red, green, blue)` का उपयोग करें।  
- **Position** – दूसरा आर्गुमेंट (`0` और `1` के बीच `float`) निर्धारित करता है कि स्टॉप ग्रेडिएंट लाइन पर कहाँ दिखेगा। इन मानों को बदलकर रंगों को बाएँ या दाएँ शिफ्ट करें।

## स्टेप 3: ग्रेडिएंट के साथ पाथ जोड़ें
एक आयताकार पाथ बनाएँ, आवश्यकता अनुसार ट्रांसफ़ॉर्म लागू करें, और उसे लीनियर ग्रेडिएंट ब्रश से भरें। ब्रश दो बिंदुओं (`(10,0)` से `(228,0)`) का उपयोग करके क्षैतिज प्रभाव उत्पन्न करता है।

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Pro tip:** कई पाथ्स के लिए वही `stops` सूची पुन: उपयोग करने से प्रदर्शन बेहतर हो सकता है, लेकिन नई स्टॉप्स जोड़ने से पहले `clear()` करना न भूलें।

## स्टेप 4: डॉक्यूमेंट सेव करें
XPS फ़ाइल को डिस्क पर सहेजें। अब आप इसे किसी भी XPS व्यूअर में खोलकर क्षैतिज ग्रेडिएंट को देख सकते हैं।

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## आम दिक्कतें और समाधान
| दिक्कत | कारण | ठीक करें |
|-------|---------|-----|
| ग्रेडिएंट सॉलिड दिखता है | कोई ग्रेडिएंट स्टॉप नहीं जोड़ा गया है या ब्रश सेट नहीं है | पक्का करें कि `path.setFill(...)` `LinearGradientBrush` का इस्तेमाल करता है और स्टॉप `getGradientStops().addAll(stops)` के ज़रिए जोड़े गए हैं। |
| रंग फीके दिखते हैं | गलत अल्फ़ा वैल्यू (पहला पैरामीटर) | जब तक ट्रांसपेरेंसी न चाहिए, पूरी तरह से ओपेक रंगों के लिए `255` का इस्तेमाल करें। |
| पाथ साइज़ बंद है | ट्रांसफ़ॉर्म मैट्रिक्स वैल्यू गलत हैं | मैट्रिक्स पैरामीटर (`scaleX, skewY, skewX, scaleY, translateX, translateY`) को एडजस्ट करें। |

## अक्सर पूछे जाने वाले सवाल

**सवाल: क्या मैं एक ही XPS डॉक्यूमेंट में कई ग्रेडिएंट लगा सकता हूँ?**
जवाब: हाँ, आप कॉम्प्लेक्स लेयर्ड डिज़ाइन बनाने के लिए कई पाथ जोड़ सकते हैं, हर एक का अपना ग्रेडिएंट ब्रश हो।

**सवाल: क्या Aspose.Page लेटेस्ट Java वर्शन के साथ कम्पैटिबल है?**
जवाब: Java के लिए Aspose.Page रेगुलर अपडेट होता है और Java8 और नए रिलीज़ के साथ काम करता है।

**सवाल: क्या Aspose.Page में दूसरे ग्रेडिएंट टाइप भी उपलब्ध हैं?**
जवाब: लीनियर ग्रेडिएंट के अलावा, Aspose.Page सर्कुलर कलर ट्रांज़िशन के लिए रेडियल ग्रेडिएंट को भी सपोर्ट करता है।

**सवाल: क्या मैं ग्रेडिएंट स्टॉप के रंग और पोज़िशन को कस्टमाइज़ कर सकता हूँ?**
जवाब: बिल्कुल! हर स्टॉप के ARGB कलर और उसकी रिलेटिव पोज़िशन (0‑1 रेंज) पर आपका पूरा कंट्रोल होता है।

**सवाल: क्या Aspose.Page के लिए कोई कम्युनिटी फ़ोरम है जहाँ मैं मदद ले सकूँ?**
जवाब: हाँ, आप कम्युनिटी से जुड़ने और मदद पाने के लिए [Aspose.Page फ़ोरम](https://forum.aspose.com/c/page/39) पर जा सकते हैं।

---

**पिछला अपडेट:** 2025-12-25
**इसके साथ टेस्ट किया गया:** Aspose.Page for Java 24.11
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}