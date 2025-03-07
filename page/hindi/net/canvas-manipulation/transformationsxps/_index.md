---
title: .NET के लिए Aspose.Page के साथ XPS रूपांतरण
linktitle: परिवर्तन एक्सपीएस
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page के साथ आसानी से XPS दस्तावेज़ों को रूपांतरित करें। निर्बाध परिवर्तनों के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 13
url: /hi/net/canvas-manipulation/transformationsxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Page के साथ XPS रूपांतरण

## परिचय

.NET के लिए Aspose.Page की दुनिया में आपका स्वागत है, एक शक्तिशाली लाइब्रेरी जो आपको XPS दस्तावेज़ों पर आसानी से विभिन्न परिवर्तन करने में सक्षम बनाती है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.Page का उपयोग करके XPS दस्तावेज़ों को बदलने की प्रक्रिया के बारे में जानेंगे। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, यह मार्गदर्शिका आपको प्रत्येक चरण में ले जाएगी, यह सुनिश्चित करते हुए कि आप अवधारणाओं को आसानी से समझ सकें।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित स्थान हैं:

-  .NET लाइब्रेरी के लिए Aspose.Page: लाइब्रेरी को यहां से डाउनलोड और इंस्टॉल करें[.NET दस्तावेज़ीकरण के लिए Aspose.Page](https://reference.aspose.com/page/net/).

- विकास वातावरण: एक संगत विकास वातावरण स्थापित करें, जैसे विज़ुअल स्टूडियो या कोई अन्य .NET विकास उपकरण।

- आपकी दस्तावेज़ निर्देशिका: कोड में प्लेसहोल्डर को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से बदलें।

अब, चलिए ट्यूटोरियल पर चलते हैं!

## नामस्थान आयात करें

सबसे पहले, सुनिश्चित करें कि आप अपने कोड में .NET कार्यात्मकताओं के लिए Aspose.Page उपलब्ध कराने के लिए आवश्यक नामस्थान आयात करें। अपनी स्क्रिप्ट की शुरुआत में निम्नलिखित नामस्थान जोड़ें:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## चरण 1: एक नया XPS दस्तावेज़ बनाएँ

```csharp
// एक्सस्टार्ट:1
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";

// नया XPS दस्तावेज़ बनाएं
XpsDocument doc = new XpsDocument();
```

## चरण 2: एक मुख्य कैनवास बनाएं

```csharp
// मुख्य कैनवास बनाएं, जो सभी पृष्ठ तत्वों के लिए सामान्य हो
XpsCanvas canvas1 = doc.AddCanvas();

// मुख्य कैनवास में बाएँ और शीर्ष ऑफ़सेट बनाएँ
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## चरण 3: एक आयत पथ ज्यामिति बनाएं

```csharp
// आयत पथ ज्यामिति बनाएं
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## चरण 4: आयतों के लिए भरण जोड़ें

```csharp
// आयतों के लिए भरण बनाएँ
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## चरण 5: परिवर्तनों के बिना एक नया कैनवास जोड़ें

```csharp
// मुख्य कैनवास में बिना किसी बदलाव के नया कैनवास जोड़ें
XpsCanvas canvas2 = canvas1.AddCanvas();

// इस कैनवास में आयत बनाएं और इसे भरें
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## चरण 6: अनुवाद परिवर्तन के साथ एक नया कैनवास जोड़ें

```csharp
// मुख्य कैनवास में अनुवाद परिवर्तन के साथ नया कैनवास जोड़ें
XpsCanvas canvas3 = canvas1.AddCanvas();

// पिछले आयत के नीचे एक नया आयत रखने के लिए इस कैनवास का अनुवाद करें
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// इस कैनवास का अनुवाद पृष्ठ के दाईं ओर करें
canvas3.RenderTransform.Translate(500, 0);

// इस कैनवास में आयत बनाएं और इसे भरें
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## चरण 7: डबल स्केल परिवर्तन के साथ एक नया कैनवास जोड़ें

```csharp
//मुख्य कैनवास में दोहरे पैमाने के परिवर्तन के साथ नया कैनवास जोड़ें
XpsCanvas canvas4 = canvas1.AddCanvas();

// पिछले आयत के नीचे एक नया आयत रखने के लिए इस कैनवास का अनुवाद करें
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// इस कैनवास को स्केल करें
canvas4.RenderTransform.Scale(2, 2);

// इस कैनवास में आयत बनाएं और इसे भरें
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## चरण 8: एक बिंदु परिवर्तन के चारों ओर घूर्णन के साथ एक नया कैनवास जोड़ें

```csharp
// मुख्य कैनवास में एक बिंदु परिवर्तन के चारों ओर घूर्णन के साथ नया कैनवास जोड़ें
XpsCanvas canvas5 = canvas1.AddCanvas();

// पिछले आयत के नीचे एक नया आयत रखने के लिए इस कैनवास का अनुवाद करें
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// इस कैनवास को एक बिंदु के चारों ओर 45 डिग्री पर घुमाएँ
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// इस कैनवास में आयत बनाएं और इसे भरें
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## चरण 9: परिणामी XPS दस्तावेज़ सहेजें

```csharp
// परिणामी XPS दस्तावेज़ सहेजें
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके एक XPS दस्तावेज़ को सफलतापूर्वक रूपांतरित कर दिया है। इस गाइड में पूर्वापेक्षाएँ स्थापित करने से लेकर विभिन्न परिवर्तन करने तक आवश्यक कदम शामिल हैं। इन तकनीकों के साथ प्रयोग करें और अपनी परियोजनाओं में .NET के लिए Aspose.Page की पूरी क्षमता को अनलॉक करें।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या .NET के लिए Aspose.Page सभी .NET विकास परिवेशों के साथ संगत है?

A1: हाँ, .NET के लिए Aspose.Page को विज़ुअल स्टूडियो सहित विभिन्न .NET विकास परिवेशों के साथ निर्बाध रूप से काम करने के लिए डिज़ाइन किया गया है।

### Q2: मुझे .NET के लिए Aspose.Page के लिए अतिरिक्त उदाहरण और दस्तावेज़ कहां मिल सकते हैं?

 A2: पर जाएँ[.NET दस्तावेज़ीकरण के लिए Aspose.Page](https://reference.aspose.com/page/net/) व्यापक दस्तावेज़ीकरण और उदाहरणों के लिए।

### Q3: क्या मैं खरीदने से पहले .NET के लिए Aspose.Page आज़मा सकता हूँ?

 उ3: हां, आप यहां जाकर नि:शुल्क परीक्षण संस्करण का पता लगा सकते हैं[Aspose.पेज नि:शुल्क परीक्षण](https://releases.aspose.com/).

### Q4: मैं .NET के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 A4: विजिट करके अस्थायी लाइसेंस प्राप्त करें[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/).

### Q5: मैं .NET के लिए Aspose.Page कहां से खरीद सकता हूं?

 A5: .NET के लिए Aspose.Page खरीदें[Aspose.पेज खरीदें](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
