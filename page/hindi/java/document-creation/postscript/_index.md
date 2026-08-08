---
date: 2026-06-20
description: सीखें कैसे सेट करें A4 पेज साइज, जावा में PostScript फ़ाइलें बनाएं, और
  Aspose.Page का उपयोग करके कस्टम फ़ॉन्ट जोड़ें। आज ही मुफ्त ट्रायल आज़माएँ!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: जावा में PostScript के साथ डॉक्यूमेंट बनाएं
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: कैसे सेट करें A4 पेज साइज और जावा में Aspose.Page के साथ PostScript बनाएं
url: /hi/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में Aspose.Page के साथ A4 पेज आकार सेट करने और PostScript बनाने का तरीका

## परिचय
यदि आपको Java से PostScript फ़ाइलें बनाते समय **set a4 page size** की आवश्यकता है, तो Aspose.Page एक तेज़, विश्वसनीय API प्रदान करता है जो निम्न‑स्तरीय विवरणों को छुपाता है। इस ट्यूटोरियल में हम पूरे वर्कफ़्लो को चरण‑दर‑चरण देखेंगे—PostScript दस्तावेज़ बनाना, A4 पेज आयाम कॉन्फ़िगर करना, और आवश्यकता पड़ने पर **adding custom fonts**। अंत तक आपके पास एक तैयार‑उपयोग कोड स्निपेट होगा जिसे आप किसी भी Java प्रोजेक्ट में डाल सकते हैं।

## त्वरित उत्तर
- **Java में PostScript बनाने वाली लाइब्रेरी कौन सी है?** Aspose.Page for Java.  
- **इस गाइड में लक्षित पेज आकार कौन सा है?** A4 (210 mm × 297 mm).  
- **क्या मैं अपने स्वयं के फ़ॉन्ट एम्बेड कर सकता हूँ?** Yes – set the additional fonts folder in the save options.  
- **उत्पादन के लिए क्या मुझे लाइसेंस चाहिए?** A commercial license is required; a free trial is available.  
- **कौन से Java संस्करण समर्थित हैं?** Java 8 and later.

## Java में a4 पेज आकार सेट करने और postscript बनाने का तरीका
Aspose.Page लाइब्रेरी लोड करें, `PsSaveOptions` को A4 स्थिरांक के साथ कॉन्फ़िगर करें, और दस्तावेज़ को फ़ाइल में लिखें – सभी दस लाइनों के कोड से कम में। यह सीधा तरीका सही पेज आयाम सुनिश्चित करता है और अतिरिक्त कॉन्फ़िगरेशन के बिना आपको कस्टम फ़ॉन्ट जोड़ने देता है।

## PostScript A4 आकार क्या है?
PostScript A4 आकार ISO 216 मानक (210 mm × 297 mm) को PostScript पेज विवरण भाषा में व्यक्त करता है। यह प्रिंटर और व्यूअर्स द्वारा व्याख्यायित प्रिंटेबल क्षेत्र को परिभाषित करता है, जिससे विभिन्न प्लेटफ़ॉर्म पर लेआउट सुसंगत रहता है। क्योंकि PostScript पेज सामग्री को डिवाइस‑स्वतंत्र तरीके से वर्णित करता है, A4 आकार का उपयोग करने से यह सुनिश्चित होता है कि दस्तावेज़ किसी भी A4‑सक्षम प्रिंटर या व्यूअर पर समान दिखेगा।

## PostScript पेज आकार सेट करने के लिए Aspose.Page का उपयोग क्यों करें?
Aspose.Page **30+ PostScript ऑपरेटर्स** का समर्थन करता है और पूरे दस्तावेज़ को मेमोरी में लोड किए बिना **500 MB** तक की फ़ाइलें बना सकता है। यह आपको पेज आयामों पर सटीक नियंत्रण देता है जबकि बड़े कार्यभार को कुशलता से संभालता है। लाइब्रेरी जटिल PostScript सिंटैक्स को भी सारांशित करती है, संसाधनों को स्वचालित रूप से प्रबंधित करती है, और उच्च‑प्रदर्शन स्ट्रीमिंग प्रदान करती है, जिससे यह सरल एक‑पेज फ्लायर्स और जटिल मल्टी‑पेज रिपोर्ट दोनों के लिए आदर्श बन जाता है।

## Java में कस्टम फ़ॉन्ट कैसे जोड़ें
अपने स्वयं के टाइपफ़ेस एम्बेड करने से यह सुनिश्चित होता है कि उत्पन्न दस्तावेज़ किसी भी प्रिंटर या व्यूअर पर ठीक वैसा ही दिखे जैसा डिज़ाइन किया गया है, और Aspose.Page निर्दिष्ट फ़ोल्डर में रखे फ़ॉन्ट को स्वचालित रूप से खोज लेता है। अतिरिक्त फ़ॉन्ट फ़ोल्डर को पंजीकृत करके, आप कोई भी TrueType या OpenType फ़ॉन्ट उपयोग कर सकते हैं, फ़ॉलबैक प्रतिस्थापन से बच सकते हैं, और सभी आउटपुट डिवाइसों में ब्रांड स्थिरता बनाए रख सकते हैं।

## पूर्वापेक्षाएँ
- Java प्रोग्रामिंग का कार्यशील ज्ञान।  
- Aspose.Page for Java स्थापित है। आप इसे [here](https://releases.aspose.com/page/java/) से डाउनलोड कर सकते हैं।  
- `necessary_fonts` नामक फ़ोल्डर (या आपका पसंदीदा कोई भी नाम) जिसमें आप एम्बेड करना चाहते हैं कोई भी कस्टम फ़ॉन्ट शामिल हों।

## पैकेज आयात करें
अपने Java प्रोजेक्ट में, आवश्यक Aspose.Page क्लासेस आयात करें:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

अब चलिए उदाहरण को स्पष्ट, क्रमांकित चरणों में विभाजित करते हैं।

### चरण 1: दस्तावेज़ डायरेक्टरी सेट करें
`OUTPUT_DIR` स्थिरांक लाइब्रेरी को बताता है कि उत्पन्न फ़ाइल कहाँ लिखनी है।

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### चरण 2: फ़ॉन्ट फ़ोल्डर परिभाषित करें
`FONTS_FOLDER` उस डायरेक्टरी की ओर इशारा करता है जिसमें आपके कस्टम TrueType या OpenType फ़ॉन्ट होते हैं।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### चरण 3: PostScript दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
`FileOutputStream` एक स्ट्रीम खोलता है जो अंतिम PostScript A4 आउटपुट प्राप्त करेगा।

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### चरण 4: A4 आकार के साथ सेव ऑप्शन बनाएं
`PsSaveOptions` आपको लक्ष्य पेज आकार निर्दिष्ट करने देता है।  
**परिभाषा:** `PsPageSize` एक enumeration है जिसमें A4, Letter, और Legal जैसे मानक पेज‑आकार स्थिरांक शामिल हैं।  
`options.setPageSize(PsPageSize.A4)` सेट करने से दस्तावेज़ मानक A4 आयामों के लिए कॉन्फ़िगर हो जाता है।

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### चरण 5: पेज मार्जिन सेट करें और कस्टम फ़ॉन्ट फ़ोल्डर जोड़ें
`options.setMargins(0, 0, 0, 0)` पूर्ण‑ब्लीड पेज के लिए सभी मार्जिन हटाता है, और `options.setAdditionalFontsFolder(FONTS_FOLDER)` आपके कस्टम फ़ॉन्ट को पंजीकृत करता है।

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### चरण 6: मल्टी‑पेज या सिंगल‑पेज PS दस्तावेज़ बनाएं
`PsDocument document = new PsDocument(outputStream, options)` दस्तावेज़ बनाता है। `PsDocument` एक PostScript दस्तावेज़ का प्रतिनिधित्व करता है जिसमें एक या कई पेज हो सकते हैं। मल्टी‑पेज आउटपुट के लिए `multiPaged` को `true` सेट करें।

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### चरण 7: वर्तमान पेज बंद करें और दस्तावेज़ सहेजें
`document.close()` को कॉल करने से फ़ाइल अंतिम रूप लेती है और **PostScript A4 size** आउटपुट डिस्क पर लिखा जाता है।

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## सामान्य समस्याएँ और सुझाव
- **फ़ॉन्ट नहीं दिख रहा है?** जाँचें कि फ़ॉन्ट फ़ाइल समर्थित TrueType या OpenType फ़ॉर्मेट में है और `FONTS_FOLDER` स्लैश (`/`) के साथ समाप्त होता है।  
- **मार्जिन अभी भी दिख रहे हैं?** `PsDocument` बनाने से **पहले** `options.setMargins(...)` को कॉल करें।  
- **मल्टी‑पेज आउटपुट खाली दिख रहा है?** प्रत्येक अतिरिक्त पेज के लिए `document.newPage()` को कॉल करना याद रखें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं अपने PostScript दस्तावेज़ में कस्टम फ़ॉन्ट उपयोग कर सकता हूँ?**  
A: हाँ, सेव ऑप्शन में अतिरिक्त फ़ॉन्ट फ़ोल्डर सेट करें (चरण 5 देखें) और Aspose.Page स्वचालित रूप से फ़ॉन्ट एम्बेड कर देगा।

**Q: क्या Aspose.Page for Java के लिए ट्रायल संस्करण उपलब्ध है?**  
A: हाँ, आप एक मुफ्त ट्रायल [here](https://releases.aspose.com/) से प्राप्त कर सकते हैं।

**Q: मैं पूरी API रेफ़रेंस कैसे एक्सेस कर सकता हूँ?**  
A: दस्तावेज़ीकरण [here](https://reference.aspose.com/page/java/) देखें।

**Q: मैं Aspose.Page for Java का लाइसेंस कहाँ खरीद सकता हूँ?**  
A: आप लाइसेंस [here](https://purchase.aspose.com/buy) से खरीद सकते हैं।

**Q: मैं समुदाय से मदद कहाँ पूछ सकता हूँ?**  
A: Aspose.Page फ़ोरम [forum](https://forum.aspose.com/c/page/39) पर जाएँ।

**Q: क्या मैं मल्टी‑पेज PostScript फ़ाइलें बना सकता हूँ?**  
A: बिल्कुल—चरण 6 में `multiPaged` को `true` सेट करें और प्रत्येक अतिरिक्त पेज के लिए `document.newPage()` को कॉल करें।

## निष्कर्ष
इन चरणों का पालन करके अब आप जानते हैं **how to set a4 page size** और Aspose.Page के साथ Java में **PostScript** फ़ाइलें बनाना, साथ ही **add custom fonts java** और पेज‑साइज़ विकल्पों को नियंत्रित करना। Aspose.Page भारी काम संभालता है, इसलिए आप अपने दस्तावेज़ों की सामग्री पर ध्यान केंद्रित कर सकते हैं।

---

**अंतिम अपडेट:** 2026-06-20  
**परीक्षण किया गया:** Aspose.Page for Java 24.11  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Page Java ट्यूटोरियल – PostScript में पेज जोड़ते समय कस्टम पेज आकार सेट करना](/page/java/postscript-page-manipulation/add-pages2/)
- [Aspose.Page for Java के साथ PostScript में टेक्स्ट कैसे जोड़ें](/page/java/postscript-text-manipulation/)
- [Aspose Page Java ट्यूटोरियल - PostScript को PDF में बदलें](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```