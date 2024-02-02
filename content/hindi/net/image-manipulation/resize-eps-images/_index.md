---
title: .NET के लिए Aspose.Page के साथ EPS छवियों का आकार बदलें
linktitle: ईपीएस छवियों का आकार बदलें
second_title: Aspose.Page .NET API
description: Aspose.Page का उपयोग करके .NET में EPS छवियों का आकार बदलने की सहज प्रक्रिया का अन्वेषण करें। आसानी से अंक, इंच, मिलीमीटर और प्रतिशत में सटीकता प्राप्त करें।
type: docs
weight: 11
url: /hi/net/image-manipulation/resize-eps-images/
---
## परिचय

क्या आप .NET के लिए Aspose.Page का उपयोग करके सहजता से EPS छवियों का आकार बदलना चाह रहे हैं? यह ट्यूटोरियल अंक, इंच, मिलीमीटर और प्रतिशत जैसी विभिन्न इकाइयों में ईपीएस छवियों के आकार में आसानी से हेरफेर करने के लिए आपका व्यापक मार्गदर्शक है। .NET के लिए Aspose.Page टूल का एक शक्तिशाली सेट प्रदान करता है, और इस ट्यूटोरियल में, हम आपको चरण दर चरण प्रक्रिया के बारे में बताएंगे।

## आवश्यक शर्तें

आकार बदलने के जादू में उतरने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

-  .NET लाइब्रेरी के लिए Aspose.Page: सुनिश्चित करें कि आपके पास .NET लाइब्रेरी के लिए Aspose.Page स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).

- दस्तावेज़ निर्देशिका: एक निर्देशिका बनाएं जहां आप अपनी इनपुट ईपीएस फ़ाइल और आउटपुट आकार की फ़ाइलें संग्रहीत करेंगे।

अब जब आपने सब कुछ सेट कर लिया है, तो आइए आवश्यक नामस्थान आयात करने के लिए आगे बढ़ें और चरण-दर-चरण मार्गदर्शिका पर ध्यान दें।

## नामस्थान आयात करें

अपने .NET प्रोजेक्ट में, Aspose.Page के साथ काम करने के लिए आवश्यक नेमस्पेस आयात करके शुरुआत करें। अपनी फ़ाइल की शुरुआत में निम्नलिखित कोड जोड़ें:

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

## चरण 1: बिंदुओं में आकार बदलना

आइए बिंदुओं में ईपीएस छवि का आकार बदलकर शुरुआत करें। मुद्रण उद्योग में अंक माप की एक मानक इकाई हैं।

```csharp
public static void ResizeInPoints()
{
    // आपकी दस्तावेज़ निर्देशिका
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

## चरण 2: इंच में आकार बदलना

अब, आइए ईपीएस छवि का आकार इंच में बदलें, जो ग्राफ़िक डिज़ाइन में उपयोग की जाने वाली एक सामान्य इकाई है।

```csharp
public static void ResizeInInches()
{
    // आपकी दस्तावेज़ निर्देशिका
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

## चरण 3: मिलीमीटर में आकार बदलना

अब, आइए ईपीएस छवि का आकार मिलीमीटर में बदलें, जो डिज़ाइन और प्रिंटिंग में व्यापक रूप से उपयोग की जाने वाली एक और इकाई है।

```csharp
public static void ResizeInMillimeters()
{
    // आपकी दस्तावेज़ निर्देशिका
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

## चरण 4: प्रतिशत में आकार बदलना

अंत में, आइए प्रतिशत का उपयोग करके एक ईपीएस छवि का आकार बदलें, जो छवि आकार को समायोजित करने के लिए एक लचीला दृष्टिकोण प्रदान करता है।

```csharp
public static void ResizeInPercents()
{
    // आपकी दस्तावेज़ निर्देशिका
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

बेझिझक इन तरीकों को अपने प्रोजेक्ट में एकीकृत करें, और आप आसानी से ईपीएस छवियों का आकार बदल देंगे। वांछित आयाम प्राप्त करने के लिए विभिन्न इकाइयों के साथ प्रयोग करें।

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Page के साथ EPS छवियों का आकार बदलने की कला में महारत हासिल कर ली है। यह शक्तिशाली लाइब्रेरी वेक्टर ग्राफिक्स में हेरफेर करने के लिए संभावनाओं की दुनिया खोलती है। चाहे आप प्रिंट या डिजिटल मीडिया के लिए डिज़ाइन कर रहे हों, Aspose.Page आपको सटीक और अनुकूलित परिणाम प्राप्त करने का अधिकार देता है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं एक साथ कई ईपीएस छवियों का आकार बदल सकता हूँ?

A1: हां, आप तदनुसार आकार बदलने के तरीकों को लागू करके ईपीएस फ़ाइलों के संग्रह के माध्यम से लूप कर सकते हैं।

### Q2: क्या Aspose.Page अन्य छवि प्रारूपों के साथ संगत है?

A2: Aspose.Page मुख्य रूप से पोस्टस्क्रिप्ट और EPS प्रारूपों पर केंद्रित है। अन्य छवि प्रारूपों के लिए, Aspose.Imaging का उपयोग करने पर विचार करें।

### Q3: क्या वाणिज्यिक परियोजनाओं के लिए कोई लाइसेंस संबंधी विचार हैं?

 उ3: हां, सुनिश्चित करें कि आपके पास वैध लाइसेंस है। मिलने जाना[यहाँ](https://purchase.aspose.com/buy) लाइसेंसिंग विवरण के लिए.

### Q4: क्या मैं खरीदने से पहले Aspose.Page आज़मा सकता हूँ?

 उ4: बिल्कुल! आप निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q5: मैं अतिरिक्त सहायता कहां मांग सकता हूं या मुद्दों पर चर्चा कर सकता हूं?

 A5: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) समुदाय से जुड़ने और सहायता प्राप्त करने के लिए।