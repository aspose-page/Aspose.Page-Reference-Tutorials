---
title: Aspose.Page के साथ नामांकित मान जोड़ें
linktitle: नामांकित मान जोड़ें
second_title: Aspose.Page .NET API
description: Aspose.Page का उपयोग करके .NET में EPS फ़ाइलों में नामित मान जोड़ने का तरीका जानें। यह व्यापक ट्यूटोरियल चरण दर चरण प्रक्रिया में आपका मार्गदर्शन करता है।
type: docs
weight: 12
url: /hi/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---
## परिचय

.NET के साथ दस्तावेज़ प्रसंस्करण के क्षेत्र में, Aspose.Page EPS फ़ाइलों को संभालने के लिए एक शक्तिशाली उपकरण के रूप में सामने आता है। Aspose.Page डेवलपर्स को XMP मेटाडेटा में हेरफेर करने, नामित मान जोड़ने जैसे कार्यों को सुविधाजनक बनाने का अधिकार देता है। यह ट्यूटोरियल चरण-दर-चरण तरीके से Aspose.Page का उपयोग करके EPS फ़ाइल में नामित मान जोड़ने की प्रक्रिया में आपका मार्गदर्शन करेगा।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- विजुअल स्टूडियो जैसा एक एकीकृत विकास वातावरण (आईडीई) स्थापित किया गया।
-  .NET लाइब्रेरी के लिए Aspose.Page। यदि इंस्टॉल नहीं है तो आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).

## नामस्थान आयात करें

सबसे पहले, आइए आपके C# कोड में आवश्यक नामस्थान आयात करें। Aspose.Page द्वारा प्रदान की गई कार्यक्षमताओं तक पहुँचने के लिए ये नामस्थान महत्वपूर्ण हैं:

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

 प्रारंभिक चरण में ईपीएस फ़ाइल के लिए इनपुट स्ट्रीम प्रारंभ करना शामिल है। प्रतिस्थापित करें`"Your Document Directory"` आपकी दस्तावेज़ निर्देशिका के पथ के साथ:

```csharp
// एक्सस्टार्ट:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## चरण 2: एक्सएमपी मेटाडेटा प्राप्त करें

ईपीएस फ़ाइल से एक्सएमपी मेटाडेटा पुनर्प्राप्त करें। यदि ईपीएस फ़ाइल में एक्सएमपी मेटाडेटा का अभाव है, तो एक नया बनाया जाएगा, जो पीएस मेटाडेटा टिप्पणियों के मूल्यों से भरा होगा:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## चरण 3: XMP मेटाडेटा मान बदलें

अब, आइए XMP मेटाडेटा में परिवर्तन करें। इस उदाहरण में, हम "xmpTPg:MaxPageSize" संरचना में एक नामित मान जोड़ेंगे:

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## चरण 4: परिवर्तित XMP मेटाडेटा के साथ EPS फ़ाइल सहेजें

अद्यतन XMP मेटाडेटा के साथ EPS फ़ाइल सहेजें। एक आउटपुट स्ट्रीम बनाएं और संशोधित ईपीएस फ़ाइल सहेजें:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## निष्कर्ष

बधाई हो! आपने .NET में Aspose.Page का उपयोग करके EPS फ़ाइल में एक नामित मान सफलतापूर्वक जोड़ दिया है। यह ट्यूटोरियल दस्तावेज़ हेरफेर में Aspose.Page की सरलता और प्रभावशीलता को प्रदर्शित करते हुए आपको आवश्यक चरणों से परिचित कराता है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.Page विभिन्न EPS फ़ाइल संस्करणों के साथ संगत है?

A1: Aspose.Page विभिन्न EPS फ़ाइल संस्करणों का समर्थन करता है, जो दस्तावेज़ों की एक विस्तृत श्रृंखला के साथ संगतता सुनिश्चित करता है।

### Q2: क्या मैं व्यावसायिक परियोजनाओं के लिए Aspose.Page का उपयोग कर सकता हूँ?

 A2: हां, Aspose.Page एक वाणिज्यिक लाइसेंस के साथ आता है, और आप इसे खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).

### Q3: क्या Aspose.Page के लिए कोई निःशुल्क परीक्षण उपलब्ध है?

 उ3: हां, आप नि:शुल्क परीक्षण के साथ Aspose.Page को एक्सप्लोर कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q4: मैं Aspose समुदाय से समर्थन कैसे प्राप्त कर सकता हूं या उससे कैसे जुड़ सकता हूं?

 A4: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) समर्थन प्राप्त करने और समुदाय से जुड़ने के लिए।

### Q5: अस्थायी लाइसेंस क्या है, और मैं इसे कैसे प्राप्त कर सकता हूं?

 A5: यदि आपको परीक्षण या मूल्यांकन उद्देश्यों के लिए अस्थायी लाइसेंस की आवश्यकता है, तो आप एक प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).