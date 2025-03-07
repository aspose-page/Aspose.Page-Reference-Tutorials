---
title: जावा का उपयोग करके एक्सएमपी से मेटाडेटा प्राप्त करें
linktitle: जावा का उपयोग करके एक्सएमपी से मेटाडेटा प्राप्त करें
second_title: Aspose.Page जावा एपीआई
description: आसानी से XMP मेटाडेटा निकालने के लिए Java के लिए Aspose.Page की शक्ति को अनलॉक करें। हमारे चरण-दर-चरण मार्गदर्शिका के साथ दस्तावेज़ विश्लेषण को उन्नत बनाएं!
weight: 18
url: /hi/java/xmp-metadata-manipulation/get-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा का उपयोग करके एक्सएमपी से मेटाडेटा प्राप्त करें

## परिचय
XMP फ़ाइलों से मेटाडेटा निकालने के लिए जावा के लिए Aspose.Page का उपयोग करने पर हमारी चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। XMP (एक्स्टेंसिबल मेटाडेटा प्लेटफ़ॉर्म) फ़ाइलों में मेटाडेटा संग्रहीत करने का एक मानकीकृत तरीका प्रदान करता है। यह ट्यूटोरियल जावा का उपयोग करके एक्सएमपी से आवश्यक जानकारी प्राप्त करने, दस्तावेज़ विवरण में अंतर्दृष्टि प्रदान करने पर केंद्रित है।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपकी मशीन पर जावा स्थापित है।
-  जावा के लिए Aspose.Page: Aspose.Page लाइब्रेरी डाउनलोड और इंस्टॉल करें, जिसे आप पा सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में, आवश्यक पैकेज आयात करें:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## चरण 1: इनपुट ईपीएस फ़ाइल स्ट्रीम प्रारंभ करें
अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करके और इनपुट ईपीएस फ़ाइल स्ट्रीम प्रारंभ करके प्रारंभ करें।
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## चरण 2: एक्सएमपी मेटाडेटा प्राप्त करें
ईपीएस फ़ाइल से एक्सएमपी मेटाडेटा पुनर्प्राप्त करें। यदि फ़ाइल में XMP मेटाडेटा का अभाव है, तो PS मेटाडेटा टिप्पणियों के मानों के साथ एक नई फ़ाइल तैयार की जाएगी।
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## चरण 3: क्रिएटरटूल जानकारी निकालें
XMP मेटाडेटा से "क्रिएटरटूल" मान जांचें और प्रिंट करें।
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## चरण 4: क्रिएटडेट जानकारी निकालें
XMP मेटाडेटा से "CreateDate" मान जांचें और प्रिंट करें।
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## चरण 5: थंबनेल चौड़ाई पुनर्प्राप्त करें
यदि थंबनेल मौजूद हैं, तो पहले थंबनेल की चौड़ाई निकालें और प्रिंट करें।
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## चरण 6: प्रारूप जानकारी निकालें
XMP मेटाडेटा से "प्रारूप" मान जांचें और प्रिंट करें।
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## चरण 7: दस्तावेज़आईडी प्राप्त करें
XMP मेटाडेटा से "DocumentID" मान जांचें और प्रिंट करें।
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## निष्कर्ष
बधाई हो! आपने जावा के लिए Aspose.Page का उपयोग करके XMP मेटाडेटा निकालना सफलतापूर्वक सीख लिया है। यह मार्गदर्शिका प्रक्रिया का व्यापक अवलोकन प्रदान करती है, जिससे यह सुनिश्चित होता है कि आप अपने दस्तावेज़ों से आवश्यक जानकारी प्रभावी ढंग से प्राप्त कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ जावा के लिए Aspose.Page का उपयोग कर सकता हूँ?
 हां, Aspose.Page जावा, .NET और अन्य सहित कई भाषाओं का समर्थन करता है। जाँचें[प्रलेखन](https://reference.aspose.com/page/java/) जानकारी के लिए।
### क्या जावा के लिए Aspose.Page का निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मुझे जावा के लिए Aspose.Page के लिए समर्थन कहां मिल सकता है?
 दौरा करना[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक समर्थन के लिए.
### मैं जावा के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त करूं?
 आपको अस्थायी लाइसेंस मिल सकता है[यहाँ](https://purchase.aspose.com/temporary-license/).
### क्या जावा के लिए Aspose.Page के लिए अतिरिक्त संसाधन हैं?
 पूरा अन्वेषण करें[प्रलेखन](https://reference.aspose.com/page/java/) और लाइब्रेरी डाउनलोड करें[यहाँ](https://releases.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
