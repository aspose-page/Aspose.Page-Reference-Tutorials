---
date: 2026-03-05
description: जावा में बैकग्राउंड रंग कैसे सेट करें और Aspose.Page for Java का उपयोग
  करके पोस्टस्क्रिप्ट में पारदर्शी छवियाँ जोड़ना सीखें। PNG को आसानी से पोस्टस्क्रिप्ट
  में परिवर्तित करें।
linktitle: Add Transparent Image in Java PostScript
second_title: Aspose.Page Java API
title: 'पृष्ठभूमि रंग सेट करें जावा: पीएस में पारदर्शी छवि जोड़ें'
url: /hi/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# बैकग्राउंड कलर सेट करें जावा: पोस्टस्क्रिप्ट में ट्रांसपेरेंट इमेज जोड़ें

## परिचय
यदि आपको Java PostScript के साथ काम करते समय **set background color java** करने की आवश्यकता है, तो ट्रांसपेरेंट इमेज जोड़ने से आपके दस्तावेज़ों को एक पॉलिश्ड, प्रोफेशनल लुक मिल सकता है। इस ट्यूटोरियल में हम आपको रंगीन बैकग्राउंड सेट करने, PNG को PostScript में कन्वर्ट करने, और Aspose.Page for Java लाइब्रेरी का उपयोग करके अपारदर्शी और पारदर्शी दोनों इमेज ड्रॉ करने की पूरी प्रक्रिया से गुजरेंगे। अंत में आप **add image to postscript** फ़ाइलों में अपारदर्शिता पर पूर्ण नियंत्रण के साथ इमेज जोड़ सकेंगे।

## त्वरित उत्तर
- **Java PostScript में ट्रांसपेरेंसी को कौनसी लाइब्रेरी संभालती है?** Aspose.Page for Java.  
- **क्या मैं इमेज ड्रॉ करने से पहले बैकग्राउंड कलर सेट कर सकता हूँ?** Yes – use `document.setPaint()` and `fill()`.  
- **PNG को PostScript में कैसे कन्वर्ट करें?** Load the PNG with `ImageIO.read()` and draw it with `drawImage` or `drawTransparentImage`.  
- **क्या इमेज के लिए अपारदर्शिता समर्थित है?** Use `drawTransparentImage` to specify an opacity value (0‑255).  
- **क्या प्रोडक्शन उपयोग के लिए लाइसेंस की आवश्यकता है?** A valid Aspose.Page for Java license is required; a free trial is available.

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:

1. **Java Development Kit (JDK)** – नवीनतम संस्करण स्थापित हो।  
2. **Aspose.Page for Java** – इसे [website](https://releases.aspose.com/page/java/) से डाउनलोड करें।  
3. **Document Directory** – वह फ़ोल्डर जहाँ आप PostScript फ़ाइलें लिखेंगे।  
4. **Translucent Image File** – उदाहरण के लिए `mask1.png`, जिसे हम ट्रांसपेरेंसी दिखाने के लिए उपयोग करेंगे।

## पैकेज इम्पोर्ट करें
अपने Java प्रोजेक्ट में आवश्यक क्लासेस इम्पोर्ट करें। यह ब्लॉक जैसा का तैसा रहेगा:

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

## चरण 1: बैकग्राउंड कलर सेट करें जावा
यहाँ हम दस्तावेज़ बनाते हैं, A4 आकार चुनते हैं, और बैकग्राउंड कंट्रास्ट दिखाने के लिए एक लाल आयत भरते हैं।

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

## चरण 2: कॉर्डिनेट्स ट्रांसलेट करें
इमेज रखने से पहले ड्राइंग कर्सर को पेज पर एक सुविधाजनक स्थान पर ले जाएँ।

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

## चरण 3: इमेज ऑब्जेक्ट बनाएं
PNG फ़ाइल लोड करें (हमारा **convert png to postscript** चरण)।

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

## चरण 4: अपारदर्शी इमेज जोड़ें
इमेज को सामान्य रूप से ड्रॉ करें—यह **add image to postscript** को बिना ट्रांसपेरेंसी के दर्शाता है।

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

## चरण 5: ट्रांसपेरेंट इमेज जोड़ें (अपारदर्शिता के साथ इमेज ड्रॉ करें)
अब हम `drawTransparentImage` का उपयोग करके वही PNG पूर्ण अपारदर्शिता (255) के साथ रेंडर करते हैं। ट्रांसपेरेंसी को नियंत्रित करने के लिए मान को समायोजित करें।

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

## चरण 6: सेव और क्लोज करें
दस्तावेज़ को अंतिम रूप दें और संसाधनों को रिलीज़ करें।

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## यह क्यों महत्वपूर्ण है
Java के साथ बैकग्राउंड कलर सेट करने से आपको एक कैनवास मिलता है जो ओवरले ग्राफिक्स को हाइलाइट कर सकता है। इसे **draw image with opacity** के साथ मिलाकर आप सीधे PostScript में वॉटरमार्क, लोगो, या UI मॉक‑अप बना सकते हैं, बिना बाहरी एडिटिंग टूल्स की आवश्यकता के।

## सामान्य समस्याएँ और टिप्स
- **इमेज ट्रांसपेरेंट नहीं दिख रही है:** सुनिश्चित करें कि PNG में वास्तव में अल्फा चैनल है।  
- **गलत रंग:** याद रखें कि बैकग्राउंड आयत इमेज से पहले ड्रॉ की जाती है; अपने डिज़ाइन के अनुसार `Color` मान बदलें।  
- **परफ़ॉर्मेंस:** बड़े दस्तावेज़ों के लिए, एक ही `AffineTransform` इंस्टेंस को पुन: उपयोग करें ताकि ऑब्जेक्ट निर्माण ओवरहेड कम हो।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ सहजता से एकीकृत किया जा सकता है ताकि दस्तावेज़ प्रोसेसिंग क्षमताओं को बढ़ाया जा सके।

**Q: क्या Aspose.Page for Java का फ्री ट्रायल उपलब्ध है?**  
A: हाँ, आप Aspose.Page for Java का फ्री ट्रायल [here](https://releases.aspose.com/) से एक्सेस कर सकते हैं।

**Q: मैं Aspose.Page for Java के लिए टेम्पररी लाइसेंस कैसे प्राप्त कर सकता हूँ?**  
A: आप टेम्पररी लाइसेंस [this link](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

**Q: क्या Aspose.Page for Java सपोर्ट के लिए कोई फ़ोरम हैं?**  
A: हाँ, समुदाय समर्थन और चर्चा के लिए [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) पर जाएँ।

**Q: मैं Aspose.Page for Java की डॉक्यूमेंटेशन कहाँ पा सकता हूँ?**  
A: विस्तृत जानकारी के लिए व्यापक [documentation](https://reference.aspose.com/page/java/) देखें।

---

**अंतिम अपडेट:** 2026-03-05  
**परीक्षित संस्करण:** Aspose.Page for Java 24.11 (latest)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}