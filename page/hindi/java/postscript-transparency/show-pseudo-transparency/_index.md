---
date: 2025-12-17
description: Aspose.Page का उपयोग करके जावा में स्यूडो ट्रांसपेरेंसी बनाना सीखें।
  पोस्टस्क्रिप्ट फ़ाइलों में जीवंत ग्राफ़िक्स जोड़ने के लिए हमारे चरण‑दर‑चरण गाइड
  का पालन करें।
linktitle: Show Pseudo-Transparency in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page के साथ जावा में स्यूडो ट्रांसपेरेंसी कैसे बनाएं
url: /hi/java/postscript-transparency/show-pseudo-transparency/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ Java PostScript छद्म-पारदर्शिता

## परिचय
इस व्यापक ट्यूटोरियल में आप **छद्म पारदर्शी जावा** ग्राफ़िक्स Aspose.Page for Java के साथ बनाएँगे। हम पर्यावरण सेटअप से लेकर दो ओवरलैपिंग आयतों को रेंडर करने तक के हर चरण को कवर करेंगे, जिससे PostScript फ़ाइल में पारदर्शिता का भ्रम उत्पन्न होगा। अंत तक, आप समझ जाएंगे कि छद्म‑पारदर्शिता क्यों उपयोगी है, इसे कैसे लागू किया जाता है, और अपने डिज़ाइनों के लिए पैरामीटर कैसे समायोजित किए जा सकते हैं।

## त्वरित उत्तर
- **छद्म‑पारदर्शिता का क्या अर्थ है?** यह अर्ध‑पारदर्शी ग्रेडिएंट को मिलाकर पारदर्शिता का अनुकरण करता है।
- **कौन‑सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java।
- **क्या उदाहरण चलाने के लिए लाइसेंस चाहिए?** विकास के लिए मुफ्त ट्रायल चलती है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है।
- **मैं कौन‑सा IDE उपयोग कर सकता हूँ?** कोई भी Java IDE (IntelliJ IDEA, Eclipse, VS Code) जो Java 8+ को सपोर्ट करता हो।
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बेसिक उदाहरण के लिए लगभग 10‑15 मिनट।

## Java PostScript में छद्म पारदर्शिता क्या है?
छद्म पारदर्शिता एक तकनीक है जो अर्ध‑पारदर्शी ग्रेडिएंट फ़िल्स का उपयोग करके वस्तुओं को देख‑सकने वाला प्रभाव देती है। चूँकि पारंपरिक PostScript वास्तविक अल्फा चैनल को सपोर्ट नहीं करता, Aspose.Page इसे ट्रांसलूसेंट आकारों को लेयर करके अनुकरण करता है।

## Aspose.Page को छद्म पारदर्शिता के लिए क्यों चुनें?
- **क्रॉस‑प्लेटफ़ॉर्म** – किसी भी OS पर वैध PostScript उत्पन्न करता है।
- **कोई बाहरी निर्भरताएँ नहीं** – शुद्ध Java API।
- **सूक्ष्म नियंत्रण** – रंग, अपारदर्शिता, और ग्रेडिएंट दिशा को प्रोग्रामेटिकली समायोजित करें।
- **सुसंगत आउटपुट** – प्रिंटर और व्यूअर्स में समान रूप से काम करता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास है:
- Java का बुनियादी ज्ञान।
- PostScript अवधारणाओं की परिचितता।
- Aspose.Page for Java लाइब्रेरी स्थापित। यदि अभी तक डाउनलोड नहीं किया है, तो इसे **[यहाँ](https://releases.aspose.com/page/java/)** प्राप्त करें।
- एक Java IDE या बिल्ड टूल (Maven/Gradle) तैयार।

## पैकेज आयात करें
रंग, ग्रेडिएंट, और PostScript दस्तावेज़ ऑब्जेक्ट के साथ काम करने के लिए आवश्यक क्लासेज़ को आयात करें।

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

## चरण 1: एक PS दस्तावेज़ बनाएँ
पहले, हम एक आउटपुट स्ट्रीम बनाते हैं और नया `PsDocument` प्रारंभ करते हैं। यह वह कैनवास सेट करता है जहाँ हम अपने आकारों को ड्रॉ करेंगे।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "ShowPseudoTransparency_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## चरण 2: अपारदर्शी ग्रेडिएंट फ़िल के साथ आयत परिभाषित करें
हम पहली आयत को पूरी तरह अपारदर्शी ग्रेडिएंट के साथ ड्रॉ करते हैं। यह हमारे छद्म‑पारदर्शी ओवरले के लिए पृष्ठभूमि के रूप में कार्य करेगा।

```java
float offsetX = 50;
float offsetY = 100;
float width = 200;
float height = 100;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create opaque gradient fill
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0), new Color(40, 128, 70)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## चरण 3: ट्रांसलूसेंट ग्रेडिएंट फ़िल के साथ आयत परिभाषित करें
अब हम दूसरी आयत रखते हैं जो अल्फा मानों के साथ ग्रेडिएंट का उपयोग करती है। यह पहली आकृति के ऊपर ओवरलैप होने पर **छद्म पारदर्शिता** प्रभाव उत्पन्न करती है।

```java
offsetX = 350;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create translucent gradient fill
paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## चरण 4: पृष्ठ बंद करें और दस्तावेज़ सहेजें
अंत में, हम वर्तमान पृष्ठ को बंद करते हैं और PostScript फ़ाइल को डिस्क पर लिखते हैं।

```java
document.closePage();
document.save();
```

## सामान्य समस्याएँ एवं ट्रबलशूटिंग
- **FileNotFoundException** – सुनिश्चित करें कि `dataDir` किसी मौजूदा फ़ोल्डर की ओर इशारा कर रहा है और आपके एप्लिकेशन को लिखने की अनुमति है।
- **गलत रंग** – ट्रांसलूसेंट रंगों के लिए `Color(int r, int g, int b, int a)` कंस्ट्रक्टर का उपयोग करें; चौथा पैरामीटर अल्फा (0‑255) है।
- **ग्रेडिएंट दिखाई नहीं दे रहा** – जाँचें कि `AffineTransform` पैरामीटर ग्रेडिएंट को आयत के आयामों के साथ सही ढंग से मैप कर रहे हैं।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Page for Java को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?
हाँ, Aspose.Page for Java व्यावसायिक उपयोग के लिए उपलब्ध है। आप लाइसेंस **[यहाँ](https://purchase.aspose.com/buy)** खरीद सकते हैं।

### क्या मुफ्त ट्रायल उपलब्ध है?
हाँ, आप मुफ्त ट्रायल **[यहाँ](https://releases.aspose.com/)** प्राप्त कर सकते हैं।

### अतिरिक्त दस्तावेज़ीकरण कहाँ मिल सकता है?
विस्तृत दस्तावेज़ीकरण **[यहाँ](https://reference.aspose.com/page/java/)** उपलब्ध है।

### परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस कैसे प्राप्त करें?
आप अस्थायी लाइसेंस **[यहाँ](https://purchase.aspose.com/temporary-license/)** प्राप्त कर सकते हैं।

### मदद चाहिए या Aspose.Page पर चर्चा करना चाहते हैं?
**[Aspose.Page फ़ोरम](https://forum.aspose.com/c/page/39)** पर जाएँ।

---

**अंतिम अद्यतन:** 2025-12-17  
**परीक्षण किया गया:** Aspose.Page for Java 24.12 (नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}