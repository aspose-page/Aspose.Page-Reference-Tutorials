---
date: 2026-03-16
description: जानिए कैसे .NET में Aspose.Page का उपयोग करके EPS इमेज को क्रॉप करें
  और EPS इमेज फ़ाइलों का आकार बदलें। इस चरण‑दर‑चरण गाइड का पालन करके आसानी से EPS
  को क्रॉप करें और EPS इमेज का आकार बदलें।
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET के साथ EPS इमेज को कैसे क्रॉप करें
url: /hi/net/image-manipulation/crop-eps-images/
weight: 10
---

:" etc.

Let's produce final content.

Be careful with markdown tables: translate content but keep pipes.

Also ensure we keep "Aspose.Page" unchanged.

Let's craft.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET के साथ EPS इमेजेज को कैसे क्रॉप करें

## परिचय

यदि आपको एक .NET एप्लिकेशन में **EPS इमेज को कैसे क्रॉप करें** यह जानना है, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम शक्तिशाली Aspose.Page for .NET लाइब्रेरी का उपयोग करके EPS फ़ाइलों को क्रॉप और रिसाइज़ करने की प्रक्रिया दिखाएंगे। चाहे आप रिपोर्टिंग टूल को परिष्कृत कर रहे हों या वेब सर्विस के लिए ग्राफ़िक्स तैयार कर रहे हों, इस तकनीक में महारत हासिल करने से आपका समय बचेगा और आपको पिक्सेल‑परफेक्ट परिणाम मिलेंगे।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी EPS क्रॉपिंग संभालती है?** Aspose.Page for .NET  
- **मुख्य मेथड?** `doc.CropEps(outputStream, newBoundingBox)`  
- **क्या मैं EPS को रिसाइज़ भी कर सकता हूँ?** हाँ – `ResizeEps` का उपयोग इंच, मिलीमीटर या प्रतिशत में करें।  
- **पूर्वापेक्षाएँ?** .NET (Framework 4.5+ / .NET Core 3.1+), Aspose.Page स्थापित, एक EPS फ़ाइल।  
- **आम कार्यान्वयन समय?** बुनियादी क्रॉप‑और‑रिसाइज़ वर्कफ़्लो के लिए लगभग 10 मिनट।

## पूर्वापेक्षाएँ

कोड में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास है:

- .NET विकास का कार्यात्मक ज्ञान।  
- Aspose.Page for .NET लाइब्रेरी स्थापित। यदि नहीं, तो इसे [यहाँ](https://releases.aspose.com/page/net/) से डाउनलोड कर सकते हैं।  
- एक नमूना EPS इमेज (कोड में `"input.eps"` को अपनी वास्तविक फ़ाइल से बदलें)।

## नेमस्पेस इम्पोर्ट करें

आइए उन नेमस्पेस को इम्पोर्ट करें जो हमें EPS हैंडलिंग क्लासेज़ तक पहुँच देते हैं।

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## EPS इमेजेज को क्रॉप करने की चरण‑दर‑चरण गाइड

### चरण 1: `PsDocument` को इनिशियलाइज़ करें

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

हम इनपुट EPS स्ट्रीम से एक `PsDocument` इंस्टेंस बनाते हैं। यह ऑब्जेक्ट मेमोरी में EPS फ़ाइल का प्रतिनिधित्व करता है और हमें क्रॉप और रिसाइज़ मेथड्स तक पहुँच देता है।

### चरण 2: मूल बाउंडिंग बॉक्स निकालें

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

बाउंडिंग बॉक्स आपको EPS कैनवास के वर्तमान आयाम बताता है। इन मानों को जानने से आप एक सुरक्षित क्रॉप रेक्टेंगल परिभाषित कर सकते हैं।

### चरण 3: आउटपुट स्ट्रीम बनाएं

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

हम एक लिखने योग्य स्ट्रीम खोलते हैं जहाँ क्रॉप किया गया EPS सहेजा जाएगा। `using` ब्लॉक का उपयोग स्ट्रीम को सही तरीके से बंद करने की गारंटी देता है।

### चरण 4: नया बाउंडिंग बॉक्स परिभाषित करें

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

संख्याओं को उन निर्देशांक से बदलें जिन्हें आप रखना चाहते हैं। सुनिश्चित करें कि नए मान मूल बाउंडिंग बॉक्स के भीतर रहें; अन्यथा ऑपरेशन विफल होगा।

### चरण 5: EPS को क्रॉप और सेव करें

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

यह एकल पंक्ति क्रॉप को निष्पादित करती है और परिणाम `output_crop.eps` में लिखती है। मेथड दस्तावेज़ को मेमोरी में संशोधित करता है, इसलिए आवश्यकता पड़ने पर आप आगे के ऑपरेशन चेन कर सकते हैं।

## EPS इमेज को रिसाइज़ करें

क्रॉप करने के बाद, अक्सर आप डिस्प्ले या प्रिंटिंग के लिए EPS का आकार बदलना चाहते हैं। Aspose.Page तीन माप इकाइयों का समर्थन करता है।

### इंच में रिसाइज़ करें

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### मिलीमीटर में रिसाइज़ करें

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### प्रतिशत में रिसाइज़ करें

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

प्रत्येक कॉल पिछले आउटपुट को ओवरराइट कर देती है, इसलिए यदि आपको प्रत्येक आकार के लिए अलग फ़ाइल चाहिए तो एक नया स्ट्रीम बनाना सुनिश्चित करें।

## सामान्य समस्याएँ और ट्रबलशूटिंग

| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| **बाउंडिंग बॉक्स मान सीमा से बाहर** | नया बॉक्स मूल आयामों से अधिक है | `initialBoundingBox` मानों की जाँच करें और उन निर्देशांक को चुनें जो उस सीमा के भीतर हों। |
| **आउटपुट फ़ाइल खाली है** | आउटपुट स्ट्रीम फ्लश या क्लोज नहीं हुआ | सुनिश्चित करें कि `using` ब्लॉक समाप्त हो गया है फ़ाइल तक पहुँचने से पहले, या `outputEpsStream.Flush()` कॉल करें। |
| **अनपेक्षित स्केलिंग** | इकाइयों का मिश्रण (जैसे, इंच बनाम मिलीमीटर) | हमेशा सही `Units` एन्नुम का उपयोग करें जो आपके आकार मानों से मेल खाता हो। |

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं Aspose.Page for .NET को अन्य इमेज फ़ॉर्मेट्स के साथ उपयोग कर सकता हूँ?

A1: Aspose.Page मुख्यतः EPS इमेजेज पर केंद्रित है, लेकिन Aspose विभिन्न फ़ॉर्मेट्स के लिए कई लाइब्रेरी प्रदान करता है। विशिष्ट फ़ॉर्मेट्स के लिए उनके दस्तावेज़ देखें।

### Q2: मैं Aspose.Page for .NET के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?

A2: परीक्षण के लिए अस्थायी लाइसेंस प्राप्त करने हेतु [इस लिंक](https://purchase.aspose.com/temporary-license/) पर जाएँ।

### Q3: क्या Aspose.Page for .NET के साथ मैं जिस इमेज साइज को प्रोसेस कर सकता हूँ, उसमें कोई सीमा है?

A3: Aspose.Page विभिन्न आकारों की इमेज को संभालने के लिए डिज़ाइन किया गया है। हालांकि, इमेज की जटिलता के आधार पर प्रदर्शन में अंतर आ सकता है।

### Q4: क्या Aspose.Page चर्चा के लिए कोई कम्युनिटी फ़ोरम है?

A5: हाँ, आप Aspose.Page कम्युनिटी से [यहाँ](https://forum.aspose.com/c/page/39) जुड़ सकते हैं।

### Q5: Aspose.Page for .NET के विस्तृत दस्तावेज़ कहाँ मिलेंगे?

A5: दस्तावेज़ के लिए [यहाँ](https://reference.aspose.com/page/net/) देखें।

---

**अंतिम अपडेट:** 2026-03-16  
**टेस्टेड विद:** Aspose.Page 24.11 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}