---
title: Aspose.Page के साथ पोस्टस्क्रिप्ट (PS) दस्तावेज़ में टेक्स्ट जोड़ें
linktitle: पोस्टस्क्रिप्ट (पीएस) दस्तावेज़ में टेक्स्ट जोड़ें
second_title: Aspose.Page .NET API
description: Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट (PS) दस्तावेज़ों में टेक्स्ट जोड़ना सीखकर अपने .NET विकास कौशल को बढ़ाएं। चरण-दर-चरण उदाहरण खोजें और दस्तावेज़ हेरफेर की शक्ति को उजागर करें।
weight: 10
url: /hi/net/text-manipulation/add-text-to-postscript-ps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ पोस्टस्क्रिप्ट (PS) दस्तावेज़ में टेक्स्ट जोड़ें

## परिचय

.NET विकास की गतिशील दुनिया में, पोस्टस्क्रिप्ट (PS) दस्तावेज़ों में हेरफेर करना और उन्हें बढ़ाना एक सामान्य आवश्यकता है। .NET के लिए Aspose.Page आपके PS दस्तावेज़ों में आसानी से टेक्स्ट जोड़ने के लिए टूल का एक शक्तिशाली सेट प्रदान करता है। यह ट्यूटोरियल आपको प्रक्रिया के माध्यम से मार्गदर्शन करेगा, यह सुनिश्चित करते हुए कि आप इस कार्यक्षमता को अपनी परियोजनाओं में निर्बाध रूप से एकीकृत कर सकते हैं।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET के लिए Aspose.Page: सुनिश्चित करें कि आपके पास Aspose.Page लाइब्रेरी आपके .NET प्रोजेक्ट में एकीकृत है। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose.Page .NET दस्तावेज़ीकरण](https://reference.aspose.com/page/net/).

- दस्तावेज़ निर्देशिका: एक निर्देशिका स्थापित करें जहाँ आपके दस्तावेज़ संग्रहीत किए जाएंगे। इसे उदाहरणों में "आपकी दस्तावेज़ निर्देशिका" के रूप में संदर्भित किया जाएगा।

- फ़ॉन्ट फ़ोल्डर: कस्टम फ़ॉन्ट संग्रहीत करने के लिए एक फ़ोल्डर बनाएं, जिसे उदाहरणों में "आपकी दस्तावेज़ निर्देशिका" कहा गया है।

## नामस्थान आयात करें

आरंभ करने से पहले, अपने प्रोजेक्ट में आवश्यक नामस्थान शामिल करना सुनिश्चित करें:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

अब, आइए उदाहरण को कई चरणों में विभाजित करें।

## चरण 1: पीएस दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## चरण 2: टेक्स्ट को सिस्टम फॉन्ट से भरें

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

## चरण 3: टेक्स्ट को कस्टम फ़ॉन्ट से भरें

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## चरण 4: सिस्टम फॉन्ट के साथ टेक्स्ट की रूपरेखा तैयार करें

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

## चरण 5: कस्टम फ़ॉन्ट के साथ टेक्स्ट की रूपरेखा तैयार करें

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

## चरण 6: बंद करें और सहेजें

```csharp
document.ClosePage();
document.Save();
}
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट (PS) दस्तावेज़ में टेक्स्ट जोड़ने का तरीका सफलतापूर्वक सीख लिया है। अधिक सुविधाओं का पता लगाने और अपनी दस्तावेज़ हेरफेर क्षमताओं को बढ़ाने के लिए स्वतंत्र महसूस करें।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं अन्य .NET लाइब्रेरीज़ के साथ Aspose.Page का उपयोग कर सकता हूँ?

A1: हां, Aspose.Page अन्य .NET लाइब्रेरीज़ के साथ सहजता से एकीकृत होता है, जो दस्तावेज़ हेरफेर के लिए एक बहुमुखी वातावरण प्रदान करता है।

### Q2: क्या कस्टम फ़ॉन्ट इस प्रक्रिया के लिए आवश्यक हैं?

A2: जबकि आप सिस्टम फ़ॉन्ट का उपयोग कर सकते हैं, कस्टम फ़ॉन्ट को शामिल करने से अधिक लचीलेपन और डिज़ाइन विकल्पों की अनुमति मिलती है।

### Q3: क्या Aspose.Page बड़े पैमाने पर दस्तावेज़ प्रसंस्करण के लिए उपयुक्त है?

उ3: बिल्कुल! Aspose.Page को दक्षता और विश्वसनीयता के साथ बड़े पैमाने पर दस्तावेज़ प्रसंस्करण को संभालने के लिए डिज़ाइन किया गया है।

### Q4: क्या मैं PS दस्तावेज़ में टेक्स्ट की स्थिति को संशोधित कर सकता हूँ?

ए4: निश्चित रूप से! जोड़े गए पाठ की स्थिति बदलने के लिए दिए गए उदाहरणों में निर्देशांक समायोजित करें।

### Q5: मैं Aspose.Page-संबंधी प्रश्नों के लिए सहायता कहां से प्राप्त कर सकता हूं?

 A5: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) समुदाय से जुड़ने और विशेषज्ञ की सलाह लेने के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
