---
date: 2025-12-20
description: Aspose Page Java ट्यूटोरियल के साथ EPS फ़ाइलों में XMP मेटाडेटा जोड़ना
  सीखें। अपने दस्तावेज़ प्रबंधन को बेहतर बनाने के लिए इस चरण‑दर‑चरण गाइड का पालन करें।
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Aspose Page Java ट्यूटोरियल – EPS फ़ाइलों में XMP मेटाडेटा जोड़ें
url: /hi/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा का उपयोग करके XMP में मेटाडेटा जोड़ें

## परिचय
इस **aspose page java tutorial** में, आप जावा का उपयोग करके XMP जानकारी जोड़कर अपने दस्तावेज़ की मेटाडेटा को कैसे बढ़ाएँ, यह सीखेंगे। यह चरण‑दर‑चरण गाइड आपको मौजूदा EPS फ़ाइल पढ़ने, उसकी XMP मेटाडेटा निकालने, और Aspose.Page for Java लाइब्रेरी के साथ बदलावों को डिस्क पर सहेजने की प्रक्रिया से गुज़राता है। ट्यूटोरियल के अंत तक आपके पास किसी भी EPS वर्कफ़्लो में XMP के साथ काम करने के लिए एक ठोस, पुन: उपयोग योग्य पैटर्न होगा।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java  
- **क्या मैं किसी भी EPS फ़ाइल में XMP जोड़ सकता हूँ?** हाँ – यदि पहले से मौजूद नहीं है तो API नया XMP ब्लॉक बनाता है।  
- **क्या विकास के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन सा जावा संस्करण समर्थित है?** Java 8 और बाद के संस्करण।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** सामान्यतः बुनियादी मेटाडेटा अपडेट के लिए 10 मिनट से कम।

## Aspose Page Java ट्यूटोरियल अवलोकन
यह ट्यूटोरियल EPS फ़ाइलों में XMP मेटाडेटा को हेरफेर करने के मुख्य चरणों को दर्शाता है। इन चरणों को समझने से आप मेटाडेटा हैंडलिंग को बड़े दस्तावेज़‑प्रोसेसिंग पाइपलाइन में एकीकृत कर सकते हैं, खोजयोग्यता में सुधार कर सकते हैं, और डिजिटल एसेट मैनेजमेंट के उद्योग मानकों का पालन कर सकते हैं।

## पूर्वापेक्षाएँ
ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान।  
- Aspose.Page for Java लाइब्रेरी स्थापित हो। आप इसे [यहाँ](https://releases.aspose.com/page/java/) से डाउनलोड कर सकते हैं।  
- वह EPS फ़ाइल जिसे आप संशोधित करना चाहते हैं।

## पैकेज आयात करें
सबसे पहले, आवश्यक पैकेजों को अपने जावा प्रोग्राम में आयात करें:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## चरण 1: XMP मेटाडेटा प्राप्त करें
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

`"Your Document Directory"` को उस वास्तविक पथ से बदलें जहाँ आपके दस्तावेज़ संग्रहीत हैं।

## चरण 2: CreatorTool मान प्राप्त करें
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## चरण 3: CreateDate मान प्राप्त करें
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## चरण 4: Title मान प्राप्त करें
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## चरण 5: Format मान प्राप्त करें
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## चरण 6: Creator मान प्राप्त करें
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## चरण 7: MetadataDate मान प्राप्त करें
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## चरण 8: नई XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

अंत में, इनपुट EPS स्ट्रीम को बंद करना न भूलें:

```java
// Close input EPS stream
psStream.close();
```

अब, आपने Aspose.Page for Java का उपयोग करके अपने EPS फ़ाइल में सफलतापूर्वक मेटाडेटा जोड़ दिया है!

## निष्कर्ष
इस **aspose page java tutorial** में, हमने Aspose.Page for Java लाइब्रेरी का उपयोग करके EPS फ़ाइल में XMP मेटाडेटा जोड़ने का तरीका खोजा। यह शक्तिशाली API आपको प्रोग्रामेटिक रूप से दस्तावेज़ मेटाडेटा को हेरफेर करने की सुविधा देती है, जिससे आप एसेट्स को व्यवस्थित और खोजने योग्य रख सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या Aspose.Page for Java मुफ्त में उपयोग किया जा सकता है?**  
उत्तर: Aspose.Page for Java एक व्यावसायिक उत्पाद है। आप इसकी सुविधाओं को एक मुफ्त ट्रायल के माध्यम से [यहाँ](https://releases.aspose.com/) देख सकते हैं।

**प्रश्न: Aspose.Page for Java की दस्तावेज़ीकरण कहाँ मिल सकती है?**  
उत्तर: दस्तावेज़ीकरण उपलब्ध है [यहाँ](https://reference.aspose.com/page/java/)।

**प्रश्न: मैं Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
उत्तर: आप अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) प्राप्त कर सकते हैं।

**प्रश्न: Aspose.Page for Java किन फ़ाइल फ़ॉर्मेट्स को सपोर्ट करता है?**  
उत्तर: Aspose.Page for Java विभिन्न फ़ॉर्मेट्स को सपोर्ट करता है, जैसे EPS, PDF, और XPS।

**प्रश्न: क्या मैं Aspose.Page for Java खरीद सकता हूँ?**  
उत्तर: हाँ, आप Aspose.Page for Java को [यहाँ](https://purchase.aspose.com/buy) खरीद सकते हैं।

**प्रश्न: बड़े EPS फ़ाइलों में मेटाडेटा जोड़ते समय क्या करना चाहिए?**  
उत्तर: फ़ाइल को स्ट्रीमिंग मोड में प्रोसेस करें (जैसा कि दिखाया गया है) ताकि मेमोरी उपयोग कम रहे, और स्ट्रीम्स को तुरंत बंद करें।

**प्रश्न: क्या मैं केवल पढ़ने के बजाय मौजूदा XMP फ़ील्ड्स को संशोधित कर सकता हूँ?**  
उत्तर: बिल्कुल – आप `xmp.put(key, value)` का उपयोग करके नई एंट्रीज़ जोड़ या अपडेट कर सकते हैं, फिर सहेजें।

---

**अंतिम अपडेट:** 2025-12-20  
**परीक्षित संस्करण:** Aspose.Page for Java 24.12 (नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}