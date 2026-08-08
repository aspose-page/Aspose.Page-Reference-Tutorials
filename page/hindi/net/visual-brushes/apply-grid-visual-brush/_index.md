---
date: 2026-04-03
description: Aspose.Page का उपयोग करके .NET में एक पारदर्शी आयत जोड़ना और ग्रिड विज़ुअल
  ब्रश लागू करना सीखें, जिससे शानदार XPS दस्तावेज़ बनें।
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: ग्रिड विज़ुअल ब्रश लागू करें
second_title: Aspose.Page .NET API
title: ग्रिड विज़ुअल ब्रश (.NET) का उपयोग करके पारदर्शी आयत जोड़ें
url: /hi/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ग्रिड विज़ुअल ब्रश (.NET) का उपयोग करके पारदर्शी आयत जोड़ें

## परिचय

यदि आप XPS दस्तावेज़ में **पारदर्शी आयत** जोड़ते हुए एक स्टाइलिश ग्रिड विज़ुअल ब्रश लागू करना चाहते हैं, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम Aspose.Page for .NET के साथ आवश्यक चरणों को विस्तार से बताएँगे, ताकि आप दृश्य रूप से समृद्ध दस्तावेज़ बना सकें जो अलग दिखें। अंत तक आपके पास एक पूर्ण, चलाने योग्य उदाहरण होगा जो दोनों तकनीकों को एक आसान‑से‑फ़ॉलो वर्कफ़्लो में प्रदर्शित करता है।

## त्वरित उत्तर
- **पारदर्शी आयत क्या करती है?** यह एक अर्ध‑अस्पष्ट ओवरले जोड़ती है जो पृष्ठभूमि की सामग्री को दिखने देती है।  
- **कौन सा API ब्रश बनाता है?** `XpsDocument.CreateVisualBrush` ग्रिड विज़ुअल ब्रश बनाता है।  
- **क्या मुझे लाइसेंस चाहिए?** परीक्षण के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **इम्प्लीमेंटेशन में कितना समय लगता है?** एक बुनियादी उदाहरण के लिए लगभग 10‑15 मिनट।

## XPS में पारदर्शी आयत क्या है?
पारदर्शी आयत केवल एक आकार है जिसका भराव रंग में अल्फा घटक 1.0 से कम होता है, जिससे नीचे की ग्राफ़िक्स आंशिक रूप से दिखाई देती है। यह पृष्ठभूमि को पूरी तरह से छिपाए बिना सेक्शन को हाइलाइट करने के लिए उपयुक्त है।

## ग्रिड विज़ुअल ब्रश क्यों उपयोग करें?
ग्रिड विज़ुअल ब्रश आपको एक छोटे वेक्टर ग्राफ़िक को बड़े क्षेत्र में टाइल करने देता है, जिससे ग्रिड, हैच या कस्टम टेक्सचर जैसे पैटर्न बनते हैं। इसे पारदर्शी आयत के साथ मिलाने से आपको लेयरड विज़ुअल इफ़ेक्ट मिलते हैं जो हल्के और रिज़ॉल्यूशन‑इंडिपेंडेंट होते हैं।

## आवश्यकताएँ

कोड में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास है:

- **Aspose.Page for .NET** – आप इसे [यहाँ](https://releases.aspose.com/page/net/) डाउनलोड कर सकते हैं।  
- एक .NET विकास वातावरण (Visual Studio, VS Code, या कोई भी पसंदीदा IDE)।  
- एक फ़ोल्डर जहाँ उत्पन्न XPS फ़ाइलें सहेजी जाएँगी।

## नेमस्पेसेस आयात करें

अपने C# फ़ाइल में, आवश्यक नेमस्पेसेस आयात करें:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

अब हम समाधान को स्पष्ट, क्रमांकित चरणों में विभाजित करेंगे।

## चरण 1: XpsDocument को प्रारंभ करें

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

हम एक `XpsDocument` इंस्टेंस बनाकर शुरू करते हैं, जो सभी बाद के ड्रॉइंग ऑपरेशन्स को रखेगा।

## चरण 2: मैजेंटा ग्रिड ज्योमेट्री बनाएं

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

यह ज्योमेट्री ग्रिड की रूपरेखा निर्धारित करती है जिसे विज़ुअल ब्रश भर देगा।

## चरण 3: मैजेंटा ग्रिड विज़ुअलब्रश डिजाइन करें

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

यहाँ हम एक छोटा मैजेंटा टाइल बनाते हैं जिसे ग्रिड में दोहराया जाएगा।

## चरण 4: ग्रिड पर विज़ुअलब्रश लागू करें

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

`CreateVisualBrush` कॉल मैजेंटा टाइल को ग्रिड ज्योमेट्री से जोड़ती है और टाइलिंग को सक्षम करती है।

## चरण 5: कैनवास में ग्रिड जोड़ें

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

हम टाइल्ड ग्रिड को कैनवास पर रखते हैं और एक ट्रांसलेशन ट्रांसफ़ॉर्म लागू करते हैं ताकि यह इच्छित स्थान पर दिखे।

## चरण 6: पारदर्शी आयत जोड़ें

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

इस चरण में हम **पारदर्शी आयत जोड़ते हैं** (लाल आकार जिसमें `Opacity = 0.7f` है)। आयत की पारदर्शिता को नियंत्रित करने के लिए opacity मान को समायोजित करें।

## चरण 7: दस्तावेज़ सहेजें

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

XPS फ़ाइल को उस फ़ोल्डर में लिखा जाता है जिसे आपने पहले निर्दिष्ट किया था।

## सामान्य उपयोग केस

- **रिपोर्ट हाइलाइटिंग:** चार्ट या तालिका को उजागर करने के लिए एक अर्ध‑पारदर्शी आयत ओवरले करें।  
- **वॉटरमार्क इफ़ेक्ट्स:** सूक्ष्म ब्रांडिंग के लिए टाइल्ड ग्रिड को पारदर्शी ओवरले के साथ मिलाएँ।  
- **इंटरैक्टिव PDFs/XPS:** फ़ॉर्म फ़ील्ड्स के लिए पृष्ठभूमि के रूप में पैटर्न का उपयोग करें जबकि UI पठनीय रहे।

## समस्या निवारण टिप्स

- **Opacity दिखाई नहीं दे रहा?** सुनिश्चित करें कि आपका व्यूअर XPS पारदर्शिता का समर्थन करता है; कुछ पुराने व्यूअर `Opacity` प्रॉपर्टी को अनदेखा कर सकते हैं।  
- **टाइल आकार गलत?** स्रोत आयत (`new RectangleF(0f, 0f, 10f, 10f)`) को वेक्टर टाइल के आयामों से मिलाएँ।  
- **फ़ाइल सहेजी नहीं गई?** दोबारा जाँचें कि `dataDir` एक मौजूदा, लिखने योग्य डायरेक्टरी की ओर इशारा कर रहा है।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Page for .NET को वेब और डेस्कटॉप दोनों एप्लिकेशन में उपयोग कर सकता हूँ?**  
A: हाँ, लाइब्रेरी सभी .NET एप्लिकेशन प्रकारों में काम करती है।

**Q: क्या खरीदने से पहले कोई ट्रायल संस्करण उपलब्ध है?**  
A: बिल्कुल, आप मुफ्त ट्रायल [यहाँ](https://releases.aspose.com/) एक्सेस कर सकते हैं।

**Q: अतिरिक्त समर्थन या समुदाय चर्चा कहाँ मिल सकती है?**  
A: समुदाय और Aspose इंजीनियरों से मदद के लिए [Aspose.Page फ़ोरम](https://forum.aspose.com/c/page/39) पर जाएँ।

**Q: मूल्यांकन के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A: आप अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) प्राप्त कर सकते हैं।

**Q: Aspose.Page for .NET के लिए अन्य कौन से दस्तावेज़ उपलब्ध हैं?**  
A: व्यापक दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/page/net/) देखें।

---

**अंतिम अपडेट:** 2026-04-03  
**परीक्षित संस्करण:** Aspose.Page 24.12 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}