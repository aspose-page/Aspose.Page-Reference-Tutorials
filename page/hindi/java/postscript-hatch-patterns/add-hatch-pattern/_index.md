---
date: 2025-12-08
description: Aspose.Page Java का उपयोग करके Java PostScript दस्तावेज़ों में हैच पैटर्न
  कैसे जोड़ें, सीखें। यह चरण‑दर‑चरण गाइड आपको दिखाता है कि हैच पैटर्न ग्राफ़िक्स को
  प्रभावी ढंग से कैसे जोड़ें।
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: जावा पोस्टस्क्रिप्ट में हैच पैटर्न जोड़ें'
url: /hi/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript में Hatch पैटर्न जोड़ें

## परिचय
यदि आप **Aspose.Page Java** के साथ काम कर रहे हैं और अपने PostScript आउटपुट को टेक्सचर ग्राफ़िक्स से समृद्ध करना चाहते हैं, तो Hatch पैटर्न एक तेज़ और लचीला समाधान है। इस ट्यूटोरियल में हम **how to add hatch** डिज़ाइनों को एक PostScript दस्तावेज़ में जोड़ने की प्रक्रिया को समझेंगे, यह बताएँगे कि ये क्यों उपयोगी हैं, और आपको एक पूर्ण, तैयार‑चलाने‑योग्य कोड उदाहरण देंगे। अंत तक, आप केवल कुछ Java लाइनों से दृश्यात्मक रूप से आकर्षक Hatch‑भरे आकार और टेक्स्ट बना पाएँगे।

## त्वरित उत्तर
- **मुझे कौनसी लाइब्रेरी चाहिए?** Aspose.Page for Java (the “aspose page java” SDK).  
- **हम कौनसा विज़ुअल इफ़ेक्ट जोड़ रहे हैं?** Hatch पैटर्न (जैसे, तिरछी रेखाएँ, क्रॉसहैच)।  
- **क्या सैंपल चलाने के लिए लाइसेंस चाहिए?** विकास के लिए फ्री ट्रायल काम करता है; प्रोडक्शन के लिए लाइसेंस आवश्यक है।  
- **कोड की कितनी लाइन्स हैं?** लगभग 70 लाइन्स, स्पष्ट चरणों में विभाजित।  
- **क्या मैं PDFs के लिए भी यही तरीका इस्तेमाल कर सकता हूँ?** हाँ—Aspose.Page कई आउटपुट फॉर्मैट्स को सपोर्ट करता है, जिसमें PDF भी शामिल है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

- **Java विकास पर्यावरण** – JDK 8 या उससे ऊपर और आपका पसंदीदा IDE।  
- **Aspose.Page for Java लाइब्रेरी** – आधिकारिक साइट से नवीनतम JAR डाउनलोड करें [here](https://releases.aspose.com/page/java/).  
- **लिखने की अनुमति** उस फ़ोल्डर में जहाँ उत्पन्न PostScript फ़ाइल सहेजी जाएगी।

## पैकेज इम्पोर्ट करें
सबसे पहले, आवश्यक क्लासेज़ को अपने प्रोजेक्ट में लाएँ। ये इम्पोर्ट्स आपको ड्रॉइंग प्रिमिटिव्स, रंग हैंडलिंग, और Aspose.Page API तक पहुँच प्रदान करते हैं।

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## चरण 1: प्रारंभिक पैरामीटर सेट करें
आउटपुट स्ट्रीम बनाएँ, पेज साइज (A4) कॉन्फ़िगर करें, और कुछ लेआउट वेरिएबल्स को परिभाषित करें जो प्रत्येक Hatch‑भरे वर्ग को ड्रॉ करते समय पुनः उपयोग किए जाएंगे।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## चरण 2: ग्राफ़िक्स स्टेट सहेजें और ट्रांसलेट करें
ग्राफ़िक्स स्टेट को सहेजने से बाद में मूल कोऑर्डिनेट सिस्टम पर लौटना आसान हो जाता है, जबकि `translate` मूल बिंदु को एक सुविधाजनक प्रारंभिक बिंदु पर ले जाता है।

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## चरण 3: प्रत्येक पैटर्न के लिए वर्ग बनाएं
एक पुन: उपयोग योग्य आयत (रैक्टैंगल) परिभाषित करें जो प्रत्येक Hatch‑भरे सेल का प्रतिनिधित्व करेगा।

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## चरण 4: पैटर्न वर्ग की रूपरेखा के लिए पेन सेट करें
2 पॉइंट की `BasicStroke` प्रत्येक वर्ग के चारों ओर एक स्पष्ट रूपरेखा देती है।

```java
BasicStroke stroke = new BasicStroke(2);
```

## चरण 5: Hatch पैटर्न के माध्यम से इटररेट करें
`HatchStyle` एन्नुम के प्रत्येक मान पर लूप करें, प्रत्येक वर्ग को संबंधित टेक्सचर से भरें, और फिर उसकी रूपरेखा ड्रॉ करें। यह **adding hatch pattern** कार्यक्षमता का मुख्य भाग है।

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## चरण 6: ग्राफ़िक्स स्टेट पुनर्स्थापित करें
ग्रिड ऑफ़ स्क्वेयर्स को ड्रॉ करने के बाद मूल कोऑर्डिनेट सिस्टम पर लौटें।

```java
document.writeGraphicsRestore();
```

## चरण 7: Hatch पैटर्न के साथ टेक्स्ट भरें
यहाँ हम दिखाते हैं कि कैसे Hatch टेक्सचर का उपयोग करके टेक्स्ट को पेंट किया जाता है। उदाहरण में शब्द “ABC” को एक डायगोनल‑क्रॉस पैटर्न से भरा गया है।

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## चरण 8: Hatch पैटर्न के साथ टेक्स्ट की रूपरेखा बनाएं
अब हम उसी टेक्स्ट की रूपरेखा बनाते हैं, लेकिन इस बार 70 % Hatch स्टाइल और मोटी स्ट्रोक का उपयोग करते हैं।

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## चरण 9: दस्तावेज़ बंद करें और सहेजें
पेज को फाइनलाइज़ करें, फ़ाइल को डिस्क पर लिखें, और रिसोर्सेज़ को रिलीज़ करें।

```java
document.closePage();
document.save();
```

इन चरणों का पालन करें, और आपके पास एक PostScript फ़ाइल होगी जो आकार और टेक्स्ट दोनों पर लागू पूर्ण Hatch पैटर्न सेट को प्रदर्शित करती है—सभी **aspose page java** द्वारा संचालित।

## Aspose.Page Java के साथ Hatch पैटर्न क्यों उपयोग करें?
- **विज़ुअल अंतर** – Hatch फ़िल्स प्रिंटरों के मोनोक्रोम आउटपुट तक सीमित होने पर भी काम करते हैं।  
- **परफ़ॉर्मेंस** – टेक्सचर ऑन‑द‑फ्लाई जेनरेट होते हैं, जिससे बड़े इमेज फ़ाइलों से बचा जा सकता है।  
- **क्रॉस‑फ़ॉर्मेट सपोर्ट** – वही कोड न्यूनतम बदलावों के साथ PDF, EPS, या SVG को टार्गेट कर सकता है।

## सामान्य समस्याएँ और टिप्स
- **फ़ाइल पाथ त्रुटियाँ** – सुनिश्चित करें कि `dataDir` उचित फ़ाइल‑सेपरेटर (`/` या `\`) पर समाप्त हो।  
- **असमर्थित रंग** – कुछ पुराने PostScript इंटरप्रेटर कुछ कलर स्पेसेस को संभाल नहीं सकते; अधिकतम संगतता के लिए बेसिक RGB उपयोग करें।  
- **लाइसेंस चेतावनियाँ** – वैध लाइसेंस के बिना सैंपल चलाने पर आउटपुट में वॉटरमार्क एम्बेड हो जाएगा।

## निष्कर्ष
Hatch पैटर्न को शामिल करने से तकनीकी ड्रॉइंग, मानचित्र, या किसी भी Java‑जनित ग्राफ़िक्स की पठनीयता और सौंदर्य में उल्लेखनीय सुधार हो सकता है। **Aspose.Page Java** के साथ, आपको एक संक्षिप्त API मिलता है जो लो‑लेवल PostScript कमांड्स को एब्स्ट्रैक्ट करता है, जिससे आप फ़ाइल फ़ॉर्मेट की जटिलताओं के बजाय डिज़ाइन पर ध्यान केंद्रित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Page Java को अन्य Java फ्रेमवर्क्स के साथ उपयोग कर सकता हूँ?**  
A: हाँ, लाइब्रेरी फ्रेमवर्क‑अज्ञेय है और Spring, Jakarta EE, Android (सीमित), तथा साधारण Java SE के साथ काम करती है।

**Q: क्या Aspose.Page Java के लिए ट्रायल संस्करण उपलब्ध है?**  
A: बिल्कुल। एक मुफ्त 30‑दिन ट्रायल [here](https://releases.aspose.com/) डाउनलोड करें।

**Q: विकास के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A: एक अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) का अनुरोध करें। यह मूल्यांकन वॉटरमार्क को हटाता है।

**Q: अधिक ट्यूटोरियल और कम्युनिटी सपोर्ट कहाँ मिल सकता है?**  
A: आधिकारिक फ़ोरम [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) पर अतिरिक्त उदाहरण और Q&A देखें।

**Q: सभी क्लासेज़ और मेथड्स के लिए व्यापक दस्तावेज़ीकरण उपलब्ध है?**  
A: हाँ, पूर्ण API रेफ़रेंस [here](https://reference.aspose.com/page/java/) पर उपलब्ध है।

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
