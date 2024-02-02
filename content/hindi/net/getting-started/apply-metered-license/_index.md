---
title: .NET के लिए Aspose.Page के साथ मीटर्ड लाइसेंस लागू करें
linktitle: मीटरयुक्त लाइसेंस लागू करें
second_title: Aspose.Page .NET API
description: मीटर्ड लाइसेंस लागू करने पर इस चरण-दर-चरण मार्गदर्शिका के साथ .NET के लिए Aspose.Page के निर्बाध एकीकरण का अन्वेषण करें। दस्तावेज़ प्रसंस्करण को सहजता से अनुकूलित करें।
type: docs
weight: 10
url: /hi/net/getting-started/apply-metered-license/
---
## परिचय

मीटर्ड लाइसेंस लागू करके .NET के लिए Aspose.Page की पूरी क्षमता को अनलॉक करें। यह ट्यूटोरियल इस शक्तिशाली .NET लाइब्रेरी के सुचारू और अनुकूलित उपयोग को सुनिश्चित करते हुए, मीटर्ड लाइसेंस को स्थापित करने और लागू करने की प्रक्रिया में आपका मार्गदर्शन करेगा।

## आवश्यक शर्तें

चरणों में उतरने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET लाइसेंस के लिए एक वैध Aspose.Page: आप इसे यहां से प्राप्त कर सकते हैं[buy.aspose.com](https://purchase.aspose.com/buy).
-  Aspose.Page लाइब्रेरी स्थापित: देखें[प्रलेखन](https://reference.aspose.com/page/net/) स्थापना निर्देशों के लिए.
- .NET विकास वातावरण: सुनिश्चित करें कि आपकी मशीन पर एक कार्यशील .NET वातावरण स्थापित है।

## नामस्थान आयात करें

अपने .NET प्रोजेक्ट में, Aspose.Page कार्यात्मकताओं तक पहुँचने के लिए आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## चरण 1: मीटरयुक्त सार्वजनिक और निजी कुंजी सेट करें

 को आरंभ करें`Aspose.Page.Metered` क्लास करें और मीटर वाली सार्वजनिक और निजी कुंजियाँ सेट करें। प्रतिस्थापित करें`<type public key here>` और`<type private key here>` आपकी वास्तविक कुंजियों के साथ।

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## चरण 2: ईपीएस फ़ाइल लोड करें और दस्तावेज़ बनाएं

 अपनी ईपीएस फ़ाइल का पथ निर्दिष्ट करें और इसकी सामग्री को पढ़ने के लिए एक स्ट्रीम बनाएं। फिर, का एक उदाहरण बनाएं`PsDocument` धारा से कक्षा.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## चरण 3: ईपीएस को पीएनजी छवि में बदलें

 एक बनाएं`ImageDevice` ईपीएस फ़ाइल को पीएनजी छवि में परिवर्तित करने के लिए। का उपयोग करके ईपीएस फ़ाइल को एक छवि के रूप में सहेजें`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## चरण 4: छवि बाइट्स पुनर्प्राप्त करें

छवि बाइट्स प्राप्त करें, जहां प्रत्येक बाइट सरणी एक पृष्ठ का प्रतिनिधित्व करती है। इस मामले में, हमारे पास एक पेज है।

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## चरण 5: छवि बाइट्स को फ़ाइल में सहेजें

ईपीएस से पीएनजी में सफल रूपांतरण सुनिश्चित करते हुए, छवि बाइट्स को एक फ़ाइल में सहेजें।

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## चरण 6: मीटर्ड लाइसेंस सत्यापित करें

दृष्टिगत रूप से जांचें कि मीटर्ड लाइसेंस सफलतापूर्वक लागू हुआ है या नहीं। यदि परिणामी छवि में लाल मूल्यांकन संदेश नहीं है, तो यह इंगित करता है कि मीटर्ड लाइसेंस बिना किसी समस्या के लागू किया गया है।

अब आप मीटर्ड लाइसेंस के साथ .NET के लिए Aspose.Page की पूर्ण क्षमताओं का लाभ उठाने के लिए तैयार हैं!

## निष्कर्ष

इस चरण-दर-चरण मार्गदर्शिका ने आपको .NET के लिए Aspose.Page का उपयोग करके मीटर्ड लाइसेंस को निर्बाध रूप से लागू करने के ज्ञान से सुसज्जित किया है। अपनी दस्तावेज़ प्रसंस्करण क्षमताओं को बढ़ाएं और इस शक्तिशाली लाइब्रेरी द्वारा प्रदान की जाने वाली विशाल सुविधाओं का पता लगाएं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: मैं .NET के लिए Aspose.Page के लिए मीटर्ड लाइसेंस कैसे प्राप्त कर सकता हूँ?

 A1: यात्रा[buy.aspose.com](https://purchase.aspose.com/buy) वैध लाइसेंस प्राप्त करने के लिए.

### Q2: मुझे .NET के लिए Aspose.Page का दस्तावेज़ कहां मिल सकता है?

 ए2: देखें[Aspose.पेज .NET](https://reference.aspose.com/page/net/) व्यापक दस्तावेज़ीकरण के लिए.

### Q3: क्या Aspose.Page पर चर्चा और समर्थन के लिए कोई मंच है?

 A3: हाँ, पधारें[मंच](https://forum.aspose.com/c/page/39) समुदाय के साथ जुड़ना और सहायता प्राप्त करना।

### Q4: क्या मैं खरीदने से पहले .NET के लिए Aspose.Page आज़मा सकता हूँ?

 उ4: बिल्कुल! निःशुल्क परीक्षण तक पहुंचें[यहाँ](https://releases.aspose.com/).

### Q5: मैं .NET के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 ए5: विजिट करें[अस्थायी लाइसेंस/](https://purchase.aspose.com/temporary-license/) अस्थायी लाइसेंस प्राप्त करने के लिए.