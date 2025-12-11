---
date: 2025-12-09
description: Aspose.Page का उपयोग करके सहज इमेज मैनिपुलेशन के लिए जावा में पोस्टस्क्रिप्ट
  दस्तावेज़ बनाना और इमेज को ट्रांसलेट व रोटेट करना सीखें।
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: जावा में पोस्टस्क्रिप्ट दस्तावेज़ बनाएं – जावा पोस्टस्क्रिप्ट में छवि जोड़ें
url: /hi/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript दस्तावेज़ जावा बनाएं – जावा PostScript में इमेज जोड़ें

## परिचय
इस ट्यूटोरियल में, आप सीखेंगे कि **PostScript दस्तावेज़ जावा** कैसे बनाएं और Aspose.Page for Java लाइब्रेरी का उपयोग करके इमेजेज़ को एम्बेड करें। हम प्रत्येक चरण को विस्तार से बताएंगे, दस्तावेज़ सेटअप से लेकर **translate और rotate image** जैसी ट्रांसफ़ॉर्मेशन लागू करने तक। अंत तक, आप प्रोग्रामेटिक रूप से समृद्ध PostScript फ़ाइलें जेनरेट कर सकेंगे और इमेज प्लेसमेंट को अपनी लेआउट आवश्यकताओं के अनुसार कस्टमाइज़ कर सकेंगे।

## त्वरित उत्तर
- **क्या लाइब्रेरी आवश्यक है?** Aspose.Page for Java  
- **क्या मैं कई इमेजेज़ जोड़ सकता हूँ?** हाँ – ट्रांसफ़ॉर्म और ड्रॉ चरणों को दोहराएँ  
- **क्या विकास के लिए लाइसेंस चाहिए?** परीक्षण के लिए फ्री ट्रायल काम करता है; प्रोडक्शन के लिए लाइसेंस आवश्यक है  
- **कौन सा जावा संस्करण समर्थित है?** Java 8 और बाद के संस्करण  
- **क्या इमेज रोटेशन समर्थित है?** बिल्कुल – `AffineTransform.rotate()` का उपयोग करें  

## जावा में PostScript दस्तावेज़ बनाना क्या है?
PostScript दस्तावेज़ एक पेज डिस्क्रिप्शन लैंग्वेज फ़ाइल है जो टेक्स्ट, ग्राफ़िक्स और इमेजेज़ का वर्णन करती है। Aspose.Page का उपयोग करके, आप जावा में इन फ़ाइलों को प्रोग्रामेटिक रूप से जेनरेट कर सकते हैं, जिससे आपको लेआउट, ग्राफ़िक्स स्टेट और इमेज हैंडलिंग पर पूर्ण नियंत्रण मिलता है, बिना किसी PostScript इंटरप्रेटर की आवश्यकता के।

## इमेज मैनिपुलेशन के लिए Aspose.Page क्यों उपयोग करें?
- **हाई‑लेवल API:** जटिल PostScript कमांड्स को सरल बनाता है।  
- **क्रॉस‑प्लेटफ़ॉर्म:** किसी भी OS पर काम करता है जो जावा को सपोर्ट करता है।  
- **पूर्ण ग्राफ़िक्स स्टेट कंट्रोल:** ग्राफ़िक्स को आसानी से सेव, रिस्टोर, ट्रांसलेट, स्केल और रोटेट कर सकते हैं।  
- **कोई बाहरी निर्भरताएँ नहीं:** इमेज लोडिंग और कन्वर्ज़न को आंतरिक रूप से संभालता है।  

## पूर्वापेक्षाएँ
कोड में जाने से पहले, सुनिश्चित करें कि आपके पास है:

- आपके सिस्टम पर स्थापित Java Development Kit (JDK)।  
- Aspose.Page for Java लाइब्रेरी। आप इसे [here](https://releases.aspose.com/page/java/) से डाउनलोड कर सकते हैं।  
- जावा प्रोग्रामिंग की बुनियादी समझ।

## पैकेज इम्पोर्ट करें
शुरू करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज इम्पोर्ट करें। नीचे दिया गया कोड स्निपेट संदर्भ के रूप में उपयोग करें:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## चरण 1: ग्राफ़िक्स सेव लिखें
पहला चरण दस्तावेज़ में ग्राफ़िक्स सेव लिखने से संबंधित है। यह सुनिश्चित करता है कि बाद में किए गए किसी भी ट्रांसफ़ॉर्मेशन या संशोधन को आवश्यकता पड़ने पर वापस किया जा सके।

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

## चरण 2: ट्रांसलेट और ट्रांसफ़ॉर्म (translate और rotate image)
अगला, दस्तावेज़ को ट्रांसलेट करें और इमेज फ़ाइल से एक `BufferedImage` ऑब्जेक्ट बनाएं। `AffineTransform` का उपयोग करके स्केलिंग और रोटेशन जैसी कई ट्रांसफ़ॉर्मेशन लागू करें। यहाँ **translate और rotate image** ऑपरेशन होता है।

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

## चरण 3: दस्तावेज़ में इमेज जोड़ें
अब, ट्रांसफ़ॉर्म की गई इमेज को दस्तावेज़ में जोड़ें।

```java
document.drawImage(image, transform, null);
```

## चरण 4: ग्राफ़िक्स रिस्टोर लिखें
इमेज जोड़ने के बाद, किए गए बदलावों को अंतिम रूप देने के लिए ग्राफ़िक्स रिस्टोर लिखें।

```java
document.writeGraphicsRestore();
```

## चरण 5: वर्तमान पेज बंद करें और सहेजें
वर्तमान पेज को बंद करें और दस्तावेज़ को सहेजें।

```java
document.closePage();
document.save();
```

आप इन चरणों को दोहराकर कई इमेजेज़ जोड़ सकते हैं या अपनी आवश्यकताओं के अनुसार ट्रांसफ़ॉर्मेशन को कस्टमाइज़ कर सकते हैं।

## सामान्य समस्याएँ और समाधान
- **FileNotFoundException:** सुनिश्चित करें कि `dataDir` पाथ फ़ाइल सेपरेटर (`/` या `\\`) पर समाप्त हो और इमेज फ़ाइल का नाम बिल्कुल मेल खाता हो।  
- **ImageIO.read returns null:** जांचें कि इमेज फ़ॉर्मेट समर्थित है (जैसे, JPEG, PNG)।  
- **Incorrect rotation angle:** `AffineTransform.rotate` रैडियन की अपेक्षा करता है। आवश्यकता होने पर डिग्री को रैडियन में बदलें (`Math.toRadians(degrees)`)।

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या मैं Aspose.Page for Java को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?**  
**उ:** Aspose.Page मुख्यतः जावा को सपोर्ट करता है, लेकिन अन्य प्रोग्रामिंग भाषाओं के लिए भी संस्करण उपलब्ध हैं।

**प्र: क्या Aspose.Page for Java के लिए फ्री ट्रायल उपलब्ध है?**  
**उ:** हाँ, आप फ्री ट्रायल [here](https://releases.aspose.com/) से एक्सेस कर सकते हैं।

**प्र: Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
**उ:** आप अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

**प्र: Aspose.Page for Java से संबंधित समुदाय समर्थन और चर्चाएँ कहाँ मिलेंगी?**  
**उ:** समुदाय समर्थन के लिए [Aspose.Page Forum](https://forum.aspose.com/c/page/39) पर जाएँ।

**प्र: Aspose.Page for Java खरीदने के लिए कोई अतिरिक्त संसाधन हैं?**  
**उ:** आप लाइब्रेरी [here](https://purchase.aspose.com/buy) से खरीद सकते हैं।

## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक **PostScript दस्तावेज़ जावा** बनाना और Aspose.Page for Java का उपयोग करके इमेजेज़ एम्बेड करना सीख लिया है। अधिक उन्नत फीचर्स और कार्यक्षमताओं, जैसे वेक्टर ग्राफ़िक्स, टेक्स्ट रेंडरिंग, और कस्टम पेज साइज के लिए [documentation](https://reference.aspose.com/page/java/) देखें।

---

**अंतिम अपडेट:** 2025-12-09  
**परीक्षित संस्करण:** Aspose.Page for Java 23.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}