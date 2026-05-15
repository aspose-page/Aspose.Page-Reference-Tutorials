---
date: 2026-05-15
description: Java के लिए aspose.page xmp ट्यूटोरियल का अन्वेषण करें—जानें कि XMP मेटाडेटा
  में एरे आइटम कैसे बदलें, EPS शीर्षक, निर्माताओं आदि को केवल कुछ कोड लाइनों में अपडेट
  करें।
keywords:
- aspose.page xmp tutorial
- change array items java
- xmp metadata java
linktitle: Java का उपयोग करके XMP में एरे आइटम बदलें
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  headline: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  type: TechArticle
- description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  name: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  steps:
  - name: Get XMP Metadata
    text: Call `document.getXmpMetadata()` to retrieve the XMP metadata object associated
      with the EPS file.
  - name: Set "dc:title" Array Item
    text: Use `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` to replace the
      first title entry.
  - name: Set "dc:creator" Array Item
    text: Similarly, `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` updates
      the first creator entry.
  - name: Initialize Output EPS File Stream
    text: Create a `FileOutputStream` pointing to the destination EPS file to write
      the updated document.
  - name: Save Document with Changed XMP Metadata
    text: The `PsDocument` class represents an EPS document and provides the `save`
      method to write changes to a stream.
  type: HowTo
- questions:
  - answer: No. You must invoke `setArrayItem` for each index you wish to modify;
      the API does not provide a bulk‑update method.
    question: Can I update multiple array items in one call?
  - answer: Yes. Provide the full prefix (e.g., `myNS:customProp`) when calling `setArrayItem`
      or `removeArrayItem`.
    question: Does aspose.page xmp java support custom namespaces?
  - answer: Reload the EPS with `PsDocument`, call `getXmpMetadata()`, and inspect
      the returned values, or open the file in an XMP viewer.
    question: How do I verify that the metadata was updated correctly?
  - answer: Use `removeArrayItem(namespace, index)` to delete a specific entry from
      an XMP array.
    question: Is it possible to remove an array item entirely?
  - answer: No. XMP metadata is stored separately from the graphic content and does
      not alter how the EPS renders.
    question: Will the changes affect the visual appearance of the EPS?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'aspose.page xmp ट्यूटोरियल: Java का उपयोग करके XMP में एरे आइटम बदलें'
url: /hi/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp ट्यूटोरियल: XMP में एरे आइटम्स को Java का उपयोग करके बदलें

## परिचय
हमारे व्यापक **aspose.page xmp ट्यूटोरियल** में आपका स्वागत है। इस गाइड में हम आपको चरण‑दर‑चरण दिखाएंगे कि कैसे Aspose.Page for Java का उपयोग करके EPS फ़ाइलों में XMP मेटाडेटा के एरे आइटम्स को बदलें। चाहे आपको दस्तावेज़ शीर्षक, लेखक सूची, या कोई अन्य XMP एरे अपडेट करना हो, प्रक्रिया सरल, पूरी तरह प्रोग्रामेटिक है, और Java 8 + के साथ काम करती है।

## त्वरित उत्तर
- **aspose.page xmp java क्या करता है?** यह EPS फ़ाइलों में XMP मेटाडेटा को सीधे Java से पढ़ता और लिखता है।  
- **क्या इसे आज़माने के लिए लाइसेंस चाहिए?** हाँ—एक मुफ्त 30‑दिन का ट्रायल उपलब्ध है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन सा JDK संस्करण समर्थित है?** Java 8 या बाद का (Java 11, 17, और 21 सहित)।  
- **क्या मैं अन्य मेटाडेटा फ़ील्ड्स को संशोधित कर सकता हूँ?** बिल्कुल—कोई भी XMP प्रॉपर्टी, जिसमें कस्टम नेमस्पेस भी शामिल हैं, पढ़ी या अपडेट की जा सकती है।  
- **क्या API थ्रेड‑सेफ़ है?** अधिकांश पढ़ने/लिखने के ऑपरेशन सुरक्षित हैं जब प्रत्येक थ्रेड अपने स्वयं के `PsDocument` इंस्टेंस के साथ काम करता है।

## aspose.page xmp java क्या है?
`aspose.page xmp java` Aspose.Page for Java का वह घटक है जो Extensible Metadata Platform (XMP) को आसान‑से‑उपयोगी Java ऑब्जेक्ट्स में बदलता है। यह आपको एरे, बैग, और संरचित प्रॉपर्टीज़ को बिना कच्चे XML को संभाले संशोधित करने देता है। व्यवहार में, आप `setArrayItem` और `removeArrayItem` जैसे उच्च‑स्तरीय मेथड्स का उपयोग करके मेटाडेटा को तुरंत संपादित करते हैं।

## EPS मेटाडेटा के लिए aspose.page xmp java क्यों उपयोग करें?
जब आपको बड़े पैमाने पर EPS मेटाडेटा पर सटीक, स्वचालित नियंत्रण चाहिए, तो आपको यह लाइब्रेरी उपयोग करनी चाहिए। Aspose.Page **30+ XMP स्कीमा फ़ील्ड्स** का समर्थन करता है और **500 MB** तक की फ़ाइलों को पूरे दस्तावेज़ को मेमोरी में लोड किए बिना प्रोसेस कर सकता है, जिससे आपको गति और कम मेमोरी उपयोग मिलता है। API यह भी सुनिश्चित करता है कि परिवर्तन मूल ग्राफ़िक्स को संरक्षित रखें, इसलिए दृश्य रेंडरिंग अपरिवर्तित रहती है।

## पूर्वापेक्षाएँ
- Java Development Kit (JDK) 8 या नया स्थापित होना चाहिए।  
- Aspose.Page for Java लाइब्रेरी। नवीनतम JAR [here](https://releases.aspose.com/page/java/) से डाउनलोड करें।  
- एक वैध Aspose लाइसेंस फ़ाइल (या ट्रायल लाइसेंस) को क्लासपाथ पर रखें।

## aspose.page xmp java के साथ एरे आइटम्स कैसे बदलें
यह अनुभाग पूर्ण कार्यप्रवाह को दर्शाता है: EPS फ़ाइल खोलें, उसकी XMP मेटाडेटा ऑब्जेक्ट प्राप्त करें, विशिष्ट एरे प्रविष्टियों को संशोधित करें, और अंत में अपडेटेड दस्तावेज़ को डिस्क पर लिखें। प्रत्येक चरण संक्षिप्त Java कोड के साथ दिखाया गया है, जिससे इसे आपके अपने एप्लिकेशन में एकीकृत करना आसान हो जाता है।

### चरण 1: XMP मेटाडेटा प्राप्त करें
`document.getXmpMetadata()` को कॉल करके EPS फ़ाइल से जुड़ा XMP मेटाडेटा ऑब्जेक्ट प्राप्त करें।

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

### चरण 2: "dc:title" एरे आइटम सेट करें
पहले शीर्षक प्रविष्टि को बदलने के लिए `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` का उपयोग करें।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```

### चरण 3: "dc:creator" एरे आइटम सेट करें
इसी प्रकार, `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` पहले निर्माता प्रविष्टि को अपडेट करता है।

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### चरण 4: आउटपुट EPS फ़ाइल स्ट्रीम को इनिशियलाइज़ करें
अपडेटेड दस्तावेज़ को लिखने के लिए गंतव्य EPS फ़ाइल की ओर इशारा करने वाला `FileOutputStream` बनाएं।

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### चरण 5: बदले हुए XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
`PsDocument` क्लास एक EPS दस्तावेज़ का प्रतिनिधित्व करता है और परिवर्तन को स्ट्रीम में लिखने के लिए `save` मेथड प्रदान करता है।

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

## सामान्य कठिनाइयाँ और सुझाव
- **Index Out of Bounds:** लक्ष्य इंडेक्स मौजूद है या नहीं, इसकी जाँच करें; नहीं तो Aspose `ArrayIndexOutOfBoundsException` फेंकेगा।  
- **Stream Management:** हमेशा स्ट्रीम को `finally` ब्लॉक में बंद करें या फ़ाइल लॉक से बचने के लिए try‑with‑resources का उपयोग करें।  
- **License Activation:** वैध लाइसेंस लागू करना न भूलें, अन्यथा ट्रायल मोड में EPS पर वॉटरमार्क लगेगा।  
- **Large Files:** 200 MB से बड़ी EPS फ़ाइलों के लिए JVM हीप साइज (`-Xmx2g`) बढ़ाने पर विचार करें ताकि मेमोरी दबाव न हो।

## अक्सर पूछे जाने वाले प्रश्न
**Q: क्या मैं एक कॉल में कई एरे आइटम्स को अपडेट कर सकता हूँ?**  
A: नहीं। आपको प्रत्येक इंडेक्स के लिए `setArrayItem` को कॉल करना होगा जिसे आप संशोधित करना चाहते हैं; API कोई बल्क‑अपडेट मेथड प्रदान नहीं करता।

**Q: क्या aspose.page xmp java कस्टम नेमस्पेस का समर्थन करता है?**  
A: हाँ। `setArrayItem` या `removeArrayItem` कॉल करते समय पूर्ण प्रीफ़िक्स (जैसे `myNS:customProp`) प्रदान करें।

**Q: मैं कैसे सत्यापित करूँ कि मेटाडेटा सही ढंग से अपडेट हुआ है?**  
A: `PsDocument` से EPS को पुनः लोड करें, `getXmpMetadata()` कॉल करें, और लौटाए गए मानों की जांच करें, या फ़ाइल को XMP व्यूअर में खोलें।

**Q: क्या एरे आइटम को पूरी तरह हटाना संभव है?**  
A: किसी विशिष्ट XMP एरे प्रविष्टि को हटाने के लिए `removeArrayItem(namespace, index)` का उपयोग करें।

**Q: क्या परिवर्तन EPS की दृश्य उपस्थिति को प्रभावित करेंगे?**  
A: नहीं। XMP मेटाडेटा ग्राफ़िक सामग्री से अलग संग्रहीत होता है और EPS के रेंडरिंग को नहीं बदलता।

## निष्कर्ष
आप अब Java के लिए **aspose.page xmp ट्यूटोरियल** में निपुण हो गए हैं और EPS XMP मेटाडेटा में एरे आइटम्स को आत्मविश्वास से बदल सकते हैं। यह क्षमता स्वचालित दस्तावेज़ पाइपलाइन, बड़े पैमाने पर मेटाडेटा अपडेट, और दृश्य डेटा को छुए बिना बेहतर एसेट प्रबंधन को सक्षम बनाती है।

---

**अंतिम अपडेट:** 2026-05-15  
**परीक्षण किया गया:** Aspose.Page for Java 24.11 (लेखन के समय नवीनतम)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## संबंधित ट्यूटोरियल

- [Java का उपयोग करके XMP मेटाडेटा में एरे आइटम्स जोड़ें](/page/java/xmp-metadata-manipulation/add-array-items/)
- [aspose page xmp ट्यूटोरियल – Java का उपयोग करके XMP में नामित मान बदलें](/page/java/xmp-metadata-manipulation/change-named-value/)
- [Java का उपयोग करके XMP मेटाडेटा कैसे पढ़ें – Aspose.Page गाइड](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}