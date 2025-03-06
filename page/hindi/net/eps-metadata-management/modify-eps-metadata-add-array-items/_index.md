---
title: Aspose.Page के साथ ऐरे आइटम जोड़ें
linktitle: सारणी आइटम जोड़ें
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page का उपयोग करके EPS फ़ाइलों में ऐरे आइटम जोड़ने का तरीका जानें। निर्बाध दस्तावेज़ हेरफेर के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 11
url: /hi/net/eps-metadata-management/modify-eps-metadata-add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ ऐरे आइटम जोड़ें

## परिचय

.NET में दस्तावेज़ हेरफेर और प्रसंस्करण के क्षेत्र में, Aspose.Page एक शक्तिशाली उपकरण के रूप में सामने आता है। इसकी कई क्षमताओं के बीच, ईपीएस फ़ाइल के भीतर सरणी आइटम को संभालना एक सामान्य आवश्यकता है। इस ट्यूटोरियल में, हम .NET वातावरण में Aspose.Page का उपयोग करके सरणी आइटम जोड़ने की चरण-दर-चरण प्रक्रिया का पता लगाएंगे। चाहे आप अनुभवी डेवलपर हों या नवागंतुक, यह मार्गदर्शिका आपको स्पष्टता और सटीकता के साथ प्रक्रिया से गुजराएगी।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- .NET प्रोग्रामिंग की बुनियादी समझ।
-  .NET के लिए Aspose.Page स्थापित। यदि नहीं, तो आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).
- उदाहरणों के साथ अनुसरण करने के लिए विज़ुअल स्टूडियो जैसा एक कोड संपादक।

## नामस्थान आयात करें

अपने .NET प्रोजेक्ट में, Aspose.Page कार्यात्मकताओं का उपयोग करने के लिए आवश्यक नामस्थान आयात करना सुनिश्चित करें। अपने कोड की शुरुआत में निम्नलिखित पंक्तियाँ जोड़ें:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

ये नामस्थान ईपीएस फ़ाइल हेरफेर के लिए आवश्यक आवश्यक वर्गों और विधियों तक पहुंच प्रदान करते हैं।

## चरण 1: ईपीएस फ़ाइल इनपुट स्ट्रीम प्रारंभ करें

```csharp
// एक्सस्टार्ट:3
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
// ईपीएस फ़ाइल इनपुट स्ट्रीम प्रारंभ करें
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//स्ट्रीम से PsDocument इंस्टेंस बनाएं
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

 यहां, हम ईपीएस फ़ाइल के लिए प्रारंभिक इनपुट स्ट्रीम सेट कर रहे हैं और एक बना रहे हैं`PsDocument` उदाहरण।

## चरण 2: एक्सएमपी मेटाडेटा प्राप्त करें

```csharp
// एक्सस्टार्ट:4
// XMP मेटाडेटा प्राप्त करें. यदि EPS फ़ाइल में XMP मेटाडेटा नहीं है, तो हमें PS मेटाडेटा टिप्पणियों (%%Creator, %%CreateDate, %%Title आदि) से मानों से भरी नई फ़ाइल मिलती है।
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

ईपीएस फ़ाइल से एक्सएमपी मेटाडेटा पुनर्प्राप्त करें। यदि EPS फ़ाइल में XMP मेटाडेटा का अभाव है, तो PS मेटाडेटा टिप्पणियों के मानों के साथ एक नई फ़ाइल बनाई जाती है।

## चरण 3: XMP मेटाडेटा मान बदलें

```csharp
// एक्सस्टार्ट:5
// XMP मेटाडेटा मान बदलें

// एक और शीर्षक जोड़ें. इसे डिफ़ॉल्ट रूप से सरणी के अंत में जोड़ा जाएगा।
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// एक और रचनाकार जोड़ें. इसे एक इंडेक्स (0) द्वारा ऐरे में जोड़ा जाएगा।
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

सरणी में नए शीर्षक और निर्माता जोड़कर XMP मेटाडेटा को संशोधित करें।

## चरण 4: परिवर्तित XMP मेटाडेटा के साथ EPS फ़ाइल सहेजें

```csharp
// एक्सस्टार्ट:6
// परिवर्तित XMP मेटाडेटा के साथ EPS फ़ाइल सहेजें

// आउटपुट स्ट्रीम बनाएं
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // ईपीएस फ़ाइल सहेजें
    document.Save(outPsStream);
}
// ExEnd:6
```

अंत में, अद्यतन XMP मेटाडेटा के साथ EPS फ़ाइल को सहेजें। सरणी आइटम में किए गए परिवर्तन आउटपुट फ़ाइल में दिखाई देंगे।

## निष्कर्ष

.NET में Aspose.Page के साथ ऐरे आइटम जोड़ना एक सीधी प्रक्रिया है, जैसा कि इस ट्यूटोरियल में दिखाया गया है। सही पूर्वापेक्षाओं और चरण-दर-चरण मार्गदर्शिका के साथ, डेवलपर्स ईपीएस फ़ाइलों में निर्बाध रूप से हेरफेर कर सकते हैं, यह सुनिश्चित करते हुए कि उनके दस्तावेज़ विशिष्ट मेटाडेटा आवश्यकताओं को पूरा करते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.Page सभी .NET परिवेशों के साथ संगत है?

A1: हां, Aspose.Page को सभी .NET वातावरणों के साथ निर्बाध रूप से काम करने के लिए डिज़ाइन किया गया है, जो सभी प्लेटफार्मों पर लगातार कार्यक्षमता प्रदान करता है।

### Q2: क्या मैं Aspose.Page का निःशुल्क उपयोग कर सकता हूँ?

 A2: Aspose.Page एक निःशुल्क परीक्षण संस्करण प्रदान करता है, जिससे उपयोगकर्ता इसकी सुविधाओं का पता लगा सकते हैं। निरंतर उपयोग के लिए, एक लाइसेंस खरीदा जाना चाहिए[यहाँ](https://purchase.aspose.com/buy).

### Q3: क्या Aspose.Page के लिए अस्थायी लाइसेंस उपलब्ध हैं?

 A3: हाँ, अस्थायी लाइसेंस प्राप्त किया जा सकता है[यहाँ](https://purchase.aspose.com/temporary-license/) अल्पकालिक परियोजना आवश्यकताओं के लिए.

### Q4: मुझे Aspose.Page के लिए सामुदायिक समर्थन कहां मिल सकता है?

A4: सामुदायिक चर्चा और समर्थन के लिए, पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39).

### Q5: .NET के लिए Aspose.Page का नवीनतम संस्करण क्या है?

 A5: .NET के लिए Aspose.Page के नवीनतम संस्करण तक पहुंचने के लिए, देखें[प्रलेखन](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
