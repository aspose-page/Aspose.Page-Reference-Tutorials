---
date: 2026-05-15
description: Aspose.Page for Java के साथ EPS फ़ाइलों में XMP मान बदलने और XMP मेटाडेटा
  को संपादित करने के बारे में जानें – एक स्पष्ट चरण‑दर‑चरण गाइड।
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Java का उपयोग करके XMP में नामित मान बदलें
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: xmp को कैसे संपादित करें – XMP में नामित मान बदलें Java का उपयोग करके
url: /hi/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP को कैसे संपादित करें – Java का उपयोग करके XMP में नामित मान बदलें

आधुनिक दस्तावेज़ कार्यप्रवाहों में, **Aspose.Page for Java** EPS फ़ाइलों के भीतर XMP मेटाडेटा को पढ़ना, संपादित करना और लिखना आसान बनाता है। **यह ट्यूटोरियल दिखाता है कि XMP** मेटाडेटा को EPS दस्तावेज़ों में Aspose.Page API का उपयोग करके कैसे संपादित किया जाए, ताकि आप अपने दस्तावेज़ की जानकारी को सटीक, खोज योग्य और उद्योग मानकों के अनुरूप रख सकें। चाहे आप पृष्ठ आयाम, लेखक जानकारी, या कस्टम टैग अपडेट कर रहे हों, नीचे दिए गए चरण जावा में प्रक्रिया के माध्यम से आपका मार्गदर्शन करेंगे।

## त्वरित उत्तर
- **इस ट्यूटोरियल में क्या कवर किया गया है?** Aspose.Page for Java के साथ EPS फ़ाइल में नामित XMP मान बदलना।  
- **कौन सा लाइब्रेरी संस्करण आवश्यक है?** कोई भी नवीनतम Aspose.Page for Java रिलीज़ (API कई वर्षों से स्थिर है)।  
- **क्या मुझे लाइसेंस चाहिए?** उत्पादन के लिए एक अस्थायी या पूर्ण लाइसेंस आवश्यक है; परीक्षण के लिए एक मुफ्त ट्रायल काम करता है।  
- **कार्यान्वयन में कितना समय लगेगा?** Java I/O से परिचित डेवलपर के लिए लगभग 10‑15 मिनट।  
- **क्या मैं इसे अन्य फ़ाइल फ़ॉर्मैट्स के साथ उपयोग कर सकता हूँ?** XMP API PDF, SVG और Aspose.Page द्वारा समर्थित अन्य फ़ॉर्मैट्स के लिए भी उपलब्ध है।

## XMP मेटाडेटा क्या है?
XMP (Extensible Metadata Platform) एक मानकीकृत XML‑आधारित फ़ॉर्मैट है जो फ़ाइलों के भीतर समृद्ध मेटाडेटा—जैसे निर्माता, शीर्षक, और कस्टम प्रॉपर्टीज़—को सीधे एम्बेड करने की अनुमति देता है। EPS दस्तावेज़ों में, XMP पारंपरिक PostScript टिप्पणियों के साथ रहता है, जिससे एप्लिकेशन दृश्य सामग्री को बदले बिना मेटाडेटा को पढ़ और संशोधित कर सकते हैं।

## XMP को संपादित करने के लिए Aspose.Page for Java का उपयोग क्यों करें?
Aspose.Page आपको **150 से अधिक XMP स्कीमा प्रॉपर्टीज़ पर पूर्ण नियंत्रण** देता है और EPS, PDF, और SVG फ़ॉर्मैट्स में लगातार काम करता है। यह फ़ाइलों को **500 MB** तक प्रोसेस करता है बिना पूरे दस्तावेज़ को मेमोरी में लोड किए, और इसमें बिल्ट‑इन वैलिडेशन शामिल है जो सुनिश्चित करता है कि परिणामी EPS मानकों के अनुरूप रहे। कोई बाहरी XML पार्सर या नेटिव लाइब्रेरी आवश्यक नहीं है।

## परिचय
Aspose.Page for Java एक मजबूत लाइब्रेरी है जो EPS फ़ाइलों के हेरफेर और प्रोसेसिंग को सुविधाजनक बनाती है। जब इन फ़ाइलों के भीतर XMP मेटाडेटा को संभालने की बात आती है, तो Aspose.Page डेवलपर्स को व्यापक फीचर सेट प्रदान करता है। इस ट्यूटोरियल में हम XMP में नामित मान बदलने पर ध्यान केंद्रित करेंगे, जिससे डेवलपर्स अपने दस्तावेज़ प्रोसेसिंग क्षमताओं को बढ़ा सकें।

## पूर्वापेक्षाएँ
ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित उपलब्ध हों:
1. **Java Development Environment** – एक JDK (8 या उच्चतर) और एक IDE या बिल्ड टूल (Maven/Gradle)।  
2. **Aspose.Page for Java Library** – Aspose.Page for Java लाइब्रेरी को डाउनलोड करके अपने प्रोजेक्ट में इंटीग्रेट करें। आप लाइब्रेरी और विस्तृत दस्तावेज़ीकरण [here](https://reference.aspose.com/page/java/) पर पा सकते हैं।  
3. **Sample EPS File** – प्रयोग के लिए एक नमूना EPS फ़ाइल तैयार रखें। यदि आपके पास नहीं है, तो प्रदान की गई उदाहरण फ़ाइल **"xmp4.eps."** का उपयोग करें।

## पैकेज आयात करें
`import` स्टेटमेंट्स आवश्यक Aspose.Page क्लासेज़ को स्कोप में लाते हैं।

`PsDocument` क्लास Aspose.Page का मुख्य ऑब्जेक्ट है जो मेमोरी में EPS दस्तावेज़ का प्रतिनिधित्व करता है।  
`XmpMetadata` क्लास EPS फ़ाइल में एम्बेडेड XMP पैकेट तक पहुंच प्रदान करती है।  

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## XMP मेटाडेटा को कैसे संपादित करें?
EPS फ़ाइल लोड करें, उसका XMP पैकेट प्राप्त करें, इच्छित प्रॉपर्टी को संशोधित करें, और दस्तावेज़ को सहेजें—सभी कुछ सरल लाइनों में। यह तरीका किसी भी नामित XMP मान के लिए काम करता है, चाहे वह मानक Dublin Core फ़ील्ड हो या आपका परिभाषित कस्टम नेमस्पेस।

## चरण 1: इनपुट EPS फ़ाइल स्ट्रीम को प्रारंभ करें
`FileInputStream` स्रोत EPS फ़ाइल के लिए केवल‑पढ़ने वाला स्ट्रीम खोलता है, जिससे Aspose.Page दस्तावेज़ को फ़ाइल सिस्टम को लॉक किए बिना इनजेस्ट कर सकता है।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## चरण 2: PsDocument को प्रारंभ करें
`PsDocument` प्राथमिक ऑब्जेक्ट है जो EPS सामग्री को संलग्न करता है और उसके मेटाडेटा, पृष्ठ, और संसाधनों तक पहुंच प्रदान करता है।

```java
PsDocument document = new PsDocument(psStream);
```

## चरण 3: XMP मेटाडेटा प्राप्त करें
`XmpMetadata` EPS फ़ाइल के भीतर XMP पैकेट का प्रतिनिधित्व करता है और व्यक्तिगत प्रॉपर्टीज़ को पढ़ने, संशोधित करने या हटाने के लिए मेथड्स प्रदान करता है।

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## चरण 4: XMP में नया मान सेट करें
`setProperty` मेटाडेटा पैकेट में निर्दिष्ट XMP प्रॉपर्टी का मान सेट करता है।

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## चरण 5: आउटपुट EPS फ़ाइल स्ट्रीम को प्रारंभ करें
`FileOutputStream` संशोधित EPS फ़ाइल को सहेजने के लिए एक लिखने योग्य स्ट्रीम बनाता है।

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## चरण 6: बदले हुए XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
`save` इन‑मेमोरी PsDocument को, अपडेटेड XMP सहित, आउटपुट स्ट्रीम में लिखता है।

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## चरण 7: इनपुट EPS स्ट्रीम को बंद करें
`close` फ़ाइल हैंडल को रिलीज़ करता है और इनपुट स्ट्रीम से जुड़े संसाधनों को मुक्त करता है।

```java
// Close input EPS stream
psStream.close();
```

## सामान्य समस्याएँ और समाधान
- **FileNotFoundException** – यह सुनिश्चित करें कि `dataDir` सही फ़ोल्डर की ओर इशारा कर रहा है और `xmp4.eps` मौजूद है।  
- **LicenseException** – यदि आप लाइसेंसिंग त्रुटियाँ देखते हैं, तो `PsDocument` बनाने से पहले एक वैध Aspose.Page लाइसेंस फ़ाइल लोड करें।  
- **Metadata Not Updated** – सहेजने के बाद, परिणामस्वरूप EPS को एक मेटाडेटा व्यूअर (जैसे Adobe Bridge) में खोलें ताकि नया मान दिखाई दे।

## अक्सर पूछे जाने वाले प्रश्न
**Q: क्या मैं Aspose.Page for Java को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?**  
A: Aspose.Page मुख्यतः Java को सपोर्ट करता है, लेकिन Aspose .NET, C++, और Python के लिए समान लाइब्रेरीज़ प्रदान करता है जो समान XMP हेरफेर क्षमताएँ देती हैं।

**Q: क्या Aspose.Page for Java के लिए कोई मुफ्त ट्रायल उपलब्ध है?**  
A: हाँ, आप Aspose.Page for Java का मुफ्त ट्रायल [here](https://releases.aspose.com/) पर एक्सप्लोर कर सकते हैं।

**Q: Aspose.Page for Java के बारे में अतिरिक्त समर्थन और चर्चा कहाँ मिल सकती है?**  
A: समुदाय समर्थन और चर्चाओं के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) देखें।

**Q: Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A: आप अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

**Q: Aspose.Page for Java कहाँ खरीद सकता हूँ?**  
A: Aspose.Page for Java खरीदने के लिए [purchase page](https://purchase.aspose.com/buy) पर जाएँ।

---

**अंतिम अपडेट:** 2026-05-15  
**परीक्षण किया गया:** Aspose.Page for Java (latest release)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [How to Read XMP Metadata using Java – Aspose.Page Guide](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Aspose Page Java Tutorial – Add XMP Metadata to EPS Files](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – Change Values in XMP using Java](/page/java/xmp-metadata-manipulation/change-values/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}