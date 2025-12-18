---
date: 2025-12-18
description: जावा में पोस्टस्क्रिप्ट दस्तावेज़ बनाना और Aspose.Page for Java का उपयोग
  करके पारदर्शी छवि जोड़ना सीखें। यह गाइड दिखाता है कि पोस्टस्क्रिप्ट में छवि को आसानी
  से कैसे जोड़ें।
linktitle: Create PostScript Document Java – Add Transparent Image
second_title: Aspose.Page Java API
title: PostScript दस्तावेज़ जावा बनाएं – पारदर्शी छवि जोड़ें
url: /hi/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा पोस्टस्क्रिप्ट में पारदर्शी छवि जोड़ें

## परिचय
जावा पोस्टस्क्रिप्ट की दुनिया में, दस्तावेज़ों की दृश्य आकर्षण को बढ़ाने के लिए अक्सर पारदर्शी छवियों को जोड़ना शामिल होता है। यह ट्यूटोरियल आपको **create postscript document java** प्रक्रिया के माध्यम से मार्गदर्शन करेगा, जबकि शक्तिशाली Aspose.Page for Java लाइब्रेरी का उपयोग करके पारदर्शी ग्राफ़िक्स को शामिल करेगा। आप देखेंगे कि पोस्टस्क्रिप्ट में छवि कैसे जोड़ें, उसे सटीक रूप से कैसे स्थित करें, और पेशेवर दिखने वाले परिणामों के लिए उसकी अपारदर्शिता (opacity) को कैसे नियंत्रित करें।

## त्वरित उत्तर
- **इस ट्यूटोरियल में क्या कवर किया गया है?** Adding a transparent PNG to a PostScript document with Aspose.Page for Java.  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java (download from the official website).  
- **क्या मुझे लाइसेंस चाहिए?** उत्पादन के लिए एक अस्थायी या पूर्ण लाइसेंस आवश्यक है; एक मुफ्त ट्रायल उपलब्ध है।  
- **क्या मैं अन्य इमेज फ़ॉर्मेट उपयोग कर सकता हूँ?** हाँ, लेकिन पारदर्शिता के लिए PNG जिसमें अल्फा चैनल हो, सबसे अच्छा काम करता है।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** एक बुनियादी उदाहरण के लिए लगभग 10‑15 मिनट।

## जावा में PostScript दस्तावेज़ क्या है?
PostScript दस्तावेज़ एक पेज डिस्क्रिप्शन लैंग्वेज फ़ाइल है जो टेक्स्ट, ग्राफ़िक्स और इमेजेज़ का वर्णन करती है। जावा का उपयोग करके, आप प्रोग्रामेटिक रूप से इन फ़ाइलों को जनरेट कर सकते हैं, जिससे आपको लेआउट और रेंडरिंग पर पूर्ण नियंत्रण मिलता है। प्रमुख कीवर्ड **create postscript document java** इस क्षमता को दर्शाता है।

## पारदर्शी छवियां क्यों जोड़ें?
पारदर्शी छवियां आपको ग्राफ़िक्स को ओवरले करने देती हैं बिना नीचे की सामग्री को छुपाए, जो वॉटरमार्क, लोगो या सजावटी तत्वों के लिए आदर्श है। पारदर्शिता को सटीक पोजिशनिंग के साथ मिलाकर परिष्कृत, ब्रांड‑संगत दस्तावेज़ बनते हैं।

## पूर्वापेक्षाएँ
ट्यूटोरियल में डुबकी लगाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1. Java Development Kit (JDK): सुनिश्चित करें कि आपके मशीन पर नवीनतम JDK स्थापित है।  
2. Aspose.Page for Java: Aspose.Page for Java लाइब्रेरी को [website](https://releases.aspose.com/page/java/) से डाउनलोड और इंस्टॉल करें।  
3. Document Directory: अपने सिस्टम पर एक डायरेकरी बनाएं जहाँ आप अपने Java PostScript दस्तावेज़ संग्रहीत करेंगे।  
4. Translucent Image File: ट्यूटोरियल में उपयोग करने के लिए एक पारदर्शी इमेज फ़ाइल तैयार करें (उदा., "mask1.png")।

## पैकेज इम्पोर्ट करें
अपने Java प्रोजेक्ट में, Aspose.Page for Java द्वारा प्रदान की गई कार्यक्षमताओं का उपयोग करने के लिए आवश्यक पैकेज इम्पोर्ट करें। नीचे वह सटीक इम्पोर्ट ब्लॉक दिया गया है जिसकी आपको आवश्यकता होगी:

```java
import java.awt.Color;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## पारदर्शी छवि के साथ postscript document java कैसे बनाएं?
नीचे चरण‑दर‑चरण गाइड दिया गया है। प्रत्येक चरण में एक संक्षिप्त व्याख्या और उसके बाद मूल कोड ब्लॉक (अपरिवर्तित) शामिल है।

### चरण 1: बैकग्राउंड रंग सेट करें
हम पोस्टस्क्रिप्ट दस्तावेज़ बनाकर, एक आउटपुट स्ट्रीम खोलकर, और पारदर्शी छवि के लिए एक दृश्य संदर्भ के रूप में लाल आयत पेंट करके शुरू करते हैं।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTransparentImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Add a red rectangle under images for visual contrast
document.setPaint(new Color(211, 8, 48));
document.fill(new Rectangle2D.Float(0, 0, (int) options.getPageSize().getWidth(), 300));
```

### चरण 2: निर्देशांक ट्रांसलेट करें
ड्रॉ करने से पहले, हम पेज पर एक सुविधाजनक स्थान पर मूल बिंदु को ले जाते हैं ताकि छवि वहीँ दिखाई दे जहाँ हम चाहते हैं।

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

### चरण 3: इमेज ऑब्जेक्ट बनाएं
PNG फ़ाइल लोड करें जिसमें अल्फा चैनल हो। इस छवि का उपयोग अपारदर्शी और पारदर्शी दोनों रेंडरिंग के लिए किया जाएगा।

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

### चरण 4: अपारदर्शी छवि जोड़ें
पहले, हम छवि को एक सामान्य RGB बिटमैप के रूप में ड्रॉ करते हैं। यह बाद में पारदर्शिता लागू करने पर अंतर दिखाता है।

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

### चरण 5: पारदर्शी छवि जोड़ें
अब हम वही छवि पूर्ण अपारदर्शिता (255) या 0‑255 के बीच कोई भी मान उपयोग करके पारदर्शिता नियंत्रित करते हुए ड्रॉ करते हैं। यहाँ हम पूर्ण अपारदर्शिता के लिए 255 का उपयोग करते हैं, लेकिन आप देख‑सकने वाला प्रभाव पाने के लिए मान को कम कर सकते हैं।

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

### चरण 6: सहेजें और बंद करें
अंत में, हम ग्राफ़िक्स स्टेट को पुनर्स्थापित करते हैं, पेज को बंद करते हैं, और दस्तावेज़ को डिस्क पर सहेजते हैं।

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## सामान्य समस्याएँ और समाधान
- **FileNotFoundException** – सुनिश्चित करें कि `dataDir` सही फ़ोल्डर की ओर इशारा कर रहा है और `mask1.png` मौजूद है।  
- **ImageIO.read returns null** – सुनिश्चित करें कि PNG का फ़ॉर्मेट वैध है और वह करप्ट नहीं है।  
- **Transparent image appears opaque** – `drawTransparentImage` के तीसरे पैरामीटर को समायोजित करें (0 = पूरी तरह पारदर्शी, 255 = पूरी तरह अपारदर्शी)।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?
हाँ, Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ सहजता से एकीकृत किया जा सकता है ताकि दस्तावेज़ प्रोसेसिंग क्षमताओं को बढ़ाया जा सके।

### क्या Aspose.Page for Java के लिए मुफ्त ट्रायल उपलब्ध है?
हाँ, आप Aspose.Page for Java का मुफ्त ट्रायल [here](https://releases.aspose.com/) से प्राप्त कर सकते हैं।

### मैं Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
आप एक अस्थायी लाइसेंस [this link](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

### क्या Aspose.Page for Java समर्थन के लिए कोई फ़ोरम हैं?
हाँ, समुदाय समर्थन और चर्चाओं के लिए [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) पर जाएँ।

### मैं Aspose.Page for Java की डॉक्यूमेंटेशन कहाँ पा सकता हूँ?
विस्तृत जानकारी के लिए व्यापक [documentation](https://reference.aspose.com/page/java/) देखें।

## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक **create postscript document java** और Aspose.Page for Java का उपयोग करके पारदर्शी छवियां जोड़ना सीख लिया है। विभिन्न छवियों, अपारदर्शिता स्तरों और स्थितियों के साथ प्रयोग करें ताकि आप अपने ब्रांडिंग आवश्यकताओं को पूरा करने वाले दृश्य रूप से शानदार दस्तावेज़ बना सकें।

---

**अंतिम अपडेट:** 2025-12-18  
**परीक्षण किया गया:** Aspose.Page for Java 24.11 (लेखन के समय नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}