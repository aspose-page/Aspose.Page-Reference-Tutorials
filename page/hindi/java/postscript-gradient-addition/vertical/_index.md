---
date: 2025-12-09
description: जावा में Aspose.Page का उपयोग करके PostScript ग्रेडिएंट बनाना सीखें।
  यह चरण‑दर‑चरण गाइड आपको दिखाता है कि कैसे आप अपने PostScript दस्तावेज़ों में आसानी
  से एक लंबवत ग्रेडिएंट जोड़ सकते हैं।
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: जावा में पोस्टस्क्रिप्ट ग्रेडिएंट बनाएं – वर्टिकल ग्रेडिएंट जोड़ें
url: /hi/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में PostScript ग्रेडिएंट बनाएं – वर्टिकल ग्रेडिएंट जोड़ें

## परिचय
इस व्यापक ट्यूटोरियल में, आप **जावा में PostScript ग्रेडिएंट बनाना** सीखेंगे, Aspose.Page for Java के साथ। वर्टिकल ग्रेडिएंट जोड़ने से आपके दस्तावेज़ अधिक जीवंत और पेशेवर दिखेंगे, और कुछ ही लाइनों के कोड से आप शानदार दृश्य प्रभाव प्राप्त कर सकते हैं। हम आपको प्रत्येक चरण के माध्यम से ले जाएंगे, समझाएंगे कि प्रत्येक भाग क्यों महत्वपूर्ण है, और सामान्य समस्याओं से बचने के लिए व्यावहारिक टिप्स देंगे।  
इस गाइड में हम **postscript gradient java** को चरण-दर-चरण बनाएँगे।

## त्वरित उत्तर
- **कौनसी लाइब्रेरी चाहिए?** Aspose.Page for Java  
- **क्या मैं रंग कस्टमाइज़ कर सकता हूँ?** हाँ, कोई भी `java.awt.Color` उपयोग किया जा सकता है  
- **क्या रोटेशन समर्थित है?** हाँ, आप `AffineTransform` के साथ ग्रेडिएंट को घुमा सकते हैं  
- **कौनसा आउटपुट फॉर्मेट बनता है?** एक मानक PostScript (.ps) फ़ाइल  
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** हाँ, एक व्यावसायिक लाइसेंस आवश्यक है  

## पूर्वापेक्षाएँ
ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हों:
- आपके मशीन पर Java Development Kit (JDK) स्थापित हो।  
- Aspose.Page for Java लाइब्रेरी। आप इसे [यहाँ](https://releases.aspose.com/page/java/) से डाउनलोड कर सकते हैं।

## पैकेज इम्पोर्ट करें
अपने Java प्रोजेक्ट में, आवश्यक पैकेज इम्पोर्ट करें ताकि आप शुरू कर सकें:
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

अब, चलिए जावा PostScript में वर्टिकल ग्रेडिएंट जोड़ने की प्रक्रिया को कई चरणों में विभाजित करते हैं।

## जावा में PostScript ग्रेडिएंट कैसे बनाएं
नीचे एक चरण‑दर‑चरण गाइड है जो दिखाता है कि **जावा में PostScript ग्रेडिएंट कैसे बनाएं** Aspose.Page API का उपयोग करके।

### चरण 1: अपने डॉक्यूमेंट डायरेक्टरी सेट करें
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### चरण 2: PostScript डॉक्यूमेंट के लिए आउटपुट स्ट्रीम बनाएं
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### चरण 3: A4 आकार के साथ सेव ऑप्शन बनाएं
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### चरण 4: नया PS डॉक्यूमेंट बनाएं
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### चरण 5: एक रेक्टैंगल बनाएं
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### चरण 6: ग्रेडिएंट के लिए रंग और फ्रैक्शन सेट करें
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### चरण 7: ग्रेडिएंट ट्रांसफ़ॉर्म बनाएं
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### चरण 8: वर्टिकल लीनियर ग्रेडिएंट पेंट बनाएं
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### चरण 9: पेंट सेट करें और रेक्टैंगल को फ़िल करें
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### चरण 10: वर्तमान पेज बंद करें और डॉक्यूमेंट सेव करें
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

बधाई हो! आपने Aspose.Page for Java का उपयोग करके अपने जावा PostScript डॉक्यूमेंट में सफलतापूर्वक वर्टिकल ग्रेडिएंट जोड़ दिया है।

## PostScript में वर्टिकल ग्रेडिएंट क्यों उपयोग करें?
वर्टिकल ग्रेडिएंट आपके पेजों को गहराई और दृश्य आकर्षण देते हैं, बिना फ़ाइल आकार को काफी बढ़ाए। ये विशेष रूप से उपयोगी होते हैं:
- रिपोर्ट हेडर और फुटर  
- चार्ट या डायग्राम के बैकग्राउंड फ़िल  
- तकनीकी दस्तावेज़ों में सेक्शन को हाइलाइट करने के लिए  

## सामान्य समस्याएँ और समाधान
- **ग्रेडिएंट सपाट दिख रहा है:** सुनिश्चित करें कि `AffineTransform` स्केलिंग रेक्टैंगल के आयामों से मेल खाती हो।  
- **रंग फीके दिख रहे हैं:** जांचें कि आप सही `ColorSpaceType` (SRGB) उपयोग कर रहे हैं और फ्रैक्शन एरे 0.0 से 1.0 तक क्रम में है।  
- **फ़ाइल जनरेट नहीं हो रही:** जाँचें कि आउटपुट डायरेक्टरी (`dataDir`) मौजूद है और एप्लिकेशन के पास लिखने की अनुमति है।  

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?
हां, Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ सहजता से काम करने के लिए डिज़ाइन किया गया है।

### क्या Aspose.Page for Java के लिए कोई फ्री ट्रायल उपलब्ध है?
हां, आप एक फ्री ट्रायल [यहाँ](https://releases.aspose.com/) प्राप्त कर सकते हैं।

### अतिरिक्त दस्तावेज़ीकरण कहाँ मिल सकता है?
विस्तृत दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/page/java/) उपलब्ध है।

### मैं Aspose.Page for Java कैसे खरीद सकता हूँ?
आप Aspose.Page for Java [यहाँ](https://purchase.aspose.com/buy) खरीद सकते हैं।

### Aspose.Page चर्चा के लिए कोई फोरम है?
हां, आप कम्युनिटी फोरम [यहाँ](https://forum.aspose.com/c/page/39) में शामिल हो सकते हैं।

## अतिरिक्त अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं अन्य ग्रेडिएंट दिशाएँ (हॉरिज़ॉन्टल, डायगोनल) बना सकता हूँ?**  
उत्तर: बिल्कुल। `LinearGradientPaint` में स्टार्ट और एंड पॉइंट्स को समायोजित करें और `AffineTransform` में रोटेशन एंगल बदलें।

**प्रश्न: क्या यह PDF आउटपुट के साथ भी काम करता है?**  
उत्तर: वही ग्रेडिएंट लॉजिक `PdfSaveOptions` का उपयोग करके PDF में सेव करने पर लागू किया जा सकता है, `PsSaveOptions` की जगह।

**प्रश्न: ग्रेडिएंट आकार को डायनामिक रूप से कैसे बदलूँ?**  
उत्तर: रनटाइम पर रेक्टैंगल के आयामों की गणना करें और उन मानों को `Rectangle2D` और `AffineTransform` कंस्ट्रक्टर दोनों में पास करें।

---

**अंतिम अपडेट:** 2025-12-09  
**टेस्टेड विथ:** Aspose.Page for Java 24.11 (latest)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}