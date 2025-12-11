---
date: 2025-12-11
description: Aspose.Page का उपयोग करके जावा में पोस्टस्क्रिप्ट एलिप्स बनाना सीखें।
  यह चरण-दर-चरण गाइड आपको दिखाता है कि जावा का उपयोग करके एलिप्स को रंग से कैसे भरें
  और एलिप्स को कैसे ड्रॉ करें।
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: जावा में Aspose.Page के साथ पोस्टस्क्रिप्ट एलिप्स कैसे बनाएं
url: /hi/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में Aspose.Page के साथ PostScript दीर्घवृत्त कैसे बनाएं

## परिचय
प्रोग्रामेटिक रूप से **PostScript ellipse** बनाना आपको रिपोर्ट, इनवॉइस या किसी भी प्रिंटेबल दस्तावेज़ में वेक्टर ग्राफ़िक्स पर सूक्ष्म नियंत्रण देता है। इस ट्यूटोरियल में आप सीखेंगे कि Aspose.Page for Java लाइब्रेरी का उपयोग करके **PostScript ellipse** आकार कैसे बनाएं, दीर्घवृत्त को रंग से भरें, और उसकी रूपरेखा कैसे ड्रॉ करें। अंत तक आप अपने PostScript आउटपुट में सीधे कस्टम ग्राफ़िक्स एम्बेड करने के लिए तैयार हो जाएंगे।

## त्वरित उत्तर
- **Java में PostScript ग्राफ़िक्स ड्रॉ करने के लिए कौन सी लाइब्रेरी सबसे अच्छी है?** Aspose.Page for Java.  
- **क्या मैं दीर्घवृत्त को सॉलिड रंग से भर सकता हूँ?** हाँ – `fill` से पहले `document.setPaint(Color.YOUR_COLOR)` का उपयोग करें।  
- **दीर्घवृत्त की केवल रूपरेखा कैसे बनाऊँ?** पेंट और स्ट्रोक सेट करें, फिर `document.draw(...)` कॉल करें।  
- **उत्पादन उपयोग के लिए लाइसेंस चाहिए?** एक वाणिज्यिक लाइसेंस आवश्यक है; परीक्षण के लिए एक अस्थायी लाइसेंस उपलब्ध है।  
- **कौन सा Java संस्करण समर्थित है?** वर्तमान Aspose.Page रिलीज़ के साथ कोई भी Java 8+ रनटाइम काम करता है।

## PostScript दीर्घवृत्त क्या है?
PostScript दीर्घवृत्त एक वेक्टर आकार है जो बाउंडिंग आयत द्वारा परिभाषित होता है। रास्टर इमेज़ के विपरीत, यह गुणवत्ता खोए बिना स्केल होता है, जिससे यह हाई‑रेज़ोल्यूशन प्रिंटिंग और PDF रूपांतरण के लिए आदर्श बनता है।

## PostScript दीर्घवृत्त बनाने के लिए Aspose.Page का उपयोग क्यों करें?
- **Full control** ड्रॉइंग प्रिमिटिव्स (लाइन, कर्व, दीर्घवृत्त) पर पूरी नियंत्रण।  
- **Cross‑platform** – Windows, Linux, और macOS पर काम करता है।  
- **No external dependencies** – शुद्ध Java API, कोई नेटिव कोड नहीं।  
- **Easy integration** मौजूदा Java एप्लिकेशन और बिल्ड टूल्स के साथ आसान एकीकरण।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

1. एक कार्यशील Java विकास वातावरण (JDK 8 या बाद का)।  
2. आपके प्रोजेक्ट में Aspose.Page for Java लाइब्रेरी जोड़ी गई हो। आप इसे **[here](https://releases.aspose.com/page/java/)** से डाउनलोड कर सकते हैं।  

## पैकेज आयात करें
अपने Java स्रोत फ़ाइल में, PostScript सामग्री को ड्रॉ और सहेजने के लिए आवश्यक क्लासेज़ आयात करें।

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## चरण‑दर‑चरण मार्गदर्शिका

### चरण 1: PostScript दस्तावेज़ सेट करें
एक आउटपुट स्ट्रीम बनाएं, पेज आकार कॉन्फ़िगर करें, और एक `PsDocument` इंस्टैंसिएट करें।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### चरण 2: दीर्घवृत्त को रंग से भरें
वांछित फ़िल रंग के लिए पेंट सेट करें और `Ellipse2D` इंस्टैंस के साथ `fill` कॉल करें।

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### चरण 3: स्ट्रोक के साथ दीर्घवृत्त का रूपरेखा बनाएं
पेंट को स्ट्रोक रंग पर बदलें, लाइन मोटाई के लिए `BasicStroke` परिभाषित करें, और दीर्घवृत्त की रूपरेखा ड्रॉ करें।

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### चरण 4: दस्तावेज़ को बंद करें और सहेजें
पेज को फाइनलाइज़ करें और PostScript फ़ाइल को डिस्क पर लिखें।

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

अब आपके पास एक PostScript फ़ाइल है जिसमें दो दीर्घवृत्त हैं—एक नारंगी रंग से भरा हुआ और दूसरा लाल रंग की रूपरेखा वाला। विभिन्न निर्देशांक, आकार और रंगों के साथ प्रयोग करने के लिए स्वतंत्र महसूस करें ताकि आपका डिज़ाइन आवश्यकताओं के अनुरूप हो सके।

## सामान्य समस्याएँ और ट्रबलशूटिंग
- **Incorrect file path** – सुनिश्चित करें कि `dataDir` आपके OS के अनुसार एक सेपरेटर (`/` या `\\`) के साथ समाप्त हो।  
- **Missing license** – वैध लाइसेंस के बिना, लाइब्रेरी इवैल्युएशन मोड में चलती है और वॉटरमार्क जोड़ सकती है।  
- **Color not applied** – प्रत्येक `fill` या `draw` कॉल से पहले `document.setPaint(...)` सेट करना याद रखें; पेंट सेटिंग अलग-अलग ऑपरेशनों के बीच स्वतः नहीं रहती।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ सहजता से एकीकृत करने के लिए डिज़ाइन किया गया है।

**Q: Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A: परीक्षण उद्देश्यों के लिए एक अस्थायी लाइसेंस **[here](https://purchase.aspose.com/temporary-license/)** प्राप्त करें।

**Q: क्या Aspose.Page वाणिज्यिक प्रोजेक्ट्स के लिए उपयुक्त है?**  
A: बिल्कुल! वाणिज्यिक उपयोग के लिए लाइसेंस विकल्पों को देखना **[here](https://purchase.aspose.com/buy)**।

**Q: Aspose.Page‑संबंधित प्रश्नों के लिए मदद या चर्चा कहाँ प्राप्त करूँ?**  
A: चर्चाओं और सहायता के लिए **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** में शामिल हों।

**Q: Aspose.Page for Java के बारे में अधिक सीखने के लिए कोई मुफ्त संसाधन हैं?**  
A: **[free trial](https://releases.aspose.com/)** का उपयोग करें और दस्तावेज़ीकरण में उदाहरण देखें।

## निष्कर्ष
Aspose.Page for Java **PostScript ellipse** ग्राफ़िक्स को बनाना आसान बनाता है, चाहे आपको एक साधारण भरा हुआ आकार चाहिए या जटिल स्ट्रोक वाली रूपरेखा। ऊपर दिए गए चरणों के साथ आप किसी भी प्रिंटेबल दस्तावेज़ में पेशेवर‑ग्रेड वेक्टर ग्राफ़िक्स जल्दी से जोड़ सकते हैं। अधिक गहन अन्वेषण—जैसे कई आकारों को मिलाना, ग्रेडिएंट लागू करना, या PDF में रूपांतरण—के लिए आधिकारिक **[documentation](https://reference.aspose.com/page/java/)** देखें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2025-12-11  
**परीक्षण किया गया:** Aspose.Page for Java 24.11  
**लेखक:** Aspose