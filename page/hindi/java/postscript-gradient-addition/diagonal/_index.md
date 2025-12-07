---
date: 2025-12-07
description: Aspose.Page Java का उपयोग करके अपने Java PostScript दस्तावेज़ों को तिरछी
  ग्रेडिएंट्स के साथ बेहतर बनाएं। Java में LinearGradientPaint के साथ ग्रेडिएंट इफ़ेक्ट
  जोड़ना सीखें और आसानी से जीवंत रंग संक्रमण बनाएं।
language: hi
linktitle: Add Diagonal Gradient in Java PostScript using Aspose.Page Java
second_title: Aspose.Page Java API
title: Aspose.Page Java का उपयोग करके Java PostScript में तिरछा ग्रेडिएंट जोड़ें
url: /java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java का उपयोग करके Java PostScript में विकर्ण ग्रेडिएंट जोड़ें

## परिचय
यदि आप एक PostScript फ़ाइल को सुगम विकर्ण रंग संक्रमण से समृद्ध करना चाहते हैं, तो **Aspose.Page Java** इसे आश्चर्यजनक रूप से आसान बनाता है। इस ट्यूटोरियल में हम **ग्रेडिएंट कैसे जोड़ें** को चरण‑दर‑चरण समझेंगे, Java 2D की `LinearGradientPaint` क्लास का उपयोग करके। अंत तक आपके पास एक तैयार‑चलाने‑योग्य स्निपेट होगा जो जीवंत विकर्ण ग्रेडिएंट के साथ एक PostScript दस्तावेज़ बनाता है।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java.  
- **ग्रेडिएंट बनाने वाली क्लास कौन सी है?** `LinearGradientPaint`.  
- **क्या मैं रंग बदल सकता हूँ?** हाँ – `Color[]` एरे को संशोधित करें।  
- **उत्पादन के लिए लाइसेंस चाहिए?** एक वाणिज्यिक लाइसेंस आवश्यक है; एक मुफ्त ट्रायल उपलब्ध है।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बुनियादी ग्रेडिएंट के लिए लगभग 10 मिनट।

## Aspose.Page Java क्या है?
Aspose.Page Java एक शक्तिशाली API है जो डेवलपर्स को किसी बाहरी सॉफ़्टवेयर की आवश्यकता के बिना PostScript और PDF फ़ाइलें उत्पन्न, संपादित और परिवर्तित करने की सुविधा देता है। यह PostScript भाषा की पूरी ग्राफ़िक्स क्षमताओं को एक साफ़, ऑब्जेक्ट‑ओरिएंटेड Java इंटरफ़ेस के माध्यम से उजागर करता है।

## विकर्ण ग्रेडिएंट क्यों उपयोग करें?
विकर्ण ग्रेडिएंट चार्ट, बैनर या किसी भी ग्राफ़िक तत्व में गहराई और दृश्य आकर्षण जोड़ता है जिसे आधुनिक लुक चाहिए। क्योंकि ग्रेडिएंट एक कोने से विपरीत कोने तक चलता है, यह बैकग्राउंड, बटन स्किन और सजावटी आकारों के लिए उपयुक्त है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हों:

- Java Development Kit (JDK) 8 या उससे ऊपर।  
- Eclipse, IntelliJ IDEA, या VS Code जैसे IDE।  
- **Aspose.Page for Java** लाइब्रेरी – नवीनतम संस्करण [official download page](https://releases.aspose.com/page/java/) से डाउनलोड करें।

## पैकेज आयात करें
सबसे पहले, Java 2D और Aspose क्लासेज़ को आयात करें जो आपको चाहिए। ये इम्पोर्ट्स आपको रंग परिभाषाएँ, ज्यामितीय आकार, ग्रेडिएंट पेंटिंग, और PostScript दस्तावेज़ API तक पहुँच प्रदान करते हैं।

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

## चरण 1: PostScript दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
हम फ़ाइल को सहेजने वाले फ़ोल्डर को परिभाषित करके और एक `FileOutputStream` खोलकर शुरू करते हैं। यह स्ट्रीम उत्पन्न PostScript डेटा को प्राप्त करेगा।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## चरण 2: A4 आकार के साथ सेव ऑप्शन बनाएं
`PsSaveOptions` आपको पेज आकार, रिज़ॉल्यूशन और अन्य आउटपुट सेटिंग्स निर्दिष्ट करने की अनुमति देता है। यहाँ हम डिफ़ॉल्ट A4 आकार का उपयोग करते हैं।

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## चरण 3: नया PS दस्तावेज़ बनाएं
आउटपुट स्ट्रीम और सेव ऑप्शन का उपयोग करके एक `PsDocument` इंस्टैंशिएट करें। `false` फ़्लैग कंस्ट्रक्टर को स्वचालित रूप से नया पेज खोलने से रोकता है – हम बाद में यह करेंगे।

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## चरण 4: एक आयत बनाएं
ऐसी आयत परिभाषित करें जो ग्रेडिएंट भराव प्राप्त करेगी। आयत की स्थिति (200, 100) और आकार (200 × 100) को इस तरह चुना गया है कि ग्रेडिएंट स्पष्ट रूप से दिखाई दे।

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## चरण 5: ग्रेडिएंट ट्रांसफ़ॉर्म बनाएं
`AffineTransform` हमें ग्रेडिएंट को घुमाने, स्केल करने और ट्रांसलेट करने की सुविधा देता है ताकि वह आयत के पार विकर्ण रूप से चले। नीचे दिया गया गणित हाइपोटेन्यूस की गणना करता है और स्केलिंग अनुपात को उसी अनुसार समायोजित करता है।

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## चरण 6: विकर्ण लीनियर ग्रेडिएंट पेंट बनाएं
यहाँ **ग्रेडिएंट कैसे जोड़ें** का मूल भाग है – हम एक `LinearGradientPaint` बनाते हैं जो आयत के शीर्ष‑बाएँ से नीचे‑दाएँ तक फैला होता है, पहले परिभाषित ट्रांसफ़ॉर्म का उपयोग करके। `MultipleGradientPaint.CycleMethod.NO_CYCLE` सुनिश्चित करता है कि ग्रेडिएंट दोहराया न जाए।

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## चरण 7: पेंट सेट करें और आयत को भरें
ग्रेडिएंट पेंट को दस्तावेज़ पर लागू करें और आयत के आकार को भरें। यह चरण विकर्ण रंग संक्रमण को PostScript पेज पर रेंडर करता है।

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## चरण 8: वर्तमान पेज बंद करें और दस्तावेज़ सहेजें
अंत में, पेज को बंद करें, स्ट्रीम को फ्लश करें, और फ़ाइल सहेजें। परिणामी `DiagonalGradient_outPS.ps` फ़ाइल को किसी भी PostScript व्यूअर से खोला जा सकता है।

```java
// Close current page and save the document
document.closePage();
document.save();
```

इन आठ चरणों का पालन करके आपने **Aspose.Page Java** का उपयोग करके एक PostScript दस्तावेज़ में सफलतापूर्वक विकर्ण ग्रेडिएंट जोड़ दिया है। विभिन्न रंगों, कोणों और आयत आकारों के साथ प्रयोग करने में संकोच न करें ताकि कस्टम दृश्य प्रभाव बना सकें।

## सामान्य समस्याएँ और सुझाव
- **ग्रेडिएंट सपाट दिख रहा है** – घूर्णन कोण को दोबारा जाँचें; 45° का घूर्णन वास्तविक विकर्ण बनाता है।  
- **रंग फीके लग रहे हैं** – सटीक रंग रेंडरिंग के लिए `MultipleGradientPaint.ColorSpaceType.SRGB` का उपयोग सुनिश्चित करें।  
- **फ़ाइल नहीं मिली त्रुटि** – यह सत्यापित करें कि `dataDir` एक मौजूदा फ़ोल्डर की ओर इशारा कर रहा है और एप्लिकेशन के पास लिखने की अनुमति है।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं इस लाइब्रेरी का उपयोग Java में अन्य ग्राफ़िक ऑपरेशनों के लिए कर सकता हूँ?**  
उत्तर: हाँ, Aspose.Page for Java ड्राइंग प्रिमिटिव्स, टेक्स्ट रेंडरिंग और इमेज हैंडलिंग क्षमताओं का पूरा सेट प्रदान करता है।

**प्रश्न: क्या Aspose.Page Java के लिए कोई मुफ्त ट्रायल उपलब्ध है?**  
उत्तर: बिल्कुल। आप पूरी तरह कार्यात्मक ट्रायल [Aspose free trial page](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

**प्रश्न: Aspose.Page Java की दस्तावेज़ीकरण कहाँ मिल सकती है?**  
उत्तर: आधिकारिक API रेफ़रेंस [here](https://reference.aspose.com/page/java/) उपलब्ध है।

**प्रश्न: Aspose.Page Java के लिए लाइसेंस कैसे खरीदें?**  
उत्तर: लाइसेंस सीधे [Aspose purchase portal](https://purchase.aspose.com/buy) से खरीदा जा सकता है।

**प्रश्न: सहायता चाहिए या कोई प्रश्न हैं?**  
उत्तर: मदद के लिए समुदाय‑चलित [Aspose.Page forum](https://forum.aspose.com/c/page/39) पर जाएँ, जहाँ Aspose इंजीनियर और अन्य डेवलपर्स सहायता प्रदान करते हैं।

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}