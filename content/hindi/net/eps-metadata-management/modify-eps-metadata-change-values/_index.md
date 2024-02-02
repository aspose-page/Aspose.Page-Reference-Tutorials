---
title: .NET के लिए Aspose.Page के साथ मान बदलें
linktitle: मूल्यों में बदलाव करें
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page के साथ मास्टर ईपीएस फ़ाइल हेरफेर। XMP मेटाडेटा मान आसानी से बदलें।
type: docs
weight: 17
url: /hi/net/eps-metadata-management/modify-eps-metadata-change-values/
---
## परिचय

दस्तावेज़ प्रसंस्करण की गतिशील दुनिया में, .NET के लिए Aspose.Page एक शक्तिशाली उपकरण के रूप में सामने आता है, जो डेवलपर्स को EPS फ़ाइलों में आसानी से हेरफेर करने की क्षमता प्रदान करता है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.Page का उपयोग करके EPS फ़ाइलों के भीतर मान बदलने की प्रक्रिया के बारे में विस्तार से जानेंगे। चाहे आप एक अनुभवी डेवलपर हों या जिज्ञासु शुरुआती, यह चरण-दर-चरण मार्गदर्शिका आपको अपनी ईपीएस फ़ाइलों में एक्सएमपी मेटाडेटा को कुशलतापूर्वक संशोधित करने के लिए आवश्यक कौशल से लैस करेगी।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

### 1. .NET लाइब्रेरी के लिए Aspose.Page

सुनिश्चित करें कि आपके पास अपने विकास परिवेश में .NET लाइब्रेरी के लिए Aspose.Page स्थापित है। यदि नहीं, तो आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).

### 2. दस्तावेज़ निर्देशिका

अपने दस्तावेज़ों के लिए एक निर्देशिका सेट करें. यह वह स्थान होगा जहां आपकी ईपीएस फ़ाइलें संग्रहीत हैं।

अब जब हमने अपनी पूर्वापेक्षाएँ सुलझा ली हैं, तो आइए अगले महत्वपूर्ण कदमों पर आगे बढ़ें।

## नामस्थान आयात करें

किसी भी .NET प्रोजेक्ट में, Aspose.Page की कार्यक्षमताओं का उपयोग करने के लिए आवश्यक नामस्थान आयात करना आवश्यक है। यहां बताया गया है कि आप यह कैसे कर सकते हैं:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## चरण 1: ईपीएस फ़ाइल इनपुट स्ट्रीम प्रारंभ करें

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
// ईपीएस फ़ाइल इनपुट स्ट्रीम प्रारंभ करें
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## चरण 2: स्ट्रीम से PsDocument इंस्टेंस बनाएं

```csharp
//स्ट्रीम से PsDocument इंस्टेंस बनाएं
PsDocument document = new PsDocument(psStream);
```

अब जब हमने मंच तैयार कर लिया है, तो आइए अपने ट्यूटोरियल के मूल भाग पर आगे बढ़ें - ईपीएस फ़ाइल के भीतर एक्सएमपी मेटाडेटा मान बदलना।

## चरण 3: एक्सएमपी मेटाडेटा प्राप्त करें

```csharp
// XMP मेटाडेटा प्राप्त करें. यदि EPS फ़ाइल में XMP मेटाडेटा नहीं है, तो हमें PS मेटाडेटा टिप्पणियों (%%Creator, %%CreateDate, %%Title, आदि) से मानों से भरी नई फ़ाइल मिलती है।
XmpMetadata xmp = document.GetXmpMetadata();
```

## चरण 4: XMP मेटाडेटा मान संशोधित करें

अब, आइए XMP मेटाडेटा में कुछ प्रमुख मान बदलें:

### चरण 4.1: संशोधित दिनांक मान बदलें

```csharp
// ModifyDate मान बदलें
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### चरण 4.2: क्रिएटर मान बदलें

```csharp
// क्रिएटर मान बदलें
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### चरण 4.3: शीर्षक मान बदलें

```csharp
// शीर्षक मान बदलें
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

इन परिवर्तनों के साथ, आइए अंतिम चरण पर आगे बढ़ें - संशोधित ईपीएस फ़ाइल को सहेजना।

## चरण 5: बदले हुए XMP मेटाडेटा के साथ EPS फ़ाइल सहेजें

### चरण 5.1: आउटपुट स्ट्रीम बनाएं

```csharp
// आउटपुट स्ट्रीम बनाएं
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### चरण 5.2: ईपीएस फ़ाइल सहेजें

```csharp
// ईपीएस फ़ाइल सहेजें
document.Save(outPsStream);
```

अंत में, इनपुट स्ट्रीम बंद करें:

```csharp
finally
{
    psStream.Close();
}
```

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके EPS फ़ाइल में XMP मेटाडेटा मानों को सफलतापूर्वक संशोधित किया है।

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Page का उपयोग करके ईपीएस फ़ाइलों के भीतर मूल्यों को बदलने की निर्बाध प्रक्रिया का पता लगाया। एक डेवलपर के रूप में, अब आपके पास कुशल दस्तावेज़ हेरफेर के लिए एक शक्तिशाली उपकरण है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं अन्य फ़ाइल स्वरूपों के साथ .NET के लिए Aspose.Page का उपयोग कर सकता हूँ?

A1: Aspose.Page मुख्य रूप से EPS फ़ाइल हेरफेर पर केंद्रित है। अन्य प्रारूपों के लिए, Aspose के उत्पादों की विविध श्रृंखला का पता लगाएं।

### Q2: क्या कोई परीक्षण संस्करण उपलब्ध है?

 उ2: हां, आप नि:शुल्क परीक्षण के साथ .NET के लिए Aspose.Page को आज़मा सकते हैं[यहाँ](https://releases.aspose.com/).

### Q3: मुझे विस्तृत दस्तावेज कहां मिल सकते हैं?

 A3: व्यापक दस्तावेज़ पाया जा सकता है[यहाँ](https://reference.aspose.com/page/net/).

### Q4: मैं अस्थायी लाइसेंस कैसे प्राप्त करूं?

 A4: आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### Q5: क्या मैं .NET के लिए Aspose.Page खरीद सकता हूँ?

 ए5: बिल्कुल! खरीद पृष्ठ पर जाएँ[यहाँ](https://purchase.aspose.com/buy) लाइसेंसिंग विकल्पों के लिए.