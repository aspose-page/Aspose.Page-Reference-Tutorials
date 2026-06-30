---
date: 2026-06-30
description: सीखें कि कैसे XPS document .NET बनाएं और Aspose.Page for .NET का उपयोग
  करके कुछ आसान चरणों में image‑filled glyphs या foreign images जोड़ें।
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Image Filled Glyph और Foreign Image जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: XPS Document .NET बनाएं – Aspose.Page के साथ Image Filled Glyph और Foreign
  Image जोड़ें
url: /hi/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS दस्तावेज़ .NET बनाएं – इमेज‑भरा ग्लिफ़ और विदेशी इमेज जोड़ें Aspose.Page के साथ

## परिचय

.NET विकास में, **create XPS document .NET** कार्य आम हैं जब आपको उच्च‑गुणवत्ता, रिज़ॉल्यूशन‑स्वतंत्र ग्राफ़िक्स की आवश्यकता होती है। Aspose.Page for .NET इसे सरल बनाता है और आपको XPS फ़ाइलों को इमेज‑भरे ग्लिफ़ से समृद्ध करने या किसी अन्य XPS दस्तावेज़ से इमेज खींचने की अनुमति देता है। इस ट्यूटोरियल के अंत तक आप दो XPS दस्तावेज़ बनाना, ग्लिफ़ को इमेज से भरना, और उन इमेज को दस्तावेज़ों के बीच पुनः उपयोग करना सीखेंगे—इनवॉइस, प्रमाणपत्र, या किसी भी विज़ुअल‑रिच आउटपुट के निर्माण के लिए उपयुक्त।

## त्वरित उत्तर
- **Aspose.Page क्या समर्थन करता है?** 25 से अधिक इमेज फ़ॉर्मेट और 500 MB तक के XPS फ़ाइलों को पूरी मेमोरी लोड किए बिना प्रोसेस करने की क्षमता।  
- **इमेज‑भरे ग्लिफ़ को जोड़ने के लिए कितनी कोड लाइनों की आवश्यकता है?** केवल दो लाइनें: एक `ImageBrush` बनाएं और उसे `Glyph` को असाइन करें।  
- **उत्पादन के लिए लाइसेंस की आवश्यकता है?** हाँ, एक व्यावसायिक लाइसेंस मूल्यांकन वॉटरमार्क को हटाता है।  
- **कौन से .NET संस्करण संगत हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7।  
- **क्या मैं किसी अन्य XPS से फ़ॉन्ट पुनः उपयोग कर सकता हूँ?** बिल्कुल – आप पहले दस्तावेज़ से फ़ॉन्ट संग्रह को दूसरे में आयात कर सकते हैं।

## Aspose.Page .NET का उपयोग करके XPS दस्तावेज़ कैसे बनाते हैं?

Aspose.Page लाइब्रेरी लोड करें, एक `XpsDocument` का इंस्टेंस बनाएं, एक पेज जोड़ें, और `Save` कॉल करें – यह तीन संक्षिप्त कथनों में पूरा वर्कफ़्लो है। API स्वचालित रूप से पेज आकार, DPI, और संसाधन प्रबंधन को संभालती है, इसलिए आपको लो‑लेवल XPS संरचनाओं को स्वयं प्रबंधित करने की आवश्यकता नहीं है। यह दृष्टिकोण एक‑पेज फ़्लायर से लेकर सैकड़ों‑पेज के कैटलॉग तक स्केलेबल है।

## पूर्वापेक्षाएँ

- **Aspose.Page for .NET** – इसे [यहाँ](https://releases.aspose.com/page/net/) से डाउनलोड करें।  
- **एक .NET IDE** – Visual Studio, Rider, या C# एक्सटेंशन के साथ VS Code।  
- **आपके दस्तावेज़ों के लिए एक फ़ोल्डर** – कोड स्निपेट्स में हम इसे **Your Document Directory** कहेंगे।

## नामस्थान आयात करें

`Aspose.Page.XPS` नामस्थान कोर XPS दस्तावेज़ क्लास प्रदान करता है, जबकि `Aspose.Page.XPS.XpsModel` में ग्लिफ़ और ब्रश जैसे मॉडल तत्व होते हैं। इन्हें फ़ाइल के शीर्ष पर आयात करें:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## इमेज‑भरा ग्लिफ़ क्या है?

एक ग्लिफ़ एक वेक्टर आकार है जिसे ठोस रंग, ग्रेडिएंट, या इमेज ब्रश से रेंडर किया जा सकता है। जब आप `ImageBrush` लागू करते हैं, तो ग्लिफ़ के अंदरूनी भाग को प्रदान की गई इमेज से पेंट किया जाता है, जिससे पूरे पेज को रास्टराइज़ किए बिना जटिल विज़ुअल प्रभाव संभव होते हैं।

## चरण 1: पहला XPS दस्तावेज़ बनाएं

`XpsDocument` XPS पैकेज का प्रतिनिधित्व करता है और XPS फ़ाइलों को बनाने और सहेजने का प्रवेश बिंदु है। पहले XPS दस्तावेज़ को बनाकर शुरू करें जिसमें इमेज‑भरे ग्लिफ़ होंगे।

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## चरण 2: पहले दस्तावेज़ में ग्लिफ़ जोड़ें

`XpsGlyphs` ग्लिफ़ (टेक्स्ट कैरेक्टर) का संग्रह परिभाषित करता है जिसे पेज पर रखा जा सकता है। पहले दस्तावेज़ में ग्लिफ़ जोड़ें, फ़ॉन्ट, आकार, शैली और स्थिति निर्दिष्ट करें।

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## चरण 3: ग्लिफ़ को इमेज ब्रश से भरें

`ImageBrush` एक क्षेत्र को इमेज से पेंट करता है, जिससे पैटर्न या चित्र आकारों को भर सकते हैं। अपने डेटा डायरेक्टरी से इमेज का उपयोग करके ग्लिफ़ को इमेज ब्रश से भरें।

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## चरण 4: दूसरा XPS दस्तावेज़ बनाएं

`XpsDocument` का उपयोग करके एक नया XPS फ़ाइल बनाएं जिसमें पेज, संसाधन, और कंटेंट हो सकता है। अब, दूसरा XPS दस्तावेज़ बनाएं जो पहले दस्तावेज़ के ग्लिफ़ को शामिल करेगा।

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## चरण 5: पहले दस्तावेज़ के फ़ॉन्ट के साथ ग्लिफ़ जोड़ें

`Font` XPS दस्तावेज़ में टेक्स्ट रेंडर करने के लिए उपयोग किया जाने वाला टाइपफ़ेस दर्शाता है। दूसरे दस्तावेज़ में ग्लिफ़ जोड़ें, पहले दस्तावेज़ से निकाले गए फ़ॉन्ट का उपयोग करके। फ़ॉन्ट संग्रह को साझा करने से फ़ाइल आकार कम रहता है और विज़ुअल संगति बनी रहती है।

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## चरण 6: पहले दस्तावेज़ की फ़िल से इमेज ब्रश बनाएं

`ImageBrush` को मौजूदा फ़िल से बनाया जा सकता है ताकि वही इमेज कई दस्तावेज़ों में पुनः उपयोग हो सके। पहले दस्तावेज़ की फ़िल से एक इमेज ब्रश बनाएं और उसे दूसरे दस्तावेज़ में ग्लिफ़ को भरने के लिए उपयोग करें। यह “विदेशी इमेज” तकनीक स्रोत फ़ाइल को डुप्लिकेट किए बिना कला कार्य को पुनः उपयोग करने देती है।

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## चरण 7: दस्तावेज़ों को सहेजें

`Save` XPS पैकेज को फ़ाइल में लिखता है, सभी संसाधनों को एम्बेड करता है। दोनों पहले और दूसरे XPS दस्तावेज़ को आउटपुट फ़ोल्डर में सहेजें। `Save` मेथड XPS पैकेज को लिखता है, सभी संसाधनों को एम्बेड करता है और इमेज‑भरे ग्लिफ़ को संरक्षित रखता है।

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## सामान्य समस्याएँ और समाधान

| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| **ग्लिफ़ के अंदर इमेज नहीं दिख रही है** | `ImageBrush` को गलत URI के साथ बनाया गया था या इमेज का आकार ग्लिफ़ की सीमा से अधिक है। | इमेज पाथ की जाँच करें, और वैकल्पिक रूप से `ImageBrush.Stretch = Stretch.Uniform` सेट करें। |
| **दूसरे दस्तावेज़ में फ़ॉन्ट गायब हैं** | फ़ॉन्ट संसाधन पहले XPS से निर्यात नहीं किए गए थे। | `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` का उपयोग करके glyph जोड़ने से पहले। |
| **बड़ी फ़ाइलों पर प्रदर्शन में गिरावट** | प्रत्येक glyph के लिए बड़ी इमेज को मेमोरी में लोड करना। | सभी glyph के लिए एक ही `ImageBrush` इंस्टेंस का पुन: उपयोग करें, या उपयोग से पहले इमेज को डाउन‑सैंपल करें। |

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं ग्लिफ़ भरने के लिए विभिन्न इमेज फ़ॉर्मेट उपयोग कर सकता हूँ?
**A1:** हाँ, Aspose.Page PNG, JPEG, BMP, GIF, TIFF आदि को समर्थन देता है—कुल मिलाकर 25 से अधिक फ़ॉर्मेट।

### Q2: मैं ग्लिफ़ की उपस्थिति को आगे कैसे अनुकूलित कर सकता हूँ?
**A2:** `Glyph.Stroke`, `Glyph.FillOpacity`, और `Glyph.Transform` जैसी प्रॉपर्टीज़ का उपयोग करके आउटलाइन, पारदर्शिता, और घूर्णन को समायोजित करें।

### Q3: क्या Aspose.Page बड़े दस्तावेज़ सेट को संभालने के लिए उपयुक्त है?
**A3:** बिल्कुल। लाइब्रेरी स्ट्रीमिंग का उपयोग करके सैकड़ों‑पेज के XPS फ़ाइलों को प्रोसेस करती है, जिससे 500‑पेज के दस्तावेज़ों के लिए भी मेमोरी उपयोग 100 MB से कम रहता है।

### Q4: क्या मैं व्यक्तिगत ग्लिफ़ पर विभिन्न शैलियाँ लागू कर सकता हूँ?
**A4:** हाँ, प्रत्येक `Glyph` इंस्टेंस के पास अपना `Fill`, `Stroke`, और `Transform` होता है, जिससे प्रति‑ग्लिफ़ स्टाइलिंग संभव है।

### Q5: अन्य XPS टूल्स की तुलना में Aspose.Page उपयोग करने के क्या लाभ हैं?
**A5:** Aspose.Page 25+ इमेज फ़ॉर्मेट का समर्थन करता है, 500 MB तक की फ़ाइलों को पूरी मेमोरी लोड किए बिना प्रोसेस करता है, और 100 % .NET‑नेटिव API प्रदान करता है—जिससे COM इंटरऑप या बाहरी टूल की आवश्यकता समाप्त हो जाती है।

---

**अंतिम अपडेट:** 2026-06-30  
**परीक्षण किया गया:** Aspose.Page 24.11 for .NET  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [XPS दस्तावेज़ बनाएं – Aspose.Page for .NET](/page/net/document-creation/)
- [Aspose.Page for .NET के साथ XPS दस्तावेज़ में इमेज जोड़ें](/page/net/image-management/add-image-to-xps-document/)
- [Aspose.Page for .NET के साथ ग्लिफ़ क्लोन जोड़ें और रंग बदलें](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}