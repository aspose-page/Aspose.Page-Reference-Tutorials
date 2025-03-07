---
title: जावा का उपयोग करके XMP में नेमस्पेस जोड़ें
linktitle: जावा का उपयोग करके XMP में नेमस्पेस जोड़ें
second_title: Aspose.Page जावा एपीआई
description: जावा के लिए Aspose.Page के साथ दस्तावेज़ हेरफेर की शक्ति को अनलॉक करें। इस व्यापक गाइड में आसानी से XMP नेमस्पेस जोड़ना सीखें।
weight: 13
url: /hi/java/xmp-metadata-manipulation/add-namespace/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा का उपयोग करके XMP में नेमस्पेस जोड़ें


## परिचय

दस्तावेज़ हेरफेर के क्षेत्र में, जावा के लिए Aspose.Page एक मजबूत उपकरण के रूप में सामने आता है, जो कार्यात्मकताओं की एक विस्तृत श्रृंखला पेश करता है। एक शक्तिशाली विशेषता जावा का उपयोग करके एक्सएमपी (एक्स्टेंसिबल मेटाडेटा प्लेटफ़ॉर्म) में नेमस्पेस जोड़ने की क्षमता है। यह ट्यूटोरियल आपको प्रक्रिया के माध्यम से मार्गदर्शन करेगा, इसे पालन करने में आसान चरणों में विभाजित करेगा।

## आवश्यक शर्तें

ट्यूटोरियल में गहराई से जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

-  जावा के लिए Aspose.Page: सुनिश्चित करें कि आपके पास लाइब्रेरी स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/java/).

- जावा विकास पर्यावरण: अपने सिस्टम पर एक जावा वातावरण स्थापित करें।

- दस्तावेज़ फ़ाइल: XMP मेटाडेटा के साथ एक EPS फ़ाइल रखें। यदि इसमें XMP मेटाडेटा नहीं है, तो लाइब्रेरी PS मेटाडेटा टिप्पणियों के आधार पर एक बनाएगी।

## पैकेज आयात करें

आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

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
// XMP मेटाडेटा प्राप्त करें. यदि EPS फ़ाइल में XMP मेटाडेटा नहीं है, तो PS मेटाडेटा टिप्पणियों (%%Creator, %%CreateDate, %%Title, आदि) से मानों से भरी एक नई फ़ाइल बनाएं।
XmpMetadata xmp = document.getXmpMetadata();
```

## चरण 2: नया नामस्थान पंजीकृत करें

```java
// उपसर्ग "tmp" के साथ नया XML नामस्थान "http://www.some.org/schema/tmp#" जोड़ें
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

## चरण 3: नई संपत्ति जोड़ें

```java
// नए XML नेमस्पेस में नई प्रॉपर्टी "tmp:newKey" जोड़ें
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

## चरण 4: दस्तावेज़ सहेजें

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

## चरण 5: स्ट्रीम बंद करें

```java
// इनपुट ईपीएस स्ट्रीम बंद करें
psStream.close();
```

अब आपने Java के लिए Aspose.Page का उपयोग करके XMP में सफलतापूर्वक एक नेमस्पेस जोड़ लिया है। अधिक सुविधाओं का पता लगाने और इस लाइब्रेरी की पूरी क्षमता का उपयोग करने के लिए स्वतंत्र महसूस करें।

## निष्कर्ष

Java के लिए Aspose.Page EPS फ़ाइलों में XMP मेटाडेटा में हेरफेर करने के जटिल कार्य को सरल बनाता है। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आपने अपनी दस्तावेज़ प्रसंस्करण क्षमताओं को बढ़ाने के लिए एक मूल्यवान कौशल हासिल कर लिया है।

## पूछे जाने वाले प्रश्न

### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ जावा के लिए Aspose.Page का उपयोग कर सकता हूँ?
Aspose.Page मुख्य रूप से जावा का समर्थन करता है, लेकिन .NET जैसी अन्य भाषाओं के लिए भी संस्करण उपलब्ध हैं।

### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप नि:शुल्क परीक्षण का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).

### मुझे व्यापक दस्तावेज कहां मिल सकते हैं?
 दस्तावेज़ देखें[यहाँ](https://reference.aspose.com/page/java/).

### मैं अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
 आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### क्या Aspose.Page के लिए कोई सामुदायिक मंच हैं?
 हाँ, आप समुदाय के साथ जुड़ सकते हैं[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
