---
title: .NET के लिए Aspose.Page के साथ XPS में वर्टिकल ग्रेडिएंट जोड़ें
linktitle: XPS में वर्टिकल ग्रेडिएंट जोड़ें
second_title: Aspose.Page .NET API
description: जानें कि .NET के लिए Aspose.Page का उपयोग करके वर्टिकल ग्रेडिएंट्स के साथ XPS दस्तावेज़ों को कैसे बढ़ाया जाए। निर्बाध एकीकरण के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 15
url: /hi/net/gradient-fills/add-vertical-gradient-to-xps/
---
## परिचय

.NET के लिए Aspose.Page का उपयोग करके XPS दस्तावेज़ में वर्टिकल ग्रेडिएंट कैसे जोड़ें, इस चरण-दर-चरण ट्यूटोरियल में आपका स्वागत है। Aspose.Page एक शक्तिशाली API है जो आपको अपने .NET अनुप्रयोगों में XPS (XML पेपर विशिष्टता) फ़ाइलों के साथ काम करने की अनुमति देता है। इस ट्यूटोरियल में, हम आपको एक नया XPS दस्तावेज़ बनाने, पथ में लंबवत ग्रेडिएंट जोड़ने और परिणाम को सहेजने की प्रक्रिया में मार्गदर्शन करेंगे।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

-  .NET लाइब्रेरी के लिए Aspose.Page: सुनिश्चित करें कि आपके विकास परिवेश में .NET लाइब्रेरी के लिए Aspose.Page स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).

- विकास परिवेश: अपने पसंदीदा IDE, जैसे विज़ुअल स्टूडियो, के साथ एक .NET विकास परिवेश स्थापित करें।

अब, आइए .NET के लिए Aspose.Page का उपयोग करके XPS दस्तावेज़ में एक वर्टिकल ग्रेडिएंट जोड़ना शुरू करें।

## नामस्थान आयात करें

अपने .NET एप्लिकेशन में, Aspose.Page कक्षाओं और विधियों तक पहुंचने के लिए आवश्यक नामस्थान शामिल करें।

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें

शुरू करने से पहले, अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करें जहाँ आप परिणामी XPS दस्तावेज़ को सहेजना चाहते हैं।

```csharp
// एक्सस्टार्ट:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## चरण 2: एक नया XPS दस्तावेज़ बनाएँ

निम्नलिखित कोड का उपयोग करके एक नया XPS दस्तावेज़ प्रारंभ करें:

```csharp
// एक्सस्टार्ट:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## चरण 3: ग्रेडिएंट स्टॉप्स को परिभाषित करें

प्रत्येक स्टॉप के लिए रंग और स्थिति निर्दिष्ट करते हुए, ग्रेडिएंट स्टॉप की एक सूची बनाएं। इस उदाहरण में, हम पांच स्टॉप के साथ एक ऊर्ध्वाधर ढाल को परिभाषित करते हैं।

```csharp
// एक्सस्टार्ट:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## चरण 4: ग्रेडिएंट के साथ एक पथ बनाएं

किसी पथ की ज्यामिति निर्दिष्ट करके उसे परिभाषित करें और उस पर एक रैखिक ग्रेडिएंट ब्रश लागू करें।

```csharp
// एक्सस्टार्ट:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## चरण 5: परिणामी XPS दस्तावेज़ सहेजें

संशोधित XPS दस्तावेज़ को अपनी निर्दिष्ट निर्देशिका में सहेजें।

```csharp
// एक्सस्टार्ट:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके XPS दस्तावेज़ में सफलतापूर्वक एक लंबवत ग्रेडिएंट जोड़ा है।

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया कि वर्टिकल ग्रेडिएंट्स के साथ XPS दस्तावेज़ों को बढ़ाने के लिए .NET के लिए Aspose.Page का लाभ कैसे उठाया जाए। Aspose.Page जटिल कार्यों को सरल बनाता है, डेवलपर्स को उनके .NET अनुप्रयोगों में XPS फ़ाइलों में हेरफेर करने का एक सहज तरीका प्रदान करता है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.Page विज़ुअल स्टूडियो 2019 के साथ संगत है?

A1: हाँ, Aspose.Page विज़ुअल स्टूडियो 2019 के साथ संगत है। सुनिश्चित करें कि आपके पास लाइब्रेरी का सही संस्करण स्थापित है।

### Q2: क्या मैं व्यावसायिक परियोजनाओं के लिए Aspose.Page का उपयोग कर सकता हूँ?

 A2: हाँ, Aspose.Page का उपयोग व्यावसायिक परियोजनाओं के लिए किया जा सकता है। मिलने जाना[यहाँ](https://purchase.aspose.com/buy) लाइसेंसिंग विकल्पों का पता लगाने के लिए।

### Q3: क्या कोई निःशुल्क परीक्षण उपलब्ध है?

 उ3: हाँ, आप Aspose.Page का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q4: मुझे Aspose.Page दस्तावेज़ कहां मिल सकता है?

 A4: दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/page/net/).

### Q5: मैं समर्थन कैसे प्राप्त कर सकता हूं या प्रश्न कैसे पूछ सकता हूं?

 A5: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक समर्थन के लिए.