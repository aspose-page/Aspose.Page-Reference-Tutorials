---
date: 2026-02-18
description: जावा में Aspose.Page का उपयोग करके पेंट रंग सेट करना और पोस्टस्क्रिप्ट
  एलिप्स बनाना सीखें। यह गाइड दिखाता है कि जावा में एलिप्स को कैसे भरें, एलिप्स की
  रूपरेखा कैसे बनाएं, और स्ट्रोक की मोटाई कैसे सेट करें।
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: जावा में पोस्टस्क्रिप्ट एलिप्स ड्रॉ करने के लिए पेंट रंग सेट करें
url: /hi/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में PostScript अंडाकार (ellipse) बनाने के लिए पेंट रंग सेट करें

## परिचय
यदि आपको वेक्टर ग्राफ़िक्स बनाते समय **पेंट रंग सेट** करना है, तो Aspose.Page for Java लाइब्रेरी आपको प्रत्येक स्ट्रोक और फ़िल पर पूर्ण नियंत्रण देती है। इस ट्यूटोरियल में आप सीखेंगे कि कैसे **पेंट रंग सेट** करें, **ellipse को Java में भरें**, और **ellipse की रूपरेखा (outline) बनाएं** एक सरल, चरण‑दर‑चरण दृष्टिकोण से। अंत तक, आप इनवॉइस, रिपोर्ट या किसी भी प्रिंटेबल दस्तावेज़ में उच्च‑गुणवत्ता वाले PostScript अंडाकार जोड़ सकेंगे।

## त्वरित उत्तर
- **Java में PostScript ग्राफ़िक्स बनाने के लिए कौन सी लाइब्रेरी सबसे अच्छी है?** Aspose.Page for Java.  
- **क्या मैं अंडाकार को ठोस रंग से भर सकता हूँ?** हाँ – `fill` से पहले `document.setPaint(Color.YOUR_COLOR)` का उपयोग करें।  
- **अंडाकार की केवल रूपरेखा कैसे बनाऊँ?** पेंट और स्ट्रोक सेट करें, फिर `document.draw(...)` को कॉल करें।  
- **उत्पादन उपयोग के लिए लाइसेंस चाहिए?** एक व्यावसायिक लाइसेंस आवश्यक है; परीक्षण के लिए एक अस्थायी लाइसेंस उपलब्ध है।  
- **कौन सा Java संस्करण समर्थित है?** वर्तमान Aspose.Page रिलीज़ के साथ कोई भी Java 8+ रनटाइम काम करता है।

## PostScript अंडाकार क्या है?
PostScript अंडाकार एक वेक्टर आकार है जो एक बाउंडिंग आयत द्वारा परिभाषित होता है। रास्टर छवियों के विपरीत, यह गुणवत्ता खोए बिना स्केल होता है, जिससे यह उच्च‑रिज़ॉल्यूशन प्रिंटिंग और PDF रूपांतरण के लिए आदर्श बनता है।

## Aspose.Page से PostScript अंडाकार बनाने के लाभ
- **ड्राइंग प्रिमिटिव्स (रेखाएँ, कर्व, अंडाकार) पर पूर्ण नियंत्रण**।  
- **क्रॉस‑प्लेटफ़ॉर्म** – Windows, Linux, और macOS पर काम करता है।  
- **कोई बाहरी निर्भरताएँ नहीं** – शुद्ध Java API, कोई नेटिव कोड नहीं।  
- **मौजूदा Java एप्लिकेशन और बिल्ड टूल्स के साथ आसान एकीकरण**।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. एक कार्यशील Java विकास वातावरण (JDK 8 या बाद का)।  
2. आपके प्रोजेक्ट में Aspose.Page for Java लाइब्रेरी जोड़ी गई हो। आप इसे **[यहाँ](https://releases.aspose.com/page/java/)** डाउनलोड कर सकते हैं।  

## पैकेज आयात करें
अपने Java स्रोत फ़ाइल में, PostScript सामग्री को ड्रॉ और सेव करने के लिए आवश्यक क्लासेस को आयात करें।

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## अंडाकार के लिए पेंट रंग कैसे सेट करें
पेंट रंग सेट करना किसी भी फ़िल या स्ट्रोक ऑपरेशन से पहले पहला कदम है। `setPaint` मेथड वह रंग निर्धारित करता है जो अगली ड्रॉइंग कमांड के लिए उपयोग किया जाएगा।

### चरण 1: PostScript दस्तावेज़ सेट अप करें
एक आउटपुट स्ट्रीम बनाएँ, पेज आकार कॉन्फ़िगर करें, और एक `PsDocument` का इंस्टेंस बनाएँ।

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

### चरण 2: अंडाकार भरें – पेंट रंग सेट करें
**अंडाकार भरने** के लिए, पहले इच्छित फ़िल रंग के साथ `setPaint` कॉल करें, फिर `Ellipse2D` इंस्टेंस के साथ `fill` को इनवोक करें।

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### चरण 3: अंडाकार की रूपरेखा बनाएं और स्ट्रोक मोटाई सेट करें
फ़िल करने के बाद, आप पेंट को किसी अन्य रंग में बदल सकते हैं, लाइन की चौड़ाई नियंत्रित करने के लिए `BasicStroke` परिभाषित कर सकते हैं, और अंडाकार की रूपरेखा ड्रॉ कर सकते हैं।

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### चरण 4: दस्तावेज़ को बंद करें और सेव करें
पेज को अंतिम रूप दें और PostScript फ़ाइल को डिस्क पर लिखें।

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

अब आपके पास एक PostScript फ़ाइल है जिसमें दो अंडाकार हैं—एक नारंगी रंग से भरा हुआ और दूसरा लाल रंग में रूपरेखा वाला। विभिन्न निर्देशांक, आकार और रंगों के साथ प्रयोग करके अपने डिज़ाइन आवश्यकताओं के अनुसार अनुकूलित करें।

## सामान्य समस्याएँ और समाधान
- **गलत फ़ाइल पथ** – सुनिश्चित करें कि `dataDir` आपके OS के अनुसार एक सेपरेटर (`/` या `\\`) के साथ समाप्त हो।  
- **लाइसेंस अनुपलब्ध** – वैध लाइसेंस के बिना लाइब्रेरी मूल्यांकन मोड में चलती है और वॉटरमार्क जोड़ सकती है।  
- **रंग लागू नहीं हो रहा** – याद रखें कि प्रत्येक `fill` या `draw` कॉल से पहले `document.setPaint(...)` सेट करें; पेंट सेटिंग अलग-अलग ऑपरेशनों के बीच स्वतः नहीं रहती।

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या मैं Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
उ: हाँ, Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ सहजता से एकीकृत किया जा सकता है।

**प्र: Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
उ: परीक्षण उद्देश्यों के लिए **[यहाँ](https://purchase.aspose.com/temporary-license/)** एक अस्थायी लाइसेंस प्राप्त करें।

**प्र: क्या Aspose.Page व्यावसायिक प्रोजेक्ट्स के लिए उपयुक्त है?**  
उ: बिल्कुल! व्यावसायिक उपयोग के लिए लाइसेंस विकल्पों को **[यहाँ](https://purchase.aspose.com/buy)** देखें।

**प्र: Aspose.Page‑से संबंधित प्रश्नों के लिए सहायता या चर्चा कहाँ प्राप्त करूँ?**  
उ: चर्चा और सहायता के लिए **[Aspose.Page फ़ोरम](https://forum.aspose.com/c/page/39)** में शामिल हों।

**प्र: Aspose.Page for Java के बारे में अधिक सीखने के लिए कोई मुफ्त संसाधन हैं?**  
उ: **[फ्री ट्रायल](https://releases.aspose.com/)** का उपयोग करें और दस्तावेज़ में उदाहरण देखें।

## निष्कर्ष
Aspose.Page for Java आपको **पेंट रंग सेट**, **ellipse भरना**, और **ellipse की रूपरेखा बनाना** सरल बनाता है—चाहे आपको एक साधारण भरा हुआ आकार चाहिए या जटिल स्ट्रोक वाला ग्राफ़िक। ऊपर बताए गए चरणों के साथ आप किसी भी प्रिंटेबल दस्तावेज़ में पेशेवर‑स्तर के वेक्टर ग्राफ़िक्स जल्दी जोड़ सकते हैं। अधिक गहन अन्वेषण के लिए—जैसे कई आकारों को मिलाना, ग्रेडिएंट लागू करना, या PDF में रूपांतरण—आधिकारिक **[दस्तावेज़ीकरण](https://reference.aspose.com/page/java/)** देखें।

---

**अंतिम अपडेट:** 2026-02-18  
**परीक्षित संस्करण:** Aspose.Page for Java 24.11  
**लेखक:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}