---
title: .NET के लिए Aspose.Page के साथ सरल गुण जोड़ें
linktitle: सरल गुण जोड़ें
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page के साथ EPS फ़ाइलें बढ़ाएँ। अनुकूलित दस्तावेज़ मेटाडेटा के लिए सहजता से सरल गुण जोड़ें।
type: docs
weight: 14
url: /hi/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---
## परिचय

दस्तावेज़ हेरफेर और संवर्द्धन के क्षेत्र में, .NET के लिए Aspose.Page एक शक्तिशाली उपकरण के रूप में उभरता है, जो डेवलपर्स को EPS फ़ाइलों के भीतर XMP मेटाडेटा को सहजता से जोड़ने और संशोधित करने की क्षमता प्रदान करता है। यह ट्यूटोरियल .NET के लिए Aspose.Page का उपयोग करके EPS फ़ाइल में सरल गुण जोड़ने की प्रक्रिया में आपका मार्गदर्शन करेगा।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1.  .NET के लिए Aspose.Page: सुनिश्चित करें कि आपके विकास परिवेश में .NET के लिए Aspose.Page स्थापित है। यदि नहीं, तो आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).

2.  दस्तावेज़ निर्देशिका: अपनी ईपीएस फ़ाइलों को संग्रहीत करने के लिए एक निर्देशिका सेट करें। अद्यतन करें`dataDir` आपके दस्तावेज़ निर्देशिका के पथ के साथ दिए गए कोड स्निपेट में परिवर्तनीय।

## नामस्थान आयात करें

आरंभ करने के लिए, .NET के लिए Aspose.Page के साथ संचार सक्षम करने के लिए आवश्यक नामस्थान आयात करें। अपनी कोड फ़ाइल की शुरुआत में निम्नलिखित पंक्तियाँ जोड़ें:

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
// एक्सस्टार्ट:1
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
// ईपीएस फ़ाइल इनपुट स्ट्रीम प्रारंभ करें
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//स्ट्रीम से PsDocument इंस्टेंस बनाएं
PsDocument document = new PsDocument(psStream);
```

## चरण 2: एक्सएमपी मेटाडेटा प्राप्त करें

```csharp
// XMP मेटाडेटा प्राप्त करें. यदि ईपीएस फ़ाइल में एक्सएमपी मेटाडेटा नहीं है, तो हमें पीएस मेटाडेटा टिप्पणियों (%%निर्माता, %%CreateDate, %%शीर्षक, आदि) से मूल्यों से भरा एक नया मिलता है।
XmpMetadata xmp = document.GetXmpMetadata();
```

## चरण 3: XMP मेटाडेटा मान बदलें

```csharp
// XMP मेटाडेटा मान बदलें
DateTime now = DateTime.UtcNow;

// पूर्णांक गुण जोड़ें
xmp.Add("xmp:Intg1", new XmpValue(111));

// दिनांक समय गुण जोड़ें
xmp.Add("xmp:Date1", new XmpValue(now));

// डबल प्रॉपर्टी जोड़ें
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//स्ट्रिंग गुण जोड़ें
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## चरण 4: परिवर्तित XMP मेटाडेटा के साथ EPS फ़ाइल सहेजें

```csharp
// परिवर्तित XMP मेटाडेटा के साथ EPS फ़ाइल सहेजें

// आउटपुट स्ट्रीम बनाएं
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // ईपीएस फ़ाइल सहेजें
    document.Save(outPsStream);
}
```

## चरण 5: फ़ाइलस्ट्रीम बंद करें

```csharp
finally
{
    psStream.Close();
}
```

इन चरणों का पालन करके, आप .NET के लिए Aspose.Page का उपयोग करके अपनी EPS फ़ाइलों में सरल गुणों को आसानी से शामिल कर सकते हैं।

## निष्कर्ष

अंत में, .NET के लिए Aspose.Page उन डेवलपर्स के लिए एक अमूल्य संपत्ति साबित होती है जो कस्टम XMP मेटाडेटा के साथ EPS फ़ाइलों को बढ़ाना चाहते हैं। सरल गुणों को जोड़कर, आप विशिष्ट आवश्यकताओं को पूरा करने के लिए अपने दस्तावेज़ों को अनुकूलित और समृद्ध कर सकते हैं, जिससे दस्तावेज़ में हेरफेर के लिए संभावनाओं की दुनिया खुल जाती है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या .NET के लिए Aspose.Page सभी EPS फ़ाइलों के साथ संगत है?

A1: .NET के लिए Aspose.Page EPS फ़ाइलों की एक विस्तृत श्रृंखला का समर्थन करता है। हालाँकि, संगतता अलग-अलग फ़ाइलों की जटिलता और संरचना के आधार पर भिन्न हो सकती है।

### Q2: क्या मैं .NET के लिए Aspose.Page के साथ मौजूदा XMP मेटाडेटा को संशोधित कर सकता हूँ?

ए2: बिल्कुल! जैसा कि इस ट्यूटोरियल में दिखाया गया है, आप मौजूदा XMP मेटाडेटा मानों को आसानी से बदल सकते हैं या अपनी आवश्यकताओं के अनुरूप नए जोड़ सकते हैं।

### Q3: क्या मैं जिन प्रकार की संपत्तियों को जोड़ सकता हूँ उनकी कोई सीमाएँ हैं?

A3: .NET के लिए Aspose.Page पूर्णांक, दिनांक, युगल और स्ट्रिंग सहित गुणों के लिए विभिन्न डेटा प्रकारों का समर्थन करता है। आपके पास अपने मेटाडेटा के लिए उपयुक्त प्रकार चुनने में लचीलापन है।

### Q4: मैं .NET के लिए Aspose.Page के लिए तकनीकी सहायता कैसे प्राप्त कर सकता हूं?

 A4: तकनीकी सहायता के लिए, पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) या अन्वेषण करें[प्रलेखन](https://reference.aspose.com/page/net/) व्यापक मार्गदर्शन के लिए.

### Q5: क्या .NET के लिए Aspose.Page का कोई निःशुल्क परीक्षण उपलब्ध है?

 A5: हाँ, आप निःशुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).