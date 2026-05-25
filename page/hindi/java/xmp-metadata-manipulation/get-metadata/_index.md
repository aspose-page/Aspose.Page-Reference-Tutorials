---
date: 2026-05-25
description: जाने कैसे Java के साथ Aspose.Page का उपयोग करके XMP पढ़ें। यह चरण‑दर‑चरण
  गाइड XMP metadata, creator info, timestamps, thumbnails, और अधिक दिखाता है।
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Java का उपयोग करके XMP Metadata पढ़ने का तरीका
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Aspose.Page का उपयोग करके XMP पढ़ें – Java गाइड
url: /hi/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा का उपयोग करके XMP से मेटाडेटा प्राप्त करें

## Aspose.Page (Java) का उपयोग करके XMP कैसे पढ़ें?

EPS फ़ाइल को `new Document("file.eps")` के साथ लोड करें—`Document` क्लास लोड की गई फ़ाइल का प्रतिनिधित्व करती है। `getXmpMetadata()` को कॉल करें, जो XMP पैकेट को निकालता है, और फिर लौटाए गए `XmpMetadata` ऑब्जेक्ट—जो XMP प्रॉपर्टीज़ के लिए एक मैप‑जैसा इंटरफ़ेस है—से आवश्यक कुंजियों को प्राप्त करें। यह Aspose.Page का उपयोग करके XMP पढ़ने के लिए आवश्यक सब कुछ है। API लो‑लेवल पार्सिंग को एब्स्ट्रैक्ट करती है, इसलिए आप केवल दो पंक्तियों के कोड में उपयोग‑के‑लिए तैयार प्रॉपर्टी मैप प्राप्त कर लेते हैं।

Welcome to our step‑by‑step tutorial that shows **XMP कैसे पढ़ें** metadata with Java and the Aspose.Page library. XMP (Extensible Metadata Platform) is a widely adopted standard for embedding rich metadata inside documents. By the end of this guide you’ll be able to read document format XMP, pull out creator information, timestamps, thumbnails, and more—empowering you to build smarter document‑analysis solutions.

## त्वरित उत्तर
- **XMP पढ़ना** क्या मतलब है? यह फ़ाइल के भीतर मेटाडेटा संग्रहीत करने वाले XMP पैकेट को प्रोग्रामेटिकली निकालने को दर्शाता है।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java (download from the official page [here](https://releases.aspose.com/page/java/)).  
- **क्या मुझे लाइसेंस चाहिए?** उत्पादन के लिए एक अस्थायी या पूर्ण लाइसेंस आवश्यक है; मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है।  
- **कौन सा जावा संस्करण समर्थित है?** Java 8 या उससे ऊपर।  
- **क्या मैं XMP को अन्य फ़ॉर्मेट्स से पढ़ सकता हूँ?** हाँ – Aspose.Page EPS, PDF, JPEG, PNG और 20 से अधिक अन्य फ़ॉर्मेट्स से XMP निकालता है।

## आवश्यकताएँ
- **Java Development Kit (JDK)** – आपके मशीन पर Java 8+ स्थापित और कॉन्फ़िगर किया हुआ।  
- **Aspose.Page for Java** – आधिकारिक साइट से लाइब्रेरी डाउनलोड करें [here](https://releases.aspose.com/page/java/).  
- एक EPS फ़ाइल जिसमें XMP मेटाडेटा हो (उदा., `xmp1.eps`).  

## पैकेज आयात करें
The `XmpMetadata` class lives in the `com.aspose.page.xmp` namespace, while the `Document` class is in `com.aspose.page`. Import both so you can work with the EPS file and its metadata.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## चरण 1: इनपुट EPS फ़ाइल स्ट्रीम को प्रारंभ करें
Begin by setting the path to your document directory and initializing the input EPS file stream.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## चरण 2: XMP मेटाडेटा प्राप्त करें
`XmpMetadata` is Aspose.Page's object that holds the XMP packet extracted from a document. Retrieve it with `document.getXmpMetadata()`. If the file lacks XMP, the API synthesises a minimal packet from existing PostScript comments.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## चरण 3: CreatorTool जानकारी निकालें
The `CreatorTool` key lives under the `xmp` namespace and records the application that generated the file. Check for its presence and print the value.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## चरण 4: CreateDate जानकारी निकालें
`CreateDate` stores the timestamp when the document was originally created. Use the same `containsKey`/`get` pattern to read it.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## चरण 5: थंबनेल की चौड़ाई प्राप्त करें
If thumbnails exist, the `xmp:Thumbnails` array holds one or more entries. Each entry contains `width`, `height`, and binary data. The example extracts the width of the first thumbnail.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## चरण 6: फ़ॉर्मेट जानकारी निकालें
The `format` key tells you the original file format (e.g., “application/postscript”). This is useful when you need to log or validate source types.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## चरण 7: DocumentID प्राप्त करें
`DocumentID` is a unique identifier assigned by the creator application. It can be used for deduplication in large asset libraries.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## क्यों यह महत्वपूर्ण है
Aspose.Page can read XMP from **20+** file formats and processes documents up to **500 MB** without loading the entire file into memory, giving you fast, low‑overhead access to essential metadata. This capability is critical for batch‑processing pipelines, digital asset management systems, and any solution that relies on searchable, machine‑readable document attributes.

## सामान्य कठिनाइयाँ और सुझाव
- **XMP अनुपलब्ध:** कुछ EPS फ़ाइलों में XMP नहीं हो सकता। `getXmpMetadata()` कॉल मौजूदा PS टिप्पणियों के आधार पर एक न्यूनतम सेट बनाता है, लेकिन पूर्ण मेटाडेटा तब तक नहीं मिलेगा जब तक वह एम्बेड न हो।  
- **थंबनेल एरेज़:** `xmp:Thumbnails` कुंजी कई प्रविष्टियों को रख सकती है। उदाहरण केवल पहले थंबनेल की चौड़ाई निकालता है; यदि आपको सभी थंबनेल चाहिए तो एरे को इटररेट करें।  
- **नेमस्पेस जागरूकता:** XMP कुंजियों में नेमस्पेस होते हैं (जैसे `xmp:`, `dc:`)। सुनिश्चित करें कि आप सटीक कुंजी नाम का उपयोग करें; अन्यथा `containsKey` false लौटाएगा।  

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Page for Java को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?
Yes, Aspose.Page supports Java, .NET, and several other languages. See the full list in the [documentation](https://reference.aspose.com/page/java/).

### क्या Aspose.Page for Java के लिए मुफ्त ट्रायल उपलब्ध है?
Yes, you can access the free trial [here](https://releases.aspose.com/).

### Aspose.Page for Java के लिए समर्थन कहाँ मिल सकता है?
Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community help and official support.

### Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करें?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

### क्या Aspose.Page for Java के लिए अतिरिक्त संसाधन हैं?
Explore the complete [documentation](https://reference.aspose.com/page/java/) and download the library [here](https://releases.aspose.com/page/java/).

## अतिरिक्त अक्सर पूछे जाने वाले प्रश्न
**प्रश्न: क्या यह तरीका PDF फ़ाइलों पर काम करता है जिनमें XMP है?**  
**उत्तर:** हाँ, Aspose.Page PDF, EPS और कई इमेज फ़ॉर्मेट्स से XMP पढ़ सकता है।

**प्रश्न: क्या मैं XMP मेटाडेटा को पढ़ने के बाद संशोधित कर सकता हूँ?**  
**उत्तर:** बिल्कुल। `XmpMetadata` ऑब्जेक्ट परिवर्तनशील है; आप कुंजियों को जोड़, अपडेट या हटाकर दस्तावेज़ को सहेज सकते हैं।

**प्रश्न: क्या केवल आयामों के बजाय सभी थंबनेल इमेज़ निकालने का कोई तरीका है?**  
**उत्तर:** आप प्रत्येक थंबनेल प्रविष्टि के `xmpGImg:data` प्रॉपर्टी से बाइनरी डेटा प्राप्त कर सकते हैं और उसे फ़ाइल में लिख सकते हैं।

## निष्कर्ष
You've now mastered **how to read XMP** metadata using Java and Aspose.Page. By following these steps you can extract creator tools, timestamps, thumbnails, format information, and document IDs—giving you full insight into the embedded metadata of your EPS files. Feel free to experiment with additional XMP namespaces to pull even richer data for your applications.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose Page Java ट्यूटोरियल – EPS फ़ाइलों में XMP मेटाडेटा जोड़ें](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page XMP ट्यूटोरियल – जावा का उपयोग करके XMP में नेमस्पेस जोड़ें](/page/java/xmp-metadata-manipulation/add-namespace/)
- [aspose page XMP ट्यूटोरियल – जावा का उपयोग करके XMP में नामित मान बदलें](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}