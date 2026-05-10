---
date: 2026-03-03
description: Aspose.Page के साथ .NET में EPS इमेजेज़ को रिसाइज़ करना सीखें – पॉइंट्स,
  इंच, मिलीमीटर या प्रतिशत का उपयोग करके EPS को रिसाइज़ करने की चरण‑दर‑चरण गाइड।
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET के साथ EPS इमेज को कैसे री‑साइज़ करें
url: /hi/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET के साथ EPS इमेजेज़ को रिसाइज़ कैसे करें

## परिचय

क्या आप **EPS इमेजेज़ को सहजता से रिसाइज़ करने** के बारे में खोज रहे हैं Aspose.Page for .NET का उपयोग करके? यह ट्यूटोरियल EPS इमेजेज़ के आकार को पॉइंट्स, इंच, मिलीमीटर और प्रतिशत जैसे विभिन्न इकाइयों में आसानी से बदलने के लिए आपका व्यापक मार्गदर्शक है। Aspose.Page for .NET एक शक्तिशाली टूल‑सेट प्रदान करता है, और इस ट्यूटोरियल में हम आपको चरण‑दर‑चरण प्रक्रिया दिखाएंगे।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी EPS रिसाइज़िंग संभालती है?** Aspose.Page for .NET  
- **कौन सी इकाइयाँ समर्थित हैं?** पॉइंट्स, इंच, मिलीमीटर, और प्रतिशत  
- **क्या प्रोडक्शन के लिए लाइसेंस चाहिए?** हाँ – एक वाणिज्यिक लाइसेंस आवश्यक है  
- **क्या मैं एक साथ कई फ़ाइलें रिसाइज़ कर सकता हूँ?** बिल्कुल – फ़ाइलों को लूप करके  
- **क्या .NET Core समर्थित है?** हाँ, API .NET Framework और .NET Core दोनों के साथ काम करता है  

## EPS रिसाइज़िंग क्या है?
Encapsulated PostScript (EPS) एक वेक्टर‑आधारित ग्राफ़िक्स फ़ॉर्मेट है जो प्रिंट और डिज़ाइन वर्कफ़्लो में आमतौर पर उपयोग होता है। EPS फ़ाइल को रिसाइज़ करने से उसका बाउंडिंग बॉक्स बदलता है बिना आर्टवर्क को रास्टर किए, जिससे किसी भी स्केल पर स्पष्टता बनी रहती है।

## EPS इमेजेज़ को रिसाइज़ क्यों करें?
- **प्रिंट क्वालिटी बनाए रखें:** वेक्टर स्केलिंग किनारों को तेज़ रखती है।  
- **लेआउट आवश्यकताओं के अनुसार फिट करें:** पेज या कैनवास के आकार से मेल खाने के लिए आयाम समायोजित करें।  
- **बैच जॉब्स को ऑटोमेट करें:** प्रोग्रामेटिक रूप से सेकंड में दर्जनों फ़ाइलों को रिसाइज़ करें।  

## पूर्वापेक्षाएँ

रिसाइज़िंग जादू में डुबने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- Aspose.Page for .NET लाइब्रेरी: सुनिश्चित करें कि आपके पास Aspose.Page for .NET लाइब्रेरी स्थापित है। आप इसे [यहाँ](https://releases.aspose.com/page/net/) से डाउनलोड कर सकते हैं।

- डॉक्यूमेंट डायरेक्टरी: एक फ़ोल्डर बनाएं जहाँ आप अपना इनपुट EPS फ़ाइल और आउटपुट रिसाइज़्ड फ़ाइलें संग्रहीत करेंगे।

अब जब सब सेट हो गया है, चलिए आवश्यक नेमस्पेस इम्पोर्ट करते हैं और चरण‑दर‑चरण गाइड में आगे बढ़ते हैं।

## नेमस्पेस इम्पोर्ट करें

अपने .NET प्रोजेक्ट में, Aspose.Page के साथ काम करने के लिए आवश्यक नेमस्पेस इम्पोर्ट करके शुरू करें। फ़ाइल की शुरुआत में निम्न कोड जोड़ें:

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

## पॉइंट्स में EPS रिसाइज़ करना

पॉइंट्स प्रिंटिंग उद्योग में एक मानक माप इकाई है। नीचे दिया गया उदाहरण मूल चौड़ाई और ऊँचाई को दोगुना करता है।

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## इंच में EPS रिसाइज़ करना

इंच ग्राफ़िक डिज़ाइनरों द्वारा प्रिंट एसेट्स तैयार करते समय अक्सर उपयोग किया जाता है।

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## मिलीमीटर में EPS रिसाइज़ करना

मिलीमीटर उन क्षेत्रों में सामान्य है जहाँ मीट्रिक सिस्टम उपयोग किया जाता है।

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## प्रतिशत में EPS रिसाइज़ करना

प्रतिशत‑आधारित रिसाइज़िंग आपको इमेज को उसके मूल आकार के सापेक्ष स्केल करने की अनुमति देती है।

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

इन विधियों को अपने प्रोजेक्ट में एकीकृत करने में संकोच न करें, और आप EPS इमेजेज़ को आसानी से रिसाइज़ कर पाएँगे। वांछित आयाम प्राप्त करने के लिए विभिन्न इकाइयों के साथ प्रयोग करें।

## सामान्य समस्याएँ और समाधान
- **फ़ाइल नहीं मिली:** सुनिश्चित करें कि `dataDir` सही फ़ोल्डर की ओर इशारा कर रहा है और `input.eps` मौजूद है।  
- **अनपेक्षित आकार:** याद रखें कि `Units.Percents` को 150 जैसे मान चाहिए जो मूल आकार के 150 % को दर्शाता है।  
- **लाइसेंस अपवाद:** यदि आपको लाइसेंसिंग त्रुटि दिखती है, तो `PsDocument` बनाने से पहले एक वैध Aspose.Page लाइसेंस फ़ाइल लोड करें।

## निष्कर्ष

बधाई हो! आपने Aspose.Page for .NET के साथ **EPS इमेजेज़ को रिसाइज़ करना** में महारत हासिल कर ली है। यह शक्तिशाली लाइब्रेरी वेक्टर ग्राफ़िक्स को मैनीपुलेट करने के असीम संभावनाएँ खोलती है। चाहे आप प्रिंट के लिए डिज़ाइन कर रहे हों या डिजिटल मीडिया के लिए, Aspose.Page आपको सटीक और कस्टमाइज़्ड परिणाम प्राप्त करने में सक्षम बनाता है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं एक साथ कई EPS इमेजेज़ को रिसाइज़ कर सकता हूँ?

A1: हाँ, आप EPS फ़ाइलों के संग्रह पर लूप करके उपयुक्त रिसाइज़िंग मेथड लागू कर सकते हैं।

### Q2: क्या Aspose.Page अन्य इमेज फ़ॉर्मेट्स के साथ संगत है?

A2: Aspose.Page मुख्यतः PostScript और EPS फ़ॉर्मेट्स पर केंद्रित है। अन्य इमेज फ़ॉर्मेट्स के लिए Aspose.Imaging पर विचार करें।

### Q3: व्यावसायिक प्रोजेक्ट्स के लिए लाइसेंसिंग संबंधी क्या विचार हैं?

A3: हाँ, एक वैध लाइसेंस रखें। लाइसेंसिंग विवरण के लिए [यहाँ](https://purchase.aspose.com/buy) देखें।

### Q4: क्या मैं खरीदने से पहले Aspose.Page आज़मा सकता हूँ?

A4: बिल्कुल! आप एक मुफ्त ट्रायल [यहाँ](https://releases.aspose.com/) प्राप्त कर सकते हैं।

### Q5: अतिरिक्त मदद या मुद्दों पर चर्चा के लिए मैं कहाँ जा सकता हूँ?

A5: समुदाय से जुड़ने और सहायता पाने के लिए [Aspose.Page फ़ोरम](https://forum.aspose.com/c/page/39) पर जाएँ।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या यह कोड .NET Core 6 के साथ काम करता है?**  
उत्तर: हाँ। API .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ और .NET 6+ के साथ संगत है।

**प्रश्न: मैं मूल कलर प्रोफ़ाइल को कैसे बनाए रखूँ?**  
उत्तर: `ResizeEps` मेथड रंग डेटा को नहीं बदलता; यह केवल बाउंडिंग बॉक्स को बदलता है।

**प्रश्न: क्या पूरी फ़ाइल को मेमोरी में लोड किए बिना EPS को रिसाइज़ करना संभव है?**  
उत्तर: जैसा कि स्ट्रीम में दिखाया गया है, मेमोरी उपयोग कम रहता है; दस्तावेज़ ऑन‑द‑फ़्लाई प्रोसेस किया जाता है।

**प्रश्न: क्या मैं कई रिसाइज़िंग ऑपरेशन्स को चेन कर सकता हूँ?**  
उत्तर: बिल्कुल। आप एक ही `PsDocument` इंस्टेंस पर क्रमिक रूप से `ResizeEps` कॉल कर सकते हैं।

**प्रश्न: EPS के अंदर एम्बेडेड इमेजेज़ का क्या होता है?**  
उत्तर: वे वेक्टर कंटेंट के साथ अनुपातिक रूप से स्केल होते हैं, गुणवत्ता बनी रहती है।

---

**अंतिम अपडेट:** 2026-03-03  
**टेस्ट किया गया संस्करण:** Aspose.Page 24.12 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}