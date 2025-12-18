---
date: 2025-12-18
description: Aspose.Page for Java का उपयोग करके EPS फ़ाइलों के XMP मेटाडेटा में एरे
  आइटम डालकर मेटाडेटा जोड़ना सीखें। हमारे चरण‑दर‑चरण मार्गदर्शिका का पालन करें।
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: मेटाडेटा कैसे जोड़ें – XMP में एरे आइटम जोड़ें (जावा)
url: /hi/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java का उपयोग करके XMP मेटाडेटा में एरे आइटम जोड़ें

## मेटाडेटा कैसे जोड़ें
हमारे चरण‑दर‑चरण गाइड में आपका स्वागत है **मेटाडेटा कैसे जोड़ें** के बारे में, जो Aspose.Page for Java के साथ EPS फ़ाइलों में मेटाडेटा जोड़ने के लिए है। इस ट्यूटोरियल में हम आपको XMP मेटाडेटा में एरे आइटम जोड़ने की प्रक्रिया से परिचित कराएंगे—एक सामान्य आवश्यकता जब आपको दस्तावेज़ जानकारी जैसे शीर्षक या निर्माता को समृद्ध करना हो। अंत तक, आप समझेंगे कि XMP क्यों मूल्यवान है, इसे प्रोग्रामेटिक रूप से कैसे नियंत्रित किया जाता है, और अपडेटेड EPS फ़ाइल को कैसे सहेजा जाता है।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी उपयोग की जाती है?** Aspose.Page for Java  
- **कौन सा फ़ाइल फ़ॉर्मेट लक्षित है?** EPS (Encapsulated PostScript)  
- **क्या मैं कई शीर्षक जोड़ सकता हूँ?** Yes, use `xmp.addArrayItem("dc:title", ...)` repeatedly  
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** Yes, a valid Aspose.Page license is required  
- **क्या कोड Java 8+ के साथ संगत है?** Absolutely, it works with all modern Java versions  

## आवश्यकताएँ
ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हों:
- Aspose.Page for Java लाइब्रेरी स्थापित हो।  
- Java प्रोग्रामिंग की बुनियादी समझ।  
- एक वैध EPS फ़ाइल जिसमें मौजूदा XMP मेटाडेटा या PS मेटाडेटा कमेंट्स हों।  

## पैकेज इम्पोर्ट करें
शुरू करने के लिए, आपको Aspose.Page के साथ काम करने के लिए आवश्यक पैकेज इम्पोर्ट करने होंगे। अपने Java फ़ाइल की शुरुआत में निम्नलाइनों को शामिल करें:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## चरण 1: XMP मेटाडेटा प्राप्त करें
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
इस चरण में, हम EPS फ़ाइल से मौजूदा XMP मेटाडेटा प्राप्त करते हैं। यदि EPS फ़ाइल में पहले से XMP मेटाडेटा नहीं है, तो Aspose.Page एक नया बनाता है और उसे PS मेटाडेटा कमेंट्स से मानों से भरता है।

## चरण 2: "dc:title" एरे आइटम जोड़ें
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
अब, हम XMP मेटाडेटा में **dc:title** प्रॉपर्टी में एक नया एरे आइटम जोड़ते हैं। `"NewTitle"` को इच्छित शीर्षक से बदलें।

## चरण 3: "dc:creator" एरे आइटम जोड़ें
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
इसी तरह, हम XMP मेटाडेटा में **dc:creator** प्रॉपर्टी में एक नया एरे आइटम जोड़ते हैं। `"NewCreator"` को इच्छित निर्माता जानकारी से बदलें।

## चरण 4: आउटपुट EPS फ़ाइल स्ट्रीम को इनिशियलाइज़ करें
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
आउटपुट EPS फ़ाइल स्ट्रीम तैयार करें जहाँ अपडेटेड XMP मेटाडेटा के साथ संशोधित दस्तावेज़ सहेजा जाएगा।

## चरण 5: बदले हुए XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
दस्तावेज़ को अपडेटेड XMP मेटाडेटा के साथ आउटपुट EPS फ़ाइल में सहेजें।

## निष्कर्ष
बधाई हो! आपने Aspose.Page for Java का उपयोग करके XMP मेटाडेटा में एरे आइटम डालकर **मेटाडेटा कैसे जोड़ें** सीख लिया है। यह शक्तिशाली लाइब्रेरी EPS फ़ाइलों को नियंत्रित करने की प्रक्रिया को सरल बनाती है और दस्तावेज़ प्रोसेसिंग के लिए व्यापक कार्यक्षमता प्रदान करती है।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं Aspose.Page for Java को अन्य दस्तावेज़ फ़ॉर्मेट्स के साथ उपयोग कर सकता हूँ?
हाँ, Aspose.Page विभिन्न दस्तावेज़ फ़ॉर्मेट्स का समर्थन करता है, जिसमें EPS, PDF, और XPS शामिल हैं।

### क्या Aspose.Page for Java के लिए मुफ्त ट्रायल उपलब्ध है?
हाँ, आप मुफ्त ट्रायल [यहाँ](https://releases.aspose.com/) एक्सेस कर सकते हैं।

### Aspose.Page for Java की दस्तावेज़ीकरण कहाँ मिल सकती है?
दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/page/java/) उपलब्ध है।

### मैं Aspose.Page for Java कैसे खरीद सकता हूँ?
आप उत्पाद [यहाँ](https://purchase.aspose.com/buy) खरीद सकते हैं।

### क्या Aspose.Page for Java के लिए अस्थायी लाइसेंस उपलब्ध हैं?
हाँ, आप एक अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) प्राप्त कर सकते हैं।

## अतिरिक्त अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं एक ही प्रॉपर्टी में एक से अधिक एरे आइटम जोड़ सकता हूँ?**  
A: बिल्कुल। एक ही प्रॉपर्टी के लिए `xmp.addArrayItem` को कई बार कॉल करके मानों की सूची बना सकते हैं।

**Q: क्या यह तरीका Dublin Core के अलावा अन्य मौजूदा XMP स्कीमा के साथ काम करता है?**  
A: हाँ, आप किसी भी XMP प्रॉपर्टी में एरे आइटम जोड़ सकते हैं बशर्ते नेमस्पेस सही ढंग से संदर्भित हो।

**Q: मैं कैसे सुनिश्चित करूँ कि मेटाडेटा सही तरीके से जोड़ा गया है?**  
A: परिणामस्वरूप EPS फ़ाइल को ऐसे व्यूअर में खोलें जो XMP का समर्थन करता हो (जैसे Adobe Bridge) या `XmpMetadata` मेथड्स का उपयोग करके प्रोग्रामेटिक रूप से मेटाडेटा निकालें।

---

**अंतिम अपडेट:** 2025-12-18  
**टेस्ट किया गया संस्करण:** Aspose.Page for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}