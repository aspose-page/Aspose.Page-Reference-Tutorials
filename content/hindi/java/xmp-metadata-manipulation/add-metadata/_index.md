---
title: जावा का उपयोग करके XMP में मेटाडेटा जोड़ें
linktitle: जावा का उपयोग करके XMP में मेटाडेटा जोड़ें
second_title: Aspose.Page जावा एपीआई
description: जावा के लिए Aspose.Page के निर्बाध एकीकरण का अन्वेषण करें और जानें कि अपनी EPS फ़ाइलों में XMP मेटाडेटा को आसानी से कैसे जोड़ा जाए। आज ही अपने दस्तावेज़ प्रबंधन गेम को उन्नत करें!
type: docs
weight: 11
url: /hi/java/xmp-metadata-manipulation/add-metadata/
---
## परिचय
क्या आप जावा का उपयोग करके एक्सएमपी जानकारी जोड़कर अपने दस्तावेज़ के मेटाडेटा को बढ़ाना चाह रहे हैं? आगे कोई तलाश नहीं करें! यह चरण-दर-चरण मार्गदर्शिका आपको जावा लाइब्रेरी के लिए Aspose.Page का उपयोग करके ईपीएस फ़ाइल में मेटाडेटा जोड़ने की प्रक्रिया के बारे में बताएगी। Aspose.Page एक शक्तिशाली उपकरण है जो जावा अनुप्रयोगों में दस्तावेज़ हेरफेर कार्यों को सरल बनाता है।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान।
-  जावा लाइब्रेरी के लिए Aspose.Page स्थापित किया गया। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
- एक ईपीएस फ़ाइल जिसे आप संशोधित करना चाहते हैं।
## पैकेज आयात करें
सबसे पहले, अपने जावा प्रोग्राम में आवश्यक पैकेज आयात करें:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## चरण 1: एक्सएमपी मेटाडेटा प्राप्त करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// इनपुट ईपीएस फ़ाइल स्ट्रीम प्रारंभ करें
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// XMP मेटाडेटा प्राप्त करें. यदि EPS फ़ाइल में XMP मेटाडेटा नहीं है, तो PS मेटाडेटा टिप्पणियों (%%Creator, %%CreateDate, %%Title, आदि) के मानों का उपयोग करके एक नया फ़ाइल बनाया जाता है।
XmpMetadata xmp = document.getXmpMetadata();
```
"आपकी दस्तावेज़ निर्देशिका" को उस वास्तविक पथ से बदलना सुनिश्चित करें जहाँ आपके दस्तावेज़ संग्रहीत हैं।

## चरण 2: क्रिएटरटूल मान पुनर्प्राप्त करें
```java
// "क्रिएटरटूल" मान प्राप्त करें
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## चरण 3: CreateDate मान पुनर्प्राप्त करें
```java
// "CreateDate" मान प्राप्त करें
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## चरण 4: शीर्षक मान पुनः प्राप्त करें
```java
// "शीर्षक" मान प्राप्त करें
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## चरण 5: प्रारूप मान पुनर्प्राप्त करें
```java
//"प्रारूप" मान प्राप्त करें
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## चरण 6: निर्माता मूल्य पुनः प्राप्त करें
```java
// "निर्माता" मान प्राप्त करें
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## चरण 7: मेटाडेटाडेट मान पुनर्प्राप्त करें
```java
// "मेटाडेटाडेट" मान प्राप्त करें
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## चरण 8: नए XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
```java
// आउटपुट ईपीएस फ़ाइल स्ट्रीम प्रारंभ करें
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// नए XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
अंत में, इनपुट ईपीएस स्ट्रीम को बंद करना न भूलें:
```java
// इनपुट ईपीएस स्ट्रीम बंद करें
psStream.close();
```
अब, आपने Java के लिए Aspose.Page का उपयोग करके अपनी EPS फ़ाइल में सफलतापूर्वक मेटाडेटा जोड़ लिया है!
## निष्कर्ष
इस ट्यूटोरियल में, हमने जावा लाइब्रेरी के लिए Aspose.Page का उपयोग करके EPS फ़ाइल में XMP मेटाडेटा जोड़ने की प्रक्रिया का पता लगाया। यह शक्तिशाली उपकरण आपको दस्तावेजों में निर्बाध रूप से हेरफेर करने में सक्षम बनाता है, जिससे आपके समग्र दस्तावेज़ प्रबंधन अनुभव में वृद्धि होती है।
## पूछे जाने वाले प्रश्न
### प्रश्न: क्या जावा के लिए Aspose.Page का उपयोग मुफ़्त है?
 उत्तर: जावा के लिए Aspose.Page एक व्यावसायिक उत्पाद है। आप निःशुल्क परीक्षण के माध्यम से इसकी विशेषताओं का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं जावा के लिए Aspose.Page के लिए दस्तावेज़ कहां पा सकता हूं?
 उत्तर: दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/page/java/).
### प्रश्न: मैं जावा के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 उत्तर: आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: जावा के लिए Aspose.Page किस फ़ाइल स्वरूप का समर्थन करता है?
उत्तर: जावा के लिए Aspose.Page ईपीएस, पीडीएफ और एक्सपीएस सहित विभिन्न प्रारूपों का समर्थन करता है।
### प्रश्न: क्या मैं जावा के लिए Aspose.Page खरीद सकता हूँ?
 उत्तर: हां, आप जावा के लिए Aspose.Page खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).