---
date: 2026-02-25
description: Aspose.Page for .NET के साथ XPS दस्तावेज़ बनाना और रैखिक ग्रेडिएंट लागू
  करना सीखें। XPS फ़ाइल को सहेजने के लिए हमारे चरण‑दर‑चरण गाइड का पालन करें।
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Aspose.Page का उपयोग करके वर्टिकल ग्रेडिएंट के साथ XPS दस्तावेज़ बनाएं
url: /hi/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

 line breaks.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET के साथ XPS में वर्टिकल ग्रेडिएंट जोड़ें

## Introduction

इस ट्यूटोरियल में आप **XPS दस्तावेज़ बनाएँगे** जिसमें एक सुगम वर्टिकल ग्रेडिएंट होगा। ग्रेडिएंट जोड़ना XPS फ़ाइलों को अधिक पेशेवर दिखाने का एक सामान्य तरीका है—रिपोर्ट, ब्रोशर, या किसी भी प्रिंटेबल ग्राफ़िक्स के लिए एकदम उपयुक्त। हम हर चरण को विस्तार से बताएँगे, प्रोजेक्ट सेटअप से लेकर अंतिम XPS फ़ाइल को सेव करने तक, ताकि आप किसी भी पाथ पर जल्दी से एक लीनियर ग्रेडिएंट लागू कर सकें।

## Quick Answers
- **इस ट्यूटोरियल में क्या कवर किया गया है?** XPS दस्तावेज़ में एक पाथ पर वर्टिकल लीनियर ग्रेडिएंट जोड़ना।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for .NET.  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल काम करता है; प्रोडक्शन के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बेसिक उदाहरण के लिए लगभग 10‑15 मिनट।  
- **क्या मैं परिणाम को XPS फ़ाइल के रूप में सेव कर सकता हूँ?** हाँ, `Save` मेथड फ़ाइल को डिस्क पर लिखता है।

## What is a vertical gradient in XPS?

वर्टिकल ग्रेडिएंट एक रंग परिवर्तन है जो आकार के शीर्ष से नीचे तक चलता है। XPS में, यह **linear gradient brush** के द्वारा प्राप्त किया जाता है जो प्रारंभ और अंत बिंदु निर्धारित करता है, साथ ही ग्रेडिएंट स्टॉप्स का संग्रह जो विशिष्ट स्थितियों पर रंग को नियंत्रित करता है।

## Why use Aspose.Page to create XPS document with gradients?

- **पूर्ण .NET इंटीग्रेशन** – .NET Framework, .NET Core, और .NET 5/6+ के साथ काम करता है।  
- **कोई बाहरी निर्भरताएँ नहीं** – सभी रेंडरिंग लाइब्रेरी द्वारा संभाली जाती है।  
- **उच्च फिडेलिटी** – ग्रेडिएंट्स बिल्कुल वही रेंडर होते हैं जैसा परिभाषित किया गया है, XPS स्पेसिफिकेशन से मेल खाता है।  
- **रखरखाव में आसान** – पाथ, ब्रश, और रंगों के लिए स्पष्ट ऑब्जेक्ट मॉडल।

## Prerequisites

- Aspose.Page for .NET लाइब्रेरी: सुनिश्चित करें कि आपके विकास वातावरण में Aspose.Page for .NET लाइब्रेरी स्थापित है। आप इसे [here](https://releases.aspose.com/page/net/) से डाउनलोड कर सकते हैं।  
- डेवलपमेंट एनवायरनमेंट: Visual Studio जैसे अपने पसंदीदा IDE के साथ .NET विकास वातावरण सेट अप करें।

अब जब सब तैयार है, चलिए कोड में डुबकी लगाते हैं।

## Import Namespaces

अपने .NET एप्लिकेशन में, Aspose.Page क्लासेज़ और मेथड्स तक पहुँचने के लिए आवश्यक नेमस्पेसेस शामिल करें।

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Step 1: Set Up Your Document Directory

उस फ़ोल्डर को परिभाषित करें जहाँ जनरेट की गई XPS फ़ाइल सेव होगी।

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Step 2: Create a New XPS Document

एक नई XPS दस्तावेज़ बनाएं जिसे हम बाद में ग्रेडिएंट‑फ़िल्ड पाथ से भरेंगे।

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Step 3: Define Gradient Stops

ग्रेडिएंट स्टॉप्स ग्रेडिएंट लाइन पर रंगों और उनके स्थानों को निर्धारित करते हैं। यहाँ हम पाँच स्टॉप्स बनाते हैं ताकि एक सुगम वर्टिकल ट्रांज़िशन प्राप्त हो सके।

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Step 4: Create a Path with Gradient

हम एक आयत‑आकार का पाथ बनाते हैं और एक **linear gradient brush** लागू करते हैं जो बिंदु (10, 110) से बिंदु (10, 200) तक वर्टिकली चलता है। ब्रश को पहले परिभाषित ग्रेडिएंट स्टॉप्स मिलते हैं।

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Step 5: Save the Resultant XPS Document

अंत में, XPS दस्तावेज़ को डिस्क पर लिखें। यह **save XPS file** चरण आपके द्वारा निर्दिष्ट फ़ोल्डर में `AddVerticalGradient_outXPS.xps` बनाता है।

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Pro tip:** आउटपुट को सत्यापित करने के लिए XPS फ़ाइल को Windows XPS Viewer या किसी भी थर्ड‑पार्टी व्यूअर में खोलें ताकि यह सुनिश्चित हो सके कि ग्रेडिएंट अपेक्षित रूप से दिख रहा है।

## Common Issues & Troubleshooting

| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| ग्रेडिएंट एक सॉलिड रंग जैसा दिखता है | ग्रेडिएंट स्टॉप्स ब्रश में नहीं जोड़े गए | सुनिश्चित करें कि `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` निष्पादित हो। |
| सेव करने पर फ़ाइल नहीं मिली | `dataDir` एक गैर‑मौजूद फ़ोल्डर की ओर इशारा करता है | पहले डायरेक्टरी बनाएं या एक एब्सोल्यूट पाथ उपयोग करें। |
| रंग अलग दिख रहे हैं | रंग मान ARGB क्रम में हैं; चैनल क्रम सत्यापित करें | `CreateColor(alpha, red, green, blue)` को सही तरीके से उपयोग करें। |

## Frequently Asked Questions

**Q: क्या Aspose.Page Visual Studio 2019 के साथ संगत है?**  
A: हाँ, Aspose.Page Visual Studio 2019 के साथ संगत है। सुनिश्चित करें कि आपके पास लाइब्रेरी का सही संस्करण स्थापित है।

**Q: क्या मैं Aspose.Page को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.Page को व्यावसायिक प्रोजेक्ट्स में उपयोग किया जा सकता है। लाइसेंसिंग विकल्पों को देखना के लिए [here](https://purchase.aspose.com/buy) पर जाएँ।

**Q: क्या फ्री ट्रायल उपलब्ध है?**  
A: हाँ, आप Aspose.Page का फ्री ट्रायल [here](https://releases.aspose.com/) से प्राप्त कर सकते हैं।

**Q: मैं Aspose.Page दस्तावेज़ीकरण कहाँ पा सकता हूँ?**  
A: दस्तावेज़ीकरण [here](https://reference.aspose.com/page/net/) पर उपलब्ध है।

**Q: मैं सपोर्ट कैसे प्राप्त करूँ या प्रश्न पूछूँ?**  
A: कम्युनिटी सपोर्ट के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) पर जाएँ।

## Conclusion

अब आप जानते हैं कि Aspose.Page for .NET का उपयोग करके **XPS दस्तावेज़ कैसे बनाएं**, **लीनियर ग्रेडिएंट कैसे लागू करें**, और **XPS फ़ाइल कैसे सेव करें**। यह तरीका आपको XPS आउटपुट में विज़ुअल स्टाइलिंग पर पूर्ण नियंत्रण देता है, जिससे आपके प्रिंटेबल दस्तावेज़ अधिक आकर्षक बनते हैं।

---  

**अंतिम अपडेट:** 2026-02-25  
**परीक्षण किया गया:** Aspose.Page for .NET 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}