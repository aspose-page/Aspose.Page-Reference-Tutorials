---
date: 2026-05-20
description: Aspose.Page for Java के साथ EPS फ़ाइलों में XMP मेटाडेटा जोड़ना सीखें।
  प्रोग्रामेटिक रूप से सरल XMP प्रॉपर्टीज़ को एम्बेड करने के लिए चरण‑दर‑चरण गाइड।
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: जावा का उपयोग करके XMP में सरल प्रॉपर्टीज़ जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: जावा का उपयोग करके EPS फ़ाइलों में XMP मेटाडेटा जोड़ें
url: /hi/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java का उपयोग करके EPS फ़ाइलों में XMP मेटाडेटा जोड़ें

## परिचय
आधुनिक ग्राफ़िक्स पाइपलाइन में, प्रोग्रामेटिक रूप से EPS फ़ाइलों में **XMP मेटाडेटा जोड़ना** सक्षम होने से आप यह नियंत्रित कर सकते हैं कि आपके चित्र कैसे वर्णित, खोजे और संग्रहित किए जाते हैं। Aspose.Page for Java के साथ आप EPS दस्तावेज़ों के भीतर XMP पैकेट को पढ़, संशोधित और लिख सकते हैं, बिना Java इकोसिस्टम छोड़े। इस ट्यूटोरियल में हम आपको EPS फ़ाइल में सरल XMP प्रॉपर्टी जोड़ने के सटीक चरणों के माध्यम से ले जाएंगे, ताकि आप अपने ग्राफ़िक्स को कस्टम मेटाडेटा के साथ जल्दी और विश्वसनीय रूप से समृद्ध कर सकें।

## त्वरित उत्तर
- **“add XMP metadata to EPS” का क्या अर्थ है?** EPS फ़ाइल के भीतर XMP पैकेट (XML‑आधारित मेटाडेटा) को एम्बेड करना।  
- **कौन‑सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java (Aspose साइट से डाउनलोड किया जा सकता है)।  
- **क्या परीक्षण के लिए लाइसेंस चाहिए?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **कोड की कितनी पंक्तियाँ?** 30 से कम Java पंक्तियों के साथ कुछ इम्पोर्ट स्टेटमेंट्स।  
- **क्या मैं अन्य डेटा प्रकार जोड़ सकता हूँ?** हाँ – तिथियाँ, पूर्णांक, डबल, स्ट्रिंग, और यहाँ तक कि एरे भी समर्थित हैं।

## Java का उपयोग करके EPS फ़ाइलों में XMP मेटाडेटा कैसे जोड़ें?
EPS फ़ाइल को `new PsDocument("input.eps")` से लोड करें, उसका XMP पैकेट प्राप्त या बनाएं, इच्छित प्रॉपर्टी डालें, और फिर दस्तावेज़ को डिस्क पर सहेजें – यह सब दस से कम Java कोड लाइनों में। यह तरीका आपको मैन्युअल EPS स्रोत संपादन के बिना खोज योग्य, मानकों‑अनुपालन मेटाडेटा एम्बेड करने की सुविधा देता है।

## EPS में XMP मेटाडेटा क्या है?
EPS में XMP मेटाडेटा एक XML पैकेट है जो EPS फ़ाइल के भीतर रहता है और लेखक, निर्माण तिथि, और कस्टम टैग जैसी जानकारी संग्रहीत करता है। इस पैकेट को एम्बेड करने से डाउनस्ट्रीम टूल्स डेटा को पढ़ और उस पर कार्य कर सकते हैं, बिना अलग साइड‑कार फ़ाइलों की आवश्यकता के।

## EPS फ़ाइलों में XMP मेटाडेटा क्यों जोड़ें?
XMP मेटाडेटा को एम्बेड करने से EPS एसेट तुरंत खोज योग्य बनते हैं, फ़ाइल के भीतर लाइसेंसिंग जानकारी संग्रहीत करके अनुपालन सुनिश्चित होता है, एम्बेडेड टैग के आधार पर स्वचालित पाइपलाइन निर्णय ले सकती हैं, और यह गारंटी देता है कि मेटाडेटा ग्राफ़िक के साथ सभी प्लेटफ़ॉर्म पर यात्रा करता रहे। Aspose.Page फ़ाइलों को 500 MB तक बिना पूरे दस्तावेज़ को मेमोरी में लोड किए प्रोसेस कर सकता है, जिससे बड़े‑स्तर के वर्कलोड के लिए तेज़ प्रदर्शन मिलता है।

## पूर्वापेक्षाएँ
- Java प्रोग्रामिंग का बुनियादी ज्ञान।  
- Aspose.Page for Java लाइब्रेरी स्थापित। आप इसे **[here](https://releases.aspose.com/page/java/)** से डाउनलोड कर सकते हैं।  
- मेटाडेटा युक्त एक नमूना EPS फ़ाइल। यदि आपके पास नहीं है, तो प्रदान की गई **`xmp3.eps`** फ़ाइल का उपयोग कर सकते हैं।

## पैकेज आयात करें
पहले, उन क्लासों को आयात करें जिनकी आपको आवश्यकता होगी। आयात मूल उदाहरण की तरह ही समान रहते हैं:

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

## चरण 1: EPS दस्तावेज़ लोड करें और XMP मेटाडेटा प्राप्त करें
`PsDocument` क्लास EPS फ़ाइल का प्रतिनिधित्व करती है और इसकी सामग्री और मेटाडेटा तक पहुँचने के लिए मेथड प्रदान करती है।  
`XmpMetadata` ऑब्जेक्ट दस्तावेज़ से जुड़ा XMP पैकेट रखता है।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## चरण 2: एक Date प्रॉपर्टी जोड़ें
`Date` क्लास समय के एक विशिष्ट क्षण को मिलिसेकंड सटीकता के साथ दर्शाती है।

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## चरण 3: एक Integer प्रॉपर्टी जोड़ें
`Integer` क्लास एक प्रिमिटिव `int` मान को ऑब्जेक्ट के रूप में रैप करती है।

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## चरण 4: एक Double प्रॉपर्टी जोड़ें
`Double` क्लास एक प्रिमिटिव `double` मान को ऑब्जेक्ट के रूप में रैप करती है।

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## चरण 5: एक String प्रॉपर्टी जोड़ें
`String` क्लास अक्षरों की एक श्रृंखला को दर्शाती है।

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## चरण 6: अपडेटेड EPS फ़ाइल सहेजें
`save` मेथड संशोधित दस्तावेज़ को डिस्क पर वापस लिखता है, EPS संरचना को संरक्षित रखते हुए।

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## चरण 7: संसाधनों को साफ़ करें
फ़ाइल‑हैंडल लीक से बचने और सभी बफ़र फ्लश होने को सुनिश्चित करने के लिए हमेशा स्ट्रीम्स को बंद करें।

```java
// Close input EPS stream
psStream.close();
```

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|--------|-----|
| **Null XMP metadata** | EPS फ़ाइल में कोई XMP पैकेट नहीं था और लाइब्रेरी PS कमेंट्स का अनुमान नहीं लगा सकी। | सुनिश्चित करें कि स्रोत EPS में कम से कम एक PS कमेंट (जैसे `%%Creator`) हो। लाइब्रेरी स्वचालित रूप से एक न्यूनतम XMP पैकेट उत्पन्न करेगी। |
| **Time zone mismatch** | तिथियाँ दूसरे एप्लिकेशन में खोलने पर शिफ्ट दिखती हैं। | `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` को `Date` ऑब्जेक्ट बनाने से पहले सेट करें, जैसा कि चरण 2 में दिखाया गया है। |
| **License exception** | रनटाइम `LicenseException` फेंकता है। | API उपयोग करने से पहले वैध Aspose.Page लाइसेंस लागू करें, या मूल्यांकन के लिए ट्रायल मोड में चलाएँ। |

## अक्सर पूछे जाने वाले प्रश्न
**Q: क्या मैं Aspose.Page for Java को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?**  
A: Aspose.Page मुख्यतः Java को सपोर्ट करता है, लेकिन .NET, C++, और Python के लिए समकक्ष लाइब्रेरी उपलब्ध हैं।

**Q: क्या Aspose.Page for Java के लिए मुफ्त ट्रायल उपलब्ध है?**  
A: हाँ, आप Aspose.Page की सुविधाओं को मुफ्त ट्रायल **[here](https://releases.aspose.com/)** प्राप्त करके एक्सप्लोर कर सकते हैं।

**Q: Aspose.Page for Java के विस्तृत दस्तावेज़ कहाँ मिलेंगे?**  
A: दस्तावेज़ **[here](https://reference.aspose.com/page/java/)** पर उपलब्ध है।

**Q: मैं Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?**  
A: एक अस्थायी लाइसेंस **[here](https://purchase.aspose.com/temporary-license/)** से प्राप्त किया जा सकता है।

**Q: मैं Aspose.Page for Java कहाँ खरीद सकता हूँ?**  
A: आप उत्पाद **[here](https://purchase.aspose.com/buy)** से खरीद सकते हैं।

---

**अंतिम अपडेट:** 2026-05-20  
**परीक्षण किया गया:** Aspose.Page for Java 24.12 (latest at time of writing)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Java का उपयोग करके XMP मेटाडेटा पढ़ने का तरीका – Aspose.Page गाइड](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page XMP ट्यूटोरियल – Java में XMP में नेमस्पेस जोड़ें](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Java का उपयोग करके XMP मेटाडेटा में एरे आइटम जोड़ें](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}