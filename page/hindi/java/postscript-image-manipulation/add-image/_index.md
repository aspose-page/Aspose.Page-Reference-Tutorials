---
date: 2026-08-23
description: aspose.page image manipulation java का उपयोग करके PostScript फ़ाइलों
  में इमेज को एम्बेड और रोटेट करने का तरीका स्पष्ट Java उदाहरणों के साथ सीखें।
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Java PostScript में इमेज जोड़ें
og_description: aspose.page image manipulation java का उपयोग करके PostScript फ़ाइलों
  में इमेज को एम्बेड और रोटेट करने का तरीका, step‑by‑step Java कोड उदाहरणों के साथ
  सीखें।
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: aspose.page image manipulation java का उपयोग करके इमेज जोड़ना
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: aspose.page image manipulation java का उपयोग करके इमेज जोड़ना
url: /hi/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page इमेज मैनिपुलेशन जावा का उपयोग करके इमेज जोड़ना

## परिचय
इस ट्यूटोरियल में आप सीखेंगे कि **aspose.page इमेज मैनिपुलेशन जावा** का उपयोग करके PostScript फ़ाइलें कैसे बनाएं, रास्टर इमेज एम्बेड करें, और ट्रांसलेशन‑और‑रोटेशन ट्रांसफ़ॉर्म लागू करें। गाइड के अंत तक आप जावा से पिक्सेल‑परफेक्ट PostScript आउटपुट जेनरेट करने में सक्षम होंगे—स्वचालित रिपोर्टिंग, प्रिंटिंग पाइपलाइन, या किसी भी वर्कफ़्लो के लिए आदर्श जहाँ PostScript दस्तावेज़ में सटीक इमेज प्लेसमेंट आवश्यक हो।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java  
- **क्या मैं कई इमेज जोड़ सकता हूँ?** हाँ – प्रत्येक इमेज के लिए ट्रांसफ़ॉर्म और ड्रॉ चरण दोहराएँ  
- **क्या विकास के लिए लाइसेंस चाहिए?** परीक्षण के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है  
- **कौन सा जावा संस्करण समर्थित है?** Java 8 और बाद के संस्करण  
- **क्या इमेज रोटेशन समर्थित है?** बिल्कुल – `AffineTransform.rotate()` का उपयोग करें  

## aspose.page इमेज मैनिपुलेशन जावा क्या है?
`aspose.page image manipulation java` Aspose.Page API है जो आपको जावा कोड से प्रोग्रामेटिक रूप से PostScript दस्तावेज़ बनाना, संपादित करना और रेंडर करना संभव बनाता है, जिसमें इमेज प्लेसमेंट, स्केलिंग और रोटेशन पर पूर्ण नियंत्रण मिलता है। इस API के साथ आप लो‑लेवल PostScript सिंटैक्स से बचते हैं और लाइब्रेरी को फ़ॉर्मेट रूपांतरण और एम्बेडिंग आंतरिक रूप से संभालने देते हैं।

## इमेज मैनिपुलेशन के लिए aspose.page क्यों उपयोग करें?
Aspose.Page **50+ इमेज फ़ॉर्मेट** (जैसे JPEG, PNG, BMP, TIFF) प्रदान करता है और इन्हें PostScript में एम्बेड कर सकता है बिना पूरे दस्तावेज़ को मेमोरी में लोड किए, जिससे सैकड़ों पेज वाली फ़ाइलों को प्रोसेस करते समय भी सामान्य सर्वर पर मेमोरी उपयोग 100 MB से कम रहता है। हाई‑लेवल API जटिल PostScript कमांड्स को एब्स्ट्रैक्ट करती है, इसलिए आप कच्चे PS ऑपरेटरों के बजाय संक्षिप्त जावा कोड लिखते हैं।

## आवश्यकताएँ
- Java Development Kit (JDK) 8 या नया स्थापित हो।  
- Aspose.Page for Java लाइब्रेरी – इसे **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)** से डाउनलोड करें।  
- Java सिंटैक्स और ऑब्जेक्ट‑ओरिएंटेड प्रोग्रामिंग की बुनियादी समझ।

## जावा में पोस्टस्क्रिप्ट बनाना क्या है?
जावा से PostScript फ़ाइल बनाना मतलब प्रोग्रामेटिक रूप से एक `.ps` दस्तावेज़ जेनरेट करना है जो पेज लेआउट, वेक्टर ग्राफ़िक्स और रास्टर इमेज को PostScript भाषा में वर्णित करता है। Aspose.Page आपके जावा कॉल्स को वैध PostScript निर्देशों में बदल देता है, जिससे आप बिना अलग PostScript इंटरप्रेटर के प्रिंट‑रेडी फ़ाइलें बना सकते हैं।

## ट्रांसलेशन और रोटेशन के साथ इमेज जोड़ने के चरण-दर-चरण

इमेज लोड करें, `AffineTransform` लागू करें, और पेज पर ड्रॉ करें। नीचे दिए गए चरणों में आपको ठीक‑ठीक क्रम बताया गया है जिसे आपको फॉलो करना है।

### चरण 1: ग्राफ़िक्स सहेजें
ग्राफ़िक्स स्टेट को सेव करने से आपके ट्रांसफ़ॉर्म अलग हो जाते हैं और बाद में आप उन्हें रिवर्ट कर सकते हैं। यह कच्चे PostScript में `gsave` ऑपरेटर के बराबर है।

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### चरण 2: ट्रांसलेट और ट्रांसफ़ॉर्म (इमेज को ट्रांसलेट और रोटेट करें)
पहले स्रोत फ़ाइल से एक `BufferedImage` बनाएं, फिर एक `AffineTransform` बनाएं जो इमेज को वांछित निर्देशांक पर ट्रांसलेट करे और उसके केंद्र के चारों ओर रोटेट करे। `AffineTransform.rotate` रैडियन में एंगल लेता है, इसलिए डिग्री को `Math.toRadians(degrees)` से बदलें।

**AffineTransform** एक जावा क्लास है जो 2‑D अफ़ाइन ट्रांसफ़ॉर्मेशन (जैसे ट्रांसलेशन, रोटेशन, स्केलिंग या शीयरिंग) को दर्शाता है।  
**BufferedImage** एक जावा क्लास है जो इमेज को पिक्सेल रास्टर के रूप में मेमोरी में स्टोर करता है।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### चरण 3: दस्तावेज़ में इमेज जोड़ें
ट्रांसफ़ॉर्म कॉन्फ़िगर करने के बाद, इमेज को वर्तमान पेज पर ड्रॉ करें। लाइब्रेरी स्वचालित रूप से `BufferedImage` को उपयुक्त PostScript इमेज स्ट्रीम में बदल देती है।

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### चरण 4: ग्राफ़िक्स पुनर्स्थापित करें
`grestore` को कॉल करने से ग्राफ़िक्स स्टेट उस स्थिति में लौट आती है जो सेव करने से पहले थी, जिससे बाद के ड्रॉ कमांड्स पिछले ट्रांसफ़ॉर्म से प्रभावित नहीं होते।

```java
document.drawImage(image, transform, null);
```

### चरण 5: वर्तमान पेज बंद करें और सहेजें
पेज को समाप्त करें, दस्तावेज़ को बंद करें, और आउटपुट फ़ाइल को डिस्क पर लिखें।

```java
document.writeGraphicsRestore();
```

आप ऊपर दिए गए क्रम को दोहरा सकते हैं ताकि अतिरिक्त इमेज एम्बेड की जा सके, प्रत्येक बार ट्रांसलेशन कॉर्डिनेट्स और रोटेशन एंगल को समायोजित करते हुए।

## सामान्य समस्याएँ और समाधान
- **FileNotFoundException:** सुनिश्चित करें कि `dataDir` फ़ाइल सेपरेटर (`/` या `\\`) पर समाप्त हो और इमेज फ़ाइलनाम बिल्कुल मेल खाता हो।  
- **ImageIO.read returns null:** पुष्टि करें कि इमेज फ़ॉर्मेट समर्थित सूची (JPEG, PNG, BMP, GIF, TIFF) में है।  
- **Incorrect rotation angle:** `AffineTransform.rotate` रैडियन में काम करता है; डिग्री को रैडियन में बदलने के लिए `Math.toRadians(degrees)` उपयोग करें।  
- **Memory spikes on large pages:** मेमोरी फुटप्रिंट कम करने के लिए `Document.save` के साथ `saveOptions.setCompress(true)` उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Page for Java को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?**  
A: कोर लाइब्रेरी केवल Java‑only है, लेकिन Aspose .NET, C++, और Python के लिए समकक्ष API प्रदान करता है, प्रत्येक अपने प्लेटफ़ॉर्म के अनुसार अनुकूलित।

**Q: क्या Aspose.Page for Java के लिए कोई फ्री ट्रायल उपलब्ध है?**  
A: हाँ, आप फ्री ट्रायल **[Aspose.Page free trial page](https://releases.aspose.com/)** तक पहुँच सकते हैं।

**Q: Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A: आप अस्थायी लाइसेंस **[temporary license request page](https://purchase.aspose.com/temporary-license/)** से प्राप्त कर सकते हैं।

**Q: Aspose.Page for Java से संबंधित समुदाय समर्थन और चर्चा कहाँ मिल सकती है?**  
A: समुदाय सहायता के लिए **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** देखें।

**Q: Aspose.Page for Java खरीदने के अतिरिक्त संसाधन कौन‑से हैं?**  
A: आप लाइब्रेरी **[Aspose.Page purchase page](https://purchase.aspose.com/buy)** से खरीद सकते हैं।

## निष्कर्ष
अब आपके पास **aspose.page इमेज मैनिपुलेशन जावा** का एक पूर्ण, अंत‑से‑अंत उदाहरण है जो PostScript फ़ाइल बनाता है, इमेज को ट्रांसलेट और रोटेट करता है, और परिणाम को सहेजता है। उन्नत सुविधाओं जैसे वेक्टर ग्राफ़िक्स, कस्टम पेज साइज, और टेक्स्ट रेंडरिंग के लिए पूरी **[documentation](https://reference.aspose.com/page/java/)** देखें।

---

**अंतिम अपडेट:** 2026-08-23  
**परीक्षित संस्करण:** Aspose.Page for Java 23.11  
**लेखक:** Aspose  








```java
document.closePage();
document.save();
```

## संबंधित ट्यूटोरियल

- [Aspose.Page जावा API का उपयोग करके पोस्टस्क्रिप्ट को PDF में कैसे बदलें](/page/java/postscript-conversion/to-pdf/)
- [ग्रेडिएंट जोड़ना: Aspose.Page जावा का उपयोग करके जावा पोस्टस्क्रिप्ट में डायगोनल ग्रेडिएंट](/page/java/postscript-gradient-addition/diagonal/)
- [Aspose.Page के साथ जावा पोस्टस्क्रिप्ट में हैच पैटर्न कैसे जोड़ें](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}