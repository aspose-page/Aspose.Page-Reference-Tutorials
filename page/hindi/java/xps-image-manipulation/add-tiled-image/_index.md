---
date: 2026-05-30
description: Aspose.Page का उपयोग करके जावा में XPS दस्तावेज़ बनाना सीखें और इस चरण‑दर‑चरण
  गाइड के साथ टाइल्ड इमेज को आसानी से जोड़ें। XPS फ़ाइलें जल्दी बनाना सीखें।
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: जावा XPS में टाइल्ड इमेज जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: जावा में टाइल्ड इमेज के साथ XPS दस्तावेज़ कैसे बनाएं
url: /hi/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में टाइल्ड इमेज के साथ XPS दस्तावेज़ कैसे बनाएं

## परिचय
प्रोग्रामेटिक रूप से XPS दस्तावेज़ बनाना उन Java डेवलपर्स के लिए एक मुख्य कौशल है जिन्हें प्रिंटेबल, डिवाइस‑स्वतंत्र आउटपुट चाहिए। **XPS कैसे बनाएं** फ़ाइलें प्रभावी रूप से बनाना Aspose.Page for Java द्वारा उत्तर दिया गया है, जो लो‑लेवल XML Paper Specification विवरणों को एब्स्ट्रैक्ट करता है और आपको विज़ुअल डिज़ाइन पर ध्यान केंद्रित करने देता है। इस गाइड में आप देखेंगे कि कैसे XPS दस्तावेज़ बनाएं, बैकग्राउंड या पैटर्न के रूप में टाइल्ड इमेज जोड़ें, और परिणाम सहेजें—संकुचित, प्रोडक्शन‑रेडी कोड के साथ।

## त्वरित उत्तर
- **Aspose.Page क्या करता है?** यह Java में XPS दस्तावेज़ बनाने और संशोधित करने के लिए एक उच्च‑स्तरीय API प्रदान करता है।  
- **क्या मैं इमेज को टाइल कर सकता हूँ?** हाँ – `XpsImageBrush` को `XpsTileMode.Tile` के साथ उपयोग करें।  
- **क्या मुझे लाइसेंस चाहिए?** उत्पादन उपयोग के लिए एक अस्थायी या व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** कोई भी JDK 8+ संगत है।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बुनियादी टाइल्ड‑इमेज परिदृश्य के लिए लगभग 10–15 मिनट।

## “XPS दस्तावेज़ बनाना” क्या है?
`XpsDocument` Aspose.Page का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में एकल XPS फ़ाइल का प्रतिनिधित्व करता है। यह पेजेज, रिसोर्सेज और मेटाडेटा को एन्कैप्सुलेट करता है, जिससे आप प्रोग्रामेटिक रूप से दस्तावेज़ बना सकते हैं। XPS दस्तावेज़ बनाना इसका क्लास इंस्टैंशिएट करना, विज़ुअल एलिमेंट्स जोड़ना, और अंत में `save` कॉल करके फिक्स्ड‑लेआउट फ़ाइल को डिस्क पर लिखना है। यह तरीका मैन्युअल XML हैंडलिंग को समाप्त करता है और XML Paper Specification के अनुपालन को सुनिश्चित करता है।

## टाइल्ड इमेज क्यों जोड़ें?
टाइलिंग एक ग्राफ़िक को परिभाषित क्षेत्र में दोहराती है, जो बैकग्राउंड, वॉटरमार्क या पैटर्न फ़िल्स के लिए आदर्श है। `XpsTileMode.Tile` का उपयोग करने से इमेज स्वचालित रूप से दोहराई जाती है, बिना मैन्युअल डुप्लिकेशन के, जिससे विकास समय बचता है और किसी भी डिवाइस पर सुसंगत रेंडरिंग सुनिश्चित होती है। टाइल्ड इमेज फ़ाइल आकार को भी कम रखती है क्योंकि वही बिटमैप रिसोर्स कई बार एम्बेड करने के बजाय पुनः उपयोग किया जाता है।

## पूर्वापेक्षाएँ
1. **Java Development Kit (JDK)** – JDK 8 या नया स्थापित हो।  
2. **Aspose.Page for Java** – [website](https://releases.aspose.com/page/java/) से डाउनलोड करें।  
3. **एक लिखने योग्य डायरेक्टरी** – जहाँ उत्पन्न XPS फ़ाइल सहेजी जाएगी।

## पैकेज इम्पोर्ट करें
अपने Java प्रोजेक्ट में आवश्यक क्लासेज़ इम्पोर्ट करें:

`XpsDocument` XPS फ़ाइल का मुख्य ऑब्जेक्ट है।  
`XpsImageBrush` इमेज स्रोत का उपयोग करके शेप्स को पेंट करता है।  
`XpsTileMode` निर्धारित करता है कि इमेज कैसे टाइल की जाती है।  
`Rectangle2D` पोजिशनिंग के लिए आयताकार क्षेत्र का वर्णन करता है।

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## चरण‑दर‑चरण गाइड

### चरण 1: अपने प्रोजेक्ट को सेट अप करें
Aspose.Page JAR फ़ाइलों को अपने प्रोजेक्ट के क्लासपाथ में जोड़ें और इम्पोर्ट स्टेटमेंट्स को त्रुटियों के बिना कंपाइल होते हुए सत्यापित करें।

### चरण 2: XPS दस्तावेज़ बनाएं
`XpsDocument` वह कोर कंटेनर है जो पेजेज, पाथ्स और रिसोर्सेज को रखता है। इच्छित पेज आकार के साथ इसे इंस्टैंशिएट करें, फिर आप ग्राफ़िकल एलिमेंट्स जोड़ना शुरू कर सकते हैं।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### चरण 3: टाइल्ड इमेज पाथ निर्धारित करें
उस इमेज को रखें जिसे आप टाइल करना चाहते हैं (उदा., `R08LN_NN.jpg`) `dataDir` द्वारा संदर्भित डायरेक्टरी में। इमेज को ब्रश पैटर्न के रूप में उपयोग किया जाएगा।

### चरण 4: टाइल्ड इमेज जोड़ें
एक आयताकार पाथ बनाएं और उसे `XpsImageBrush` से भरें। टाइल मोड को `Tile` सेट करने से इमेज आयत के भीतर दोहराई जाती है। टाइल आकार और पोजिशनिंग को नियंत्रित करने के लिए स्रोत और डेस्टिनेशन आयत को समायोजित करें।

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### चरण 5: दस्तावेज़ सहेजें
XPS फ़ाइल को डिस्क पर स्थायी रूप से सहेजें। आउटपुट फ़ाइल में वह टाइल्ड इमेज होगी जिसे आपने अभी परिभाषित किया है और इसे किसी भी XPS व्यूअर से खोला जा सकता है।

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

इन चरणों को तब दोहराएँ जब भी आपको समान XPS दस्तावेज़ में अन्य पेजेज या शेप्स पर **टाइल्ड इमेज जोड़नी** हो।

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| इमेज नहीं दिख रही | फ़ाइल पाथ (`dataDir + "R08LN_NN.jpg"`) सही है और इमेज एक्सेसिबल है, यह सत्यापित करें। |
| टाइल पैटर्न खिंचा हुआ दिख रहा है | टाइल आकार को नियंत्रित करने के लिए स्रोत और डेस्टिनेशन `Rectangle2D` मानों को समायोजित करें। |
| अपारदर्शिता का कोई प्रभाव नहीं | टाइल मोड कॉन्फ़िगरेशन के **बाद** ब्रश की अपारदर्शिता सेट करना सुनिश्चित करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q:** क्या Aspose.Page सभी Java संस्करणों के साथ संगत है?  
**A:** Aspose.Page Java 8 से लेकर Java 21 तक समर्थन देता है; आप पूर्ण संगतता मैट्रिक्स [here](https://reference.aspose.com/page/java/) पर पा सकते हैं।

**Q:** क्या मैं Aspose.Page को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?  
**A:** हाँ, उत्पादन उपयोग के लिए एक व्यावसायिक लाइसेंस आवश्यक है। खरीद विकल्प [here](https://purchase.aspose.com/buy) सूचीबद्ध हैं।

**Q:** क्या कोई फ्री ट्रायल उपलब्ध है?  
**A:** एक पूरी तरह कार्यात्मक फ्री ट्रायल Aspose रिलीज़ पेज से [here](https://releases.aspose.com/) डाउनलोड किया जा सकता है।

**Q:** मुझे कम्युनिटी सपोर्ट कहाँ मिल सकता है?  
**A:** प्रश्न पूछने और उदाहरण साझा करने के लिए Aspose.Page कम्युनिटी फ़ोरम [forum](https://forum.aspose.com/c/page/39) में जुड़ें।

**Q:** मूल्यांकन के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?  
**A:** अस्थायी लाइसेंस Aspose पोर्टल के माध्यम से अनुरोध पर प्रदान किए जाते हैं, विवरण [here](https://purchase.aspose.com/temporary-license/) देखें।

## निष्कर्ष
अब आपके पास Aspose.Page for Java का उपयोग करके टाइल्ड इमेज के साथ **XPS कैसे बनाएं** दस्तावेज़ों के लिए एक पूर्ण, प्रोडक्शन‑रेडी वर्कफ़्लो है। `XpsImageBrush` और `XpsTileMode.Tile` को Leveraging करके आप फ़ाइल आकार को बढ़ाए बिना समृद्ध, दोहराने योग्य ग्राफ़िक्स जेनरेट कर सकते हैं। विभिन्न टाइल आकार, अपारदर्शिता स्तर और शेप्स के साथ प्रयोग करें ताकि परिष्कृत दस्तावेज़ लेआउट बना सकें। अगले चरण में, अपने XPS फ़ाइलों को और बेहतर बनाने के लिए वेक्टर शेप्स या टेक्स्ट ओवरले जोड़ने का अन्वेषण करें।

---

**अंतिम अपडेट:** 2026-05-30  
**परीक्षित संस्करण:** Aspose.Page for Java 24.12 (latest)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Java XPS दस्तावेज़ में इमेज जोड़ना – Aspose.Page के साथ एक सरल गाइड](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - XPS में पेज जोड़ें ट्यूटोरियल](/page/java/xps-page-manipulation/add-page/)
- [Java में Aspose.Page Java का उपयोग करके XPS को PDF में बदलें](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}