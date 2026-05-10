---
date: 2026-03-26
description: Aspose.Page for .NET का उपयोग करके XPS दस्तावेज़ों में अपारदर्शिता मास्क
  सेट करना और कई अपारदर्शिता मास्क लागू करना सीखें।
linktitle: Set Opacity Mask in XPS Document
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET के साथ XPS दस्तावेज़ में कई अपारदर्शिता मास्क सेट करें
url: /hi/net/transparency-effects/set-opacity-mask-in-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS दस्तावेज़ में Aspose.Page for .NET के साथ कई अपारदर्शिता मास्क सेट करें

## परिचय

Opacity masks आपको किसी भी दृश्य तत्व की पारदर्शिता को नियंत्रित करने की सुविधा देते हैं, और **multiple opacity masks** का उपयोग करके आप जटिल लेयर प्रभाव प्राप्त कर सकते हैं जो आपके XPS दस्तावेज़ों को अलग बनाते हैं। इस ट्यूटोरियल में हम आपको **opacity mask सेट करने** की प्रक्रिया दिखाएंगे और कई मास्क को मिलाकर अधिक समृद्ध दृश्य परिणाम कैसे प्राप्त करें, यह प्रदर्शित करेंगे। अंत तक आप केवल कुछ C# कोड लाइनों से किसी भी XPS तत्व पर एक या अधिक opacity masks जोड़ सकेंगे।

## त्वरित उत्तर
- **What is an opacity mask?** एक बिटमैप, ग्रेडिएंट, या सॉलिड‑कलर ब्रश जो किसी आकार के लिए प्रति‑पिक्सेल पारदर्शिता निर्धारित करता है।  
- **Why use multiple opacity masks?** मास्कों को स्टैक करने से जटिल पारदर्शिता पैटर्न बनते हैं जो एकल मास्क से संभव नहीं होते।  
- **Which library supports this?** Aspose.Page for .NET XPS ग्राफ़िक्स पर अपारदर्शिता मास्क के लिए पूर्ण समर्थन प्रदान करता है।  
- **Do I need a license?** विकास के लिए मुफ्त ट्रायल काम करता है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है।  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7 समर्थित हैं।

## “multiple opacity masks” क्या है?
Multiple opacity masks वह तकनीक है जिसमें एक से अधिक मास्क—क्रमिक या परतदार रूप से—लागू किए जाते हैं, ताकि प्रत्येक मास्क अंतिम पारदर्शिता मानचित्र में योगदान दे। यह तरीका ग्रेडिएंट, टेक्सचर, या पैटर्नयुक्त पारदर्शिता बनाने में उपयोगी है, बिना जटिल इमेज एडिटिंग के।

## Aspose.Page for .NET का उपयोग करके अपारदर्शिता मास्क सेट क्यों करें?
- **Full XPS feature set** – सभी XPS ग्राफ़िक्स क्षमताएँ एक साफ़ .NET API के माध्यम से उपलब्ध हैं।  
- **No external dependencies** – XPS ऑब्जेक्ट्स के साथ सीधे काम करें; अतिरिक्त इमेजिंग लाइब्रेरी की आवश्यकता नहीं।  
- **Performance‑optimized** – बड़े दस्तावेज़ और उच्च‑रिज़ॉल्यूशन मास्क को कुशलता से संभालता है।  

## पूर्वापेक्षाएँ

ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित उपलब्ध हों:

- Aspose.Page for .NET: सुनिश्चित करें कि आपके पास लाइब्रेरी स्थापित है। यदि नहीं, तो आप इसे [website](https://releases.aspose.com/page/net/) से डाउनलोड कर सकते हैं।  
- Document Directory: अपने XPS दस्तावेज़ों को संग्रहीत करने के लिए एक डायरेक्टरी सेट अप करें।

## नेमस्पेस आयात करें

अपने .NET प्रोजेक्ट में, आवश्यक नेमस्पेस आयात करके शुरू करें:

```csharp
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using Aspose.Page.Xps.XpsModel.Shapes;
using Aspose.Page.Xps.XpsModel.Text;
using System.Drawing;
```

## चरण 1: नया XPS दस्तावेज़ बनाएं

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Aspose.Page for .NET का उपयोग करके एक नया XPS दस्तावेज़ बनाकर शुरू करें।

## चरण 2: XpsDocument इंस्टेंस में कैनवास जोड़ें

```csharp
// Add Canvas to XpsDocument instance
XpsCanvas canvas = doc.AddCanvas();
```

अब, XPS दस्तावेज़ में एक कैनवास जोड़ें। यह कैनवास विभिन्न ग्राफ़िकल तत्वों के लिए कंटेनर के रूप में कार्य करेगा।

## चरण 3: अपारदर्शिता मास्क के साथ आयत जोड़ें

```csharp
// Rectangle with opacity masked by ImageBrush
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.OpacityMask = doc.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)path.OpacityMask).TileMode = XpsTileMode.Tile;
```

कैनवास में एक आयत जोड़ें और उसकी पारदर्शिता `OpacityMask` प्रॉपर्टी से सेट करें। इस उदाहरण में हम अपारदर्शिता मास्क के रूप में एक इमेज का उपयोग कर रहे हैं। आप समान आकार पर **multiple opacity masks** लागू करने के लिए अलग ब्रश के साथ इस चरण को दोहरा सकते हैं, जिससे परतदार पारदर्शिता प्रभाव प्राप्त होगा।

## चरण 4: परिणामी XPS दस्तावेज़ सहेजें

```csharp
// Save resultant XPS document
doc.Save(dataDir + "OpacityMask_out.xps");
```

अंत में, लागू किए गए अपारदर्शिता मास्क के साथ संशोधित XPS दस्तावेज़ को सहेजें।

## कई अपारदर्शिता मास्क के सामान्य उपयोग केस
- **Watermarking** – टेक्स्ट मास्क को पैटर्न मास्क के साथ मिलाकर अर्ध‑पारदर्शी वॉटरमार्क बनाएं।  
- **Thematic maps** – रास्टर इमेज के ऊपर ग्रेडिएंट मास्क ओवरले करके विशिष्ट क्षेत्रों को उजागर करें।  
- **Branding** – लोगो इमेज मास्क को रंग‑ग्रेडिएंट मास्क के साथ उपयोग करके परिष्कृत ब्रांडिंग तत्व बनाएं।

## समस्या निवारण और टिप्स
- **Mask alignment** – स्रोत आयत के आयाम लक्ष्य आकार से मेल खाते हों, ताकि खिंचाव न हो।  
- **TileMode** – `XpsTileMode.Tile` या `XpsTileMode.None` के साथ प्रयोग करें ताकि मास्क की पुनरावृत्ति नियंत्रित हो सके।  
- **Performance** – एक ही मास्क को कई तत्वों पर लागू करते समय `XpsImageBrush` इंस्टेंसेस को पुन: उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं आयतों के अलावा अन्य आकारों पर अपारदर्शिता मास्क लागू कर सकता हूँ?
**A1:** हाँ, Aspose.Page for .NET आपको विभिन्न आकारों, जैसे सर्कल, पॉलीगॉन और कस्टम पाथ पर अपारदर्शिता मास्क लागू करने की अनुमति देता है।

### Q2: क्या अपारदर्शिता मास्क केवल इमेज तक सीमित है?
**A2:** नहीं, जबकि इस ट्यूटोरियल में इमेज को अपारदर्शिता मास्क के रूप में उपयोग किया गया है, आप सॉलिड रंग, ग्रेडिएंट या यहाँ तक कि पैटर्न भी उपयोग कर सकते हैं।

### Q3: क्या अपारदर्शिता स्तरों को सूक्ष्म‑समायोजन के लिए उन्नत विकल्प उपलब्ध हैं?
**A3:** बिल्कुल, Aspose.Page for .NET अपारदर्शिता सेटिंग्स पर विस्तृत नियंत्रण प्रदान करता है, जिससे आप सटीक पारदर्शिता प्रभाव प्राप्त कर सकते हैं।

### Q4: क्या मैं एक ही तत्व पर कई अपारदर्शिता मास्क लागू कर सकता हूँ?
**A4:** हाँ, आप कई अपारदर्शिता मास्क को परत करके जटिल पारदर्शिता प्रभाव बना सकते हैं।

### Q5: क्या Aspose.Page अन्य दस्तावेज़ फ़ॉर्मेट्स के साथ संगत है?
**A5:** Aspose.Page मुख्यतः XPS दस्तावेज़ों पर केंद्रित है, लेकिन Aspose विभिन्न फ़ॉर्मेट्स को संभालने के लिए कई उत्पाद प्रदान करता है।

**अतिरिक्त प्रश्न**

**Q: मैं एक ही आकार पर दो अलग-अलग मास्क कैसे संयोजित करूँ?**  
**A:** दो `XpsImageBrush` (या ग्रेडिएंट ब्रश) ऑब्जेक्ट बनाएं, एक को `OpacityMask` में असाइन करें, फिर आकार को `XpsCanvas` में रैप करें और दूसरे मास्क को सीधे कैनवास पर लागू करें।

**Q: क्या API एनीमेटेड अपारदर्शिता परिवर्तन का समर्थन करता है?**  
**A:** जबकि XPS स्वयं एनीमेशन का समर्थन नहीं करता, आप विभिन्न मास्क अपारदर्शिता वाले XPS पेजों की श्रृंखला उत्पन्न करके एनीमेशन का अनुकरण कर सकते हैं।

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.Page for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}