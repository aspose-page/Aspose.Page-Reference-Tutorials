---
date: 2025-12-21
description: जावा का उपयोग करके EPS दस्तावेज़ों में XMP को Aspose.Page के साथ कैसे
  संशोधित करें, सीखें। Aspose.Page for Java के साथ मेटाडेटा को जल्दी से सुधारें।
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page XMP संशोधित करें – Java का उपयोग करके XMP में मान बदलें
url: /hi/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP मानों को Java का उपयोग करके बदलें

## परिचय
यदि आपको **aspose.page modify xmp** डेटा को EPS फ़ाइल के भीतर संशोधित करने की आवश्यकता है, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम Aspose.Page लाइब्रेरी फॉर Java का उपयोग करके XMP (Extensible Metadata Platform) मानों को पढ़ने, अपडेट करने और सहेजने के सटीक चरणों से गुजरेंगे। अंत तक, आप दस्तावेज़ मेटाडेटा—जैसे निर्माता, शीर्षक, और संशोधित तिथि—को अपने प्रोजेक्ट की आवश्यकताओं के अनुसार अनुकूलित कर पाएँगे।

## त्वरित उत्तर
- **“aspose.page modify xmp” क्या करता है?** यह आपको Aspose.Page Java API के माध्यम से EPS फ़ाइलों में XMP मेटाडेटा को पढ़ने और लिखने की अनुमति देता है।  
- **कौन सा लाइब्रेरी संस्करण आवश्यक है?** कोई भी नवीनतम Aspose.Page for Java रिलीज़ (API संस्करणों में स्थिर है)।  
- **क्या नमूना चलाने के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या मैं एक साथ कई XMP फ़ील्ड बदल सकता हूँ?** हाँ—दस्तावेज़ सहेजने से पहले प्रत्येक फ़ील्ड के लिए `put` कॉल करें।  
- **क्या टाइमज़ोन हैंडलिंग की आवश्यकता है?** डिफ़ॉल्ट टाइमज़ोन (जैसे UTC) सेट करने से तिथि मान सुसंगत रहते हैं।

## XMP क्या है और इसे क्यों बदलें?
XMP (Extensible Metadata Platform) फ़ाइलों जैसे EPS, PDF, और इमेजेज़ के भीतर सीधे समृद्ध मेटाडेटा एम्बेड करने का एक मानकीकृत तरीका है। XMP को अपडेट करने से आप नियंत्रित कर सकते हैं कि दस्तावेज़ कैसे अनुक्रमित, प्रदर्शित और खोजे जाते हैं—जो ब्रांडिंग, अनुपालन, और वर्कफ़्लो ऑटोमेशन के लिए महत्वपूर्ण है।

## Java के लिए Aspose.Page क्यों उपयोग करें?
- **पूर्ण‑विशेषताओं वाला API** – बाहरी टूल की आवश्यकता नहीं; सब कुछ इन‑प्रोसेस संभाला जाता है।  
- **क्रॉस‑प्लेटफ़ॉर्म** – किसी भी OS पर काम करता है जो Java को सपोर्ट करता है।  
- **कोई नेटिव डिपेंडेंसी नहीं** – शुद्ध Java इम्प्लीमेंटेशन डिप्लॉयमेंट को सरल बनाता है।  
- **मज़बूत समर्थन** – मौजूदा XMP ब्लॉक्स को संभालता है और अनुपलब्ध होने पर PS टिप्पणियों से नया बनाता है।

## पूर्वापेक्षाएँ
इस ट्यूटोरियल को शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1. **Java विकास वातावरण** – JDK (8 या बाद का) और आपका पसंदीदा IDE या बिल्ड टूल।  
2. **Aspose.Page for Java लाइब्रेरी** – Aspose.Page for Java लाइब्रेरी डाउनलोड और इंस्टॉल करें। आवश्यक पैकेज आप [यहाँ](https://releases.aspose.com/page/java/) पा सकते हैं।

## पैकेज आयात करें
अपने Java प्रोजेक्ट में आवश्यक पैकेज आयात करके शुरू करें। ये पैकेज EPS दस्तावेज़ों के साथ इंटरैक्ट करने और उन्हें संशोधित करने के लिए आवश्यक हैं।

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

## चरण 1: XMP मेटाडेटा प्राप्त करें
EPS दस्तावेज़ से XMP मेटाडेटा प्राप्त करें। यदि EPS फ़ाइल में XMP मेटाडेटा नहीं है, तो PS मेटाडेटा टिप्पणियों जैसे %%Creator, %%CreateDate, और %%Title से मान लेकर नया बनाया जाएगा।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## चरण 2: "ModifyDate" मान बदलें
XMP मेटाडेटा में "ModifyDate" मान को इच्छित तिथि के अनुसार संशोधित करें।

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## चरण 3: "Creator" मान बदलें
XMP मेटाडेटा में "Creator" मान को दस्तावेज़ के निर्माता को निर्दिष्ट करने के लिए अपडेट करें।

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## चरण 4: "Title" मान बदलें
XMP मेटाडेटा में "Title" मान को दस्तावेज़ के उपयुक्त शीर्षक के रूप में सेट करने के लिए संशोधित करें।

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## चरण 5: बदलें हुए XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
अपडेट किए गए XMP मेटाडेटा के साथ दस्तावेज़ को नई EPS फ़ाइल में सहेजें।

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## सामान्य समस्याएँ और समाधान
- **XMP ब्लॉक अनुपलब्ध** – API स्वचालित रूप से PS टिप्पणियों से एक बनाता है, लेकिन आप आवश्यकता पड़ने पर `XmpMetadata` को मैन्युअल रूप से भी इंस्टैंशिएट कर सकते हैं।  
- **टाइमज़ोन असंगतता** – `Date` ऑब्जेक्ट बनाने से पहले हमेशा `TimeZone.setDefault` सेट करें ताकि अप्रत्याशित ऑफ़सेट न हों।  
- **फ़ाइल एक्सेस त्रुटियाँ** – इनपुट और आउटपुट पाथ सही हों और आपके एप्लिकेशन के पास पढ़ने/लिखने की अनुमति हो, यह सुनिश्चित करें।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: XMP मानों को संशोधित करते समय टाइमज़ोन को कैसे संभालें?**  
उत्तर: `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` का उपयोग करके टाइमज़ोन सेटिंग्स में स्थिरता बनाए रखें।

**प्रश्न: क्या मैं एक ही ऑपरेशन में कई XMP मान बदल सकता हूँ?**  
उत्तर: हाँ, प्रत्येक इच्छित मान के लिए `put` मेथड का उपयोग करके आप एक साथ कई XMP मान संशोधित कर सकते हैं।

**प्रश्न: Aspose.Page for Java के लिए अतिरिक्त दस्तावेज़ कहाँ मिलेंगे?**  
उत्तर: व्यापक दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/page/java/) देखें।

**प्रश्न: क्या Aspose.Page for Java के लिए एक मुफ्त ट्रायल उपलब्ध है?**  
उत्तर: हाँ, आप मुफ्त ट्रायल [यहाँ](https://releases.aspose.com/) प्राप्त कर सकते हैं।

**प्रश्न: Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करें?**  
उत्तर: अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) प्राप्त करें।

**प्रश्न: क्या XMP संशोधन EPS की दृश्य सामग्री को प्रभावित करता है?**  
उत्तर: नहीं। XMP परिवर्तन केवल मेटाडेटा‑स्तर के होते हैं और EPS फ़ाइल के ग्राफ़िक तत्वों को नहीं बदलते।

**प्रश्न: क्या मैं प्रोग्रामेटिक रूप से अपडेट किए गए मानों को पढ़कर परिवर्तन की पुष्टि कर सकता हूँ?**  
उत्तर: बिल्कुल—सहेजने और दस्तावेज़ बंद करने से पहले `xmp.get("dc:creator")` (या संबंधित कुंजी) को कॉल करें।

## निष्कर्ष
बधाई हो! आपने Aspose.Page for Java का उपयोग करके EPS दस्तावेज़ों में **aspose.page modify xmp** मानों को सफलतापूर्वक बदलने की प्रक्रिया पूरी कर ली है। इस ट्यूटोरियल ने आपको मेटाडेटा संशोधित करने की क्षमता प्रदान की है, जिससे आपके दस्तावेज़ आपके विशिष्ट आवश्यकताओं के अनुसार सहजता से संरेखित हो सकें।

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**अंतिम अपडेट:** 2025-12-21  
**परीक्षित संस्करण:** Aspose.Page for Java (नवीनतम रिलीज़)  
**लेखक:** Aspose  

---