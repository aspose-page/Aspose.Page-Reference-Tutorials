---
date: 2026-03-08
description: Aspose.Page for Java के साथ EPS फ़ाइलों में XMP नेमस्पेस कैसे जोड़ें
  सीखें – चरण‑दर‑चरण XMP और XMP नेमस्पेस जोड़ने का ट्यूटोरियल जावा गाइड।
linktitle: Add Namespace in XMP using Java
second_title: Aspose.Page Java API
title: Aspose.Page का उपयोग करके EPS फ़ाइलों में XMP नेमस्पेस कैसे जोड़ें – जावा ट्यूटोरियल
url: /hi/java/xmp-metadata-manipulation/add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page – Java ट्यूटोरियल का उपयोग करके EPS फ़ाइलों में XMP नेमस्पेस कैसे जोड़ें

यदि आपको EPS फ़ाइलों के मेटाडेटा को संशोधित या समृद्ध करने की आवश्यकता है, तो यह **how to add xmp** ट्यूटोरियल आपको जावा और Aspose.Page का उपयोग करके XMP नेमस्पेस जोड़ने का सटीक तरीका दिखाता है। गाइड के अंत तक आपके पास किसी भी EPS दस्तावेज़ में कस्टम मेटाडेटा इंजेक्ट करने के लिए पुन: उपयोग योग्य पैटर्न होगा।

## Quick Answers
- **What is the primary goal?** EPS फ़ाइल में एक कस्टम XMP नेमस्पेस और प्रॉपर्टी जोड़ना।  
- **Which library is required?** Aspose.Page for Java।  
- **Do I need a license for testing?** विकास के लिए एक फ्री ट्रायल काम करता है; प्रोडक्शन के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **How many code changes are needed?** केवल पाँच छोटे कोड स्निपेट—प्रत्येक चरण के लिए एक।  
- **Can I reuse this pattern for other namespaces?** हाँ, `registerNamespaceURI` कॉल में प्रीफ़िक्स और URI बदल दें।

## What is an XMP Namespace?

एक XMP (Extensible Metadata Platform) नेमस्पेस एक अद्वितीय पहचानकर्ता है जो संबंधित मेटाडेटा प्रॉपर्टीज़ को एक सामान्य URI के तहत समूहित करता है। नेमस्पेस को रजिस्टर करने से आप कस्टम डेटा—जैसे प्रोपायटरी टैग—को मौजूदा मानकों के साथ टकराव किए बिना संग्रहीत कर सकते हैं।

## Why Use Aspose.Page for XMP Manipulation?

- **Full control** EPS और PDF मेटाडेटा पर, Adobe टूल्स की आवश्यकता के बिना।  
- **Automatic creation** XMP ब्लॉक्स की जब वे मौजूद नहीं होते, PS कमेंट्स के आधार पर।  
- **Cross‑platform Java support**, जिससे इसे मौजूदा पाइपलाइन में आसानी से इंटीग्रेट किया जा सकता है।

## Prerequisites

- Aspose.Page for Java: सुनिश्चित करें कि आपके पास लाइब्रेरी इंस्टॉल है। आप इसे [here](https://releases.aspose.com/page/java/) से डाउनलोड कर सकते हैं।  
- Java Development Environment: अपने सिस्टम पर जावा वातावरण सेट अप करें।  
- Document File: एक EPS फ़ाइल जिसमें XMP मेटाडेटा हो। यदि इसमें XMP मेटाडेटा नहीं है, तो लाइब्रेरी PS मेटाडेटा कमेंट्स के आधार पर एक बना देगी।

## Import Packages

शुरू करने के लिए, आवश्यक पैकेजों को अपने जावा प्रोजेक्ट में इम्पोर्ट करें:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Step 1: Get XMP Metadata

```java

// The path to the documents directory.
String dataDir = "Your Document Directory";

// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, create a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

### Why this matters
`XmpMetadata` ऑब्जेक्ट को प्राप्त करने से आपको दस्तावेज़ के मेटाडेटा का लाइव हैंडल मिलता है, जिससे आप इसे पढ़, संशोधित या विस्तारित कर सकते हैं, फिर सेव करने से पहले।

## Step 2: Register New Namespace *(how to add xmp namespace)*

```java
// Add new XML namespace "http://www.some.org/schema/tmp#" with prefix "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

### Explanation
`registerNamespaceURI` मेथड एक छोटा प्रीफ़िक्स (`tmp`) को पूर्ण URI से मैप करता है। यह चरण अगली ऑपरेशन के लिए आवश्यक है क्योंकि XMP प्रॉपर्टीज़ को रजिस्टर्ड नेमस्पेस के साथ क्वालिफ़ाई करना पड़ता है।

## Step 3: Add New Property

```java
// Add new property "tmp:newKey" in the new XML namespace
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

### What’s happening?
यहाँ हम `tmp:newKey` नामक एक कस्टम प्रॉपर्टी बनाते हैं और उसे मान `"NewValue"` असाइन करते हैं। आप अपनी बिजनेस लॉजिक के अनुसार की और वैल्यू को बदल सकते हैं।

## Step 4: Save Document

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

### Tip
`save` कॉल को हमेशा `try/finally` ब्लॉक (या try‑with‑resources) में रैप करें ताकि आउटपुट स्ट्रीम बंद हो जाए, चाहे कोई एक्सेप्शन हो या न हो।

## Step 5: Close Streams

```java
// Close input EPS stream
psStream.close();
```

### Best practice
इनपुट स्ट्रीम को बंद करने से फ़ाइल हैंडल तुरंत रिलीज़ हो जाता है, जिससे Windows सिस्टम पर फ़ाइल‑लॉकिंग समस्याओं से बचा जा सकता है।

## Common Issues and Solutions

| Issue | Likely Cause | Fix |
|-------|--------------|-----|
| No XMP block appears after saving | Original EPS lacked XMP and comments were insufficient | Ensure the EPS contains standard PS comments (`%%Creator`, `%%Title`, etc.) or manually create an empty `XmpMetadata` object before registering a namespace. |
| `registerNamespaceURI` throws an exception | Prefix already used | Choose a unique prefix or check existing namespaces via `xmp.getRegisteredNamespaces()`. |
| Saved file is corrupted | Output stream not flushed | Use `try‑with‑resources` or explicitly call `outPsStream.flush()` before closing. |

## Conclusion

इस **how to add xmp** ट्यूटोरियल को फॉलो करके, अब आपके पास Aspose.Page for Java का उपयोग करके EPS फ़ाइलों में कस्टम नेमस्पेस और प्रॉपर्टीज़ जोड़ने की एक दोहराने योग्य विधि है। यह क्षमता अधिक समृद्ध मेटाडेटा रणनीतियों के द्वार खोलती है—चाहे आप वर्कफ़्लो आइडेंटिफ़ायर, प्रोपायटरी टैग, या डाउनस्ट्रीम सिस्टम के लिए इंटीग्रेशन डेटा एम्बेड कर रहे हों।

## FAQs

### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page primarily supports Java, but there are versions available for other languages such as .NET.

### Is there a free trial available?
Yes, you can explore a free trial [here](https://releases.aspose.com/).

### Where can I find comprehensive documentation?
Refer to the documentation [here](https://reference.aspose.com/page/java/).

### How can I obtain a temporary license?
You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Are there community forums for Aspose.Page?
Yes, you can engage with the community on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Page for Java 24.10 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}