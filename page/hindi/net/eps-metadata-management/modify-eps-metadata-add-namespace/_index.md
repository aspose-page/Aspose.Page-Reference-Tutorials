---
title: .NET के लिए Aspose.Page के साथ नेमस्पेस जोड़ें
linktitle: नेमस्पेस जोड़ें
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page के साथ EPS फ़ाइलें बढ़ाएँ। आसानी से नेमस्पेस जोड़ें, XMP मेटाडेटा को संशोधित करें, और अपने .NET विकास वर्कफ़्लो को बढ़ावा दें।
weight: 13
url: /hi/net/eps-metadata-management/modify-eps-metadata-add-namespace/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Page के साथ नेमस्पेस जोड़ें

## परिचय

.NET विकास की गतिशील दुनिया में, Aspose.Page EPS फ़ाइलों को संभालने के लिए एक शक्तिशाली उपकरण के रूप में सामने आता है। .NET के लिए Aspose.Page डेवलपर्स को XMP मेटाडेटा में निर्बाध रूप से हेरफेर करने की अनुमति देता है, जिससे नेमस्पेस जोड़ने और EPS फ़ाइलों के मेटाडेटा को बढ़ाने की सुविधा मिलती है।

इस ट्यूटोरियल में, हम .NET के लिए Aspose.Page का उपयोग करके नेमस्पेस जोड़ने की प्रक्रिया के बारे में विस्तार से जानेंगे। नेमस्पेस आयात करने से लेकर अपनी संशोधित ईपीएस फ़ाइल को सहेजने तक चरण-दर-चरण निर्देश जानने के लिए अनुसरण करें। आएँ शुरू करें!

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1.  .NET लाइब्रेरी के लिए Aspose.Page: लाइब्रेरी को डाउनलोड और इंस्टॉल करें[Aspose.पेज दस्तावेज़ीकरण](https://reference.aspose.com/page/net/).

2. विकास परिवेश: अपनी मशीन पर एक कार्यशील .NET विकास परिवेश स्थापित करें।

अब, आइए .NET के लिए Aspose.Page की रोमांचक दुनिया में कूदें।

## नामस्थान आयात करें

चीजों को शुरू करने के लिए, आपको Aspose.Page कार्यात्मकताओं तक पहुंचने के लिए आवश्यक नामस्थान आयात करने की आवश्यकता है। यहां बताया गया है कि आप यह कैसे कर सकते हैं:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## चरण 1: अपना प्रोजेक्ट प्रारंभ करें

अपने .NET प्रोजेक्ट में, अपनी इच्छित फ़ाइल खोलें और Aspose.Page लाइब्रेरी प्रारंभ करें। निम्नलिखित कोड स्निपेट का उपयोग करें:

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
```

## चरण 2: ईपीएस फ़ाइल खोलें

नीचे दिखाए अनुसार ईपीएस फ़ाइल खोलने के लिए एक फ़ाइलस्ट्रीम बनाएं:

```csharp
// ईपीएस फ़ाइल इनपुट स्ट्रीम प्रारंभ करें
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);

//स्ट्रीम से PsDocument इंस्टेंस बनाएं
PsDocument document = new PsDocument(psStream);
```

## चरण 3: एक्सएमपी मेटाडेटा प्राप्त करें

निम्नलिखित कोड का उपयोग करके ईपीएस फ़ाइल से एक्सएमपी मेटाडेटा पुनर्प्राप्त करें:

```csharp
// XMP मेटाडेटा प्राप्त करें. यदि ईपीएस फ़ाइल में एक्सएमपी मेटाडेटा नहीं है, तो पीएस मेटाडेटा टिप्पणियों के मूल्यों के साथ एक नया बनाया जाता है।
XmpMetadata xmp = document.GetXmpMetadata();
```

## चरण 4: एक्सएमपी मेटाडेटा बदलें

मौजूदा XMP मेटाडेटा को संशोधित करें या आवश्यकतानुसार नए मान जोड़ें। यहां एक नया XML नेमस्पेस और एक स्ट्रिंग प्रॉपर्टी जोड़ने का एक उदाहरण दिया गया है:

```csharp
// नया XML नेमस्पेस "tmp" जोड़ें।
xmp.RegisterNamespaceUri("tmp", "http://www.some.org/schema/tmp#");

// नए नेमस्पेस में नई स्ट्रिंग प्रॉपर्टी जोड़ें।
xmp.Add("tmp:newKey", new XmpValue("NewValue"));
```

## चरण 5: ईपीएस फ़ाइल सहेजें

निम्नलिखित कोड का उपयोग करके अद्यतन XMP मेटाडेटा के साथ EPS फ़ाइल सहेजें:

```csharp
// आउटपुट स्ट्रीम बनाएं
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_namespace_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // ईपीएस फ़ाइल सहेजें
    document.Save(outPsStream);
}
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके EPS फ़ाइल में सफलतापूर्वक नामस्थान जोड़ दिए हैं। यह शक्तिशाली लाइब्रेरी एक्सएमपी मेटाडेटा में हेरफेर करने की संभावनाओं की दुनिया खोलती है, जो ईपीएस फाइलों के साथ काम करने वाले डेवलपर्स के लिए एक सहज अनुभव प्रदान करती है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.Page .NET के सभी संस्करणों के साथ संगत है?

A1: .NET के लिए Aspose.Page, .NET फ्रेमवर्क के विभिन्न संस्करणों के साथ संगत है, जो डेवलपर्स के लिए लचीलापन सुनिश्चित करता है।

### Q2: क्या मैं EPS फ़ाइलों से मेटाडेटा निकालने के लिए Aspose.Page का उपयोग कर सकता हूँ?

ए2: बिल्कुल! Aspose.Page आपको EPS फ़ाइलों से XMP मेटाडेटा को आसानी से निकालने और संशोधित करने की अनुमति देता है।

### Q3: मुझे अतिरिक्त सहायता या सहायता कहां मिल सकती है?

 A3: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक समर्थन और चर्चा के लिए।

### Q4: क्या Aspose.Page के लिए कोई निःशुल्क परीक्षण उपलब्ध है?

 उ4: हाँ, आप Aspose.Page का निःशुल्क परीक्षण देख सकते हैं[यहाँ](https://releases.aspose.com/).

### Q5: मैं Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 A5: एक अस्थायी लाइसेंस प्राप्त करें[यहाँ](https://purchase.aspose.com/temporary-license/) परीक्षण प्रयोजनों के लिए.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
