---
title: .NET के लिए Aspose.Page के साथ नामांकित मान बदलें
linktitle: नामित मान बदलें
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page का उपयोग करके EPS फ़ाइलों में नामित मानों को बदलने का तरीका जानें। अनुकूलित दस्तावेज़ प्रसंस्करण के लिए XMP मेटाडेटा को सहजता से अनुकूलित करें।
type: docs
weight: 16
url: /hi/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---
## परिचय

दस्तावेज़ प्रसंस्करण की दुनिया में, .NET के लिए Aspose.Page EPS फ़ाइलों में हेरफेर करने के लिए एक शक्तिशाली उपकरण के रूप में सामने आता है। इसके द्वारा प्रदान की जाने वाली प्रमुख कार्यक्षमताओं में से एक XMP मेटाडेटा के भीतर नामित मानों को बदलने की क्षमता है। यह ट्यूटोरियल आपको .NET के लिए Aspose.Page का उपयोग करके नामित मान को बदलने की प्रक्रिया में मार्गदर्शन करेगा, जिससे आप अपनी विशिष्ट आवश्यकताओं के अनुसार अपनी EPS फ़ाइलों को अनुकूलित कर सकेंगे।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET के लिए Aspose.Page: सुनिश्चित करें कि आपके पास .NET लाइब्रेरी के लिए Aspose.Page स्थापित है। यदि नहीं, तो आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).

- दस्तावेज़ निर्देशिका: अपनी ईपीएस फ़ाइलों के लिए एक निर्दिष्ट निर्देशिका रखें जहाँ आप नामित मूल्य परिवर्तन कर सकते हैं।

## नामस्थान आयात करें

आपके .NET प्रोजेक्ट में, आपको Aspose.Page द्वारा प्रदान की गई कार्यक्षमता तक पहुंचने के लिए आवश्यक नेमस्पेस आयात करने की आवश्यकता है। अपने कोड में निम्नलिखित नामस्थान जोड़ें:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

अब, व्यापक समझ के लिए कोड को कई चरणों में विभाजित करते हैं:

## चरण 1: ईपीएस फ़ाइल इनपुट स्ट्रीम प्रारंभ करें

```csharp
// एक्सस्टार्ट:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:1
```

इस चरण में, हम उस ईपीएस फ़ाइल के लिए इनपुट स्ट्रीम सेट करते हैं जिसे आप संशोधित करना चाहते हैं। "आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से बदलना सुनिश्चित करें।

## चरण 2: एक्सएमपी मेटाडेटा प्राप्त करें

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

ईपीएस फ़ाइल से मौजूदा एक्सएमपी मेटाडेटा पुनर्प्राप्त करें। यदि ईपीएस फ़ाइल में एक्सएमपी मेटाडेटा नहीं है, तो पीएस मेटाडेटा टिप्पणियों के मूल्यों के साथ एक नया जेनरेट किया जाएगा।

## चरण 3: XMP मेटाडेटा मान बदलें

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

यहां, हम "xmpTPg:MaxPageSize" संरचना के भीतर दो नामित मानों को बदलते हुए प्रदर्शित करते हैं। आप इसे अपनी विशिष्ट आवश्यकताओं के अनुसार अनुकूलित कर सकते हैं।

## चरण 4: परिवर्तित XMP मेटाडेटा के साथ EPS फ़ाइल सहेजें

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

संशोधित ईपीएस फ़ाइल को आउटपुट स्ट्रीम में सहेजें। फ़ाइल अब XMP मेटाडेटा में किए गए परिवर्तनों को दर्शाएगी।

## निष्कर्ष

इस ट्यूटोरियल से, आपने सीखा कि EPS फ़ाइलों में XMP मेटाडेटा के भीतर नामित मानों को बदलने के लिए .NET के लिए Aspose.Page का लाभ कैसे उठाया जाए। यह कार्यक्षमता विशिष्ट आवश्यकताओं को पूरा करने के लिए आपके दस्तावेज़ों को अनुकूलित और अनुकूलित करने की संभावनाओं की एक दुनिया खोलती है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं अन्य दस्तावेज़ प्रारूपों के साथ .NET के लिए Aspose.Page का उपयोग कर सकता हूँ?

A1: हां, Aspose.Page EPS, XPS और PDF सहित विभिन्न दस्तावेज़ प्रारूपों का समर्थन करता है।

### Q2: क्या .NET के लिए Aspose.Page का कोई परीक्षण संस्करण उपलब्ध है?

 उ2: हाँ, आप निःशुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q3: मुझे .NET के लिए Aspose.Page पर अधिक दस्तावेज़ कहां मिल सकते हैं?

 A3: दस्तावेज़ देखें[यहाँ](https://reference.aspose.com/page/net/).

### Q4: मैं .NET के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 A4: आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### Q5: .NET उपयोगकर्ताओं के लिए Aspose.Page के लिए कौन से समर्थन विकल्प उपलब्ध हैं?

 A5: सामुदायिक मंच पर जाएँ[यहाँ](https://forum.aspose.com/c/page/39) समर्थन और चर्चा के लिए.