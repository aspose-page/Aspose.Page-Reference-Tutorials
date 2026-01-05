---
date: 2026-01-05
description: Aspose.Page for .NET के साथ XPS दस्तावेज़ों को आसानी से बदलना सीखें।
  सहज परिवर्तन के लिए हमारे चरण‑दर‑चरण मार्गदर्शिका का पालन करें।
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET के साथ XPS को कैसे ट्रांसफ़ॉर्म करें
url: /hi/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET के साथ XPS को कैसे ट्रांसफ़ॉर्म करें

## परिचय

Aspose.Page for .NET की दुनिया में आपका स्वागत है, एक शक्तिशाली लाइब्रेरी जो आपको XPS दस्तावेज़ों पर विभिन्न ट्रांसफ़ॉर्मेशन आसानी से करने में सक्षम बनाती है। **इस ट्यूटोरियल में, आप सीखेंगे कि Aspose.Page for .NET का उपयोग करके XPS दस्तावेज़ों को कैसे ट्रांसफ़ॉर्म किया जाता है**, चाहे आप अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों। हम प्रत्येक चरण को विस्तार से बताएँगे, हर ट्रांसफ़ॉर्मेशन के पीछे का कारण समझाएँगे, और आपको व्यावहारिक टिप्स देंगे जिन्हें आप वास्तविक प्रोजेक्ट्स में लागू कर सकते हैं।

## त्वरित उत्तर
- **आप क्या हासिल कर सकते हैं?** XPS कैनवास तत्वों को प्रोग्रामेटिकली बनाना, ट्रांसलेट करना, स्केल करना और रोटेट करना।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for .NET (नवीनतम संस्करण)।  
- **क्या लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल काम करता है; प्रोडक्शन के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **समर्थित प्लेटफ़ॉर्म?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** यहाँ दिखाए गए बेसिक ट्रांसफ़ॉर्मेशन के लिए लगभग 10‑15 मिनट।

## “how to transform xps” क्या है?
वाक्यांश *how to transform xps* का अर्थ है XPS (XML Paper Specification) दस्तावेज़ के भीतर तत्वों के लेआउट, आकार और अभिविन्यास को प्रोग्रामेटिकली बदलना। Aspose.Page का उपयोग करके आप मैट्रिक्स‑आधारित ट्रांसफ़ॉर्मेशन को कैनवास पर लागू कर सकते हैं, जिससे आप पोजिशनिंग, स्केलिंग और रोटेशन पर सूक्ष्म नियंत्रण प्राप्त करते हैं, बिना XPS XML को मैन्युअली एडिट किए।

## XPS ट्रांसफ़ॉर्मेशन के लिए Aspose.Page क्यों उपयोग करें?
- **पूर्ण .NET इंटीग्रेशन** – Visual Studio, Rider और अन्य IDEs के साथ सहजता से काम करता है।  
- **कोई बाहरी डिपेंडेंसी नहीं** – API सभी लो‑लेवल XPS विवरणों को आपके लिए संभालता है।  
- **समृद्ध ट्रांसफ़ॉर्मेशन सपोर्ट** – ट्रांसलेट, स्केल, रोटेट, और एक ही कॉल में कई ट्रांसफ़ॉर्म को संयोजित करें।  
- **परफ़ॉर्मेंस‑ऑप्टिमाइज़्ड** – रीयल‑टाइम में रिपोर्ट, इनवॉइस या किसी भी प्रिंटेबल ग्राफ़िक्स को जनरेट करने के लिए उपयुक्त।

## पूर्वापेक्षाएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- **Aspose.Page for .NET लाइब्रेरी** – इसे आधिकारिक दस्तावेज़ से डाउनलोड और इंस्टॉल करें: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **डेवलपमेंट एनवायरनमेंट** – Visual Studio, Visual Studio Code, या कोई भी .NET‑संगत IDE।  
- **डॉक्यूमेंट डायरेक्टरी** – आपके मशीन पर एक फ़ोल्डर जहाँ आप XPS फ़ाइलें पढ़ेंगे/लिखेंगे। कोड में प्लेसहोल्डर को वास्तविक पाथ से बदलें।

अब जब सब सेट है, चलिए कोड में डुबकी लगाते हैं।

## नेमस्पेस इम्पोर्ट करें

पहले, उन नेमस्पेस को इम्पोर्ट करें जो आवश्यक Aspose.Page क्लासेज़ को एक्सपोज़ करते हैं:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## XPS को ट्रांसफ़ॉर्म करने के चरण‑दर‑चरण गाइड

### चरण 1: नया XPS डॉक्यूमेंट बनाएं

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*व्याख्या*: हम पहले उस फ़ोल्डर को परिभाषित करते हैं जहाँ हमारे स्रोत और आउटपुट फ़ाइलें हैं, फिर एक खाली `XpsDocument` का इंस्टेंस बनाते हैं। यह ऑब्जेक्ट सभी आगे के ट्रांसफ़ॉर्मेशन के लिए कैनवास होगा।

### चरण 2: मुख्य कैनवास बनाएं

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*क्यों महत्वपूर्ण है*: मुख्य कैनवास सभी अन्य कैनवास का कंटेनर बनता है। एक छोटा ऑफ़सेट लागू करके हम सुनिश्चित करते हैं कि कंटेंट पेज के किनारे पर क्लिप न हो।

### चरण 3: एक रेक्टैंगल पाथ जियोमेट्री बनाएं

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*टिप*: पाथ स्ट्रिंग मानक XPS पाथ सिंटैक्स (`M` मूव के लिए, `L` लाइन के लिए, `Z` क्लोज़ के लिए) का पालन करती है। आयत का आकार बदलने के लिए कॉर्डिनेट्स को समायोजित करें।

### चरण 4: रेक्टैंगल्स के लिए फ़िल जोड़ें

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*प्रो टिप*: `CreateColor` को RGB वैल्यूज़ के साथ उपयोग करके अपने ब्रांड पैलेट से मेल खाने वाला रंग बनाएं।

### चरण 5: बिना ट्रांसफ़ॉर्मेशन के नया कैनवास जोड़ें

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

यहाँ हम केवल एक आयत को पेज पर बिना किसी अतिरिक्त ट्रांसफ़ॉर्मेशन के रख रहे हैं—बेसलाइन एलिमेंट के रूप में उपयोगी।

### चरण 6: ट्रांसलेट ट्रांसफ़ॉर्मेशन के साथ नया कैनवास जोड़ें

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*क्या हो रहा है?* पहला मैट्रिक्स आयत को 200 यूनिट नीचे ले जाता है। बाद का `Translate` कॉल इसे 500 यूनिट दाएँ शिफ्ट करता है, जिससे दिखता है कि कई ट्रांसलेशन को कैसे चेन किया जा सकता है।

### चरण 7: डबल स्केल ट्रांसफ़ॉर्मेशन के साथ नया कैनवास जोड़ें

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*स्केल क्यों?* 2 से स्केल करने से आयत की चौड़ाई और ऊँचाई दोगुनी हो जाती है, जिससे आप जियोमेट्री को फिर से परिभाषित किए बिना बड़े ग्राफ़िक्स बना सकते हैं।

### चरण 8: पॉइंट के चारों ओर रोटेशन ट्रांसफ़ॉर्मेशन के साथ नया कैनवास जोड़ें

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*मुख्य अंतर्दृष्टि*: `RotateAround` कैनवास को एक कस्टम पॉइंट (यहाँ (100, 50)) के चारों ओर घुमाता है, जिससे रोटेशन एंकर पर सूक्ष्म नियंत्रण मिलता है।

### चरण 9: परिणामी XPS डॉक्यूमेंट सहेजें

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

सभी ट्रांसफ़ॉर्मेशन लागू होने के बाद, डॉक्यूमेंट `output1.xps` में सहेजा जाता है। किसी भी XPS व्यूअर में फ़ाइल खोलें और देखें कि स्टैक किए गए आयतों में उनके संबंधित ट्रांसलेशन, स्केलिंग और रोटेशन कैसे दिखते हैं।

## सामान्य समस्याएँ और ट्रबलशूटिंग

| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| आउटपुट फ़ाइल खाली है | `dataDir` किसी गैर‑मौजूद फ़ोल्डर की ओर इशारा कर रहा है | सुनिश्चित करें कि डायरेक्टरी मौजूद है या एक एब्सोल्यूट पाथ उपयोग करें |
| आयतें अपेक्षित स्थान पर नहीं हैं | मैट्रिक्स वैल्यूज़ गलत हैं | `Translate`, `Scale`, और `RotateAround` कॉल्स के क्रम को दोबारा जांचें |
| रंग गलत दिख रहे हैं | RGB वैल्यू 0‑255 रेंज से बाहर हैं | प्रत्येक चैनल के लिए वैध बाइट वैल्यूज़ उपयोग करें |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या Aspose.Page for .NET सभी .NET डेवलपमेंट एनवायरनमेंट्स के साथ संगत है?**  
**उत्तर:** हाँ, यह Visual Studio, Visual Studio Code, Rider और किसी भी IDE के साथ सहजता से काम करता है जो .NET को सपोर्ट करता है।

**प्रश्न: अतिरिक्त उदाहरण और विस्तृत API डॉक्यूमेंटेशन कहाँ मिल सकते हैं?**  
**उत्तर:** आधिकारिक दस्तावेज़ देखें: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**प्रश्न: क्या लाइसेंस खरीदने से पहले Aspose.Page को ट्राई कर सकता हूँ?**  
**उत्तर:** बिल्कुल। एक फ्री ट्रायल यहाँ उपलब्ध है: [Aspose.Page Free Trial](https://releases.aspose.com/).

**प्रश्न: परीक्षण के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
**उत्तर:** आप अस्थायी‑लाइसेंस पेज से एक अनुरोध कर सकते हैं: [Temporary License](https://purchase.aspose.com/temporary-license/).

**प्रश्न: पूर्ण लाइसेंस कहाँ खरीदूँ?**  
**उत्तर:** सीधे Aspose स्टोर से खरीदें: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**अंतिम अपडेट:** 2026-01-05  
**टेस्टेड विथ:** Aspose.Page 24.11 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}