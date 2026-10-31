---
date: 2026-10-31
description: Aspose.Page का उपयोग करके Java PostScript में paint color सेट करने और
  ellipse को भरने का तरीका सीखें। यह गाइड दिखाता है कि कैसे ellipse को भरें, ellipse
  की outline ड्रॉ करें, और स्पष्ट code चरणों के साथ stroke thickness सेट करें।
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Java PostScript में Ellipse जोड़ें
og_description: Aspose.Page का उपयोग करके Java PostScript में ellipse को भरने और paint
  color सेट करने का तरीका सीखें। सेकंडों में भरे हुए और outlined ellipses ड्रॉ करने
  के लिए step‑by‑step code का पालन करें।
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Java PostScript में ellipse को भरने और paint color सेट करने का तरीका
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Java PostScript में ellipse को भरने और paint color सेट करने का तरीका
url: /hi/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा पोस्टस्क्रिप्ट में एलिप्स को भरना और पेंट रंग सेट करना कैसे करें

## परिचय
यदि आपको वेक्टर ग्राफ़िक्स बनाते समय **set paint color** सेट करने की आवश्यकता है, तो Aspose.Page for Java लाइब्रेरी आपको प्रत्येक स्ट्रोक और फ़िल पर पूर्ण नियंत्रण देती है। इस ट्यूटोरियल में आप सीखेंगे कि कैसे **set paint color**, **fill ellipse**, और **draw ellipse outline** को एक सरल, चरण‑बद्ध तरीके से उपयोग किया जाए। अंत तक, आप इनवॉइस, रिपोर्ट या किसी भी प्रिंटेबल दस्तावेज़ में उच्च‑गुणवत्ता वाले पोस्टस्क्रिप्ट एलिप्स जोड़ सकेंगे।

## त्वरित उत्तर
- **जावा में पोस्टस्क्रिप्ट ग्राफ़िक्स ड्रॉ करने के लिए सबसे अच्छी लाइब्रेरी कौन सी है?** Aspose.Page for Java.  
- **क्या मैं एक एलिप्स को ठोस रंग से भर सकता हूँ?** हाँ – `fill` से पहले `document.setPaint(Color.YOUR_COLOR)` का उपयोग करें।  
- **मैं केवल एलिप्स की रूपरेखा कैसे बना सकता हूँ?** पेंट और स्ट्रोक सेट करें, फिर `document.draw(...)` कॉल करें।  
- **उत्पादन उपयोग के लिए मुझे लाइसेंस चाहिए?** एक व्यावसायिक लाइसेंस आवश्यक है; परीक्षण के लिए एक अस्थायी लाइसेंस उपलब्ध है।  
- **कौन सा जावा संस्करण समर्थित है?** कोई भी Java 8+ रनटाइम वर्तमान Aspose.Page रिलीज़ के साथ काम करता है।

## पोस्टस्क्रिप्ट एलिप्स क्या है?
एक पोस्टस्क्रिप्ट एलिप्स एक वेक्टर आकार है जो बाउंडिंग आयत द्वारा परिभाषित होता है। रास्टर इमेजों के विपरीत, यह गुणवत्ता में कमी के बिना स्केल करता है, जिससे यह हाई‑रेज़ोल्यूशन प्रिंटिंग और PDF रूपांतरण के लिए आदर्श है। क्योंकि आकार गणितीय रूप से वर्णित है, इसे किसी भी आकार या रिज़ॉल्यूशन पर रेंडर किया जा सकता है जबकि तेज किनारे और स्मूद कर्व्स बनाए रखे जाते हैं।

## पोस्टस्क्रिप्ट एलिप्स बनाने के लिए Aspose.Page का उपयोग क्यों करें?
Aspose.Page आपको प्रत्येक ड्रॉइंग प्रिमिटिव पर निश्चित नियंत्रण देता है। यह **3 प्रमुख ऑपरेटिंग सिस्टम (Windows, Linux, macOS)**, **0 नेटिव डिपेंडेंसीज़**, का समर्थन करता है, और सामान्य सर्वर पर प्रति सेकंड **50+ वेक्टर प्रिमिटिव** रेंडर कर सकता है। लाइब्रेरी शुद्ध जावा है, इसलिए आप इसे किसी भी Java 8+ एप्लिकेशन में अतिरिक्त नेटिव लाइब्रेरीज़ के बिना एम्बेड कर सकते हैं।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:

1. एक कार्यात्मक जावा विकास वातावरण (JDK 8 या बाद का)।  
2. Aspose.Page for Java लाइब्रेरी आपके प्रोजेक्ट में जोड़ी गई हो। आप इसे **[Aspose.Page for Java रिलीज़ पेज से](https://releases.aspose.com/page/java/)** डाउनलोड कर सकते हैं।

## पैकेज आयात करें
अपने जावा स्रोत फ़ाइल में, पोस्टस्क्रिप्ट सामग्री को ड्रॉ करने और सहेजने के लिए आवश्यक क्लासेस को आयात करें।

`java.awt` पैकेज बुनियादी ग्राफ़िक्स प्रकार जैसे `Color`, `Ellipse2D`, और `BasicStroke` प्रदान करता है। `com.aspose.page` पैकेज `PsDocument` क्लास प्रदान करता है जो पोस्टस्क्रिप्ट आउटपुट लिखता है।

- **`Color`** – पेंटिंग के लिए उपयोग किए जाने वाले sRGB रंग को दर्शाता है।  
- **`Ellipse2D`** – बाउंडिंग आयत द्वारा परिभाषित एक एलिप्स आकार का वर्णन करता है।  
- **`BasicStroke`** – आउटलाइन ड्रॉ करने के लिए लाइन की चौड़ाई, डैश पैटर्न, और एंड‑कैप शैली निर्दिष्ट करता है।  
- **`PsDocument`** – एक पोस्टस्क्रिप्ट दस्तावेज़ का प्रतिनिधित्व करता है और ग्राफ़िक्स ड्रॉ करने तथा पेज प्रबंधन के लिए मेथड्स प्रदान करता है।

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## एलिप्स के लिए पेंट रंग कैसे सेट करें
पहला कदम यह है कि दस्तावेज़ को बताएं कि अगले ड्रॉइंग ऑपरेशन के लिए कौन सा रंग उपयोग करना है। `setPaint` मेथड एक ठोस रंग सेट करता है जो आगे के कॉल के आधार पर फ़िल या स्ट्रोक पर लागू होगा।

### चरण 1: पोस्टस्क्रिप्ट दस्तावेज़ सेट करें
एक आउटपुट स्ट्रीम बनाएं, पेज आकार कॉन्फ़िगर करें, और एक `PsDocument` का इंस्टैंस बनाएं।

`PsDocument` कोर क्लास है जो मेमोरी में पोस्टस्क्रिप्ट फ़ाइल का प्रतिनिधित्व करता है। सभी ड्रॉइंग कमांड्स इस ऑब्जेक्ट के माध्यम से भेजे जाते हैं, और यह पेज लेआउट, रिसोर्स मैनेजमेंट, और अंतिम फ़ाइल जनरेशन को संभालता है।

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

### चरण 2: एलिप्स भरें – सेट पेंट रंग का उपयोग करें
**fill ellipse** करने के लिए, आपको पहले इच्छित फ़िल रंग के साथ `setPaint` कॉल करना होगा, फिर `Ellipse2D` इंस्टेंस के साथ `fill` को इनवोक करना होगा।

`setPaint` वर्तमान ड्रॉइंग रंग सेट करता है जो आगे के फ़िल या स्ट्रोक ऑपरेशन्स में उपयोग होता है।  
`Ellipse2D` एलिप्स की ज्यामितीय सीमाओं को परिभाषित करता है; इसका कन्स्ट्रक्टर ऊपरी‑बाएँ कोने के X‑Y निर्देशांक तथा चौड़ाई और ऊँचाई लेता है।

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### चरण 3: एलिप्स की रूपरेखा बनाएं और स्ट्रोक मोटाई सेट करें
फ़िल करने के बाद, आप पेंट को किसी अलग रंग में बदल सकते हैं, लाइन की चौड़ाई नियंत्रित करने के लिए `BasicStroke` परिभाषित कर सकते हैं, और एलिप्स की रूपरेखा ड्रॉ कर सकते हैं।

`BasicStroke` आउटलाइन ड्रॉ करने के लिए लाइन की चौड़ाई, डैश पैटर्न, और एंड‑कैप शैली निर्दिष्ट करता है। इसके `width` प्रॉपर्टी को समायोजित करके आप एलिप्स बॉर्डर की मोटाई को नियंत्रित कर सकते हैं।

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### चरण 4: दस्तावेज़ को बंद करें और सहेजें
पेज को अंतिम रूप दें और पोस्टस्क्रिप्ट फ़ाइल को डिस्क पर लिखें।

`document.close()` को कॉल करने से सभी लंबित ड्रॉइंग कमांड्स फ्लश होते हैं और रिसोर्सेज़ रिलीज़ हो जाते हैं। परिणामी `.ps` फ़ाइल को किसी भी पोस्टस्क्रिप्ट व्यूअर से खोला जा सकता है या PDF में परिवर्तित किया जा सकता है।

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

अब आपके पास एक पोस्टस्क्रिप्ट फ़ाइल है जिसमें दो एलिप्स हैं—एक नारंगी रंग से भरा हुआ और दूसरा लाल रंग की रूपरेखा वाला। विभिन्न निर्देशांक, आकार, और रंगों के साथ प्रयोग करने में संकोच न करें ताकि आपके डिज़ाइन आवश्यकताओं के अनुरूप हो सके।

## सामान्य समस्याएँ और ट्रबलशूटिंग
- **गलत फ़ाइल पथ** – सुनिश्चित करें कि `dataDir` आपके OS के अनुसार एक सेपरेटर (`/` या `\\`) के साथ समाप्त हो।  
- **लाइसेंस अनुपलब्ध** – वैध लाइसेंस के बिना, लाइब्रेरी इवैल्यूएशन मोड में चलती है और वॉटरमार्क जोड़ सकती है।  
- **रंग लागू नहीं हुआ** – याद रखें कि प्रत्येक `fill` या `draw` कॉल से *पहले* `document.setPaint(...)` सेट करें; पेंट सेटिंग अलग-अलग ऑपरेशन्स के बीच स्वतः नहीं रहती।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Page for Java को अन्य जावा लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
**उत्तर:** हाँ, Aspose.Page for Java को अन्य जावा लाइब्रेरीज़ के साथ सहजता से एकीकृत करने के लिए डिज़ाइन किया गया है।

**प्रश्न: मैं Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?**  
**उत्तर:** परीक्षण उद्देश्यों के लिए एक अस्थायी लाइसेंस **[Aspose अस्थायी‑लाइसेंस पेज से](https://purchase.aspose.com/temporary-license/)** प्राप्त करें।

**प्रश्न: क्या Aspose.Page व्यावसायिक प्रोजेक्ट्स के लिए उपयुक्त है?**  
**उत्तर:** बिल्कुल! व्यावसायिक उपयोग के लिए लाइसेंस विकल्पों को देखने हेतु **[Aspose खरीद पेज पर जाएँ](https://purchase.aspose.com/buy)**।

**प्रश्न: मैं मदद कहाँ प्राप्त कर सकता हूँ या Aspose.Page‑संबंधित प्रश्नों पर चर्चा कहाँ कर सकता हूँ?**  
**उत्तर:** चर्चाओं और सहायता के लिए **[Aspose.Page फ़ोरम](https://forum.aspose.com/c/page/39)** में शामिल हों।

**प्रश्न: क्या Aspose.Page for Java के बारे में अधिक सीखने के लिए कोई मुफ्त संसाधन हैं?**  
**उत्तर:** **[Aspose फ्री ट्रायल पेज](https://releases.aspose.com/)** का उपयोग करें और दस्तावेज़ीकरण में उदाहरण देखें।

## निष्कर्ष
Aspose.Page for Java आपको **set paint color**, **fill ellipse**, और **draw ellipse outline** को सरल बनाता है—चाहे आपको एक साधारण भरा हुआ आकार चाहिए या जटिल स्ट्रोक वाला ग्राफ़िक। ऊपर दिए गए चरणों के साथ आप जल्दी से किसी भी प्रिंटेबल दस्तावेज़ में प्रोफ़ेशनल‑ग्रेड वेक्टर ग्राफ़िक्स जोड़ सकते हैं। अधिक गहन अन्वेषण के लिए—जैसे कई आकारों को मिलाना, ग्रेडिएंट लागू करना, या PDF में रूपांतरण—आधिकारिक **[Aspose.Page Java दस्तावेज़ीकरण](https://reference.aspose.com/page/java/)** देखें।

---

**अंतिम अपडेट:** 2026-10-31  
**परीक्षित संस्करण:** Aspose.Page for Java 24.11  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [जावा पोस्टस्क्रिप्ट में Aspose.Page के साथ आयत कैसे बनाएं](/page/java/postscript-shapes/add-rectangle/)
- [जावा पोस्टस्क्रिप्ट में Aspose.Page के साथ यूनिकोड टेक्स्ट कैसे जोड़ें](/page/java/postscript-text-manipulation/add-text-unicode/)
- [जावा के लिए Aspose.Page के साथ पोस्टस्क्रिप्ट में रेडियल ग्रेडिएंट कैसे बनाएं](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}