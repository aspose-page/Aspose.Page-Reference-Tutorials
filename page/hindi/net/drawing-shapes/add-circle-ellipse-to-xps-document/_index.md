---
title: .NET के लिए Aspose.Page के साथ XPS दस्तावेज़ में सर्कल एलिप्स जोड़ें
linktitle: XPS दस्तावेज़ में वृत्त दीर्घवृत्त जोड़ें
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page का उपयोग करके जीवंत रेडियल ग्रेडिएंट्स के साथ XPS दस्तावेज़ों को बेहतर बनाएं। आश्चर्यजनक दृश्य प्रभावों के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 11
url: /hi/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Page के साथ XPS दस्तावेज़ में सर्कल एलिप्स जोड़ें

## परिचय

दृश्य रूप से आकर्षक XPS दस्तावेज़ बनाना विभिन्न अनुप्रयोगों में एक सामान्य आवश्यकता है। .NET के लिए Aspose.Page XPS दस्तावेज़ों में कुशलतापूर्वक हेरफेर करने के लिए सुविधाओं का एक शक्तिशाली सेट प्रदान करता है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.Page का उपयोग करके एक XPS दस्तावेज़ में एक वृत्त दीर्घवृत्त जोड़ने पर ध्यान केंद्रित करेंगे। अपने XPS दस्तावेज़ों को जीवंत रेडियल ग्रेडिएंट्स के साथ बेहतर बनाने के लिए नीचे दिए गए चरणों का पालन करें।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET लाइब्रेरी के लिए Aspose.Page स्थापित किया गया। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).
- एक विकास वातावरण, अधिमानतः विज़ुअल स्टूडियो या कोई अन्य .NET विकास उपकरण।
- सी# प्रोग्रामिंग का बुनियादी ज्ञान।

## नामस्थान आयात करें

आरंभ करने के लिए, अपने C# कोड में आवश्यक नामस्थान शामिल करें:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

अब, आइए उदाहरण को कई चरणों में विभाजित करें:

## चरण 1: दस्तावेज़ सेट करें

```csharp
// एक्सस्टार्ट:1
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
// नया XPS दस्तावेज़ बनाएं
XpsDocument doc = new XpsDocument();
```

यहां, हम .NET के लिए Aspose.Page का उपयोग करके एक नया XPS दस्तावेज़ प्रारंभ करते हैं।

## चरण 2: रेडियल ग्रेडिएंट एलिप्स को परिभाषित करें

```csharp
// निचले बाएँ में रेडियल ग्रेडिएंट स्ट्रोक दीर्घवृत्त
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

इस चरण में विभिन्न रंग स्टॉप के साथ रेडियल ग्रेडिएंट दीर्घवृत्त को परिभाषित करना शामिल है।

## चरण 3: रेडियल ग्रेडिएंट ब्रश सेट करें

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

यहां, हम एलिप्स के स्ट्रोक को रेडियल ग्रेडिएंट ब्रश पर सेट करते हैं, इसे आवश्यक पैरामीटर प्रदान करते हैं।

## चरण 4: स्ट्रोक की मोटाई समायोजित करें

```csharp
path.StrokeThickness = 12f;
```

इस चरण में बेहतर विज़ुअलाइज़ेशन के लिए स्ट्रोक की मोटाई को समायोजित करना शामिल है।

## चरण 5: परिणामी XPS दस्तावेज़ सहेजें

```csharp
// परिणामी XPS दस्तावेज़ सहेजें
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// ExEnd:1
```

अंत में, संशोधित XPS दस्तावेज़ को वांछित स्थान पर सहेजें।

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके अपने XPS दस्तावेज़ में रेडियल ग्रेडिएंट्स के साथ एक वृत्त दीर्घवृत्त सफलतापूर्वक जोड़ा है। अपने दस्तावेज़ों में वांछित दृश्य प्रभाव प्राप्त करने के लिए विभिन्न मापदंडों और रंगों के साथ प्रयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं अन्य दस्तावेज़ प्रारूपों के साथ .NET के लिए Aspose.Page का उपयोग कर सकता हूँ?

A1: .NET के लिए Aspose.Page विशेष रूप से XPS दस्तावेज़ हेरफेर से संबंधित है। अन्य प्रारूपों के लिए, संबंधित Aspose लाइब्रेरीज़ का उपयोग करने पर विचार करें।

### Q2: क्या परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस उपलब्ध है?

 उ2: हां, आप यहां जाकर परीक्षण के लिए अस्थायी लाइसेंस प्राप्त कर सकते हैं[इस लिंक](https://purchase.aspose.com/temporary-license/).

### Q3: मुझे अतिरिक्त सहायता और चर्चाएँ कहाँ मिल सकती हैं?

 A3: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक समर्थन और चर्चा के लिए।

### Q4: क्या संदर्भ के लिए कोई नमूना दस्तावेज़ उपलब्ध हैं?

 ए4: अन्वेषण करें[प्रलेखन](https://reference.aspose.com/page/net/) व्यापक उदाहरणों और दिशानिर्देशों के लिए।

### Q5: क्या मैं .NET के लिए Aspose.Page खरीद सकता हूँ?

 A5: हाँ, आप लाइब्रेरी खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
