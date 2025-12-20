---
date: 2025-12-20
description: Aspose.Page for Java का उपयोग करके EPS फ़ाइलों में XMP मेटाडेटा EPS बनाना
  सीखें। प्रोग्रामेटिक रूप से सरल XMP प्रॉपर्टीज़ जोड़ने के लिए चरण‑दर‑चरण गाइड।
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: जावा के साथ XMP मेटाडेटा EPS कैसे बनाएं
url: /hi/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा का उपयोग करके XMP में सरल गुण जोड़ें

## परिचय
आधुनिक दस्तावेज़ कार्यप्रवाहों में, प्रोग्रामेटिक रूप से **create XMP metadata EPS** फ़ाइलें बनाना आपको यह पूरी नियंत्रण देता है कि आपके ग्राफ़िक्स को कैसे वर्णित, खोजा और संग्रहित किया जाता है। Aspose.Page for Java के साथ आप EPS दस्तावेज़ों के भीतर XMP पैकेट को पढ़, संशोधित और लिख सकते हैं, बिना जावा इकोसिस्टम से बाहर निकले। इस ट्यूटोरियल में हम आपको EPS फ़ाइल में सरल XMP गुण जोड़ने के सटीक चरणों के माध्यम से ले जाएंगे, ताकि आप अपने ग्राफ़िक्स को कस्टम मेटाडेटा के साथ तेज़ी और भरोसेमंद तरीके से समृद्ध कर सकें।

## त्वरित उत्तर
- **“create xmp metadata eps” का क्या अर्थ है?** EPS फ़ाइल में XMP पैकेट (XML‑आधारित मेटाडेटा) जोड़ना।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java (Aspose साइट से डाउनलोड योग्य)।  
- **परीक्षण के लिए लाइसेंस चाहिए?** विकास के लिए मुफ्त ट्रायल काम करता है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है।  
- **कोड की कितनी पंक्तियाँ?** जावा की 30 पंक्तियों से कम, साथ में कुछ इम्पोर्ट स्टेटमेंट्स।  
- **क्या अन्य डेटा प्रकार जोड़ सकते हैं?** हाँ – तिथियाँ, पूर्णांक, डबल, स्ट्रिंग, और यहाँ तक कि एरे भी समर्थित हैं।

## create xmp metadata eps क्या है?
XMP (Extensible Metadata Platform) फ़ाइलों के भीतर समृद्ध मेटाडेटा एम्बेड करने का एक मानक है। जब आप **create XMP metadata EPS** करते हैं, तो आप एक XML पैकेट को EPS (Encapsulated PostScript) दस्तावेज़ में एम्बेड करते हैं, जिससे डाउनस्ट्रीम एप्लिकेशन लेखक, निर्माण तिथि, कस्टम टैग आदि पढ़ सकें।

## EPS फ़ाइलों में XMP मेटाडेटा क्यों जोड़ें?
- **खोजयोग्यता:** DAM सिस्टम द्वारा स्वचालित इंडेक्सिंग सक्षम करता है।  
- **अनुपालन:** कानूनी या लाइसेंस जानकारी को सीधे फ़ाइल में संग्रहीत करता है।  
- **स्वचालन:** डाउनस्ट्रीम पाइपलाइन को एम्बेडेड डेटा के आधार पर निर्णय लेने देता है।  
- **पोर्टेबिलिटी:** मेटाडेटा EPS के साथ यात्रा करता है, जिससे विभिन्न प्लेटफ़ॉर्म पर स्थिरता बनी रहती है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

- जावा प्रोग्रामिंग का बुनियादी ज्ञान।  
- Aspose.Page for Java लाइब्रेरी स्थापित। आप इसे **[यहाँ](https://releases.aspose.com/page/java/)** डाउनलोड कर सकते हैं।  
- मेटाडेटा युक्त एक नमूना EPS फ़ाइल। यदि आपके पास नहीं है, तो प्रदान की गई **`xmp3.eps`** फ़ाइल का उपयोग कर सकते हैं।

## पैकेज इम्पोर्ट करें
पहले, उन क्लासों को इम्पोर्ट करें जिनकी आपको आवश्यकता होगी। इम्पोर्ट्स मूल उदाहरण की तरह ही बिल्कुल वही रहेंगे:

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

## चरण 1: EPS दस्तावेज़ लोड करें और XMP मेटाडेटा प्राप्त करें
हम EPS फ़ाइल खोलते हैं, एक `PsDocument` इंस्टेंस बनाते हैं, और XMP पैकेट को प्राप्त (या बनाते) हैं।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## चरण 2: एक तिथि गुण जोड़ें
तिथि जोड़ना इतना सरल है जितना कि एक `Date` ऑब्जेक्ट बनाना और उसे XMP मैप में डालना।

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## चरण 3: एक पूर्णांक गुण जोड़ें
आप संख्यात्मक पहचानकर्ता या संस्करण संख्या को पूर्णांक मान के रूप में संग्रहीत कर सकते हैं।

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## चरण 4: एक डबल गुण जोड़ें
फ़्लोटिंग‑पॉइंट संख्याएँ माप या रेटिंग के लिए उपयोगी होती हैं।

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## चरण 5: एक स्ट्रिंग गुण जोड़ें
कस्टम टेक्स्ट टैग (जैसे, प्रोजेक्ट कोड) स्ट्रिंग के रूप में संग्रहीत होते हैं।

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## चरण 6: अपडेटेड EPS फ़ाइल सहेजें
सभी गुण जोड़ने के बाद, दस्तावेज़ को डिस्क पर वापस लिखें।

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

## चरण 7: संसाधनों को साफ़ करें
फ़ाइल‑हैंडल लीक से बचने के लिए हमेशा इनपुट स्ट्रीम को बंद करें।

```java
// Close input EPS stream
psStream.close();
```

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|--------|-----|
| **Null XMP metadata** | EPS फ़ाइल में कोई XMP पैकेट नहीं था और लाइब्रेरी PS टिप्पणी नहीं निकाल सकी। | सुनिश्चित करें कि स्रोत EPS में कम से कम एक PS टिप्पणी (जैसे, `%%Creator`) हो। लाइब्रेरी स्वचालित रूप से एक न्यूनतम XMP पैकेट जनरेट करेगी। |
| **Time zone mismatch** | तिथियाँ दूसरे एप्लिकेशन में खुलने पर शिफ्ट दिखती हैं। | `Date` ऑब्जेक्ट बनाने से पहले `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` सेट करें, जैसा कि चरण 2 में दिखाया गया है। |
| **License exception** | रनटाइम `LicenseException` फेंकता है। | API उपयोग करने से पहले वैध Aspose.Page लाइसेंस लागू करें, या मूल्यांकन के लिए ट्रायल मोड में चलाएँ। |

## निष्कर्ष
इन चरणों का पालन करके आप अब जानते हैं कि Aspose.Page for Java का उपयोग करके **create XMP metadata EPS** फ़ाइलें कैसे बनाएं। तिथियों, पूर्णांकों, डबल और स्ट्रिंग जैसे सरल गुण जोड़ना सीधा है, और परिणामी EPS फ़ाइलें समृद्ध, खोजने योग्य मेटाडेटा ले जाती हैं जो किसी भी डाउनस्ट्रीम कार्यप्रवाह को लाभ पहुंचाती हैं।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Page for Java को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?
Aspose.Page मुख्यतः जावा को सपोर्ट करता है, लेकिन .NET जैसी अन्य भाषाओं के लिए भी संस्करण उपलब्ध हैं।

### क्या Aspose.Page for Java के लिए मुफ्त ट्रायल उपलब्ध है?
हाँ, आप **[यहाँ](https://releases.aspose.com/)** एक मुफ्त ट्रायल प्राप्त करके Aspose.Page की सुविधाओं का अन्वेषण कर सकते हैं।

### Aspose.Page for Java की विस्तृत दस्तावेज़ीकरण कहाँ मिल सकती है?
दस्तावेज़ीकरण **[यहाँ](https://reference.aspose.com/page/java/)** उपलब्ध है।

### Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?
एक अस्थायी लाइसेंस **[यहाँ](https://purchase.aspose.com/temporary-license/)** प्राप्त किया जा सकता है।

### Aspose.Page for Java को कहाँ खरीदूँ?
उत्पाद **[यहाँ](https://purchase.aspose.com/buy)** खरीदा जा सकता है।

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}