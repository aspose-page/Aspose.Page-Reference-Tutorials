---
date: 2025-12-21
description: Aspose.Page के साथ जावा का उपयोग करके XMP मेटाडेटा पढ़ना सीखें। यह चरण‑दर‑चरण
  गाइड आपको दिखाता है कि दस्तावेज़ फ़ॉर्मेट XMP को कैसे पढ़ें और प्रमुख गुणों को कैसे
  निकालें।
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: जावा का उपयोग करके XMP मेटाडेटा कैसे पढ़ें – Aspose.Page गाइड
url: /hi/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java का उपयोग करके XMP से मेटाडेटा प्राप्त करें

## Java का उपयोग करके XMP मेटाडेटा कैसे पढ़ें

Welcome to our step‑by‑step tutorial that shows **XMP को कैसे पढ़ें** metadata with Java and the Aspose.Page library. XMP (Extensible Metadata Platform) is a widely adopted standard for embedding rich metadata inside documents. By the end of this guide you’ll be able to read document format XMP, pull out creator information, timestamps, thumbnails, and more—empowering you to build smarter document‑analysis solutions.

## त्वरित उत्तर
- **“how to read xmp” का क्या अर्थ है?** यह फ़ाइलों से प्रोग्रामेटिक रूप से XMP मेटाडेटा निकालने को दर्शाता है।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java (उपलब्ध Aspose डाउनलोड पेज से)।  
- **क्या मुझे लाइसेंस चाहिए?** प्रोडक्शन उपयोग के लिए एक अस्थायी या पूर्ण लाइसेंस आवश्यक है; एक मुफ्त ट्रायल उपलब्ध है।  
- **कौन सा Java संस्करण समर्थित है?** Java 8 या उससे ऊपर।  
- **क्या मैं XMP को अन्य फ़ॉर्मेट से पढ़ सकता हूँ?** हाँ, Aspose.Page EPS, PDF और कई इमेज प्रकारों को संभाल सकता है जो XMP एम्बेड करते हैं।

## पूर्वापेक्षाएँ
Before diving into the code, make sure you have:

- **Java Development Kit (JDK)** – आपके मशीन पर Java 8+ स्थापित और कॉन्फ़िगर किया हुआ।  
- **Aspose.Page for Java** – आधिकारिक साइट से लाइब्रेरी डाउनलोड करें [here](https://releases.aspose.com/page/java/).  
- एक EPS फ़ाइल जिसमें XMP मेटाडेटा हो (जैसे, `xmp1.eps`)।  

## पैकेज इम्पोर्ट करें
In your Java project, import the necessary packages:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## चरण 1: इनपुट EPS फ़ाइल स्ट्रीम को इनिशियलाइज़ करें
Begin by setting the path to your document directory and initializing the input EPS file stream.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## चरण 2: XMP मेटाडेटा प्राप्त करें
Retrieve XMP metadata from the EPS file. If the file lacks XMP metadata, a new one will be generated with values from PS metadata comments.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## चरण 3: CreatorTool जानकारी निकालें
Check and print the "CreatorTool" value from the XMP metadata.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## चरण 4: CreateDate जानकारी निकालें
Check and print the "CreateDate" value from the XMP metadata.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## चरण 5: थंबनेल की चौड़ाई प्राप्त करें
If thumbnails exist, extract and print the width of the first thumbnail.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## चरण 6: Format जानकारी निकालें
Check and print the "format" value from the XMP metadata.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## चरण 7: DocumentID प्राप्त करें
Check and print the "DocumentID" value from the XMP metadata.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## यह क्यों महत्वपूर्ण है
Reading XMP metadata lets you programmatically discover the origin, creation date, and other essential attributes of a document without opening it in a viewer. This is especially useful for batch processing, content management systems, and digital asset pipelines where metadata drives indexing and search.

## सामान्य कठिनाइयाँ और टिप्स
- **Missing XMP:** Some EPS files may not contain XMP. The `getXmpMetadata()` call will synthesize a minimal set based on existing PS comments, but you won’t get full metadata unless it’s embedded.  
- **Thumbnail Arrays:** The `xmp:Thumbnails` key can hold multiple entries. The example extracts only the first one; iterate the array if you need all thumbnails.  
- **Namespace Awareness:** XMP keys use namespaces (e.g., `xmp:`, `dc:`). Ensure you reference the exact key name; otherwise `containsKey` will return false.

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Page for Java को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?
Yes, Aspose.Page supports multiple languages, including Java, .NET, and more. Check the [documentation](https://reference.aspose.com/page/java/) for details.

### क्या Aspose.Page for Java के लिए मुफ्त ट्रायल उपलब्ध है?
Yes, you can access the free trial [here](https://releases.aspose.com/).

### मैं Aspose.Page for Java के लिए समर्थन कहाँ पा सकता हूँ?
Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.

### मैं Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

### क्या Aspose.Page for Java के लिए अतिरिक्त संसाधन हैं?
Explore the complete [documentation](https://reference.aspose.com/page/java/) and download the library [here](https://releases.aspose.com/page/java/).

## अतिरिक्त FAQ
**Q: क्या यह तरीका PDF फ़ाइलों पर काम करता है जिनमें XMP हो?**  
A: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.

**Q: क्या मैं XMP मेटाडेटा को पढ़ने के बाद संशोधित कर सकता हूँ?**  
A: Absolutely. The `XmpMetadata` object is mutable; you can add, update, or remove keys and then save the document.

**Q: क्या केवल आयामों के बजाय सभी थंबनेल इमेज को निकालने का कोई तरीका है?**  
A: You can retrieve the binary data from the `xmpGImg:data` property of each thumbnail entry and write it to a file.

## निष्कर्ष
You've now mastered **how to read XMP** metadata using Java and Aspose.Page. By following these steps you can extract creator tools, timestamps, thumbnails, format information, and document IDs—giving you full insight into the embedded metadata of your EPS files. Feel free to experiment with additional XMP namespaces to pull even richer data for your applications.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2025-12-21  
**परीक्षण किया गया:** Aspose.Page for Java 24.12 (latest)  
**लेखक:** Aspose