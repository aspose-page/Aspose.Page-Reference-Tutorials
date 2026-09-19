---
date: 2026-09-19
description: Aspose.Page for Java का उपयोग करके EPS फ़ाइलों में XMP नामित मान जोड़ना
  सीखें – कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Java का उपयोग करके XMP में नामित मान जोड़ें
og_description: Aspose.Page for Java का उपयोग करके EPS फ़ाइलों में XMP नामित मान जोड़ना।
  कस्टम metadata को मिनटों में सम्मिलित करने के लिए इस संक्षिप्त मार्गदर्शिका का पालन
  करें।
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: Java का उपयोग करके EPS फ़ाइलों में XMP नामित मान कैसे जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: Java का उपयोग करके EPS फ़ाइलों में XMP नामित मान कैसे जोड़ें
url: /hi/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java का उपयोग करके XMP मेटाडेटा में नामित मान जोड़ें

## परिचय
आधुनिक Java विकास में, EPS फ़ाइलों के भीतर **XMP कैसे जोड़ें** मेटाडेटा सीखना दस्तावेज़ की उत्पत्ति को संरक्षित करने और खोजयोग्यता को सुधारने के लिए आवश्यक है। **Aspose.Page for Java** के साथ, आप कस्टम नामित मानों को XMP पैकेट में आसानी से डाल सकते हैं। यह ट्यूटोरियल आपको सटीक चरणों के माध्यम से ले जाता है—कोड स्निपेट्स सहित—ताकि आप आज ही अपने EPS दस्तावेज़ों में XMP मेटाडेटा जोड़ना शुरू कर सकें।

## त्वरित उत्तर
- **कौनसी लाइब्रेरी आवश्यक है?** Aspose.Page for Java (Aspose)  
- **कौनसी फ़ाइल प्रकार लक्षित है?** EPS files containing XMP metadata  
- **मुख्य उपयोग मामला?** Add custom named values (e.g., page size limits) to XMP  
- **पूर्वापेक्षाएँ?** JDK 8+ and the Aspose.Page for Java library  
- **सामान्य कार्यान्वयन समय?** 5–10 minutes once the library is set up  

## asp क्या है?
Aspose, Aspose का संक्षिप्त रूप है, एक suite of APIs है जो डेवलपर्स को विभिन्न दस्तावेज़ फ़ॉर्मेट को बिना बाहरी सॉफ़्टवेयर के बनाएँ, संपादित करें, परिवर्तित करें और रेंडर करें। Aspose.Page for Java घटक विशेष रूप से PostScript और EPS प्रोसेसिंग पर केंद्रित है, जो पेज सामग्री, ग्राफ़िक्स और XMP जैसी मेटाडेटा तक प्रोग्रामेटिक पहुँच प्रदान करता है।

## XMP मेटाडेटा में नामित मान क्यों जोड़ें?
नामित मान आपको XMP पैकेट के भीतर सीधे मनमाने कुंजी‑मान जोड़े संग्रहीत करने देते हैं, जिससे वे डाउनस्ट्रीम टूल्स द्वारा तुरंत पढ़े जा सकते हैं। यह खोज‑इंजन मित्रता को सुधारता है, वर्कफ़्लो ऑटोमेशन को सक्षम करता है, और नियामक जानकारी को दृश्य सामग्री को बदले बिना एम्बेड करके अनुपालन आवश्यकताओं को पूरा करता है।

## यह क्यों महत्वपूर्ण है
XMP में नामित मान जोड़ने से आप मनमाने कुंजी‑मान जोड़े संग्रहीत कर सकते हैं जिन्हें पूरे EPS फ़ाइल को पार्स किए बिना पढ़ा जा सकता है। यह क्षमता विशेष रूप से स्वचालित प्रकाशन पाइपलाइन, डिजिटल एसेट मैनेजमेंट सिस्टम और अनुपालन‑चालित वर्कफ़्लो में मूल्यवान है जहाँ मेटाडेटा डाउनस्ट्रीम कार्यों को संचालित करता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- **Java Development Kit (JDK):** आपके मशीन पर स्थापित नवीनतम JDK (8 या उससे ऊपर)।
- **Aspose.Page for Java Library:** इसे आधिकारिक [Aspose.Page for Java download](https://releases.aspose.com/page/java/) से डाउनलोड करें। JAR को अपने प्रोजेक्ट की classpath में जोड़ें।
- **एक EPS फ़ाइल** जिसमें पहले से XMP मेटाडेटा हो या जो स्वचालित रूप से उत्पन्न होगी।

## पैकेज आयात करें
आवश्यक Java पैकेज आयात करके शुरू करें। ये इम्पोर्ट्स आपको फ़ाइल स्ट्रीम, EPS दस्तावेज़ मॉडल, और XMP हैंडलिंग क्लासेज़ तक पहुँच प्रदान करते हैं।

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Java का उपयोग करके EPS फ़ाइलों में XMP नामित मान कैसे जोड़ें
नामित मान जोड़ने के लिए, EPS फ़ाइल को `FileInputStream` के साथ लोड करें, उसका `XmpMetadata` ऑब्जेक्ट प्राप्त या बनाएं, इच्छित `NamedValue` को उपयुक्त नेमस्पेस में डालें, और फिर संशोधित दस्तावेज़ को `FileOutputStream` का उपयोग करके वापस लिखें। यदि XMP पैकेट अनुपलब्ध है तो Aspose.Page स्वचालित रूप से इसे बनाता है, जिससे नया मेटाडेटा सही ढंग से एम्बेड हो जाता है।

### चरण 1: इनपुट EPS फ़ाइल स्ट्रीम प्रारंभ करें
**FileInputStream** एक Java I/O क्लास है जो फ़ाइल से कच्चे बाइट्स पढ़ता है। स्रोत EPS फ़ाइल को `FileInputStream` में लोड करें। यह स्ट्रीम दस्तावेज़ को Aspose की API में फीड करता है।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Pro tip:** `dataDir` वेरिएबल को कॉन्फ़िगरेबल रखें ताकि समान कोड विभिन्न वातावरणों में काम करे।

### चरण 2: XMP मेटाडेटा प्राप्त करें
**XmpMetadata** एक EPS दस्तावेज़ से जुड़ा XMP पैकेट दर्शाता है। मौजूदा XMP पैकेट प्राप्त करें; यदि EPS फ़ाइल में यह नहीं है, तो Aspose PS टिप्पणियों से भरकर एक नया XMP ऑब्जेक्ट बनाता है।

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### चरण 3: नामित मान जोड़ें
**NamedValue** XMP मेटाडेटा नेमस्पेस के भीतर संग्रहीत एक कुंजी‑मान जोड़ा है। XMP संरचना में एक कस्टम नामित मान डालें। इस उदाहरण में हम `xmpTPg:MaxPageSize` नेमस्पेस के तहत एक नई कुंजी जोड़ते हैं।

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Why this matters:** नामित मान आपको मनमाने कुंजी‑मान जोड़े संग्रहीत करने देते हैं जिन्हें डाउनस्ट्रीम एप्लिकेशन पूरे दस्तावेज़ को पार्स किए बिना पढ़ सकते हैं।

### चरण 4: आउटपुट EPS फ़ाइल स्ट्रीम प्रारंभ करें
**FileOutputStream** एक Java I/O क्लास है जो फ़ाइल में कच्चे बाइट्स लिखता है। एक `FileOutputStream` तैयार करें जहाँ संशोधित EPS सहेजा जाएगा।

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### चरण 5: दस्तावेज़ सहेजें
`save` मेथड परिवर्तन को स्थायी बनाता है। यह अपडेटेड XMP पैकेट को EPS फ़ाइल में वापस लिखता है, यह सुनिश्चित करता है कि नया नामित मान दस्तावेज़ की मेटाडेटा का हिस्सा बन जाए।

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### चरण 6: इनपुट EPS स्ट्रीम बंद करें
मूल फ़ाइल हैंडल को बंद करने से संसाधन लीक रोकते हैं और यह सुनिश्चित होता है कि फ़ाइल आगे के ऑपरेशनों के लिए लॉक न रहे।

```java
psStream.close();
```

इन छह चरणों का पालन करके, आपने **Aspose.Page for Java** का उपयोग करके **XMP मेटाडेटा में नामित मान जोड़ना** सफलतापूर्वक किया है।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|-----|
| `NullPointerException` on `xmp` | EPS फ़ाइल में XMP नहीं है और Aspose इसे उत्पन्न करने में विफल रहा | सुनिश्चित करें कि EPS में कम से कम एक PS टिप्पणी हो या मैन्युअल रूप से नया `XmpMetadata` इंस्टेंस बनाएं। |
| आउटपुट फ़ाइल खाली है | आउटपुट स्ट्रीम फ़्लश/बंद नहीं किया गया | `outPsStream.close()` को `finally` ब्लॉक में कॉल किया गया है, यह सुनिश्चित करें (जैसा दिखाया गया है)। |
| डुप्लिकेट कुंजी त्रुटि | एक ही नामित मान दो बार जोड़ा गया | जोड़ने से पहले `xmp.containsNamedValue(...)` के साथ जांचें कि कुंजी पहले से मौजूद है या नहीं। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.Page for Java को अन्य Java लाइब्रेरीज़ के साथ सहजता से काम करने के लिए डिज़ाइन किया गया है, जिससे आपके विकास वातावरण में लचीलापन मिलता है।

**Q: क्या Aspose.Page for Java के लिए मुफ्त ट्रायल उपलब्ध है?**  
A: हाँ, आप Aspose.Page for Java का मुफ्त ट्रायल [Aspose releases page](https://releases.aspose.com/) पर प्राप्त कर सकते हैं।

**Q: मैं Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?**  
A: Aspose.Page for Java के लिए अस्थायी लाइसेंस प्राप्त करने हेतु [temporary license page](https://purchase.aspose.com/temporary-license/) पर जाएँ।

**Q: मैं Aspose.Page for Java के लिए अधिक ट्यूटोरियल और उदाहरण कहाँ पा सकता हूँ?**  
A: व्यापक ट्यूटोरियल और उदाहरणों के लिए [documentation](https://reference.aspose.com/page/java/) देखें।

**Q: क्या Aspose.Page for Java बड़े‑पैमाने के प्रोजेक्ट्स के लिए उपयुक्त है?**  
A: बिल्कुल, Aspose.Page for Java को बड़े‑पैमाने के प्रोजेक्ट्स को कुशलतापूर्वक संभालने के लिए डिज़ाइन किया गया है, जो मजबूत दस्तावेज़ हेरफेर क्षमताएँ प्रदान करता है।

## निष्कर्ष
इस गाइड में हमने दिखाया कि **Aspose.Page for Java** कैसे EPS फ़ाइलों के भीतर **XMP मेटाडेटा में नामित मान जोड़ना** सरल बनाता है। ऊपर बताए गए चरणों के साथ, आप अपने दस्तावेज़ों को कस्टम मेटाडेटा से समृद्ध कर सकते हैं, खोजयोग्यता सुधार सकते हैं, और अधिक स्मार्ट डाउनस्ट्रीम प्रोसेसिंग को सक्षम कर सकते हैं।

---

**Last Updated:** 2026-09-19  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Page का उपयोग करके EPS फ़ाइलों में XMP नेमस्पेस कैसे जोड़ें – Java ट्यूटोरियल](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Java का उपयोग करके EPS फ़ाइलों में XMP मेटाडेटा जोड़ें](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [Aspose.Page का उपयोग करके XMP पढ़ें – Java गाइड](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}