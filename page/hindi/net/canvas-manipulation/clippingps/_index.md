---
title: .NET के लिए Aspose.Page के साथ PS को क्लिप करना
linktitle: क्लिपिंग पी.एस
second_title: Aspose.Page .NET API
description: पोस्टस्क्रिप्ट दस्तावेज़ों को क्लिप करने के इस चरण-दर-चरण ट्यूटोरियल में .NET के लिए Aspose.Page की शक्ति का अन्वेषण करें। अपनी दस्तावेज़ प्रसंस्करण क्षमताओं को सहजता से बढ़ाना सीखें।
weight: 10
url: /hi/net/canvas-manipulation/clippingps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Page के साथ PS को क्लिप करना

## परिचय

पोस्टस्क्रिप्ट (पीएस) दस्तावेज़ों में क्लिपिंग लागू करने के लिए .NET के लिए Aspose.Page का उपयोग करने पर व्यापक ट्यूटोरियल में आपका स्वागत है। यह ट्यूटोरियल आपको Aspose.Page का उपयोग करके PS दस्तावेज़ों को क्लिप करने की प्रक्रिया में मार्गदर्शन करेगा, जो .NET अनुप्रयोगों में विभिन्न दस्तावेज़ प्रारूपों के साथ काम करने के लिए एक शक्तिशाली लाइब्रेरी है।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- C# प्रोग्रामिंग भाषा का कार्यसाधक ज्ञान।
-  .NET लाइब्रेरी के लिए Aspose.Page स्थापित किया गया। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).
- एक एकीकृत विकास वातावरण (आईडीई) जैसे विजुअल स्टूडियो।

## नामस्थान आयात करें

अपने C# कोड में आवश्यक नामस्थान आयात करके प्रारंभ करें:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

अब, आइए उदाहरण को कई चरणों में विभाजित करें:

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
```

## चरण 2: पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं

```csharp
// पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

## चरण 3: सहेजें विकल्प बनाएं

```csharp
// डिफ़ॉल्ट मानों के साथ सेव विकल्प बनाएं
PsSaveOptions options = new PsSaveOptions();
```

## चरण 4: एक नया 1-पृष्ठ पीएस दस्तावेज़ बनाएँ

```csharp
// नया 1-पृष्ठ वाला PS दस्तावेज़ बनाएँ
PsDocument document = new PsDocument(outPsStream, options, false);
```

## चरण 5: आयत से ग्राफ़िक्स पथ बनाएं

```csharp
// आयत से ग्राफ़िक्स पथ बनाएं
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

## चरण 6: आकार के अनुसार क्लिपिंग

```csharp
// परिवर्तन के बाद इस स्थिति में वापस लौटने के लिए ग्राफ़िक्स स्थिति को सहेजें
document.WriteGraphicsSave();

//वर्तमान ग्राफ़िक्स स्थिति को 100 बिंदुओं पर दाईं ओर और 100 बिंदुओं को नीचे की ओर विस्थापित करें।
document.Translate(100, 100);

// वृत्त से ग्राफ़िक्स पथ बनाएं
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// मौजूदा ग्राफ़िक्स स्थिति में सर्कल के अनुसार क्लिपिंग जोड़ें
document.Clip(circlePath);

// पेंट को वर्तमान ग्राफ़िक्स स्थिति में सेट करें
document.SetPaint(new SolidBrush(Color.Blue));

// आयत को वर्तमान ग्राफ़िक्स स्थिति में भरें (क्लिपिंग के साथ)
document.Fill(rectanglePath);

// ग्राफ़िक्स स्थिति को पिछले (ऊपरी) स्तर पर पुनर्स्थापित करें
document.WriteGraphicsRestore();
```

## चरण 7: ऊपरी स्तर की ग्राफ़िक्स स्थिति को विस्थापित करें

```csharp
// ऊपरी-स्तरीय ग्राफ़िक्स स्थिति को 100 बिंदुओं पर दाईं ओर और 100 बिंदुओं को नीचे की ओर विस्थापित करें।
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// क्लिप किए गए आयत के ऊपर वर्तमान ग्राफ़िक स्थिति (कोई क्लिपिंग नहीं है) में आयत बनाएं
document.Draw(rectanglePath);
```

## चरण 8: दस्तावेज़ को बंद करें और सहेजें

```csharp
// वर्तमान पृष्ठ बंद करें
document.ClosePage();

// दस्तावेज़ सहेजें
document.Save();
```

अब, आपने .NET के लिए Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट दस्तावेज़ में क्लिपिंग को सफलतापूर्वक लागू कर दिया है।

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि पोस्टस्क्रिप्ट दस्तावेज़ों में क्लिपिंग लागू करने के लिए .NET के लिए Aspose.Page का उपयोग कैसे करें। यह शक्तिशाली लाइब्रेरी आपके .NET अनुप्रयोगों में विभिन्न दस्तावेज़ प्रारूपों को संभालने का एक सहज और कुशल तरीका प्रदान करती है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Page का उपयोग कर सकता हूँ?

A1: Aspose.Page मुख्य रूप से .NET अनुप्रयोगों के लिए डिज़ाइन किया गया है। हालाँकि, Aspose अन्य प्रोग्रामिंग भाषाओं के लिए समान लाइब्रेरी प्रदान करता है।

### Q2: मुझे .NET के लिए Aspose.Page के लिए अतिरिक्त उदाहरण और दस्तावेज़ कहां मिल सकते हैं?

 A2: आप इस पर अधिक उदाहरण और विस्तृत दस्तावेज़ देख सकते हैं[Aspose.पेज दस्तावेज़ीकरण](https://reference.aspose.com/page/net/).

### Q3: क्या .NET के लिए Aspose.Page का कोई निःशुल्क परीक्षण उपलब्ध है?

 उ3: हां, आप .NET के लिए Aspose.Page के निःशुल्क परीक्षण तक पहुंच सकते हैं[यहाँ](https://releases.aspose.com/).

### Q4: मैं .NET के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 A4: आप एक अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### Q5: मुझे Aspose.Page से संबंधित प्रश्नों के लिए सहायता कहां मिल सकती है या चर्चा कहां हो सकती है?

 A5: पर जाएँ[Aspose.पेज फ़ोरम](https://forum.aspose.com/c/page/39) सामुदायिक समर्थन और चर्चा के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
