---
title: जावा का उपयोग करके एक्सएमपी में सरल गुण जोड़ें
linktitle: जावा का उपयोग करके एक्सएमपी में सरल गुण जोड़ें
second_title: Aspose.Page जावा एपीआई
description: ईपीएस फ़ाइलों में एक्सएमपी मेटाडेटा में गुण जोड़ने पर हमारे गाइड के साथ जावा की क्षमता के लिए Aspose.Page को अनलॉक करें। दस्तावेज़ प्रसंस्करण को सहजता से उन्नत करें!
weight: 14
url: /hi/java/xmp-metadata-manipulation/add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा का उपयोग करके एक्सएमपी में सरल गुण जोड़ें

## परिचय
दस्तावेज़ प्रसंस्करण के निरंतर विकसित होते परिदृश्य में, मेटाडेटा को कुशलतापूर्वक प्रबंधित करना महत्वपूर्ण है। जावा के लिए Aspose.Page डेवलपर्स को एक्स्टेंसिबल मेटाडेटा प्लेटफ़ॉर्म (XMP) डेटा में निर्बाध रूप से हेरफेर करने का अधिकार देता है। इस ट्यूटोरियल में, हम जावा का उपयोग करके एक्सएमपी में सरल गुण जोड़ने की प्रक्रिया का पता लगाएंगे, जो आपको एक व्यापक चरण-दर-चरण मार्गदर्शिका प्रदान करेगा।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान।
-  जावा लाइब्रेरी के लिए Aspose.Page स्थापित किया गया। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
- मेटाडेटा युक्त एक नमूना ईपीएस फ़ाइल। यदि आपके पास एक नहीं है, तो बेझिझक दी गई "xmp3.eps" फ़ाइल का उपयोग करें।
## पैकेज आयात करें
सुनिश्चित करें कि आप अपने प्रोजेक्ट को किकस्टार्ट करने के लिए आवश्यक पैकेज आयात करें:
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
## चरण 1: एक्सएमपी मेटाडेटा प्राप्त करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// इनपुट ईपीएस फ़ाइल स्ट्रीम प्रारंभ करें
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// XMP मेटाडेटा प्राप्त करें. यदि ईपीएस फ़ाइल में एक्सएमपी मेटाडेटा नहीं है, तो हमें पीएस मेटाडेटा टिप्पणियों (%%निर्माता, %%CreateDate, %%शीर्षक, आदि) से मूल्यों से भरा एक नया मिलता है।
XmpMetadata xmp = document.getXmpMetadata();
```
## चरण 2: दिनांक संपत्ति जोड़ें
```java
// दिनांक संपत्ति "xmp:Date1" मान जोड़ें
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## चरण 3: पूर्णांक गुण जोड़ें
```java
// पूर्णांक गुण "xmp:Intg1" मान जोड़ें
xmp.put("xmp:Intg1", new XmpValue(111));
```
## चरण 4: दोहरी संपत्ति जोड़ें
```java
// डबल प्रॉपर्टी "xmp:Double1" मान जोड़ें
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## चरण 5: स्ट्रिंग संपत्ति जोड़ें
```java
// स्ट्रिंग गुण "xmp:String1" मान जोड़ें
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## चरण 6: दस्तावेज़ सहेजें
```java
// आउटपुट ईपीएस फ़ाइल स्ट्रीम प्रारंभ करें
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//परिवर्तित XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## चरण 7: स्ट्रीम बंद करें
```java
// इनपुट ईपीएस स्ट्रीम बंद करें
psStream.close();
```
## निष्कर्ष
Java के लिए Aspose.Page EPS फ़ाइलों में XMP मेटाडेटा में हेरफेर करने की प्रक्रिया को सरल बनाता है। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने दस्तावेज़ के मेटाडेटा को बढ़ाने के लिए आसानी से सरल गुण जोड़ सकते हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ जावा के लिए Aspose.Page का उपयोग कर सकता हूँ?
Aspose.Page मुख्य रूप से जावा का समर्थन करता है, लेकिन .NET जैसी अन्य भाषाओं के लिए भी संस्करण उपलब्ध हैं।
### क्या जावा के लिए Aspose.Page का निःशुल्क परीक्षण उपलब्ध है?
 हां, आप निःशुल्क परीक्षण प्राप्त करके Aspose.Page की विशेषताओं का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं जावा के लिए Aspose.Page के लिए विस्तृत दस्तावेज़ कहाँ पा सकता हूँ?
 दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/page/java/).
### मैं जावा के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 अस्थायी लाइसेंस प्राप्त किया जा सकता है[यहाँ](https://purchase.aspose.com/temporary-license/).
### मैं जावा के लिए Aspose.Page कहां से खरीद सकता हूं?
 आप उत्पाद खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
