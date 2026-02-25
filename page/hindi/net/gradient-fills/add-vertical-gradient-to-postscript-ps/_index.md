---
date: 2026-02-25
description: C# लीनियर ग्रेडिएंट ब्रश का उपयोग करके PS फ़ाइलों में ग्रेडिएंट जोड़ना
  और Aspose.Page for .NET का उपयोग करके आयत को ग्रेडिएंट से भरना सीखें।
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# लीनियर ग्रेडिएंट ब्रश – Aspose.Page के साथ पोस्टस्क्रिप्ट (PS) में वर्टिकल
  ग्रेडिएंट जोड़ें
url: /hi/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

 keep.

Now produce final content with translations.

Be careful to keep markdown formatting exactly.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – पोस्टस्क्रिप्ट (PS) में वर्टिकल ग्रेडिएंट जोड़ें Aspose.Page के साथ

## परिचय

दस्तावेज़ हेरफेर और निर्माण के क्षेत्र में, **Aspose.Page for .NET** डेवलपर्स के लिए एक शक्तिशाली टूल के रूप में उभरता है। इस गाइड में आप सीखेंगे कि **C# linear gradient brush** का उपयोग करके **PS** फ़ाइलों में **ग्रेडिएंट जोड़ना** और **ग्रेडिएंट के साथ आयत भरना** कैसे किया जाता है। इस ट्यूटोरियल के अंत तक, आपको आवश्यक कोड की स्पष्ट, चरण‑दर‑चरण समझ होगी और यह तकनीक आपके पोस्टस्क्रिप्ट आउटपुट में स्मूद वर्टिकल ग्रेडिएंट क्यों बनाती है, यह भी पता चलेगा।

## त्वरित उत्तर
- **C# linear gradient brush क्या करता है?** यह एक आकार में कई रंगों के बीच एक स्मूद ट्रांज़िशन बनाता है।
- **क्या मैं इसे किसी भी .NET संस्करण के साथ उपयोग कर सकता हूँ?** हाँ, Aspose.Page .NET Framework 4.5+ और .NET Core/5+ को सपोर्ट करता है।
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** गैर‑मूल्यांकन बिल्ड्स के लिए एक व्यावसायिक लाइसेंस आवश्यक है।
- **क्या ग्रेडिएंट वास्तव में वर्टिकल है?** ब्रश को 90° घुमाया जाता है, जिससे वर्टिकल प्रवाह सुनिश्चित होता है।
- **आउटपुट कहाँ सेव होता है?** वह पथ जहाँ आप `dataDir` में निर्दिष्ट करते हैं (उदाहरण के लिए, `VerticalGradient_outPS.ps`).

## C# Linear Gradient Brush क्या है?
एक **C# linear gradient brush** एक GDI+ ऑब्जेक्ट (`LinearGradientBrush`) है जो परिभाषित बिंदुओं के बीच रैखिक रंग परिवर्तन को पेंट करता है। जब इसे Aspose.Page की ड्राइंग API के साथ मिलाया जाता है, तो यह आपको सीधे पोस्टस्क्रिप्ट (PS) दस्तावेज़ में परिष्कृत ग्रेडिएंट रेंडर करने की सुविधा देता है।

## पोस्टस्क्रिप्ट के लिए Linear Gradient Brush क्यों उपयोग करें?
- **उच्च‑गुणवत्ता आउटपुट:** ग्रेडिएंट प्रिंटर‑लेवल पर रेंडर होते हैं, जिससे सटीकता बनी रहती है।
- **पूर्ण नियंत्रण:** आप कस्टम कलर स्टॉप्स, रोटेशन और स्केलिंग सेट कर सकते हैं।
- **पुन: उपयोग योग्य कोड:** वही ब्रश लॉजिक PDF, SVG और Aspose.Page द्वारा समर्थित अन्य फ़ॉर्मैट्स के लिए काम करता है।

## आवश्यकताएँ

ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित उपलब्ध हैं:

- Aspose.Page for .NET: सुनिश्चित करें कि आपके पास Aspose.Page लाइब्रेरी स्थापित है। आवश्यक संसाधन और दस्तावेज़ आप [here](https://reference.aspose.com/page/net/) पर पा सकते हैं।
- डेवलपमेंट एनवायरनमेंट: एक उपयुक्त विकास वातावरण सेट करें, जिसमें .NET विकास के लिए एक इंटीग्रेटेड डेवलपमेंट एनवायरनमेंट (IDE) शामिल हो।
- बुनियादी समझ: .NET विकास की बुनियादी बातों से परिचित हों, जिसमें स्ट्रीम्स, ग्राफ़िक्स पाथ्स, और कलर मैनीपुलेशन शामिल हैं।

## नेमस्पेस इम्पोर्ट करें

अपने C# प्रोजेक्ट में, कोड फ़ाइल की शुरुआत में आवश्यक नेमस्पेस शामिल करें:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## चरण 1: दस्तावेज़ डायरेक्टरी सेट करें

अपने दस्तावेज़ डायरेक्टरी का पथ निर्दिष्ट करके शुरू करें। यह वह स्थान है जहाँ आपका PS दस्तावेज़ सेव होगा।

```csharp
string dataDir = "Your Document Directory";
```

## चरण 2: पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं

`FileStream` क्लास का उपयोग करके पोस्टस्क्रिप्ट दस्तावेज़ के लिए एक आउटपुट स्ट्रीम जेनरेट करें।

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## चरण 3: सेव ऑप्शन और PS दस्तावेज़ बनाएं

A4 आकार के साथ सेव ऑप्शन बनाएं और एक नया 1‑पेज वाला PS दस्तावेज़ इनिशियलाइज़ करें।

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## चरण 4: आयत के आयाम निर्धारित करें

उस आयत के आयाम और स्थिति निर्दिष्ट करें जहाँ वर्टिकल ग्रेडिएंट लागू किया जाएगा।

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## चरण 5: ग्राफ़िक्स पाथ बनाएं

परिभाषित आयत से एक ग्राफ़िक्स पाथ बनाएं।

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## चरण 6: इंटरपोलेशन कलर्स निर्धारित करें

ग्रेडिएंट के लिए इंटरपोलेशन कलर्स और पोज़िशन्स की एक एरे स्थापित करें।

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## चरण 7: लीनियर ग्रेडिएंट ब्रश बनाएं

आयत को बाउंड्स, स्टार्ट और एंड कलर्स के रूप में उपयोग करके एक लीनियर ग्रेडिएंट ब्रश बनाएं।

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## चरण 8: ब्रश ट्रांसफ़ॉर्म सेट करें

ब्रश के लिए एक ट्रांसफ़ॉर्म स्थापित करें, यह सुनिश्चित करते हुए कि X और Y स्केल कॉम्पोनेन्ट्स आयत की चौड़ाई और ऊँचाई से मेल खाते हों।

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## चरण 9: पेंट सेट करें और आयत को ग्रेडिएंट के साथ भरें

दस्तावेज़ के लिए पेंट सेट करें, और पहले परिभाषित पाथ का उपयोग करके **fill rectangle with gradient** करें।

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## चरण 10: वर्तमान पेज बंद करें और दस्तावेज़ सेव करें

वर्तमान पेज को बंद करें और पोस्टस्क्रिप्ट दस्तावेज़ को सेव करें।

```csharp
document.ClosePage();
document.Save();
```

बधाई हो! आपने **Aspose.Page for .NET** के साथ **C# linear gradient brush** का उपयोग करके एक पोस्टस्क्रिप्ट दस्तावेज़ में **वर्टिकल ग्रेडिएंट जोड़ना** सफलतापूर्वक पूरा कर लिया है। विभिन्न पैरामीटर और रंगों के साथ प्रयोग करें ताकि अपने दस्तावेज़ों में विभिन्न दृश्य प्रभाव प्राप्त कर सकें।

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|------|--------|
| ग्रेडिएंट क्षैतिज दिखता है | ब्रश रोटेशन लागू नहीं हुआ | सुनिश्चित करें कि `brushTransform.Rotate(90);` को `brush.Transform` को असाइन करने से पहले कॉल किया गया है। |
| रंग फीके दिखते हैं | निम्न‑रिज़ॉल्यूशन आउटपुट स्ट्रीम | उच्च‑रिज़ॉल्यूशन `PsSaveOptions` का उपयोग करें या दस्तावेज़ का आकार बढ़ाएँ। |
| आउटपुट फ़ाइल खाली है | स्ट्रीम फ़्लश नहीं हुई | सुनिश्चित करें कि `document.Save();` `using` ब्लॉक के बाहर कॉल किया गया है। |

## अक्सर पूछे जाने वाले प्रश्न

**Q1: क्या मैं एक ही दस्तावेज़ के विभिन्न क्षेत्रों में कई ग्रेडिएंट लागू कर सकता हूँ?**  
A: हाँ, आप कर सकते हैं। प्रत्येक क्षेत्र के लिए उसके विशिष्ट आयाम और रंग योजना के साथ चरणों को दोहराएँ।

**Q2: मैं इस कोड को अपने मौजूदा .NET प्रोजेक्ट में कैसे इंटीग्रेट करूँ?**  
A: कोड को अपने प्रोजेक्ट फ़ाइल में कॉपी‑पेस्ट करें और सुनिश्चित करें कि आपके पास Aspose.Page लाइब्रेरी का रेफ़रेंस है।

**Q3: क्या Aspose.Page for .NET में अन्य ग्रेडिएंट प्रकार उपलब्ध हैं?**  
A: Aspose.Page विभिन्न ग्रेडिएंट प्रकारों को सपोर्ट करता है, जिसमें रेडियल और पाथ ग्रेडिएंट शामिल हैं। अधिक विवरण के लिए दस्तावेज़ देखें।

**Q4: क्या मैं Aspose.Page को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?**  
A: हाँ, आप कर सकते हैं। लाइसेंस विकल्पों को एक्सप्लोर करने के लिए [here](https://purchase.aspose.com/buy) पर जाएँ।

**Q5: क्या Aspose.Page के लिए कोई कम्युनिटी फ़ोरम है जहाँ मैं मदद ले सकूँ?**  
A: बिल्कुल! अन्य डेवलपर्स से जुड़ने और सहायता प्राप्त करने के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) पर जाएँ।

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}