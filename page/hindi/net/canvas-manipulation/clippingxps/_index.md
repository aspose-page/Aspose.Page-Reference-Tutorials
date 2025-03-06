---
title: .NET के लिए Aspose.Page के साथ XPS को क्लिप करना
linktitle: एक्सपीएस क्लिपिंग
second_title: Aspose.Page .NET API
description: XPS दस्तावेज़ों की क्लिपिंग पर इस चरण-दर-चरण मार्गदर्शिका में .NET के लिए Aspose.Page की शक्ति का अन्वेषण करें। XPS फ़ाइलें आसानी से बनाएं, हेरफेर करें और सहेजें।
weight: 11
url: /hi/net/canvas-manipulation/clippingxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Page के साथ XPS को क्लिप करना

## परिचय

.NET के लिए Aspose.Page का उपयोग करके क्लिपिंग XPS पर इस व्यापक ट्यूटोरियल में आपका स्वागत है! इस गाइड में, हम आपको .NET के लिए Aspose.Page का उपयोग करके XPS दस्तावेज़ बनाने, हेरफेर करने और सहेजने की प्रक्रिया के बारे में बताएंगे। XPS, या XML पेपर विशिष्टता, एक मानकीकृत और खुला दस्तावेज़ प्रारूप है, और .NET के लिए Aspose.Page आपके .NET अनुप्रयोगों में XPS दस्तावेज़ों के साथ काम करने के लिए शक्तिशाली उपकरण प्रदान करता है।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

- आपकी मशीन पर विज़ुअल स्टूडियो स्थापित है।
-  .NET लाइब्रेरी के लिए Aspose.Page आपके प्रोजेक्ट में जोड़ा गया। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).
- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।

## नामस्थान आयात करें

.NET कार्यात्मकताओं के लिए Aspose.Page का उपयोग करने के लिए, आपको अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करने की आवश्यकता है। इन चरणों का पालन करें:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

अब, आइए आपके द्वारा प्रदान किए गए उदाहरण कोड को कई चरणों में तोड़ें।

## चरण 1: दस्तावेज़ निर्देशिका पथ सेट करें।

```csharp
string dataDir = "Your Document Directory";
```

"आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से बदलना सुनिश्चित करें।

## चरण 2: एक नया XPS दस्तावेज़ बनाएँ।

```csharp
XpsDocument doc = new XpsDocument();
```

यह एक नया XPS दस्तावेज़ बनाता है जिसके साथ आप काम करेंगे।

## चरण 3: मुख्य कैनवास बनाएं.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

यह चरण मुख्य कैनवास बनाता है, जो सभी पृष्ठ तत्वों के लिए सामान्य है।

## चरण 4: मुख्य कैनवास में बाएँ और शीर्ष ऑफ़सेट सेट करें।

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

अपनी आवश्यकताओं के अनुसार बाएँ और शीर्ष ऑफसेट को समायोजित करें।

## चरण 5: एक आयताकार पथ ज्यामिति बनाएं।

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

यह एक आयत के लिए पथ ज्यामिति बनाता है।

## चरण 6: आयतों के लिए एक भराव बनाएँ।

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

आयतों के लिए भरण रंग परिभाषित करें।

## चरण 7: मुख्य कैनवास में क्लिप के साथ एक और कैनवास जोड़ें।

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

यह चरण मुख्य कैनवास में एक और कैनवास जोड़ता है।

## चरण 8: क्लिप के लिए एक वृत्त ज्यामिति बनाएं।

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

यह एक गोलाकार क्लिप ज्यामिति बनाता है और इसे दूसरे कैनवास पर लागू करता है।

## चरण 9: दूसरे कैनवास में एक आयत बनाएं और उसे भरें।

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

यह चरण दूसरे कैनवास में एक आयत बनाता है और उसे भरता है।

## चरण 10: मुख्य कैनवास में एक स्ट्रोक वाले आयत के साथ दूसरा कैनवास जोड़ें।

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

यह मुख्य कैनवास में एक और कैनवास जोड़ता है।

## चरण 11: तीसरे कैनवास में एक आयत बनाएं और उसे स्ट्रोक करें।

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

यह तीसरे कैनवास में एक आयत बनाता है और उस पर एक स्ट्रोक लगाता है।

## चरण 12: परिणामी XPS दस्तावेज़ सहेजें।

```csharp
doc.Save(dataDir + "output2.xps");
```

यह XPS दस्तावेज़ को निर्दिष्ट निर्देशिका में सहेजता है।

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके XPS को क्लिप करना सफलतापूर्वक सीख लिया है। इस गाइड ने प्रक्रिया में शामिल चरणों का विस्तृत विवरण प्रदान किया।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं अन्य दस्तावेज़ प्रारूपों के साथ .NET के लिए Aspose.Page का उपयोग कर सकता हूँ?

A1: .NET के लिए Aspose.Page मुख्य रूप से XPS दस्तावेज़ों पर केंद्रित है, लेकिन Aspose विभिन्न दस्तावेज़ प्रारूपों के लिए अन्य लाइब्रेरी प्रदान करता है।

### Q2: क्या .NET के लिए Aspose.Page शुरुआती लोगों के लिए उपयुक्त है?

A2: हां, .NET के लिए Aspose.Page को उपयोगकर्ता के अनुकूल बनाया गया है, और शुरुआती लोग उचित दस्तावेज़ीकरण के साथ इसकी कार्यक्षमता को जल्दी से समझ सकते हैं।

### Q3: मुझे और अधिक उदाहरण और संसाधन कहां मिल सकते हैं?

 A3: पर जाएँ[प्रलेखन](https://reference.aspose.com/page/net/) और[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) व्यापक संसाधनों और उदाहरणों के लिए।

### Q4: मैं .NET के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 A4: आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### Q5: क्या .NET के लिए Aspose.Page का कोई निःशुल्क परीक्षण उपलब्ध है?

 A5: हां, आप नि:शुल्क परीक्षण का लाभ उठा सकते हैं[यहाँ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
