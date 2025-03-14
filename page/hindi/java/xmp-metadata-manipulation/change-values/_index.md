---
title: जावा का उपयोग करके एक्सएमपी में मान बदलें
linktitle: जावा का उपयोग करके एक्सएमपी में मान बदलें
second_title: Aspose.Page जावा एपीआई
description: Java के लिए Aspose.Page के साथ EPS दस्तावेज़ों को बेहतर बनाएं। अनुकूलित और पेशेवर सामग्री के लिए XMP मेटाडेटा को आसानी से संशोधित करें। #जावाडेवलपमेंट
weight: 17
url: /hi/java/xmp-metadata-manipulation/change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा का उपयोग करके एक्सएमपी में मान बदलें

## परिचय
दस्तावेज़ प्रसंस्करण और हेरफेर के क्षेत्र में, जावा के लिए Aspose.Page एक शक्तिशाली उपकरण के रूप में सामने आता है। यह ट्यूटोरियल Aspose.Page लाइब्रेरी के साथ जावा का उपयोग करके EPS (एनकैप्सुलेटेड पोस्टस्क्रिप्ट) दस्तावेज़ों में XMP (एक्स्टेंसिबल मेटाडेटा प्लेटफ़ॉर्म) मानों को बदलने की प्रक्रिया पर प्रकाश डालता है। प्रदान की गई चरण-दर-चरण मार्गदर्शिका का पालन करके, आप सीखेंगे कि मेटाडेटा को आसानी से कैसे संशोधित किया जाए, यह सुनिश्चित करते हुए कि आपके दस्तावेज़ आपकी विशिष्ट आवश्यकताओं के अनुरूप हैं।
## आवश्यक शर्तें
इससे पहले कि हम इस ट्यूटोरियल को शुरू करें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1. जावा विकास वातावरण: सुनिश्चित करें कि आपकी मशीन पर कार्यशील जावा विकास वातावरण है।
2.  जावा लाइब्रेरी के लिए Aspose.Page: जावा लाइब्रेरी के लिए Aspose.Page को डाउनलोड और इंस्टॉल करें। आपको आवश्यक पैकेज मिल सकता है[यहाँ](https://releases.aspose.com/page/java/).
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करके शुरुआत करें। ये पैकेज ईपीएस दस्तावेजों के साथ बातचीत करने और उनमें हेरफेर करने के लिए महत्वपूर्ण हैं।
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
ईपीएस दस्तावेज़ से एक्सएमपी मेटाडेटा पुनर्प्राप्त करें। यदि EPS फ़ाइल में XMP मेटाडेटा नहीं है, तो PS मेटाडेटा टिप्पणियों जैसे %%Creator, %%CreateDate, और %%Title के मानों के साथ एक नई फ़ाइल बनाई जाएगी।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// इनपुट ईपीएस फ़ाइल स्ट्रीम प्रारंभ करें
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// XMP मेटाडेटा प्राप्त करें. यदि ईपीएस फ़ाइल में एक्सएमपी मेटाडेटा नहीं है, तो पीएस मेटाडेटा टिप्पणियों के मूल्यों के साथ एक नया बनाया जाता है
XmpMetadata xmp = document.getXmpMetadata();
```
## चरण 2: "संशोधित दिनांक" मान बदलें
वांछित तिथि को प्रतिबिंबित करने के लिए एक्सएमपी मेटाडेटा में "संशोधित दिनांक" मान को संशोधित करें।
```java
// "संशोधित दिनांक" मान बदलें
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## चरण 3: "निर्माता" मान बदलें
दस्तावेज़ के निर्माता को निर्दिष्ट करने के लिए XMP मेटाडेटा में "निर्माता" मान को अपडेट करें।
```java
// "निर्माता" मान बदलें
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## चरण 4: "शीर्षक" मान बदलें
दस्तावेज़ के लिए उपयुक्त शीर्षक सेट करने के लिए XMP मेटाडेटा में "शीर्षक" मान को संशोधित करें।
```java
//"शीर्षक" मान बदलें
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## चरण 5: परिवर्तित XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
अद्यतन XMP मेटाडेटा के साथ दस्तावेज़ को एक नई EPS फ़ाइल में सहेजें।
```java
// आउटपुट ईपीएस फ़ाइल स्ट्रीम प्रारंभ करें
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//परिवर्तित XMP मेटाडेटा के साथ दस्तावेज़ सहेजें
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## निष्कर्ष
बधाई हो! आपने Java के लिए Aspose.Page का उपयोग करके EPS दस्तावेज़ों में XMP मान बदलने की प्रक्रिया को सफलतापूर्वक नेविगेट कर लिया है। इस ट्यूटोरियल ने आपको मेटाडेटा को संशोधित करने के ज्ञान से सुसज्जित किया है, जिससे यह सुनिश्चित होता है कि आपके दस्तावेज़ आपकी विशिष्ट आवश्यकताओं के साथ सहजता से संरेखित हों।
## पूछे जाने वाले प्रश्न
### प्रश्न: एक्सएमपी मानों को संशोधित करते समय मैं समय क्षेत्र संबंधी विचारों को कैसे संभाल सकता हूं?
 उपयोग`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` समय क्षेत्र सेटिंग्स में एकरूपता सुनिश्चित करने के लिए।
### प्रश्न: क्या मैं एक ही ऑपरेशन में एकाधिक XMP मान बदल सकता हूँ?
 हाँ, का उपयोग करके`put` प्रत्येक वांछित मान के लिए विधि, आप एकाधिक XMP मानों को एक साथ संशोधित कर सकते हैं।
### प्रश्न: मैं जावा के लिए Aspose.Page के लिए अतिरिक्त दस्तावेज़ कहां पा सकता हूं?
 व्यापक दस्तावेज़ीकरण का अन्वेषण करें[यहाँ](https://reference.aspose.com/page/java/).
### प्रश्न: क्या जावा के लिए Aspose.Page के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं जावा के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 एक अस्थायी लाइसेंस प्राप्त करें[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
