---
title: जावा का उपयोग करके एक्सएमपी में ऐरे आइटम बदलें
linktitle: जावा का उपयोग करके एक्सएमपी में ऐरे आइटम बदलें
second_title: Aspose.Page जावा एपीआई
description: जावा के लिए Aspose.Page का उपयोग करके XMP में ऐरे आइटम बदलने का तरीका जानें। हमारे चरण-दर-चरण मार्गदर्शिका के साथ मेटाडेटा को आसानी से संशोधित करें। अभी अपने ईपीएस दस्तावेज़ों को बेहतर बनाएं!
weight: 15
url: /hi/java/xmp-metadata-manipulation/change-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा का उपयोग करके एक्सएमपी में ऐरे आइटम बदलें

## परिचय
जावा के लिए Aspose.Page का उपयोग करके XMP में ऐरे आइटम बदलने पर हमारी व्यापक मार्गदर्शिका में आपका स्वागत है! Aspose.Page एक शक्तिशाली जावा लाइब्रेरी है जो आपको EPS फ़ाइलों में XMP मेटाडेटा के साथ निर्बाध रूप से काम करने की अनुमति देती है। इस ट्यूटोरियल में, हम आपको एक्सएमपी मेटाडेटा के भीतर सरणी आइटम को संशोधित करने की प्रक्रिया के बारे में बताएंगे, जिससे आपको अपने ईपीएस दस्तावेज़ों को बढ़ाने और अनुकूलित करने में मदद मिलेगी।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा के लिए Aspose.Page लाइब्रेरी। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
## पैकेज आयात करें
आरंभ करने के लिए, आइए अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Page लाइब्रेरी शामिल है।
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;

```
## चरण 1: एक्सएमपी मेटाडेटा प्राप्त करें
सबसे पहले, अपनी ईपीएस फ़ाइल से एक्सएमपी मेटाडेटा पुनर्प्राप्त करें। यदि EPS फ़ाइल में पहले से ही XMP मेटाडेटा नहीं है, तो PS मेटाडेटा टिप्पणियों जैसे %%Creator, %%CreateDate, %%Title, आदि के मानों के साथ एक नई फ़ाइल बनाई जाएगी।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// इनपुट ईपीएस फ़ाइल स्ट्रीम प्रारंभ करें
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// XMP मेटाडेटा प्राप्त करें. यदि EPS फ़ाइल में XMP मेटाडेटा नहीं है, तो एक नई फ़ाइल PS मेटाडेटा टिप्पणियों के मानों से भरी जाएगी।
XmpMetadata xmp = document.getXmpMetadata();
```
## चरण 2: "dc:title" ऐरे आइटम सेट करें
अब, आइए "dc:title" ऐरे आइटम को एक नए मान के साथ इंडेक्स 0 पर सेट करें।
```java
// इंडेक्स 0 द्वारा "dc:title" ऐरे आइटम सेट करें
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```
## चरण 3: "dc:creator" ऐरे आइटम सेट करें
इसी तरह, "dc:creator" ऐरे आइटम को नए क्रिएटर मान के साथ इंडेक्स 0 पर सेट करें।
```java
// इंडेक्स 0 द्वारा "dc:creator" ऐरे आइटम सेट करें
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```
## चरण 4: आउटपुट ईपीएस फ़ाइल स्ट्रीम प्रारंभ करें
आउटपुट ईपीएस फ़ाइल स्ट्रीम तैयार करें जहां संशोधित दस्तावेज़ सहेजा जाएगा।
```java
// आउटपुट ईपीएस फ़ाइल स्ट्रीम प्रारंभ करें
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
## चरण 5: परिवर्तित XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
दस्तावेज़ को अद्यतन XMP मेटाडेटा के साथ सहेजें।
```java
//परिवर्तित XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## निष्कर्ष
बधाई हो! आपने जावा के लिए Aspose.Page का उपयोग करके XMP में ऐरे आइटम को बदलने का तरीका सफलतापूर्वक सीख लिया है। यह ट्यूटोरियल चरण-दर-चरण मार्गदर्शन प्रदान करता है, जिससे यह सुनिश्चित होता है कि आप अनुकूलित मेटाडेटा के साथ अपने ईपीएस दस्तावेज़ों को आसानी से बढ़ा सकते हैं।

## पूछे जाने वाले प्रश्न
### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ जावा के लिए Aspose.Page का उपयोग कर सकता हूँ?
Aspose.Page मुख्य रूप से जावा के लिए डिज़ाइन किया गया है, लेकिन Aspose अन्य भाषाओं के लिए समान लाइब्रेरी प्रदान करता है।
### मैं जावा के लिए Aspose.Page के लिए विस्तृत दस्तावेज़ कहाँ पा सकता हूँ?
 दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/page/java/).
### क्या जावा के लिए Aspose.Page के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं जावा के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आपको अस्थायी लाइसेंस मिल सकता है[यहाँ](https://purchase.aspose.com/temporary-license/).
### मैं जावा के लिए Aspose.Page का पूर्ण संस्करण कहां से खरीद सकता हूं?
 आप पूर्ण संस्करण खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
