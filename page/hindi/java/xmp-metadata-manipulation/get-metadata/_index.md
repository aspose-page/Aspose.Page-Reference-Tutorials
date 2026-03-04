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

हमारे स्टेप-बाय-स्टेप ट्यूटोरियल में आपका स्वागत है जो दिखाता है कि **XMP को Java और Aspose.Page लाइब्रेरी के साथ मेटाडेटा कैसे पढ़ें**। XMP (एक्सटेंसिबल मेटाडेटा प्लेटफ़ॉर्म) डॉक्यूमेंट्स के अंदर रिच मेटाडेटा एम्बेड करने के लिए एक बहुत ज़्यादा अपनाया जाने वाला स्टैंडर्ड है। इस गाइड के आखिर तक आप डॉक्यूमेंट फ़ॉर्मेट XMP पढ़ पाएँगे, क्रिएटर की जानकारी, टाइमस्टैम्प, थंबनेल और भी बहुत कुछ निकाल पाएँगे—जिससे आप बेहतर डॉक्यूमेंट-एनालिसिस सॉल्यूशन बना पाएँगे।

##तुरंत जवाब
- **“how to read xmp” का क्या मतलब है?** यह मौजूदा से प्रोग्रामेटिक रूप से XMP मेटाडेटा निकालने को फिट है।
- **कौन सी लाइब्रेरी ज़रूरी है?** Aspose.Page for Java (उपलब्ध Aspose डाउनलोड पेज से)।
- **क्या मुझे लाइसेंस चाहिए?** प्रोडक्शन इस्तेमाल के लिए एक टेम्पररी या फुल लाइसेंस ज़रूरी है; एक फ्री ट्रायल अवेलेबल है।
- **कौन सा Java वर्जन सपोर्टेड है?** Java8 या उससे ऊपर।
- **क्या मैं XMP को दूसरे फ़ॉर्मेट से पढ़ सकता हूँ?** हाँ, Aspose.Page EPS, PDF और कई इमेज फ़ाइलों को हैंडल कर सकता है जो XMP एम्बेड करते हैं।

## पूर्वापेक्षाएँ
कोड में जाने से पहले, पक्का करें कि आपके पास ये हैं:

- **Java Development Kit (JDK)** – आपकी मशीन पर Java8+ इंस्टॉल और स्विच किया हुआ।
- **Aspose.Page for Java** – ऑफिशियल साइट से लाइब्रेरी डाउनलोड करें[here](https://releases.aspose.com/page/java/).
- एक EPS फ़ाइल जिसमें XMP मेटाडेटा हो (जैसे, `xmp1.eps`)।

## पैकेज इम्पोर्ट करें
अपने Java प्रोजेक्ट में, ज़रूरी पैकेज इम्पोर्ट करें:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## चरण 1: इनपुट EPS फ़ाइल स्ट्रीम को इनिशियलाइज़ करें
अपनी डॉक्यूमेंट डायरेक्टरी का पाथ सेट करके और इनपुट EPS फ़ाइल स्ट्रीम को इनिशियलाइज़ करके शुरू करें।
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## चरण 2: XMP मेटाडेटा प्राप्त करें
EPS फ़ाइल से XMP मेटाडेटा निकालें। अगर फ़ाइल में XMP मेटाडेटा नहीं है, तो PS मेटाडेटा कमेंट्स से वैल्यू के साथ एक नई फ़ाइल जेनरेट होगी।
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## चरण 3: CreatorTool जानकारी निकालें
XMP मेटाडेटा से "CreatorTool" वैल्यू चेक करें और प्रिंट करें।
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## चरण 4: CreateDate जानकारी निकालें
XMP मेटाडेटा से "CreateDate" वैल्यू चेक करें और प्रिंट करें।
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## चरण 5: थंबनेल की चौड़ाई प्राप्त करें
अगर थंबनेल मौजूद हैं, तो पहले थंबनेल की चौड़ाई निकालें और प्रिंट करें।
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## चरण 6: Format जानकारी निकालें
XMP मेटाडेटा से "format" वैल्यू चेक करें और प्रिंट करें।
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## चरण 7: DocumentID प्राप्त करें
XMP मेटाडेटा से "DocumentID" वैल्यू चेक करें और प्रिंट करें।
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## यह क्यों महत्वपूर्ण है
XMP मेटाडेटा पढ़ने से आप किसी डॉक्यूमेंट को व्यूअर में खोले बिना प्रोग्राम के ज़रिए उसकी शुरुआत, बनाने की तारीख और दूसरे ज़रूरी एट्रिब्यूट का पता लगा सकते हैं। यह खास तौर पर बैच प्रोसेसिंग, कंटेंट मैनेजमेंट सिस्टम और डिजिटल एसेट पाइपलाइन के लिए उपयोगी है, जहाँ मेटाडेटा इंडेक्सिंग और सर्च को चलाता है।

## आम मुश्किलें और टिप्स
- **XMP नहीं है:** कुछ EPS फ़ाइलों में XMP नहीं हो सकता है। `getXmpMetadata()` कॉल मौजूदा PS कमेंट्स के आधार पर एक मिनिमम सेट बनाएगा, लेकिन जब तक यह एम्बेडेड नहीं होगा, आपको पूरा मेटाडेटा नहीं मिलेगा।

- **थंबनेल एरे:** `xmp:Thumbnails` की में कई एंट्री हो सकती हैं। उदाहरण सिर्फ़ पहली वाली को निकालता है; अगर आपको सभी थंबनेल चाहिए तो एरे को इटरेट करें।

- **नेमस्पेस अवेयरनेस:** XMP कीज़ नेमस्पेस (जैसे, `xmp:`, `dc:`) का इस्तेमाल करती हैं। पक्का करें कि आप सही की नाम का रेफरेंस दें; नहीं तो `containsKey` गलत रिटर्न करेगा।

## अक्सर पूछे जाने वाले सवाल
### क्या मैं Aspose.Page for Java को दूसरी प्रोग्रामिंग भाषाओं के साथ इस्तेमाल कर सकता हूँ?
हाँ, Aspose.Page कई भाषाओं को सपोर्ट करता है, जिसमें Java, .NET, और भी बहुत कुछ शामिल है। ज़्यादा जानकारी के लिए [डॉक्यूमेंटेशन](https://reference.aspose.com/page/java/) देखें।

### क्या Aspose.Page for Java के लिए फ्री ट्रायल उपलब्ध है?
हाँ, आप फ्री ट्रायल [यहाँ](https://releases.aspose.com/) एक्सेस कर सकते हैं।

### मैं Aspose.Page for Java के लिए सपोर्ट कहाँ पा सकता हूँ?
कम्युनिटी सपोर्ट के लिए [Aspose.Page फोरम](https://forum.aspose.com/c/page/39) पर जाएँ।

### मैं Aspose.Page for Java के लिए टेम्पररी लाइसेंस कैसे पाऊँ?
आप टेम्पररी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) पा सकते हैं।

### क्या Aspose.Page for Java के लिए एक्स्ट्रा रिसोर्स हैं?
पूरा [डॉक्यूमेंटेशन](https://reference.aspose.com/page/java/) देखें और लाइब्रेरी [यहां](https://releases.aspose.com/page/java/) डाउनलोड करें।

## एक्स्ट्रा FAQ
**Q: क्या यह तरीका PDF फाइलों पर काम करता है जिनमें XMP हो?**
A: हां, Aspose.Page, PDF, EPS और कई इमेज फॉर्मेट से XMP पढ़ सकता है।

**Q: क्या मैं XMP मेटाडेटा को पढ़ने के बाद ऑथराइज़ कर सकता हूँ?**
A: बिल्कुल। `XmpMetadata` ऑब्जेक्ट म्यूटेबल है; आप कीज़ जोड़, अपडेट या हटा सकते हैं और फिर डॉक्यूमेंट को सेव कर सकते हैं।

**Q: क्या केवल मैप के बजाय सभी थंबनेल इमेज को निकालने का कोई तरीका है?**
A: आप हर थंबनेल एंट्री की `xmpGImg:data` प्रॉपर्टी से बाइनरी डेटा निकाल सकते हैं और उसे एक फाइल में लिख सकते हैं।

## निष्कर्ष
अब आप Java और Aspose.Page का इस्तेमाल करके **XMP मेटाडेटा पढ़ना** सीख गए हैं। इन स्टेप्स को फ़ॉलो करके आप क्रिएटर टूल्स, टाइमस्टैम्प्स, थंबनेल, फ़ॉर्मेट जानकारी और डॉक्यूमेंट IDs निकाल सकते हैं—जिससे आपको अपनी EPS फ़ाइलों के एम्बेडेड मेटाडेटा की पूरी जानकारी मिल जाएगी। अपने एप्लिकेशन्स के लिए और भी बेहतर डेटा निकालने के लिए एक्स्ट्रा XMP नेमस्पेस के साथ एक्सपेरिमेंट करने में संकोच न करें।

---

**अंतिम अपडेट:** 2025-12-21  
**परीक्षण किया गया:** Aspose.Page for Java 24.12 (latest)  
**लेखक:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
