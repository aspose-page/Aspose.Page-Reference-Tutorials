---
date: 2025-12-20
description: जानेँ कि Aspose.Page for Java (aspose.page xmp java) का उपयोग करके XMP
  में एरे आइटम्स को कैसे बदलें। हमारे चरण‑दर‑चरण गाइड के साथ मेटाडाटा को आसानी से
  संशोधित करें और आज ही अपने EPS दस्तावेज़ों को बेहतर बनाएँ।
linktitle: Change Array Items in XMP using Java
second_title: Aspose.Page Java API
title: 'aspose.page xmp java: जावा का उपयोग करके XMP में एरे आइटम बदलें'
url: /hi/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp java: XMP में एरे आइटम बदलें Java का उपयोग करके

## परिचय
Aspose.Page for Java का उपयोग करके XMP में एरे आइटम बदलने पर हमारे व्यापक गाइड में आपका स्वागत है। **aspose.page xmp java** लाइब्रेरी आपको EPS फ़ाइलों के भीतर XMP मेटाडेटा पर पूर्ण नियंत्रण देती है, जिससे शीर्षक, निर्माता और अन्य गुणों को अनुकूलित करना आसान हो जाता है। इस ट्यूटोरियल में, हम आपको एरे आइटम संशोधित करने के लिए आवश्यक प्रत्येक चरण के माध्यम से ले जाएंगे, ताकि आप अपने EPS दस्तावेज़ों को आत्मविश्वास के साथ सुधार और व्यक्तिगत बना सकें।

## त्वरित उत्तर
- **aspose.page xmp java क्या करता है?** यह Java से EPS फ़ाइलों में XMP मेटाडेटा को पढ़ने और लिखने में सक्षम बनाता है।  
- **क्या इसे आज़माने के लिए लाइसेंस चाहिए?** हाँ, एक मुफ्त ट्रायल उपलब्ध है, लेकिन उत्पादन उपयोग के लिए लाइसेंस आवश्यक है।  
- **कौन सा JDK संस्करण समर्थित है?** Java 8 या बाद का।  
- **क्या मैं अन्य मेटाडेटा फ़ील्ड संशोधित कर सकता हूँ?** बिल्कुल – कोई भी XMP प्रॉपर्टी पढ़ी या अपडेट की जा सकती है।  
- **क्या API थ्रेड‑सेफ़ है?** अधिकांश पढ़ने/लिखने के ऑपरेशन अलग-अलग दस्तावेज़ इंस्टेंस पर उपयोग करने पर सुरक्षित होते हैं।

## aspose.page xmp java क्या है?
`aspose.page xmp java` Aspose.Page for Java सूट का एक भाग है जो XMP (Extensible Metadata Platform) हैंडलिंग पर केंद्रित है। यह लो‑लेवल XMP संरचना को सरल Java ऑब्जेक्ट्स में सारांशित करता है, जिससे आप एरे, बैग और संरचित प्रॉपर्टीज़ के साथ काम कर सकते हैं बिना कच्चे XML से निपटे।

## EPS मेटाडेटा के लिए aspose.page xmp java क्यों उपयोग करें?
- **सटीकता:** विशिष्ट XMP एरे आइटम (जैसे, title, creator) को सीधे लक्षित करें।  
- **ऑटोमेशन:** मेटाडेटा अपडेट को बिल्ड पाइपलाइन या बैच प्रोसेस में एकीकृत करें।  
- **अनुकूलता:** किसी भी EPS फ़ाइल के साथ काम करता है जो XMP मानक का पालन करती है।  

## पूर्वापेक्षाएँ
कोड में जाने से पहले, सुनिश्चित करें कि आपके पास:

- आपके सिस्टम पर Java Development Kit (JDK) स्थापित हो।  
- Aspose.Page लाइब्रेरी for Java। आप इसे [here](https://releases.aspose.com/page/java/) से डाउनलोड कर सकते हैं।

## पैकेज आयात करें
शुरू करने के लिए, आवश्यक क्लासेस को अपने Java प्रोजेक्ट में आयात करें। सुनिश्चित करें कि Aspose.Page JAR आपके प्रोजेक्ट की classpath में जोड़ा गया है।

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## aspose.page xmp java के साथ एरे आइटम कैसे बदलें

### चरण 1: XMP मेटाडेटा प्राप्त करें
सबसे पहले, अपने EPS फ़ाइल से XMP मेटाडेटा प्राप्त करें। यदि फ़ाइल में XMP डेटा नहीं है, तो Aspose.Page मौजूदा PS टिप्पणियों (जैसे, %%Creator, %%Title) से भरकर एक नया XMP ब्लॉक बनाता है।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```

### चरण 2: "dc:title" एरे आइटम सेट करें
अब, **dc:title** एरे के पहले तत्व को नई शीर्षक स्ट्रिंग से बदलें।

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### चरण 3: "dc:creator" एरे आइटम सेट करें
इसी प्रकार, **dc:creator** एरे के पहले तत्व को अपडेट करें।

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### चरण 4: आउटपुट EPS फ़ाइल स्ट्रीम प्रारंभ करें
संशोधित मेटाडेटा को सहेजने के लिए आउटपुट EPS फ़ाइल के लिए एक स्ट्रीम तैयार करें।

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

### चरण 5: बदले हुए XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
अंत में, दस्तावेज़ को सहेजकर बदलावों को स्थायी बनाएं।

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## सामान्य कठिनाइयाँ और सुझाव
- **इंडेक्स आउट ऑफ बाउंड्स:** सुनिश्चित करें कि आप जो इंडेक्स प्रदान करते हैं वह मौजूद है; अन्यथा, Aspose एक अपवाद फेंकेगा।  
- **स्ट्रीम प्रबंधन:** फ़ाइल लॉक से बचने के लिए हमेशा स्ट्रीम को `finally` ब्लॉक में बंद करें।  
- **लाइसेंस सक्रियण:** वैध लाइसेंस सेट करना भूलने से ट्रायल मोड में वॉटरमार्क्ड आउटपुट हो सकता है।

## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक **aspose.page xmp java** का उपयोग करके XMP में एरे आइटम बदलना सीख लिया है। यह चरण‑दर‑चरण गाइड आपको प्रोग्रामेटिक रूप से EPS मेटाडेटा संशोधित करने में सक्षम बनाता है, जिससे स्वचालित दस्तावेज़ वर्कफ़्लो और समृद्ध कंटेंट प्रबंधन का द्वार खुलता है।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Page for Java को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?
Aspose.Page मुख्यतः Java के लिए डिज़ाइन किया गया है, लेकिन Aspose अन्य भाषाओं के लिए समान लाइब्रेरी प्रदान करता है।  
### Aspose.Page for Java की विस्तृत दस्तावेज़ीकरण कहाँ मिल सकती है?
दस्तावेज़ीकरण [here](https://reference.aspose.com/page/java/) पर उपलब्ध है।  
### क्या Aspose.Page for Java के लिए मुफ्त ट्रायल उपलब्ध है?
हाँ, आप मुफ्त ट्रायल [here](https://releases.aspose.com/) से प्राप्त कर सकते हैं।  
### मैं Aspose.Page for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?
आप अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।  
### मैं Aspose.Page for Java का पूर्ण संस्करण कहाँ खरीद सकता हूँ?
आप पूर्ण संस्करण [here](https://purchase.aspose.com/buy) से खरीद सकते हैं।

## अतिरिक्त अक्सर पूछे जाने वाले प्रश्न
**प्र: क्या मैं एक कॉल में कई एरे आइटम अपडेट कर सकता हूँ?**  
**उ:** आपको प्रत्येक इंडेक्स के लिए `setArrayItem` कॉल करना होगा जिसे आप संशोधित करना चाहते हैं; कोई बैच अपडेट मेथड नहीं है।  

**प्र: क्या aspose.page xmp java कस्टम नेमस्पेस का समर्थन करता है?**  
**उ:** हाँ, आप किसी भी पंजीकृत XMP नेमस्पेस को उसका पूरा प्रीफ़िक्स देकर उपयोग कर सकते हैं (जैसे, `myNS:customProp`)।  

**प्र: मैं कैसे सत्यापित करूँ कि मेटाडेटा सही ढंग से अपडेट हुआ है?**  
**उ:** EPS फ़ाइल को `PsDocument` से पुनः लोड करें और `getXmpMetadata()` कॉल करके मान पढ़ें, या XMP व्यूअर में फ़ाइल की जांच करें।  

**प्र: क्या एरे आइटम को पूरी तरह हटाना संभव है?**  
**उ:** एक विशिष्ट एरे एंट्री को हटाने के लिए `removeArrayItem(namespace, index)` का उपयोग करें।  

**प्र: क्या बदलाव EPS की दृश्य उपस्थिति को प्रभावित करेंगे?**  
**उ:** नहीं। XMP मेटाडेटा गैर‑दृश्य है; यह EPS फ़ाइल की ग्राफिक सामग्री को नहीं बदलता।  

---

**अंतिम अपडेट:** 2025-12-20  
**परीक्षण किया गया:** Aspose.Page for Java 24.11 (लेखन के समय नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}