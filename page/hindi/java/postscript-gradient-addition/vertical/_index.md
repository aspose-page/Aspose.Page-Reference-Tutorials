---
date: 2026-09-14
description: Aspose.Page के साथ PostScript ग्रेडिएंट जावा बनाना सीखें। यह स्टेप‑बाय‑स्टेप
  गाइड आपको दिखाता है कि कैसे कुछ ही Java कोड की पंक्तियों में PostScript फ़ाइल में
  वर्टिकल ग्रेडिएंट जोड़ा जाए।
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: Java PostScript में वर्टिकल ग्रेडिएंट जोड़ें
og_description: Aspose.Page के साथ PostScript ग्रेडिएंट जावा बनाना सीखें। यह स्टेप‑बाय‑स्टेप
  गाइड आपको दिखाता है कि कैसे कुछ ही Java कोड की पंक्तियों में PostScript फ़ाइल में
  वर्टिकल ग्रेडिएंट जोड़ा जाए।
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: PostScript ग्रेडिएंट जावा बनाएँ – वर्टिकल ग्रेडिएंट
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: PostScript ग्रेडिएंट जावा बनाएँ – वर्टिकल ग्रेडिएंट
url: /hi/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# पोस्टस्क्रिप्ट ग्रेडिएंट जावा बनाएं – वर्टिकल ग्रेडिएंट

## परिचय
Aspose.Page for Java एक लाइब्रेरी है जो प्रोग्रामेटिक रूप से PostScript और PDF फ़ाइलों के निर्माण और हेरफेर को सक्षम बनाती है। इस व्यापक ट्यूटोरियल में आप इस लाइब्रेरी का उपयोग करके **create postscript gradient java** करना सीखेंगे। एक वर्टिकल ग्रेडिएंट जोड़ने से आपके दस्तावेज़ अधिक जीवंत और पेशेवर दिखेंगे, और कुछ ही कोड लाइनों से आप शानदार दृश्य प्रभाव प्राप्त कर सकते हैं। हम आपको प्रत्येक चरण के माध्यम से ले जाएंगे, यह समझाएंगे कि प्रत्येक भाग क्यों महत्वपूर्ण है, और सामान्य गलतियों से बचने के लिए व्यावहारिक टिप्स देंगे। इस गाइड के अंत तक आप ऐसे PostScript फ़ाइलें जनरेट करने में सक्षम होंगे जिनमें सुगम, आँख‑को‑खींचने वाले वर्टिकल रंग परिवर्तन हों।

## त्वरित उत्तर
- **कौनसी लाइब्रेरी आवश्यक है?** Aspose.Page for Java  
- **क्या मैं रंगों को कस्टमाइज़ कर सकता हूँ?** हाँ, कोई भी `java.awt.Color` उपयोग किया जा सकता है  
- **क्या रोटेशन समर्थित है?** हाँ, आप ग्रेडिएंट को `AffineTransform` के साथ घुमा सकते हैं  
- **कौनसा आउटपुट फॉर्मेट उत्पन्न होता है?** एक मानक PostScript (.ps) फ़ाइल  
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** हाँ, एक व्यावसायिक लाइसेंस आवश्यक है  

## PostScript दस्तावेज़ में वर्टिकल ग्रेडिएंट क्यों जोड़ें?
वर्टिकल ग्रेडिएंट जोड़ने से आपके पृष्ठों में गहराई आती है, दृश्य पदानुक्रम सुधरता है, और फ़ाइल आकार कम रहता है क्योंकि ग्रेडिएंट वेक्टर रूप में परिभाषित होता है न कि रास्टर इमेज में। यह तकनीक रिपोर्ट हेडर, तकनीकी मैनुअल या किसी भी फ़्लायर के लिए उपयुक्त है जिसे आधुनिक लुक चाहिए बिना स्केलेबिलिटी का बलिदान किए।

## आवश्यकताएँ
ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित प्री‑रिक्विज़िट्स मौजूद हों:
- अपने मशीन पर Java Development Kit (JDK) स्थापित हो।  
- Aspose.Page for Java लाइब्रेरी। आप इसे [Aspose.Page for Java रिलीज़ पेज](https://releases.aspose.com/page/java/) से डाउनलोड कर सकते हैं।

## पैकेज आयात करें
अपने Java प्रोजेक्ट में आवश्यक पैकेज आयात करें ताकि आप शुरू कर सकें:
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

अब, चलिए वर्टिकल ग्रेडिएंट जोड़ने की प्रक्रिया को चरण‑दर‑चरण देखते हैं।

## पोस्टस्क्रिप्ट ग्रेडिएंट जावा कैसे बनाएं
अपने Java वातावरण को लोड करें, एक `PsSaveOptions` इंस्टेंस बनाएं, और `Document.save` को कॉल करें – यही मूल क्रम है जो वर्टिकल ग्रेडिएंट के साथ एक PostScript फ़ाइल बनाता है। API रंग इंटरपोलेशन, कोऑर्डिनेट ट्रांसफ़ॉर्म, और पेज फ्लशिंग को संभालता है, इसलिए आपको केवल आयत और ग्रेडिएंट पैरामीटर पर ध्यान देना है।

### चरण 1: अपने दस्तावेज़ निर्देशिका सेट करें
`File` ऑब्जेक्ट्स उस फ़ोल्डर को दर्शाते हैं जहाँ आउटपुट लिखा जाएगा। स्ट्रीम खोलने से पहले डायरेक्टरी मौजूद होनी चाहिए, अन्यथा `IOException` फेंका जाएगा।
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### चरण 2: PostScript दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
`FileOutputStream` बाइनरी PostScript डेटा को डिस्क पर लिखता है। `try‑with‑resources` ब्लॉक यह सुनिश्चित करता है कि अपवाद होने पर भी स्ट्रीम बंद हो जाए।
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### चरण 3: A4 आकार के साथ सहेजने के विकल्प बनाएं
`PsSaveOptions` आपको पेज आकार, DPI, और फ़ॉन्ट एम्बेड करने का विकल्प देता है। आकार को A4 (595 × 842 पॉइंट) सेट करने से अधिकांश प्रिंटेबल दस्तावेज़ों से मेल खाता है।
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### चरण 4: नया PS दस्तावेज़ बनाएं
`Document` शीर्ष‑स्तरीय ऑब्जेक्ट है जो मेमोरी में एकल PostScript फ़ाइल का प्रतिनिधित्व करता है। सभी ड्रॉइंग कमांड इस ऑब्जेक्ट के विरुद्ध जारी किए जाते हैं।
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### चरण 5: एक आयत बनाएं
`Rectangle2D.Double` वह क्षेत्र परिभाषित करता है जिसे ग्रेडिएंट से भरना है। आयत के कोऑर्डिनेट पॉइंट्स में व्यक्त होते हैं (1 पॉइंट = 1/72 इंच)।
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### चरण 6: ग्रेडिएंट के लिए रंग और फ्रैक्शन सेट करें
`float[]` एरे प्रत्येक रंग स्टॉप की स्थिति (0.0 से 1.0) निर्धारित करता है। `Color` ऑब्जेक्ट्स वास्तविक RGB मान रखते हैं। आप कोई भी `java.awt.Color` उपयोग कर सकते हैं।
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### चरण 7: ग्रेडिएंट ट्रांसफ़ॉर्म बनाएं
`AffineTransform` ग्रेडिएंट को स्केल और रोटेट करता है। शुद्ध वर्टिकल ग्रेडिएंट के लिए केवल Y‑अक्ष को स्केल करना पर्याप्त है; रोटेशन बाद में जोड़ा जा सकता है।
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### चरण 8: वर्टिकल लीनियर ग्रेडिएंट पेंट बनाएं
`LinearGradientPaint` आयत, रंग स्टॉप और ट्रांसफ़ॉर्म को जोड़ता है। यह ऑब्जेक्ट बाद में ग्राफ़िक्स कॉन्टेक्स्ट को पास किया जाता है।
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### चरण 9: पेंट सेट करें और आयत को भरें
`Graphics2D.setPaint` ग्रेडिएंट लागू करता है, और `fill` इसे पहले परिभाषित आयत के भीतर रेंडर करता है।
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### चरण 10: वर्तमान पृष्ठ बंद करें और दस्तावेज़ सहेजें
`document.save` पूरे PostScript स्ट्रीम को आउटपुट फ़ाइल में लिखता है और सभी नेटिव रिसोर्सेज़ को रिलीज़ करता है।
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

बधाई हो! आपने Aspose.Page for Java का उपयोग करके अपने Java PostScript दस्तावेज़ में सफलतापूर्वक वर्टिकल ग्रेडिएंट जोड़ दिया है।

## सामान्य समस्याएँ और समाधान
- **ग्रेडिएंट सपाट दिख रहा है:** सुनिश्चित करें कि `AffineTransform` का स्केल आयत के आयामों से मेल खाता हो।  
- **रंग फीके दिख रहे हैं:** जाँचें कि आप सही `ColorSpaceType` (SRGB) उपयोग कर रहे हैं और फ्रैक्शन एरे 0.0 से 1.0 तक क्रमबद्ध है।  
- **फ़ाइल नहीं बन रही:** पुष्टि करें कि आउटपुट डायरेक्टरी (`dataDir`) मौजूद है और एप्लिकेशन के पास लिखने की अनुमति है।  

## अक्सर पूछे जाने वाले प्रश्न
**Q: क्या मैं Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.Page for Java को Apache Commons या Spring जैसी अन्य Java लाइब्रेरीज़ के साथ सहजता से काम करने के लिए डिज़ाइन किया गया है।

**Q: क्या Aspose.Page for Java के लिए कोई फ्री ट्रायल उपलब्ध है?**  
A: हाँ, आप एक फ्री ट्रायल प्राप्त कर सकते हैं [free trial download page](https://releases.aspose.com/)।

**Q: अतिरिक्त दस्तावेज़ीकरण कहाँ मिल सकता है?**  
A: विस्तृत दस्तावेज़ीकरण उपलब्ध है [Aspose.Page Java API reference](https://reference.aspose.com/page/java/)।

**Q: मैं Aspose.Page for Java कैसे खरीद सकता हूँ?**  
A: आप Aspose.Page for Java खरीद सकते हैं [Aspose.Page purchase page](https://purchase.aspose.com/buy)।

**Q: क्या Aspose.Page के लिए कोई फ़ोरम है?**  
A: हाँ, आप समुदाय फ़ोरम में शामिल हो सकते हैं [Aspose.Page community forum](https://forum.aspose.com/c/page/39)।

## अतिरिक्त अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं अन्य ग्रेडिएंट दिशाएँ (हॉरिज़ॉन्टल, डायगोनल) बना सकता हूँ?**  
A: बिल्कुल। `LinearGradientPaint` में प्रारंभ और समाप्ति बिंदुओं को समायोजित करें और `AffineTransform` में रोटेशन एंगल बदलें।

**Q: क्या यह PDF आउटपुट के साथ भी काम करता है?**  
A: वही ग्रेडिएंट लॉजिक PDF में सहेजते समय `PsSaveOptions` के बजाय `PdfSaveOptions` उपयोग करके लागू किया जा सकता है।

**Q: ग्रेडिएंट का आकार डायनामिक रूप से कैसे बदलूँ?**  
A: रन‑टाइम पर आयत के आयामों की गणना करें और उन मानों को `Rectangle2D` और `AffineTransform` कंस्ट्रक्टर दोनों को पास करें।

---

**अंतिम अपडेट:** 2026-09-14  
**परीक्षण किया गया:** Aspose.Page for Java 24.11 (latest)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Create Radial Gradient in PostScript with Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [How to Convert PostScript to PDF Using Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Aspose.Page Transparency Tutorial – Add Transparency in Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}