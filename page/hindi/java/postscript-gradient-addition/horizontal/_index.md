---
date: 2025-12-07
description: Aspose.Page for Java के साथ Linear Gradient Paint Java का उपयोग करके
  Java PostScript में क्षैतिज ग्रेडिएंट कैसे जोड़ें, सीखें।
language: hi
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: जावा पोस्टस्क्रिप्ट में लीनियर ग्रेडिएंट पेंट का उपयोग करके ग्रेडिएंट जोड़ें
url: /java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा पोस्टस्क्रिप्ट में लीनियर ग्रेडिएंट पेंट जावा का उपयोग करके ग्रेडिएंट जोड़ें

## परिचय
इस व्यापक ट्यूटोरियल में आप सीखेंगे कि **Linear Gradient Paint Java** का उपयोग करके पोस्टस्क्रिप्ट दस्तावेज़ में एक सुंदर क्षैतिज ग्रेडिएंट कैसे बनाया जाए। Aspose.Page for Java पोस्टस्क्रिप्ट, PDF और अन्य वेक्टर फ़ॉर्मैट्स के साथ काम करना आसान बनाता है, और `LinearGradientPaint` क्लास आपको रंग परिवर्तन पर सूक्ष्म नियंत्रण देती है। इस गाइड के अंत तक, आप आकारों **और** टेक्स्ट पर ग्रेडिएंट रेंडर कर सकेंगे, जिससे आपके दस्तावेज़ पेशेवर और आकर्षक दिखेंगे।

## त्वरित उत्तर
- **क्या लाइब्रेरी आवश्यक है?** Aspose.Page for Java (Linear Gradient Paint Java का समर्थन करता है)।  
- **इम्प्लीमेंटेशन में कितना समय लगता है?** बेसिक ग्रेडिएंट के लिए लगभग 10‑15 मिनट।  
- **क्या मुझे लाइसेंस चाहिए?** प्रोडक्शन उपयोग के लिए एक टेम्पररी या फुल लाइसेंस आवश्यक है।  
- **कौन सा JDK संस्करण काम करता है?** Java 8 या नया।  
- **क्या मैं ग्रेडिएंट को आकारों और टेक्स्ट दोनों पर उपयोग कर सकता हूँ?** हाँ – आप आकारों को भर सकते हैं और उसी ग्रेडिएंट के साथ टेक्स्ट को स्ट्रोक या फ़िल कर सकते हैं।

## पूर्वापेक्षाएँ
कोड में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके मशीन पर Java Development Kit (JDK) स्थापित हो।  
- Aspose.Page for Java लाइब्रेरी। आप इसे [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) से डाउनलोड कर सकते हैं।

## पैकेज इम्पोर्ट करें
अपने जावा प्रोजेक्ट में आवश्यक पैकेज इम्पोर्ट करके शुरू करें। ये इम्पोर्ट्स आपको ग्राफ़िक्स प्रिमिटिव्स, ग्रेडिएंट हैंडलिंग और Aspose.Page API तक पहुँच देते हैं।

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
पहले, आउटपुट स्ट्रीम, डॉक्यूमेंट, और एक आयत सेट करें जो ग्रेडिएंट को होस्ट करेगा।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## चरण 2: क्षैतिज लीनियर ग्रेडिएंट पेंट बनाएं
यहाँ हम **Linear Gradient Paint Java** ऑब्जेक्ट बनाते हैं जो एक क्षैतिज रंग परिवर्तन को परिभाषित करता है। `AffineTransform` ग्रेडिएंट को आयत की चौड़ाई और ऊँचाई के अनुसार स्केल करता है।

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## चरण 3: आयत को भरें
अब हम अभी परिभाषित किए गए ग्रेडिएंट से आयत को भरते हैं।

```java
// Fill the rectangle
document.fill(rectangle);
```

## चरण 4: टेक्स्ट को ग्रेडिएंट से भरें
आप वही ग्रेडिएंट टेक्स्ट पर भी लागू कर सकते हैं, जिससे एक प्रभावशाली दृश्य प्रभाव बनता है।

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## चरण 5: टेक्स्ट को ग्रेडिएंट से स्ट्रोक करें
अंत में, ग्रेडिएंट को स्ट्रोक रंग के रूप में उपयोग करके टेक्स्ट की रूपरेखा बनाएं।

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|------|--------|
| ग्रेडिएंट खिंचा हुआ दिखता है | `AffineTransform` स्केलिंग गलत है | सुनिश्चित करें कि ट्रांसफ़ॉर्म की चौड़ाई और ऊँचाई आयत के आयामों (उदाहरण में 200 × 100) से मेल खाती हों। |
| रंग फीके दिखते हैं | अल्फा मान बहुत कम सेट किए गए हैं | अल्फा घटक बढ़ाएँ (`new Color(r,g,b,alpha)` में चौथा मान)। |
| टेक्स्ट दिखाई नहीं दे रहा है | टेक्स्ट ड्रॉ करने से पहले पेंट सेट नहीं किया गया | `document.setPaint(paint)` को किसी भी `fillAndStrokeText` या `outlineText` कॉल से **पहले** कॉल करें। |

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Page for Java को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?
हाँ, Aspose.Page for Java को व्यावसायिक प्रोजेक्ट्स में उपयोग किया जा सकता है। लाइसेंसिंग विवरण के लिए, देखें [Aspose.Purchase](https://purchase.aspose.com/buy)।

### क्या कोई फ्री ट्रायल उपलब्ध है?
हाँ, आप Aspose.Page for Java का फ्री ट्रायल [यहाँ](https://releases.aspose.com/) से प्राप्त कर सकते हैं।

### अतिरिक्त दस्तावेज़ीकरण और समर्थन कहाँ मिल सकता है?
व्यापक संसाधनों के लिए [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) देखें। समुदाय समर्थन के लिए, [Aspose.Page forum](https://forum.aspose.com/c/page/39) देखें।

### मैं टेम्पररी लाइसेंस कैसे प्राप्त कर सकता हूँ?
आप टेम्पररी लाइसेंस [Aspose.Purchase](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

### Aspose.Page for Java की सिस्टम आवश्यकताएँ क्या हैं?
विस्तृत सिस्टम आवश्यकताओं के लिए [documentation](https://reference.aspose.com/page/java/) देखें।

---

**अंतिम अपडेट:** 2025-12-07  
**परीक्षित संस्करण:** Aspose.Page for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}