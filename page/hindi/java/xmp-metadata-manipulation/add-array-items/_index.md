---
date: 2026-03-05
description: Aspose.Page for Java का उपयोग करके EPS फ़ाइलों के XMP मेटाडेटा में dc:title
  एरे आइटम कैसे जोड़ें, सीखें। तेज़ परिणामों के लिए इस चरण‑दर‑चरण गाइड का पालन करें।
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Java का उपयोग करके XMP मेटाडेटा में dc:title एरे आइटम कैसे जोड़ें
url: /hi/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java का उपयोग करके XMP मेटाडेटा में एरे आइटम जोड़ें

## परिचय
इस ट्यूटोरियल में आप सीखेंगे **कैसे dc:title** (और अन्य एरे आइटम) को Aspose.Page for Java के साथ EPS फ़ाइल के भीतर XMP मेटाडेटा में जोड़ें। XMP मेटाडेटा को अपडेट करना उपयोगी है जब आपको खोज योग्य जानकारी—जैसे शीर्षक, निर्माता, या कीवर्ड—सीधे अपने ग्राफ़िक्स फ़ाइलों में एम्बेड करने की आवश्यकता हो। हम प्रत्येक चरण को समझाएंगे, बताएंगे कि प्रत्येक पंक्ति क्यों महत्वपूर्ण है, और दिखाएंगे कि परिवर्तन कैसे सत्यापित करें।

## त्वरित उत्तर
- **“dc:title” क्या दर्शाता है?** यह Dublin Core शीर्षक प्रॉपर्टी है जो XMP एरे के रूप में संग्रहीत होती है।  
- **XMP मेटाडेटा को क्यों संशोधित करें?** यह बेहतर एसेट प्रबंधन, खोज क्षमता, और मानकों के साथ अनुपालन को सक्षम बनाता है।  
- **क्या मुझे मौजूदा XMP ब्लॉक की आवश्यकता है?** नहीं—यदि अनुपलब्ध हो तो Aspose.Page PS टिप्पणियों से एक उत्पन्न करेगा।  
- **कौन सा लाइब्रेरी संस्करण आवश्यक है?** कोई भी नवीनतम Aspose.Page for Java रिलीज़ (2026 के नवीनतम बिल्ड के साथ परीक्षण किया गया)।  
- **क्या मैं अन्य एरे प्रॉपर्टी जोड़ सकता हूँ?** हाँ—`dc:creator` जैसी प्रॉपर्टी के लिए वही `addArrayItem` मेथड उपयोग करें।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:

- Aspose.Page for Java लाइब्रेरी स्थापित हो (JAR को अपने प्रोजेक्ट के क्लासपाथ में जोड़ें)।  
- बुनियादी Java विकास अनुभव (JDK 8+ की सिफारिश)।  
- एक EPS फ़ाइल जिसमें पहले से XMP मेटाडेटा हो या कम से कम PS मेटाडेटा टिप्पणियाँ (जैसे `%%Title`, `%%Creator`) हों।  

## पैकेज आयात करें
शुरू करने के लिए, EPS फ़ाइलों को पढ़ने, संशोधित करने और सहेजने के लिए आवश्यक क्लासेस आयात करें:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## चरण 1: EPS दस्तावेज़ लोड करें और XMP मेटाडेटा प्राप्त करें
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

यहाँ हम EPS फ़ाइल खोलते हैं और Aspose.Page से उसका XMP ब्लॉक मांगते हैं। यदि फ़ाइल में XMP नहीं है, तो लाइब्रेरी मौजूदा PS टिप्पणियों का उपयोग करके स्वचालित रूप से एक बनाती है, जिससे आपके पास हमेशा काम करने के लिए एक मेटाडेटा कंटेनर रहता है।

## चरण 2: नया **dc:title** एरे आइटम जोड़ें  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

यह पंक्ति **कैसे dc:title जोड़ें** को दर्शाती है। `"NewTitle"` को उस वास्तविक शीर्षक से बदलें जिसे आप एम्बेड करना चाहते हैं। यह मेथड मान को मौजूदा शीर्षक एरे में जोड़ता है, जिससे पहले के सभी शीर्षक संरक्षित रहते हैं।

## चरण 3: नया **dc:creator** एरे आइटम जोड़ें  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

इसी प्रकार, आप `dc:creator` प्रॉपर्टी को समृद्ध कर सकते हैं। कई निर्माताओं को संग्रहीत किया जा सकता है; प्रत्येक कॉल एक नया प्रविष्टि जोड़ता है।

## चरण 4: आउटपुट स्ट्रीम तैयार करें  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

हम संशोधित EPS फ़ाइल के लिए एक स्ट्रीम बनाते हैं। अलग फ़ाइलनाम (`xmp3_changed.eps`) का उपयोग करने से मूल फ़ाइल अपरिवर्तित रहती है।

## चरण 5: अपडेटेड XMP मेटाडेटा के साथ दस्तावेज़ सहेजें  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

`save` कॉल EPS डेटा को अपडेटेड XMP ब्लॉक के साथ लिखता है। `finally` ब्लॉक यह सुनिश्चित करता है कि अपवाद होने पर भी फ़ाइल हैंडल रिलीज़ हो जाए।

## यह क्यों महत्वपूर्ण है
सटीक `dc:title` और `dc:creator` मान एम्बेड करने से सुधार होता है:

- **खोज क्षमता** डिजिटल एसेट मैनेजमेंट (DAM) सिस्टम में।  
- **अनुपालन** उन प्रकाशन मानकों के साथ जो मेटाडेटा की आवश्यकता रखते हैं।  
- **सहयोग**, क्योंकि टीम सदस्य EPS खोलें बिना फ़ाइल की सामग्री को जल्दी पहचान सकते हैं।

## सामान्य गलतियाँ और सुझाव
- **गलती:** मौजूदा एरे आइटम अनजाने में ओवरराइट करना।  
  **सुझाव:** नया जोड़ने से पहले वर्तमान मानों को जांचने के लिए `xmp.getArrayItems("dc:title")` उपयोग करें।  
- **गलती:** स्ट्रीम बंद करना भूल जाना, जिससे फ़ाइल लॉक हो जाती है।  
  **सुझाव:** हमेशा I/O को try‑with‑resources या दिखाए गए अनुसार `finally` ब्लॉक में रैप करें।  
- **सुझाव:** आप कई `addArrayItem` कॉल्स को चेन करके एक ही पास में कई शीर्षक या निर्माताओं को जोड़ सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं Aspose.Page for Java को अन्य दस्तावेज़ फ़ॉर्मेट्स के साथ उपयोग कर सकता हूँ?
हाँ, Aspose.Page विभिन्न दस्तावेज़ फ़ॉर्मेट्स को सपोर्ट करता है, जिसमें EPS, PDF, और XPS शामिल हैं।

### क्या Aspose.Page for Java के लिए मुफ्त ट्रायल उपलब्ध है?
हाँ, आप मुफ्त ट्रायल यहाँ प्राप्त कर सकते हैं [here](https://releases.aspose.com/)।

### मैं Aspose.Page for Java की दस्तावेज़ीकरण कहाँ पा सकता हूँ?
दस्तावेज़ीकरण यहाँ उपलब्ध है [here](https://reference.aspose.com/page/java/)।

### मैं Aspose.Page for Java कैसे खरीद सकता हूँ?
आप उत्पाद यहाँ खरीद सकते हैं [here](https://purchase.aspose.com/buy)।

### क्या Aspose.Page for Java के लिए अस्थायी लाइसेंस उपलब्ध हैं?
हाँ, आप अस्थायी लाइसेंस यहाँ प्राप्त कर सकते हैं [here](https://purchase.aspose.com/temporary-license/)।

---

**अंतिम अपडेट:** 2026-03-05  
**परीक्षण किया गया:** Aspose.Page for Java (latest 2026 release)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}