---
date: 2026-05-25
description: Aspose.Page के साथ Java का उपयोग करके EPS दस्तावेज़ों में xmp को कैसे
  संशोधित करें, जानें। मेटाडेटा को तेज़ और विश्वसनीय रूप से अपडेट करें।
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: Java का उपयोग करके XMP में मान बदलें
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Aspose.Page के साथ xmp को कैसे संशोधित करें – Java का उपयोग करके XMP में मान
  बदलें
url: /hi/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java का उपयोग करके XMP मान बदलें

## परिचय
यदि आप Java के साथ EPS फ़ाइल में **xmp को कैसे संशोधित करें** ढूँढ़ रहे हैं, तो आप सही जगह पर आए हैं। यह ट्यूटोरियल आपको प्रत्येक चरण के माध्यम से ले जाता है—मौजूदा XMP ब्लॉक को पढ़ना, creator, title, और modify date जैसे फ़ील्ड को अपडेट करना, और अंत में परिवर्तन को EPS दस्तावेज़ में वापस सहेजना। अंत तक आपके पास एक पुन: उपयोग योग्य स्निपेट होगा जो किसी भी स्वचालित वर्कफ़्लो में फिट हो जाता है, यह सुनिश्चित करते हुए कि आपके फ़ाइलों में ब्रांडिंग, अनुपालन, या सर्च‑इंजन इंडेक्सिंग के लिए सही मेटाडेटा हो।

## त्वरित उत्तर
- **“aspose.page modify xmp” क्या करता है?** यह आपको Aspose.Page Java API के माध्यम से EPS फ़ाइलों में XMP मेटाडेटा को पढ़ने और लिखने की सुविधा देता है।  
- **कौन सा लाइब्रेरी संस्करण आवश्यक है?** कोई भी नवीनतम Aspose.Page for Java रिलीज़ (API संस्करणों के बीच स्थिर है)।  
- **क्या नमूना चलाने के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या मैं एक साथ कई XMP फ़ील्ड बदल सकता हूँ?** हाँ—दस्तावेज़ सहेजने से पहले प्रत्येक फ़ील्ड के लिए `put` कॉल करें।  
- **क्या टाइमज़ोन हैंडलिंग आवश्यक है?** डिफ़ॉल्ट टाइमज़ोन सेट करना (जैसे, UTC) तिथि मानों में स्थिरता सुनिश्चित करता है।

## XMP क्या है और इसे क्यों संशोधित करें?
XMP (Extensible Metadata Platform) एक मानकीकृत, XML‑आधारित फ़ॉर्मेट है जो EPS, PDF, और छवियों जैसी फ़ाइलों के भीतर सीधे समृद्ध मेटाडेटा एम्बेड करने के लिए उपयोग किया जाता है। XMP को अपडेट करने से आप नियंत्रित कर सकते हैं कि दस्तावेज़ कैसे इंडेक्स, प्रदर्शित और खोजे जाते हैं—ब्रांड स्थिरता, नियामक अनुपालन, और स्वचालित कंटेंट पाइपलाइन के लिए महत्वपूर्ण।

## Java के लिए Aspose.Page क्यों उपयोग करें?
Aspose.Page एक **पूर्ण‑विशेषताओं वाला, शुद्ध‑Java API** प्रदान करता है जो बाहरी टूल या नेटिव लाइब्रेरी की आवश्यकता को समाप्त करता है। यह **50+ इनपुट और आउटपुट फ़ॉर्मेट** का समर्थन करता है और **500 MB** तक की EPS फ़ाइलों को पूरी दस्तावेज़ को मेमोरी में लोड किए बिना प्रोसेस कर सकता है, जिससे किसी भी Java चलाने वाले OS पर तेज़, कम‑मेमोरी मेटाडेटा हेरफेर संभव होता है।

## पूर्वापेक्षाएँ
इस ट्यूटोरियल को शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1. **Java Development Environment** – एक JDK (8 या बाद का) और आपकी पसंद का IDE या बिल्ड टूल।  
2. **Aspose.Page for Java Library** – Aspose.Page for Java लाइब्रेरी को डाउनलोड और इंस्टॉल करें। आवश्यक पैकेज आप [यहाँ](https://releases.aspose.com/page/java/) पा सकते हैं।

## पैकेज इम्पोर्ट करें
अपने Java प्रोजेक्ट में आवश्यक पैकेज इम्पोर्ट करके शुरू करें। ये पैकेज EPS दस्तावेज़ों के साथ इंटरैक्ट करने और उन्हें हेरफेर करने के लिए आवश्यक हैं।

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Java का उपयोग करके EPS में XMP कैसे संशोधित करें?
`Document` Aspose.Page क्लास है जो EPS फ़ाइल का प्रतिनिधित्व करता है और इसकी सामग्री और मेटाडेटा तक पहुँच प्रदान करता है। `XmpMetadata` दस्तावेज़ से जुड़ा XMP ब्लॉक दर्शाता है और मेटाडेटा फ़ील्ड को पढ़ने और लिखने की अनुमति देता है। `put` XmpMetadata ऑब्जेक्ट में एक मेटाडेटा एंट्री जोड़ता या अपडेट करता है। `save` संशोधित दस्तावेज़ को, जिसमें कोई भी अपडेटेड XMP मेटाडेटा शामिल है, फ़ाइल में लिखता है।

`new Document("input.eps")` के साथ EPS फ़ाइल लोड करें, उसका `XmpMetadata` ऑब्जेक्ट प्राप्त करें, इच्छित कुंजियों को `put` से अपडेट करें, और अंत में `save` को कॉल करके बदलावों को नई फ़ाइल में लिखें। यह संक्षिप्त प्रवाह स्वचालित रूप से गायब XMP ब्लॉकों को संभालता है, आवश्यकता पड़ने पर PostScript टिप्पणियों से एक बनाता है, और टाइमज़ोन‑संगत तिथियों को सुनिश्चित करता है।

## चरण 1: XMP मेटाडेटा प्राप्त करें
`XmpMetadata` क्लास EPS दस्तावेज़ से जुड़ा XMP ब्लॉक दर्शाता है। जब आप `document.getXmpMetadata()` कॉल करते हैं, तो API या तो मौजूदा ब्लॉक लौटाता है या `%%Creator`, `%%CreateDate`, और `%%Title` जैसी PS टिप्पणियों से नया बनाता है।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## चरण 2: "ModifyDate" मान बदलें
`"ModifyDate"` एंट्री को नए संशोधन टाइमस्टैम्प को दर्शाने के लिए अपडेट करें। संग्रहीत मान को टाइमज़ोन‑अज्ञेय रखने के लिए `java.util.Date` को `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` के साथ उपयोग करें।

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## चरण 3: "Creator" मान बदलें
`"Creator"` कुंजी EPS फ़ाइल बनाने वाले एप्लिकेशन या व्यक्ति का नाम संग्रहीत करती है। मौजूदा मान को एक कस्टम पहचानकर्ता से बदलने के लिए `xmp.put("dc:creator", "Your Company Name")` कॉल करें।

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## चरण 4: "Title" मान बदलें
`"Title"` फ़ील्ड कई एसेट‑मैनेजमेंट सिस्टम द्वारा प्रदर्शित किया जाता है। इसे `xmp.put("dc:title", "New Document Title")` द्वारा सेट करने से दस्तावेज़ कैटलॉग और सर्च परिणामों में सही ढंग से दिखता है।

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## चरण 5: बदले हुए XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
सभी संशोधनों के बाद, `document.save("output.eps")` को कॉल करें। लाइब्रेरी अपडेटेड XMP ब्लॉक को EPS स्ट्रीम में वापस लिखती है जबकि मूल ग्राफिक सामग्री अपरिवर्तित रहती है।

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## सामान्य समस्याएँ और समाधान
- **Missing XMP block** – API स्वचालित रूप से PS टिप्पणियों से एक बनाता है, लेकिन आवश्यकता पड़ने पर आप मैन्युअली `XmpMetadata` को इंस्टैंशिएट भी कर सकते हैं।  
- **Timezone mismatches** – अनपेक्षित ऑफ़सेट से बचने के लिए `Date` ऑब्जेक्ट बनाने से पहले हमेशा `TimeZone.setDefault` सेट करें।  
- **File access errors** – इनपुट और आउटपुट पाथ सही हैं और आपका एप्लिकेशन पढ़ने/लिखने की अनुमति रखता है, यह सुनिश्चित करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: XMP मानों को संशोधित करते समय टाइम ज़ोन विचारों को कैसे संभालूँ?**  
A: टाइम ज़ोन सेटिंग्स में स्थिरता सुनिश्चित करने के लिए `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` का उपयोग करें।

**Q: क्या मैं एक ही ऑपरेशन में कई XMP मान बदल सकता हूँ?**  
A: हाँ, प्रत्येक इच्छित मान के लिए `put` मेथड का उपयोग करके आप कई XMP मानों को एक साथ संशोधित कर सकते हैं।

**Q: Aspose.Page for Java के अतिरिक्त दस्तावेज़ कहाँ मिल सकते हैं?**  
A: व्यापक दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/page/java/) देखें।

**Q: क्या Aspose.Page for Java के लिए मुफ्त ट्रायल उपलब्ध है?**  
A: हाँ, आप मुफ्त ट्रायल [यहाँ](https://releases.aspose.com/) से प्राप्त कर सकते हैं।

**Q: Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A: अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) प्राप्त करें।

**Q: क्या XMP को संशोधित करने से EPS की दृश्य सामग्री प्रभावित होती है?**  
A: नहीं। XMP परिवर्तन केवल मेटाडेटा होते हैं और EPS फ़ाइल के ग्राफिक तत्वों को नहीं बदलते।

**Q: क्या मैं प्रोग्रामेटिक रूप से अपडेटेड मानों को पढ़कर परिवर्तन की पुष्टि कर सकता हूँ?**  
A: बिल्कुल—सहेजने के बाद और दस्तावेज़ बंद करने से पहले `xmp.get("dc:creator")` (या संबंधित कुंजी) को कॉल करें।

## निष्कर्ष
बधाई हो! आपने Aspose.Page for Java का उपयोग करके EPS दस्तावेज़ों में **xmp को कैसे संशोधित करें** मानों में महारत हासिल कर ली है। सटीक creator, title, और modify‑date मेटाडेटा एम्बेड करके आप सुनिश्चित करते हैं कि आपके एसेट्स खोज योग्य, अनुपालन योग्य, और आपके ब्रांडिंग मानकों के अनुरूप हों। इस पैटर्न को बैच‑प्रोसेसिंग पाइपलाइन, CI/CD चरण, या किसी भी स्वचालित दस्तावेज़‑जनरेशन वर्कफ़्लो में एकीकृत करने में संकोच न करें।

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose Page Java ट्यूटोरियल – EPS फ़ाइलों में XMP मेटाडेटा जोड़ें](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Java का उपयोग करके XMP मेटाडेटा कैसे पढ़ें – Aspose.Page गाइड](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java - Java का उपयोग करके XMP में एरे आइटम बदलें](/page/java/xmp-metadata-manipulation/change-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}