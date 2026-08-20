---
date: 2026-03-21
description: जानिए कैसे Aspose.Page for .NET का उपयोग करके XPS दस्तावेज़ में यूनिकोड
  टेक्स्ट जोड़ें। यह गाइड आपको दिखाता है कि C# में XPS दस्तावेज़ कैसे बनाएं और Aspose.Page
  के साथ यूनिकोड स्ट्रिंग्स का उपयोग करके टेक्स्ट जोड़ें।
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Aspose.Page के साथ XPS दस्तावेज़ में यूनिकोड टेक्स्ट कैसे जोड़ें
url: /hi/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ XPS दस्तावेज़ में Unicode टेक्स्ट कैसे जोड़ें

## परिचय

यदि आपको XPS फ़ाइल में **Unicode** अक्षर जोड़ने हैं, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम Aspose.Page for .NET का उपयोग करके **C#**‑स्टाइल में **XPS दस्तावेज़ बनाना** और Unicode स्ट्रिंग के साथ **aspose page add text** क्षमता को प्रदर्शित करने के सटीक चरणों को दिखाएंगे। अंत तक आपके पास एक पूर्ण कार्यात्मक XPS दस्तावेज़ होगा जो दाएँ‑से‑बाएँ (RTL) Unicode टेक्स्ट को सही ढंग से प्रदर्शित करेगा।

## त्वरित उत्तर
- **ट्यूटोरियल में क्या कवर किया गया है?** Aspose.Page for .NET के साथ XPS दस्तावेज़ में Unicode टेक्स्ट जोड़ना।  
- **कौन सी भाषा उपयोग की गई है?** C# ( .NET Framework और .NET Core के साथ संगत)।  
- **क्या लाइसेंस की आवश्यकता है?** विकास के लिए मुफ्त ट्रायल चलती है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या फ़ॉन्ट या आकार बदल सकते हैं?** हाँ – उदाहरण में Arial 20 pt उपयोग किया गया है, लेकिन कोई भी इंस्टॉल किया हुआ फ़ॉन्ट काम करेगा।  
- **क्या RTL समर्थन शामिल है?** `BidiLevel = 1` सेट करने से Unicode स्ट्रिंग के लिए दाएँ‑से‑बाएँ रेंडरिंग सक्षम हो जाती है।

## XPS में “Unicode कैसे जोड़ें” क्या है?

Unicode टेक्स्ट जोड़ना मतलब किसी भी भाषा—जैसे अरबी, हिब्रू, चीनी आदि—के अक्षरों को XPS दस्तावेज़ में सम्मिलित करना। Aspose.Page की `XpsGlyphs` क्लास लो‑लेवल ग्लिफ़ प्लेसमेंट संभालती है, जबकि `BidiLevel` प्रॉपर्टी RTL स्क्रिप्ट के लिए टेक्स्ट दिशा नियंत्रित करती है।

## टेक्स्ट जोड़ने के लिए Aspose.Page क्यों उपयोग करें?

- **पूर्ण .NET इंटीग्रेशन** – .NET Framework, .NET Core, .NET 5/6+ के साथ काम करता है।  
- **कोई बाहरी निर्भरताएँ नहीं** – शुद्ध मैनेज्ड कोड, कोई COM इंटरऑप नहीं।  
- **समृद्ध टाइपोग्राफी समर्थन** – फ़ॉन्ट, स्टाइल, रंग, और द्विदिशीय (bidirectional) टेक्स्ट।  
- **उच्च प्रदर्शन** – XPS फ़ाइलें तेज़ी से बनाता और सहेजता है, सर्वर‑साइड जेनरेशन के लिए आदर्श।

## पूर्वापेक्षाएँ

- C# और .NET विकास का बुनियादी ज्ञान।  
- Visual Studio (कोई भी नवीनतम संस्करण)।  
- Aspose.Page for .NET लाइब्रेरी – इसे [यहाँ](https://releases.aspose.com/page/net/) से डाउनलोड करें।

## नेमस्पेस आयात करें

पहले, उन नेमस्पेस को आयात करें जो आपको XPS मॉडल और ड्रॉइंग यूटिलिटीज़ तक पहुँच प्रदान करते हैं।

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## चरण 1: दस्तावेज़ सेट‑अप – create XPS document C#

एक नया XPS दस्तावेज़ बनाएं जो Unicode टेक्स्ट को होस्ट करेगा।

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## चरण 2: Unicode टेक्स्ट जोड़ें – aspose page add text

अब हम वास्तविक Unicode स्ट्रिंग जोड़ते हैं। इस उदाहरण में हम Arial फ़ॉन्ट, आकार 20 का उपयोग करते हैं और टेक्स्ट को (400 f, 200 f) पर स्थित करते हैं। `BidiLevel` को 1 सेट करने से रेंडरर स्ट्रिंग को दाएँ‑से‑बाएँ मानता है।

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## चरण 3: दस्तावेज़ सहेजें

अंत में, XPS फ़ाइल को डिस्क पर सहेजें।

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

बधाई हो! आपने सफलतापूर्वक Aspose.Page for .NET का उपयोग करके XPS दस्तावेज़ में **Unicode** टेक्स्ट जोड़ दिया है।

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|--------|------|--------|
| टेक्स्ट गड़बड़ दिख रहा है | फ़ॉन्ट Unicode रेंज को सपोर्ट नहीं करता | ऐसा फ़ॉन्ट उपयोग करें जिसमें आवश्यक ग्लिफ़ हों (जैसे Arial Unicode MS)। |
| RTL टेक्स्ट अभी भी बाएँ‑से‑दाएँ है | `BidiLevel` सेट नहीं है या 0 है | RTL स्क्रिप्ट के लिए `glyphs.BidiLevel = 1;` सुनिश्चित करें। |
| फ़ाइल सहेजी नहीं जा रही | `dataDir` पाथ अमान्य है | यह जाँचें कि डायरेक्टरी मौजूद है और एप्लिकेशन को लिखने की अनुमति है। |

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या Aspose.Page नवीनतम .NET फ्रेमवर्क के साथ संगत है?**  
उ: हाँ, Aspose.Page नियमित रूप से अपडेट किया जाता है ताकि .NET Framework, .NET Core, और .NET 5/6+ का समर्थन हो सके।

**प्र: टेक्स्ट जोड़ते समय फ़ॉन्ट स्टाइल और आकार को कस्टमाइज़ कर सकते हैं?**  
उ: बिल्कुल! `AddGlyphs` मेथड आपको कोई भी फ़ॉन्ट फ़ैमिली, आकार और `FontStyle` निर्दिष्ट करने की अनुमति देता है।

**प्र: Aspose.Page के अतिरिक्त दस्तावेज़ कहाँ मिलेंगे?**  
उ: व्यापक API विवरण के लिए आप दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/page/net/) देख सकते हैं।

**प्र: Aspose.Page शुरू करने के लिए कोई मुफ्त संसाधन उपलब्ध हैं?**  
उ: हाँ, टिप्स, उदाहरण और समुदाय समर्थन के लिए आप [Aspose.Page फ़ोरम](https://forum.aspose.com/c/page/39) देख सकते हैं।

**प्र: खरीदने से पहले कोई ट्रायल संस्करण उपलब्ध है?**  
उ: बिल्कुल! लाइब्रेरी का मूल्यांकन करने के लिए आप [यहाँ](https://releases.aspose.com/) से मुफ्त ट्रायल डाउनलोड कर सकते हैं।

---

**अंतिम अपडेट:** 2026-03-21  
**परीक्षित संस्करण:** Aspose.Page 24.11 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}