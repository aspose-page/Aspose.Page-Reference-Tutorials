---
title: .NET के लिए Aspose.Page के साथ XPS में क्षैतिज ग्रेडिएंट जोड़ें
linktitle: XPS में क्षैतिज ग्रेडिएंट जोड़ें
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page का उपयोग करके अपने XPS दस्तावेज़ों में आश्चर्यजनक क्षैतिज ग्रेडिएंट जोड़ने का तरीका जानें। दृश्य अपील को सहजता से बढ़ाएं।
weight: 13
url: /hi/net/gradient-fills/add-horizontal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Page के साथ XPS में क्षैतिज ग्रेडिएंट जोड़ें

## परिचय

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Page का उपयोग करके एक क्षैतिज ग्रेडिएंट जोड़कर XPS दस्तावेज़ों को कैसे बढ़ाया जाए। .NET के लिए Aspose.Page एक शक्तिशाली लाइब्रेरी है जो .NET अनुप्रयोगों में XPS (XML पेपर स्पेसिफिकेशन) दस्तावेजों की निर्बाध हैंडलिंग प्रदान करती है। ग्रेडिएंट जोड़ने से आपके दस्तावेज़ों में दृश्य अपील आ सकती है, और यह मार्गदर्शिका आपको चरण दर चरण प्रक्रिया के बारे में बताएगी।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1.  .NET लाइब्रेरी के लिए Aspose.Page: सुनिश्चित करें कि आपके विकास परिवेश में .NET लाइब्रेरी के लिए Aspose.Page स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[.NET दस्तावेज़ीकरण के लिए Aspose.Page](https://reference.aspose.com/page/net/).

2. विकास वातावरण: विजुअल स्टूडियो जैसे कोड संपादक सहित एक उपयुक्त विकास वातावरण स्थापित करें।

## नामस्थान आयात करें

अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करके प्रारंभ करें। .NET के लिए Aspose.Page के साथ काम करने के लिए ये नामस्थान आवश्यक हैं:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

अब, आइए दिए गए उदाहरण को कई चरणों में तोड़ें।

## चरण 1: दस्तावेज़ निर्देशिका पथ सेट करें

```csharp
// एक्सस्टार्ट:3
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## चरण 2: एक नया XPS दस्तावेज़ बनाएँ

```csharp
// एक्सस्टार्ट:4
// नया XPS दस्तावेज़ बनाएं
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## चरण 3: ग्रेडिएंट स्टॉप आरंभ करें

```csharp
// एक्सस्टार्ट:5
// XpsGradientStop की आरंभिक सूची
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## चरण 4: एक नया पथ बनाएँ

```csharp
// एक्सस्टार्ट:6
//ज्यामिति को संक्षिप्त रूप में परिभाषित करके नया पथ बनाएँ
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## चरण 5: परिणामी XPS दस्तावेज़ सहेजें

```csharp
// एक्सस्टार्ट:7
// परिणामी XPS दस्तावेज़ सहेजें
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

अब, आपने .NET के लिए Aspose.Page का उपयोग करके अपने XPS दस्तावेज़ में एक क्षैतिज ग्रेडिएंट सफलतापूर्वक जोड़ दिया है।

## निष्कर्ष

अपने XPS दस्तावेज़ों को ग्रेडिएंट्स के साथ बढ़ाने से न केवल उनकी दृश्य अपील में सुधार होता है बल्कि अधिक आकर्षक उपयोगकर्ता अनुभव भी मिलता है। .NET के लिए Aspose.Page इस प्रक्रिया को सरल बनाता है, जिससे आप आसानी से पेशेवर परिणाम प्राप्त कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: मुझे .NET दस्तावेज़ के लिए Aspose.Page कहां मिल सकता है?

 A1: आप दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/page/net/).

### Q2: मैं .NET के लिए Aspose.Page कैसे डाउनलोड करूं?

 A2: आप लाइब्रेरी को यहां से डाउनलोड कर सकते हैं[.NET डाउनलोड पेज के लिए Aspose.Page](https://releases.aspose.com/page/net/).

### Q3: मैं .NET के लिए Aspose.Page कहां से खरीद सकता हूं?

 A3: आप .NET के लिए Aspose.Page यहां से खरीद सकते हैं[खरीद पृष्ठ](https://purchase.aspose.com/buy).

### Q4: क्या कोई निःशुल्क परीक्षण उपलब्ध है?

 उ4: हाँ, आप नि:शुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q5: मैं .NET के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त करूं?

 A5: आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[इस लिंक](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
