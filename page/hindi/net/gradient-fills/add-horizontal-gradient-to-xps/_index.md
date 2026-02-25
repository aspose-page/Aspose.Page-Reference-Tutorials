---
date: 2026-02-25
description: Aspose.Page for .NET का उपयोग करके क्षैतिज भराव के साथ XPS ग्रेडिएंट
  बनाना सीखें। अपने दस्तावेज़ों में सहजता से दृश्य आकर्षण बढ़ाएँ।
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'XPS ग्रेडिएंट बनाएं: Aspose.Page for .NET के साथ क्षैतिज भराव'
url: /hi/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS ग्रेडिएंट बनाएं – Aspose.Page for .NET के साथ XPS में क्षैतिज ग्रेडिएंट जोड़ें

## परिचय

इस ट्यूटोरियल में आप **XPS ग्रेडिएंट** फ़िल्स बनाएँगे जो आपके पृष्ठों में क्षैतिज रूप से चलेंगे। क्षैतिज ग्रेडिएंट जोड़ने से XPS दस्तावेज़ तुरंत अधिक परिष्कृत और आकर्षक दिखता है, विशेष रूप से रिपोर्ट, ब्रोशर, या किसी भी दृश्य‑समृद्ध आउटपुट के लिए। हम Aspose.Page for .NET का उपयोग करके पूरी प्रक्रिया को चरण‑दर‑चरण दिखाएंगे, पर्यावरण सेटअप से लेकर अंतिम XPS फ़ाइल सहेजने तक।

## त्वरित उत्तर
- **यह ट्यूटोरियल क्या कवर करता है?** Aspose.Page for .NET के साथ XPS दस्तावेज़ में क्षैतिज ग्रेडिएंट जोड़ना।  
- **कौनसी लाइब्रेरी आवश्यक है?** Aspose.Page for .NET (कोई भी नवीनतम संस्करण)।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बेसिक ग्रेडिएंट के लिए लगभग 5–10 मिनट।  
- **क्या मैं ग्रेडिएंट दिशा बदल सकता हूँ?** हाँ – `LinearGradientBrush` के प्रारम्भ/अंत बिंदुओं को बदलें।  

## Aspose.Page for .NET के साथ XPS ग्रेडिएंट कैसे बनाएं

नीचे आप एक चरण‑दर‑चरण गाइड पाएँगे जो यह समझाता है कि प्रत्येक कोड लाइन क्यों मौजूद है, न कि केवल यह कि वह क्या करती है। आप इसे Visual Studio या अपने पसंदीदा .NET एडिटर में फॉलो कर सकते हैं।

## पूर्वापेक्षाएँ

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1. Aspose.Page for .NET लाइब्रेरी: सुनिश्चित करें कि आपके विकास पर्यावरण में Aspose.Page for .NET लाइब्रेरी स्थापित है। आप इसे [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/) से डाउनलोड कर सकते हैं।  
2. विकास पर्यावरण: एक उपयुक्त विकास पर्यावरण सेट करें, जिसमें Visual Studio जैसे कोड एडिटर शामिल हों।  

## नेमस्पेस इम्पोर्ट करें

अपने प्रोजेक्ट में आवश्यक नेमस्पेस इम्पोर्ट करके शुरू करें। ये नेमस्पेस Aspose.Page for .NET के साथ काम करने के लिए आवश्यक हैं:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

अब, हम प्रदान किए गए उदाहरण को कई चरणों में विभाजित करेंगे।

## चरण 1: दस्तावेज़ डायरेक्टरी पाथ सेट करें

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## चरण 2: नया XPS दस्तावेज़ बनाएं

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## चरण 3: ग्रेडिएंट स्टॉप्स इनिशियलाइज़ करें

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## चरण 4: नया पाथ बनाएं

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## चरण 5: परिणामी XPS दस्तावेज़ सहेजें

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

अब, आपने Aspose.Page for .NET का उपयोग करके अपने XPS दस्तावेज़ में सफलतापूर्वक क्षैतिज ग्रेडिएंट जोड़ दिया है।

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|--------|-----|
| ग्रेडिएंट एकसमान रंग दिखाता है | ग्रेडिएंट स्टॉप्स सही ढंग से नहीं जोड़े गए | सुनिश्चित करें कि `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` ब्रश सेट करने के बाद निष्पादित हो। |
| सहेजी गई फ़ाइल खाली है | `dataDir` एक गैर‑मौजूद फ़ोल्डर की ओर इशारा कर रहा है | फ़ोल्डर मौजूद है या नहीं, जांचें या पूर्ण पाथ उपयोग करें। |
| `PointF` पर संकलन त्रुटि | `System.Drawing` संदर्भ अनुपलब्ध है | `System.Drawing.Common` ( .NET Core/5+ के लिए) का संदर्भ जोड़ें। |

## अक्सर पूछे जाने वाले प्रश्न

### Q1: Aspose.Page for .NET दस्तावेज़ीकरण कहाँ मिल सकता है?

A1: आप दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/page/net/) पा सकते हैं।

### Q2: मैं Aspose.Page for .NET कैसे डाउनलोड करूँ?

A2: आप लाइब्रेरी को [Aspose.Page for .NET download page](https://releases.aspose.com/page/net/) से डाउनलोड कर सकते हैं।

### Q3: Aspose.Page for .NET कहाँ खरीद सकता हूँ?

A3: आप Aspose.Page for .NET को [purchase page](https://purchase.aspose.com/buy) से खरीद सकते हैं।

### Q4: क्या कोई मुफ्त ट्रायल उपलब्ध है?

A4: हाँ, आप [यहाँ](https://releases.aspose.com/) से एक मुफ्त ट्रायल प्राप्त कर सकते हैं।

### Q5: मैं Aspose.Page for .NET के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?

A5: आप अस्थायी लाइसेंस [इस लिंक](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं इस ग्रेडिएंट तकनीक को उन XPS दस्तावेज़ों में उपयोग कर सकता हूँ जिनमें पहले से ही इमेजेज़ हैं?**  
A: बिल्कुल। ग्रेडिएंट एक पाथ लेयर पर लागू किया जाता है, इसलिए मौजूदा इमेजेज़ अपरिवर्तित रहती हैं।

**Q: क्या वर्टिकल ग्रेडिएंट बनाना संभव है?**  
A: हाँ। `LinearGradientBrush` के प्रारम्भ और अंत बिंदुओं को अलग Y‑कोऑर्डिनेट्स के साथ बदलें, जबकि X स्थिर रखें।

**Q: क्या Aspose.Page .NET Core को सपोर्ट करता है?**  
A: यह लाइब्रेरी .NET Core, .NET 5 और बाद के संस्करणों के साथ पूरी तरह संगत है।

**Q: मैं एक ही ग्रेडिएंट को कई पृष्ठों पर कैसे पुन: उपयोग कर सकता हूँ?**  
A: `XpsLinearGradientBrush` को एक बार बनाएं, एक वेरिएबल में रखें, और प्रत्येक पृष्ठ पर पाथ्स को असाइन करें।

## निष्कर्ष

ग्रेडिएंट के साथ अपने XPS दस्तावेज़ों को बेहतर बनाना न केवल दृश्य आकर्षण बढ़ाता है बल्कि अधिक आकर्षक उपयोगकर्ता अनुभव भी प्रदान करता है। Aspose.Page for .NET के साथ, आप **XPS ग्रेडिएंट** फ़िल्स को तेज़ी और विश्वसनीयता से बना सकते हैं, जिससे आपके रिपोर्ट, ब्रोशर, या ई‑बुक्स को पेशेवर चमक मिलती है।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2026-02-25  
**परीक्षण किया गया:** Aspose.Page for .NET 24.11  
**लेखक:** Aspose  

---