---
title: जावा का उपयोग करके एक्सएमपी मेटाडेटा में ऐरे आइटम जोड़ें
linktitle: जावा का उपयोग करके एक्सएमपी मेटाडेटा में ऐरे आइटम जोड़ें
second_title: Aspose.Page जावा एपीआई
description: Java के लिए Aspose.Page के साथ EPS फ़ाइलें बढ़ाएँ। XMP मेटाडेटा में आसानी से ऐरे आइटम जोड़ना सीखें। अभी हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें!
weight: 10
url: /hi/java/xmp-metadata-manipulation/add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा का उपयोग करके एक्सएमपी मेटाडेटा में ऐरे आइटम जोड़ें

## परिचय
XMP मेटाडेटा में ऐरे आइटम जोड़ने के लिए जावा के लिए Aspose.Page का उपयोग करने पर हमारी चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। Aspose.Page एक शक्तिशाली जावा लाइब्रेरी है जो आपको ईपीएस फ़ाइलों सहित विभिन्न दस्तावेज़ प्रारूपों में हेरफेर करने और काम करने की अनुमति देती है। इस ट्यूटोरियल में, हम जावा का उपयोग करके एक्सएमपी मेटाडेटा में सरणी आइटम जोड़ने के विशिष्ट कार्य पर ध्यान केंद्रित करेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- जावा लाइब्रेरी के लिए Aspose.Page स्थापित किया गया।
- जावा प्रोग्रामिंग की बुनियादी समझ.
- मौजूदा एक्सएमपी मेटाडेटा या पीएस मेटाडेटा टिप्पणियों के साथ एक वैध ईपीएस फ़ाइल।
## पैकेज आयात करें
आरंभ करने के लिए, आपको Aspose.Page के साथ काम करने के लिए आवश्यक पैकेज आयात करने होंगे। अपनी जावा फ़ाइल की शुरुआत में निम्नलिखित पंक्तियाँ शामिल करें:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
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
इस चरण में, हम ईपीएस फ़ाइल से मौजूदा एक्सएमपी मेटाडेटा पुनर्प्राप्त करते हैं। यदि EPS फ़ाइल में पहले से XMP मेटाडेटा नहीं है, तो Aspose.Page एक नया बनाता है और उसे PS मेटाडेटा टिप्पणियों से मानों से भर देता है।
## चरण 2: "dc:title" ऐरे आइटम जोड़ें
```java
// एक और "dc:title" सरणी आइटम जोड़ें
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
अब, हम XMP मेटाडेटा में "dc:title" प्रॉपर्टी में एक नया ऐरे आइटम जोड़ते हैं। "न्यूटाइटल" को वांछित शीर्षक से बदलें।
## चरण 3: "dc:creator" ऐरे आइटम जोड़ें
```java
// एक और "dc:creator" सरणी आइटम जोड़ें
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
इसी तरह, हम XMP मेटाडेटा में "dc:creator" प्रॉपर्टी में एक नया ऐरे आइटम जोड़ते हैं। "न्यूक्रिएटर" को वांछित निर्माता जानकारी से बदलें।
## चरण 4: आउटपुट ईपीएस फ़ाइल स्ट्रीम प्रारंभ करें
```java
// आउटपुट ईपीएस फ़ाइल स्ट्रीम प्रारंभ करें
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
आउटपुट ईपीएस फ़ाइल स्ट्रीम तैयार करें जहां अद्यतन XMP मेटाडेटा के साथ संशोधित दस्तावेज़ सहेजा जाएगा।
## चरण 5: परिवर्तित XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
```java
//परिवर्तित XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
अद्यतन XMP मेटाडेटा के साथ दस्तावेज़ को आउटपुट EPS फ़ाइल में सहेजें।
## निष्कर्ष
बधाई हो! आपने जावा के लिए Aspose.Page का उपयोग करके XMP मेटाडेटा में ऐरे आइटम जोड़ने का तरीका सफलतापूर्वक सीख लिया है। यह शक्तिशाली लाइब्रेरी ईपीएस फ़ाइलों में हेरफेर करने की प्रक्रिया को सरल बनाती है और दस्तावेज़ प्रसंस्करण के लिए व्यापक कार्यक्षमता प्रदान करती है।
## अक्सर पूछे जाने वाले प्रश्नों

### क्या मैं अन्य दस्तावेज़ प्रारूपों के साथ जावा के लिए Aspose.Page का उपयोग कर सकता हूँ?
हां, Aspose.Page ईपीएस, पीडीएफ और एक्सपीएस सहित विभिन्न दस्तावेज़ प्रारूपों का समर्थन करता है।
### क्या जावा के लिए Aspose.Page के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं जावा के लिए Aspose.Page के लिए दस्तावेज़ कहाँ पा सकता हूँ?
 दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/page/java/).
### मैं जावा के लिए Aspose.Page कैसे खरीद सकता हूँ?
 आप उत्पाद खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### क्या जावा के लिए Aspose.Page के लिए अस्थायी लाइसेंस उपलब्ध हैं?
 हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
