---
title: .NET के लिए Aspose.Page के साथ ऐरे आइटम बदलें
linktitle: ऐरे आइटम बदलें
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page का उपयोग करके EPS फ़ाइलों में ऐरे आइटम बदलने का तरीका जानें। कुशल मेटाडेटा हेरफेर के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 15
url: /hi/net/eps-metadata-management/modify-eps-metadata-change-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Page के साथ ऐरे आइटम बदलें

## परिचय

.NET के लिए Aspose.Page का उपयोग करके सरणी आइटम बदलने पर इस व्यापक मार्गदर्शिका में आपका स्वागत है! Aspose.Page एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को ईपीएस फ़ाइलों सहित विभिन्न दस्तावेज़ प्रारूपों के साथ काम करने की अनुमति देती है। इस ट्यूटोरियल में, हम ईपीएस फ़ाइलों के भीतर एक्सएमपी मेटाडेटा में हेरफेर करने, विशेष रूप से सरणी आइटम बदलने पर ध्यान केंद्रित करेंगे।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

1. .NET लाइब्रेरी के लिए Aspose.Page: सुनिश्चित करें कि आपके पास .NET लाइब्रेरी के लिए Aspose.Page स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).

2. विकास परिवेश: अपना पसंदीदा विकास परिवेश सेट करें, चाहे वह विज़ुअल स्टूडियो हो या कोई अन्य आईडीई जो .NET विकास का समर्थन करता हो।

## नामस्थान आयात करें

अपने .NET एप्लिकेशन में, आपको Aspose.Page कार्यक्षमता तक पहुंचने के लिए आवश्यक नामस्थान आयात करने की आवश्यकता है। अपने कोड की शुरुआत में निम्नलिखित नामस्थान जोड़ें:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

```

आइए दिए गए उदाहरण को कई चरणों में तोड़ें:

## चरण 1: ईपीएस फ़ाइल इनपुट स्ट्रीम प्रारंभ करें

```csharp
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

 इस चरण में, हम ईपीएस फ़ाइल इनपुट स्ट्रीम प्रारंभ करते हैं और एक बनाते हैं`PsDocument` इसका उदाहरण.

## चरण 2: एक्सएमपी मेटाडेटा प्राप्त करें

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

ईपीएस फ़ाइल से एक्सएमपी मेटाडेटा पुनर्प्राप्त करें। यदि फ़ाइल में XMP मेटाडेटा नहीं है, तो PS मेटाडेटा टिप्पणियों के मानों के साथ एक नई फ़ाइल बनाई जाती है।

## चरण 3: XMP मेटाडेटा मान बदलें

```csharp
xmp.SetArrayItem("dc:title", 0, new XmpValue("NewTitle"));
xmp.SetArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

यहां, हम XMP मेटाडेटा के भीतर सूचकांक 0 पर शीर्षक और निर्माता आइटम बदलते हैं।

## चरण 4: परिवर्तित XMP मेटाडेटा के साथ EPS फ़ाइल सहेजें

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

एक आउटपुट स्ट्रीम बनाएं और संशोधित XMP मेटाडेटा के साथ EPS फ़ाइल को सहेजें।

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके EPS फ़ाइलों में ऐरे आइटम को बदलने का तरीका सफलतापूर्वक सीख लिया है। यह आपके दस्तावेज़ों में मेटाडेटा को अनुकूलित और प्रबंधित करने में एक महत्वपूर्ण कदम हो सकता है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं अन्य दस्तावेज़ प्रारूपों के साथ .NET के लिए Aspose.Page का उपयोग कर सकता हूँ?

A1: Aspose.Page मुख्य रूप से EPS फ़ाइलों से संबंधित है, लेकिन Aspose विभिन्न दस्तावेज़ प्रारूपों के साथ काम करने के लिए अलग-अलग लाइब्रेरी प्रदान करता है।

### Q2: मुझे अतिरिक्त दस्तावेज़ कहां मिल सकते हैं?

 A2: यहां दस्तावेज़ देखें[.NET दस्तावेज़ीकरण के लिए Aspose.Page](https://reference.aspose.com/page/net/).

### Q3: क्या कोई निःशुल्क परीक्षण उपलब्ध है?

 उ3: हाँ, आप नि:शुल्क परीक्षण संस्करण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q4: मैं अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 A4: से एक अस्थायी लाइसेंस प्राप्त करें[इस लिंक](https://purchase.aspose.com/temporary-license/).

### Q5: मुझे समर्थन कहाँ से मिल सकता है या समुदाय से जुड़ सकता हूँ?

 A5: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक समर्थन और चर्चा के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
