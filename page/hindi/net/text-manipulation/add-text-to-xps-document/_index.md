---
date: 2026-03-21
description: .NET में XPS दस्तावेज़ कैसे बनाएं और Aspose.Page for .NET का उपयोग करके
  टेक्स्ट जोड़ें, सीखें। .NET डेवलपर्स के लिए चरण‑दर‑चरण गाइड।
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: XPS दस्तावेज़ .NET में बनाएं और Aspose.Page के साथ टेक्स्ट जोड़ें
url: /hi/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create XPS document .NET and add text with Aspose.Page

आधुनिक .NET विकास में, प्रोग्रामेटिक रूप से **XPS दस्तावेज़ .NET** फ़ाइलें बनाना एक मूल्यवान कौशल है, विशेषकर जब आपको प्रिंटेबल रिपोर्ट, इनवॉइस, या कस्टम ग्राफ़िक्स जनरेट करने की आवश्यकता होती है। यह ट्यूटोरियल आपको Aspose.Page का उपयोग करके **aspose.page add text** को XPS दस्तावेज़ में जोड़ने की प्रक्रिया से परिचित कराता है, जिससे आप लेआउट और स्टाइलिंग पर पूर्ण नियंत्रण प्राप्त कर सकते हैं—सभी आपके .NET एप्लिकेशन के भीतर।

## Quick Answers
- **इस ट्यूटोरियल में क्या कवर किया गया है?** Aspose.Page for .NET का उपयोग करके नए बनाए गए XPS दस्तावेज़ में टेक्स्ट जोड़ना।  
- **इसमें कितना समय लगेगा?** बुनियादी इम्प्लीमेंटेशन के लिए लगभग 5‑10 मिनट।  
- **पूर्वापेक्षाएँ क्या हैं?** .NET विकास पर्यावरण और Aspose.Page लाइब्रेरी।  
- **क्या लाइसेंस आवश्यक है?** हाँ, प्रोडक्शन उपयोग के लिए एक वैध Aspose.Page लाइसेंस आवश्यक है।  
- **क्या यह .NET Core / .NET 6+ पर चल सकता है?** बिल्कुल—Aspose.Page सभी नवीनतम .NET संस्करणों को सपोर्ट करता है।

## What is create xps document .net?

.NET में XPS दस्तावेज़ बनाना का अर्थ है एक फिक्स्ड‑लेआउट फ़ाइल उत्पन्न करना जो विभिन्न डिवाइस और प्रिंटरों पर आपके कंटेंट की सटीक उपस्थिति को संरक्षित रखती है। XPS (XML Paper Specification) माइक्रोसॉफ्ट का ओपन स्टैंडर्ड है पेज डिस्क्रिप्शन के लिए, जो PDF के समान है लेकिन पूरी तरह से XML‑आधारित है।

## Why use Aspose.Page to add text?

Aspose.Page एक हाई‑लेवल, ऑब्जेक्ट‑ओरिएंटेड API प्रदान करता है जो लो‑लेवल XPS मार्कअप को एब्स्ट्रैक्ट करता है। आप टेक्स्ट, ग्राफ़िक्स और शैप्स को बिना रॉ XML से निपटे जोड़ सकते हैं, जिससे विकास प्रक्रिया तेज़ और कम त्रुटिपूर्ण बनती है।

## Prerequisites

- Aspose.Page for .NET: सुनिश्चित करें कि आपके पास Aspose.Page लाइब्रेरी इंस्टॉल है। आप इसे [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) से डाउनलोड कर सकते हैं।  
- Development Environment: अपना .NET विकास पर्यावरण सेट अप करें। यदि आपने अभी तक नहीं किया है, तो [documentation](https://reference.aspose.com/page/net/) में दी गई इंस्टॉलेशन निर्देशों का पालन करें।  
- Document Directory: एक डायरेक्टरी बनाएं जहाँ आप अपने दस्तावेज़ संग्रहीत करेंगे। प्रदान किए गए कोड स्निपेट में "Your Document Directory" को वास्तविक पाथ से बदलें।

अब जब हमने बुनियादी बातें कवर कर ली हैं, चलिए कोड में डुबकी लगाते हैं।

## Import Namespaces

सबसे पहले, प्रोजेक्ट को शुरू करने के लिए आवश्यक नेमस्पेस इम्पोर्ट करें:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Create XPS document .NET

एक नया XPS दस्तावेज़ बनाएं जो हमारे टेक्स्ट का कैनवास होगा।

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## Step 2: Create a brush for text

एक सॉलिड‑कलर ब्रश परिभाषित करें जो टेक्स्ट का रंग निर्धारित करेगा। यहाँ हम काला उपयोग कर रहे हैं।

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## Step 3: Add glyphs (aspose.page add text)

ग्लिफ्स XPS दस्तावेज़ में कैरेक्टर्स का लो‑लेवल प्रतिनिधित्व होते हैं। यह कॉल निर्दिष्ट निर्देशांक पर “Hello World!” टेक्स्ट जोड़ता है।

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## Step 4: Save the resultant XPS document

दस्तावेज़ को डिस्क पर सहेजें ताकि आप बाद में इसे देख या प्रिंट कर सकें।

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

इन चरणों का पालन करके, आपने सफलतापूर्वक **create XPS document .NET** किया और Aspose.Page का उपयोग करके कस्टम टेक्स्ट जोड़ा।

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| **File not found** when saving | `dataDir` किसी गैर‑मौजूद फ़ोल्डर की ओर इशारा कर रहा है | सुनिश्चित करें कि डायरेक्टरी मौजूद है या सहेजने से पहले `Directory.CreateDirectory(dataDir)` का उपयोग करें। |
| **Text not visible** | ब्रश का रंग बैकग्राउंड के समान है | `Color.Black` को किसी अन्य कंट्रास्टिंग रंग में बदलें। |
| **Unsupported font** | फ़ॉन्ट मशीन पर इंस्टॉल नहीं है | ऐसा फ़ॉन्ट उपयोग करें जो मौजूद हो, या Aspose.Page की फ़ॉन्ट‑एंबेडिंग सुविधाओं से फ़ॉन्ट एंबेड करें। |

## Frequently Asked Questions

### Q1: क्या मैं जोड़े गए टेक्स्ट का फ़ॉन्ट और आकार कस्टमाइज़ कर सकता हूँ?

A1: हाँ, आपके पास फ़ॉन्ट और आकार पर पूर्ण नियंत्रण है। `AddGlyphs` मेथड में पैरामीटर को अनुसार समायोजित करें।

### Q2: क्या Aspose.Page .NET Core के साथ संगत है?

A2: बिल्कुल! Aspose.Page .NET Core को सपोर्ट करता है, जिससे यह नवीनतम .NET तकनीकों के साथ काम करता है।

### Q3: Aspose.Page उपयोग करने के लिए कोई लाइसेंसिंग आवश्यकताएँ हैं?

A3: हाँ, आपको एक वैध लाइसेंस चाहिए। लाइसेंस विकल्पों का पता [here](https://purchase.aspose.com/buy) से लगाएँ।

### Q4: मैं सपोर्ट कैसे प्राप्त कर सकता हूँ या मदद कहां से ले सकता हूँ?

A4: समुदाय और सहायता के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) पर जाएँ।

### Q5: क्या कोई फ्री ट्रायल उपलब्ध है?

A5: बिल्कुल! आप फ्री ट्रायल [here](https://releases.aspose.com/) से प्राप्त कर सकते हैं।

**Additional Q&A**

**Q: क्या मैं एक ही पेज पर कई टेक्स्ट ब्लॉक्स जोड़ सकता हूँ?**  
A: हाँ, विभिन्न निर्देशांक के साथ `doc.AddGlyphs` को कई बार कॉल करें।

**Q: क्या Aspose.Page टेक्स्ट रोटेशन की अनुमति देता है?**  
A: आप `XpsGlyphs` ऑब्जेक्ट पर ट्रांसफ़ॉर्मेशन मैट्रिक्स लागू करके टेक्स्ट को घुमा या स्क्यू कर सकते हैं।

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

---