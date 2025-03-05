---
title: .NET के लिए Aspose.Page के साथ ग्रिड विज़ुअल ब्रश लागू करें
linktitle: ग्रिड विज़ुअल ब्रश लगाएं
second_title: Aspose.Page .NET API
description: Aspose.Page के साथ .NET में दस्तावेज़ प्रसंस्करण की गतिशील दुनिया का अन्वेषण करें। दृश्य रूप से आश्चर्यजनक दस्तावेज़ों के लिए ग्रिड विज़ुअल ब्रश का उपयोग करना सीखें।
type: docs
weight: 10
url: /hi/net/visual-brushes/apply-grid-visual-brush/
---
## परिचय

.NET विकास की दुनिया में, Aspose.Page दस्तावेज़ प्रसंस्करण कार्यों को संभालने के लिए एक शक्तिशाली उपकरण के रूप में खड़ा है। इसकी एक आकर्षक विशेषता ग्रिड विज़ुअल ब्रश लगाने की क्षमता है, जो आपके दस्तावेज़ों में एक नया आयाम लाती है। यह ट्यूटोरियल आपको .NET के लिए Aspose.Page का उपयोग करके चरण दर चरण मैजेंटा ग्रिड विज़ुअल ब्रश को लागू करने की प्रक्रिया में मार्गदर्शन करेगा।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

-  .NET के लिए Aspose.Page: सुनिश्चित करें कि आपके पास अपने .NET वातावरण में लाइब्रेरी स्थापित और सेटअप है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).

- विकास परिवेश: एक कार्यशील .NET विकास परिवेश तैयार रखें और C# प्रोग्रामिंग की बुनियादी समझ रखें।

- दस्तावेज़ निर्देशिका: अपने दस्तावेज़ों के लिए एक निर्देशिका बनाएं जहां संसाधित फ़ाइलें सहेजी जाएंगी।

## नामस्थान आयात करें

अपने C# कोड में, आपको Aspose.Page सुविधाओं का प्रभावी ढंग से उपयोग करने के लिए आवश्यक नामस्थान आयात करने की आवश्यकता है:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

अब, आइए उदाहरण को कई चरणों में विभाजित करें।

## चरण 1: XpsDocument प्रारंभ करें

```csharp
// एक्सस्टार्ट:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

 यहां, हम इसका एक उदाहरण बनाते हैं`XpsDocument` एक्सपीएस दस्तावेजों के साथ काम करने के लिए।

## चरण 2: मैजेंटा ग्रिड ज्योमेट्री बनाएं

```csharp
// एक्सस्टार्ट:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

इस चरण में मैजेंटा ग्रिड के लिए पथ ज्यामिति बनाना शामिल है।

## चरण 3: मैजेंटा ग्रिड विज़ुअलब्रश डिज़ाइन करें

```csharp
// एक्सस्टार्ट:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

यहां, हम वेक्टर ग्राफिक्स का उपयोग करके मैजेंटा ग्रिड के दृश्य पहलू को डिज़ाइन करते हैं।

## चरण 4: विजुअलब्रश को ग्रिड पर लागू करें

```csharp
// एक्सस्टार्ट:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

विजुअल ब्रश को ग्रिड पथ पर लागू करें, यह सुनिश्चित करते हुए कि उसकी टाइलें उचित रूप से लगी हुई हैं।

## चरण 5: कैनवास में ग्रिड जोड़ें

```csharp
// एक्सस्टार्ट:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

किसी भी आवश्यक परिवर्तन को निर्दिष्ट करते हुए, कैनवास में ग्रिड जोड़ें।

## चरण 6: लाल आयत के साथ सुधारें

```csharp
// एक्सस्टार्ट:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f;
// ExEnd:8
```

एक लाल पारदर्शी आयत जोड़कर दृश्य अपील बढ़ाएँ।

## चरण 7: दस्तावेज़ सहेजें

```csharp
// एक्सस्टार्ट:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

परिणामी XPS दस्तावेज़ को अपनी निर्दिष्ट निर्देशिका में सहेजें।

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके अपने दस्तावेज़ में ग्रिड विज़ुअल ब्रश सफलतापूर्वक लागू कर लिया है। यह तकनीक आपके दस्तावेज़ों के दृश्य तत्वों को महत्वपूर्ण रूप से बढ़ा सकती है, एक गतिशील और आकर्षक उपयोगकर्ता अनुभव प्रदान कर सकती है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं वेब और डेस्कटॉप दोनों अनुप्रयोगों में .NET के लिए Aspose.Page का उपयोग कर सकता हूँ?

A1: हां, .NET के लिए Aspose.Page बहुमुखी है और इसका उपयोग विभिन्न एप्लिकेशन प्रकारों में किया जा सकता है।

### Q2: क्या खरीदने से पहले कोई परीक्षण संस्करण उपलब्ध है?

 उ2: बिल्कुल, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q3: मुझे अतिरिक्त सहायता या सामुदायिक चर्चाएँ कहाँ मिल सकती हैं?

 A3: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) चर्चा और समर्थन के लिए.

### Q4: मैं .NET के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 उ4: आप एक अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### Q5: .NET के लिए Aspose.Page के लिए अन्य कौन से दस्तावेज़ उपलब्ध हैं?

 A5: व्यापक दस्तावेज़ीकरण का अन्वेषण करें[यहाँ](https://reference.aspose.com/page/net/).