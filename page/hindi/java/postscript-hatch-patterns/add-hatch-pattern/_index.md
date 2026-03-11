---
date: 2026-02-15
description: Aspose.Page Java का उपयोग करके Java PostScript फ़ाइलों में हैच पैटर्न
  जोड़ना सीखें। यह चरण‑दर‑चरण गाइड पूर्ण कोड और टिप्स दिखाता है।
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page के साथ जावा पोस्टस्क्रिप्ट में हैच पैटर्न कैसे जोड़ें
url: /hi/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा पोस्टस्क्रिप्ट में हैच पैटर्न कैसे जोड़ें

## परिचय
यदि आप **Aspose.Page Java** के साथ काम कर रहे हैं और अपने पोस्टस्क्रिप्ट आउटपुट में **हैच पैटर्न कैसे जोड़ें** के बारे में सोच रहे हैं, तो हैच पैटर्न एक तेज़ और लचीला समाधान है। इस ट्यूटोरियल में हम **हैच** डिज़ाइन को पोस्टस्क्रिप्ट दस्तावेज़ में कैसे जोड़ें, इसका चरण‑दर‑चरण विवरण देंगे, यह बताएँगे कि यह क्यों उपयोगी है, और एक पूर्ण, तैयार‑चलाने‑योग्य कोड उदाहरण प्रदान करेंगे। अंत तक, आप केवल कुछ ही जावा लाइनों से दृश्य रूप से आकर्षक हैच‑भरे आकार और टेक्स्ट बना पाएँगे।

## त्वरित उत्तर
- **मुझे कौनसी लाइब्रेरी चाहिए?** Aspose.Page for Java (the “aspose page java” SDK).  
- **हम कौनसा दृश्य प्रभाव जोड़ रहे हैं?** हैच पैटर्न (जैसे, तिरछी रेखाएँ, क्रॉसहैच)।  
- **क्या नमूना चलाने के लिए लाइसेंस चाहिए?** विकास के लिए मुफ्त ट्रायल काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है।  
- **कोड की कितनी पंक्तियाँ?** लगभग 70 पंक्तियाँ, स्पष्ट चरणों में विभाजित।  
- **क्या मैं वही तरीका PDF के लिए उपयोग कर सकता हूँ?** हाँ—Aspose.Page कई आउटपुट फ़ॉर्मेट, जिसमें PDF भी शामिल है, को सपोर्ट करता है।

## हैच पैटर्न जोड़ने का अवलोकन
हैच पैटर्न वेक्टर‑आधारित टेक्सचर होते हैं जो किसी भी रिज़ॉल्यूशन पर साफ़ दिखते हैं और मोनोक्रोम प्रिंटरों पर भी अच्छी तरह काम करते हैं। Aspose.Page Java का उपयोग करके आप इन पैटर्न को आकार, पाथ और यहाँ तक कि टेक्स्ट पर भी लागू कर सकते हैं, बिना लो‑लेवल पोस्टस्क्रिप्ट कमांड्स के झंझट के।

## आवश्यकताएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

- **Java Development Environment** – JDK 8 या उससे ऊपर और आपका पसंदीदा IDE।  
- **Aspose.Page for Java library** – आधिकारिक साइट से नवीनतम JAR डाउनलोड करें [यहाँ](https://releases.aspose.com/page/java/)。  
- **Write access** उस फ़ोल्डर तक जहाँ जनरेट किया गया पोस्टस्क्रिप्ट फ़ाइल सहेजा जाएगा।

## पैकेज आयात करें
सबसे पहले, आवश्यक क्लासेज़ को अपने प्रोजेक्ट में लाएँ। ये इम्पोर्ट्स आपको ड्रॉइंग प्रिमिटिव्स, रंग हैंडलिंग और Aspose.Page API तक पहुँच प्रदान करते हैं।

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
आउटपुट स्ट्रीम बनाएँ, पेज साइज (A4) कॉन्फ़िगर करें, और कुछ लेआउट वेरिएबल्स परिभाषित करें जो प्रत्येक हैच‑भरे वर्ग को ड्रॉ करते समय पुन: उपयोग होंगे।

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
ग्राफ़िक्स स्टेट सहेजने से बाद में मूल कोऑर्डिनेट सिस्टम पर लौटना आसान हो जाता है, जबकि `translate` मूल बिंदु को एक सुविधाजनक प्रारंभिक बिंदु पर ले जाता है।

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## चरण 3: प्रत्येक पैटर्न के लिए वर्ग बनाएं
एक पुन: उपयोग योग्य आयत परिभाषित करें जो प्रत्येक हैच‑भरे सेल का प्रतिनिधित्व करेगा।

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## चरण 4: पैटर्न वर्ग की रूपरेखा के लिए पेन सेट करें
2 पॉइंट का `BasicStroke` प्रत्येक वर्ग के चारों ओर एक स्पष्ट रूपरेखा देता है।

```java
BasicStroke stroke = new BasicStroke(2);
```

## चरण 5: हैच पैटर्न के माध्यम से इटररेट करें
`HatchStyle` एन्‍युम के प्रत्येक मान पर लूप करें, प्रत्येक वर्ग को संबंधित टेक्सचर से भरें, और फिर उसकी रूपरेखा ड्रॉ करें। यह **हैच पैटर्न जोड़ने** की मुख्य कार्यक्षमता है।

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## चरण 6: ग्राफ़िक्स स्टेट पुनर्स्थापित करें
ग्रिड के सभी वर्गों को ड्रॉ करने के बाद मूल कोऑर्डिनेट सिस्टम पर लौटें।

```java
document.writeGraphicsRestore();
```

## चरण 7: टेक्स्ट को हैच पैटर्न से भरें
यहाँ हम दिखाते हैं कि कैसे एक हैच टेक्सचर का उपयोग करके टेक्स्ट को पेंट किया जाए। उदाहरण में शब्द “ABC” को तिरछी‑क्रॉस पैटर्न से भरा गया है।

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## चरण 8: टेक्स्ट को हैच पैटर्न से रूपरेखा दें
अब हम वही टेक्स्ट रूपरेखा देते हैं, लेकिन इस बार 70 % हैच स्टाइल और मोटी स्ट्रोक का उपयोग करके।

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## चरण 9: दस्तावेज़ बंद करें और सहेजें
पेज को अंतिम रूप दें, फ़ाइल को डिस्क पर लिखें, और संसाधनों को रिलीज़ करें।

```java
document.closePage();
document.save();
```

इन चरणों का पालन करें, और आपके पास एक पोस्टस्क्रिप्ट फ़ाइल होगी जो आकार और टेक्स्ट दोनों पर लागू पूर्ण हैच पैटर्न सेट को प्रदर्शित करती है—सभी **aspose page java** द्वारा संचालित।

## Aspose.Page Java के साथ हैच पैटर्न क्यों उपयोग करें?
- **दृश्य अंतर** – हैच फ़िल प्रिंटरों के मोनोक्रोम आउटपुट तक सीमित होने पर भी काम करता है।  
- **प्रदर्शन** – टेक्सचर ऑन‑द‑फ़्लाई जेनरेट होते हैं, इसलिए बड़े इमेज फ़ाइलों से बचा जाता है।  
- **क्रॉस‑फ़ॉर्मेट समर्थन** – वही कोड PDF, EPS या SVG को न्यूनतम बदलावों के साथ टार्गेट कर सकता है।

## सामान्य गलतियाँ एवं सुझाव
- **फ़ाइल पाथ त्रुटियाँ** – सुनिश्चित करें कि `dataDir` उचित फ़ाइल‑सेपरेटर (`/` या `\`) के साथ समाप्त हो।  
- **असमर्थित रंग** – कुछ पुराने पोस्टस्क्रिप्ट इंटरप्रेटर कुछ कलर स्पेसेज़ को संभाल नहीं सकते; अधिकतम संगतता के लिए बेसिक RGB उपयोग करें।  
- **लाइसेंस चेतावनी** – वैध लाइसेंस के बिना नमूना चलाने से आउटपुट में वॉटरमार्क एम्बेड हो जाएगा।

## निष्कर्ष
हैच पैटर्न को शामिल करने से तकनीकी ड्रॉइंग, मानचित्र या किसी भी जावा‑जनित ग्राफ़िक्स की पठनीयता और सौंदर्यशास्त्र में काफी सुधार हो सकता है। **Aspose.Page Java** के साथ, आपको एक संक्षिप्त API मिलता है जो लो‑लेवल पोस्टस्क्रिप्ट कमांड्स को एब्स्ट्रैक्ट करता है, जिससे आप फ़ॉर्मेट की जटिलताओं के बजाय डिज़ाइन पर ध्यान केंद्रित कर सकते हैं। अब आप जानते हैं **हैच पैटर्न कैसे जोड़ें** अपने पोस्टस्क्रिप्ट दस्तावेज़ों में—विभिन्न `HatchStyle` मानों के साथ प्रयोग करें और वही लुक प्राप्त करें जो आपको चाहिए।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Page Java को अन्य जावा फ्रेमवर्क के साथ उपयोग कर सकता हूँ?**  
उत्तर: हाँ, लाइब्रेरी फ्रेमवर्क‑अग्नॉस्टिक है और Spring, Jakarta EE, Android (सीमित), तथा साधारण Java SE के साथ काम करती है।

**प्रश्न: क्या Aspose.Page Java के लिए ट्रायल संस्करण उपलब्ध है?**  
उत्तर: बिल्कुल। एक मुफ्त 30‑दिन ट्रायल [यहाँ](https://releases.aspose.com/) डाउनलोड करें।

**प्रश्न: विकास के लिए अस्थायी लाइसेंस कैसे प्राप्त करें?**  
उत्तर: एक अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) अनुरोध करें। यह मूल्यांकन वॉटरमार्क को हटाता है।

**प्रश्न: अधिक ट्यूटोरियल और समुदाय समर्थन कहाँ मिल सकता है?**  
उत्तर: आधिकारिक फ़ोरम [Aspose.Page for Java फ़ोरम](https://forum.aspose.com/c/page/39) पर अतिरिक्त उदाहरण और Q&A देखें।

**प्रश्न: सभी क्लास और मेथड के लिए व्यापक दस्तावेज़ीकरण उपलब्ध है?**  
उत्तर: हाँ, पूर्ण API रेफ़रेंस [यहाँ](https://reference.aspose.com/page/java/) उपलब्ध है।

**प्रश्न: क्या मैं वही हैच पैटर्न PDF के बजाय पोस्टस्क्रिप्ट में रेंडर कर सकता हूँ?**  
उत्तर: बिल्कुल। `PsSaveOptions` को `PdfSaveOptions` (या समकक्ष) में बदलें और बाकी कोड अपरिवर्तित रहेगा।

**प्रश्न: यदि उत्पन्न फ़ाइल खाली है तो क्या करें?**  
उत्तर: सुनिश्चित करें कि आउटपुट स्ट्रीम लिखने योग्य डायरेक्टरी की ओर इशारा कर रहा है और सभी ड्रॉइंग ऑपरेशनों के बाद `document.save()` कॉल किया गया है।

**अंतिम अपडेट:** 2026-02-15  
**परीक्षण किया गया:** Aspose.Page for Java 24.12 (लेखन समय पर नवीनतम)  
**लेखक:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}