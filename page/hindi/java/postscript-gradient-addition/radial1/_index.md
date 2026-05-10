---
date: 2026-02-13
description: Aspose.Page for Java का उपयोग करके रेडियल कलर स्टॉप्स ग्रेडिएंट के साथ
  पोस्टस्क्रिप्ट ग्रेडिएंट बनाना सीखें। यह चरण‑दर‑चरण गाइड आपको आपके दस्तावेज़ों में
  कलर स्टॉप्स ग्रेडिएंट जोड़ना दिखाता है।
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: पोस्टस्क्रिप्ट ग्रेडिएंट बनाएं – जावा में रेडियल ग्रेडिएंट
url: /hi/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript में Radial Gradient कैसे जोड़ें Aspose.Page के साथ

## परिचय
यदि आपको कभी **PostScript ग्रेडिएंट** बनाना पड़ा हो जिसमें स्मूद, आकर्षक रंग परिवर्तन हो, तो रेडियल ग्रेडिएंट कैसे जोड़ें सीखना शुरू करने के लिए उत्तम जगह है। इस ट्यूटोरियल में हम प्रत्येक चरण को विस्तार से बताएँगे जिससे आप **Aspose.Page for Java** लाइब्रेरी का उपयोग करके एक सुंदर रेडियल ग्रेडिएंट वाला PostScript फ़ाइल बना सकें। अंत तक आप API को समझेंगे, एक पूर्ण चलाने योग्य उदाहरण देखेंगे, और किसी भी डिज़ाइन के अनुसार रंग, स्थिति और त्रिज्या को कैसे समायोजित करें, यह जानेंगे।

## त्वरित उत्तर
- **PostScript में रेडियल ग्रेडिएंट बनाने वाली लाइब्रेरी कौन सी है?** Aspose.Page for Java.  
- **इम्प्लीमेंटेशन में कितना समय लगता है?** बेसिक उदाहरण के लिए लगभग 10‑15 मिनट।  
- **कोड चलाने के लिए लाइसेंस चाहिए?** विकास के लिए फ्री ट्रायल चलती है; प्रोडक्शन के लिए कमर्शियल लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** Java 8 या उससे ऊपर।  
- **क्या मैं ग्रेडिएंट का आकार बदल सकता हूँ?** हाँ – `RadialGradientPaint` कन्स्ट्रक्टर में radius और center point को समायोजित करें।

## रेडियल फ़िल के साथ PostScript ग्रेडिएंट कैसे बनाएं
नीचे आपको एक संक्षिप्त, चरण‑दर‑चरण गाइड मिलेगा जो दिखाता है कि **PostScript ग्रेडिएंट** सामग्री को रेडियल फ़िल का उपयोग करके कैसे बनाएं। प्रत्येक चरण में एक छोटा विवरण और उसके बाद मूल कोड ब्लॉक (बिना बदलाव) शामिल है।

## रेडियल ग्रेडिएंट क्या है?
रेडियल ग्रेडिएंट वह रंग पेंट करता है जो केंद्र बिंदु से बाहर की ओर फैलते हैं, धीरे‑धीरे किनारों की ओर मिलते हैं। लीनियर ग्रेडिएंट के विपरीत, रंग परिवर्तन एक वृत्तीय (या दीर्घवृत्तीय) पैटर्न का अनुसरण करता है, जो हाइलाइट्स, स्पॉटलाइट्स, या सॉफ्ट बैकग्राउंड फ़िल के लिए आदर्श है।

## रेडियल ग्रेडिएंट के लिए Aspose.Page क्यों उपयोग करें?
- **PostScript आउटपुट पर पूर्ण नियंत्रण** – लो‑लेवल PS कमांड्स को हाथ से लिखने की जरूरत नहीं।  
- **क्रॉस‑प्लेटफ़ॉर्म** – वह सभी OS पर काम करता है जो Java चलाते हैं।  
- **समृद्ध रंग प्रबंधन** – कई रंग स्टॉप्स, विभिन्न कलर स्पेसेस, और साइक्ल मेथड्स को सपोर्ट करता है।  
- **इंटीग्रेशन‑रेडी** – टेक्स्ट, इमेज, और वेक्टर शैप्स जैसे अन्य Aspose.Page फीचर्स के साथ संयोजित करें।

## पूर्वापेक्षाएँ
कोड में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित तैयार हैं:

- **Java Development Kit (JDK) 8+** – `java -version` से सत्यापित करें।  
- **Aspose.Page for Java** – आधिकारिक [Aspose.Page डाउनलोड पेज](https://releases.aspose.com/page/java/) से नवीनतम JAR डाउनलोड करें।  
- **आपकी पसंद का IDE** – Eclipse, IntelliJ IDEA, या Java एक्सटेंशन वाले VS Code।  
- **एक लिखने योग्य फ़ोल्डर** – जहाँ उत्पन्न `.ps` फ़ाइल सहेजी जाएगी।

## पैकेज इम्पोर्ट करें
सबसे पहले, उन क्लासेज़ को इम्पोर्ट करें जिनकी हमें आवश्यकता होगी। `java.awt` पैकेज ग्रेडिएंट पेंट ऑब्जेक्ट्स प्रदान करता है, जबकि `com.aspose.eps` में PostScript डॉक्यूमेंट हैंडलिंग क्लासेज़ होते हैं।

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## चरण‑दर‑चरण गाइड

### चरण 1: एक Rectangle बनाएं और PS डॉक्यूमेंट खोलें
हम आउटपुट स्ट्रीम बनाकर, पेज साइज (डिफ़ॉल्ट रूप से A4) कॉन्फ़िगर करके, और एक rectangle परिभाषित करके शुरू करते हैं जो ग्रेडिएंट को होस्ट करेगा।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **प्रो टिप:** rectangle के निर्देशांक (`200, 100, 200, 200`) को समायोजित करके ग्रेडिएंट को पेज पर कहीं भी रख सकते हैं।

### चरण 2: रंग और फ्रैक्शन परिभाषित करें
रेडियल ग्रेडिएंट *color stops* (रंग) और *fractions* (उन स्टॉप्स की सापेक्ष स्थितियों) से बनता है। यहाँ हम छह रंगों और उनके संबंधित फ्रैक्शन की एक एरे बनाते हैं।

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **यह क्यों महत्वपूर्ण है:** `fractions` को बदलकर आप नियंत्रित कर सकते हैं कि रंग कितनी जल्दी ट्रांज़िशन करें, जिससे सूक्ष्म या नाटकीय प्रभाव मिलते हैं।

### रेडियल फ़िल में कलर स्टॉप्स ग्रेडिएंट जोड़ना
जब आपको **color stops gradient** जोड़ने की जरूरत हो, तो `colors` और `fractions` एरे मुख्य होते हैं। आप अपनी विज़ुअल डिज़ाइन के अनुसार एंट्रीज़ को पुनः क्रमित, जोड़ या हटाने के लिए स्वतंत्र हैं।

### चरण 3: Radial Gradient Paint बनाएं
अब हम `RadialGradientPaint` ऑब्जेक्ट बनाते हैं। कन्स्ट्रक्टर में ग्रेडिएंट का केंद्र बिंदु, radius, फोकस पॉइंट, fractions, colors, cycle method, color space, और एक वैकल्पिक transform लिया जाता है।

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **नोट:** यदि आपको अतिरिक्त स्केलिंग या रोटेशन की जरूरत नहीं है तो `transform` को `null` रखा जा सकता है। स्क्यूड ग्रेडिएंट के लिए `AffineTransform` के साथ प्रयोग करने के लिए स्वतंत्र हैं।

### चरण 4: पेंट सेट करें और Rectangle को Fill करें
पेंट तैयार होने पर, हम `PsDocument` को इसे उपयोग करने के लिए बताते हैं और फिर पहले परिभाषित rectangle को fill करते हैं।

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

इस बिंदु पर PostScript पेज में एक rectangle है जो हमने कॉन्फ़िगर किए गए रेडियल ग्रेडिएंट से स्मूदली भर गया है।

### चरण 5: डॉक्यूमेंट को बंद करें और सेव करें
अंत में, वर्तमान पेज को बंद करें और फ़ाइल को डिस्क पर लिखें।

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

`RadialGradient1_outPS.ps` को किसी भी PostScript व्यूअर (जैसे Ghostscript) में खोलें और आप देखेंगे कि ग्रेडिएंट ठीक उसी तरह रेंडर हुआ है जैसा परिभाषित किया गया था।

## सामान्य समस्याएँ और समाधान
| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| ग्रेडिएंट एक सॉलिड रंग जैसा दिखता है | `fractions` एरे `0.0f` से शुरू नहीं होता या `1.0f` पर समाप्त नहीं होता | पहला फ्रैक्शन `0.0f` और अंतिम फ्रैक्शन `1.0f` होना सुनिश्चित करें। |
| रंग फीके दिखते हैं | `ColorSpaceType` गलत उपयोग किया गया | अधिक जीवंत आउटपुट के लिए `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` पर स्विच करें। |
| कोई आउटपुट फ़ाइल उत्पन्न नहीं हुई | `FileOutputStream` पाथ अमान्य है या लिखने योग्य नहीं है | `dataDir` मौजूद है और एप्लिकेशन को लिखने की अनुमति है, यह सत्यापित करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Page for Java को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?**  
उत्तर: हाँ। प्रोडक्शन उपयोग के लिए एक कमर्शियल लाइसेंस आवश्यक है। आप इसे [Aspose लाइसेंसिंग पेज](https://purchase.aspose.com/buy) से खरीद सकते हैं।

**प्रश्न: आधिकारिक API रेफ़रेंस कहाँ मिल सकता है?**  
उत्तर: पूरी डाक्यूमेंटेशन [यहाँ](https://reference.aspose.com/page/java/) उपलब्ध है।

**प्रश्न: क्या परीक्षण के लिए फ्री ट्रायल उपलब्ध है?**  
उत्तर: बिल्कुल। आप ट्रायल संस्करण [Aspose.Page रिलीज़ पेज](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

**प्रश्न: मूल्यांकन के लिए अस्थायी लाइसेंस कैसे प्राप्त करें?**  
उत्तर: एक अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) से अनुरोध किया जा सकता है।

**प्रश्न: समुदाय समर्थन कहाँ मिल सकता है?**  
उत्तर: Aspose.Page कम्युनिटी फ़ोरम पर जुड़ें: [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39)।

## निष्कर्ष
अब आप जानते हैं कि **Aspose.Page** का उपयोग करके Java PostScript डॉक्यूमेंट में रेडियल ग्रेडिएंट कैसे जोड़ें। rectangle का आकार, रंग स्टॉप्स, और ग्रेडिएंट की त्रिज्या को समायोजित करके आप अनगिनत विज़ुअल इफ़ेक्ट बना सकते हैं—सूक्ष्म बैकग्राउंड फ़िल से लेकर बोल्ड स्पॉटलाइट ग्राफ़िक्स तक। विभिन्न `AffineTransform` मानों के साथ प्रयोग करने के लिए स्वतंत्र रहें ताकि ग्रेडिएंट को घुमा या स्क्यू किया जा सके, और इस तकनीक को टेक्स्ट और इमेज के साथ मिलाकर अधिक समृद्ध PDF या EPS आउटपुट प्राप्त करें।

---

**अंतिम अपडेट:** 2026-02-13  
**परीक्षित संस्करण:** Aspose.Page for Java latest (as of writing)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}