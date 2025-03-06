---
title: .NET के लिए Aspose.Page के साथ EPS छवियाँ क्रॉप करें
linktitle: ईपीएस छवियाँ काटें
second_title: Aspose.Page .NET API
description: Aspose.Page के साथ .NET में EPS छवि हेरफेर की निर्बाध दुनिया का अन्वेषण करें। आश्चर्यजनक परिणामों के लिए छवियों को सहजता से काटें और आकार बदलें।
weight: 10
url: /hi/net/image-manipulation/crop-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Page के साथ EPS छवियाँ क्रॉप करें

## परिचय

क्या आप अपने .NET अनुप्रयोगों में ईपीएस छवियों में हेरफेर करने से जूझ रहे हैं? आगे कोई तलाश नहीं करें! इस ट्यूटोरियल में, हम .NET लाइब्रेरी के लिए शक्तिशाली Aspose.Page का उपयोग करके ईपीएस छवियों को क्रॉप करने की प्रक्रिया में आपका मार्गदर्शन करेंगे। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, यह चरण-दर-चरण मार्गदर्शिका आपको सहजता से सटीक छवि क्रॉपिंग प्राप्त करने में मदद करेगी।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- .NET विकास का कार्यसाधक ज्ञान।
-  .NET लाइब्रेरी के लिए Aspose.Page स्थापित किया गया। यदि नहीं, तो आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).
- एक नमूना ईपीएस छवि (कोड में "input.eps" को अपनी वास्तविक फ़ाइल से बदलें)।

## नामस्थान आयात करें

आइए अपने कोड को सुचारू रूप से चलाने के लिए आवश्यक नामस्थान आयात करके शुरुआत करें। 

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

अब, आइए ट्यूटोरियल को कई चरणों में विभाजित करें।

## चरण 1: PsDocument आरंभ करें

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

 आरंभ करें a`PsDocument` इनपुट ईपीएस स्ट्रीम के साथ ऑब्जेक्ट।

## चरण 2: बाउंडिंग बॉक्स निकालें

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

ईपीएस छवि के प्रारंभिक बाउंडिंग बॉक्स को पुनः प्राप्त करें।

## चरण 3: आउटपुट स्ट्रीम बनाएं

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

क्रॉप की गई ईपीएस छवि के लिए एक आउटपुट स्ट्रीम बनाएं।

## चरण 4: नए बाउंडिंग बॉक्स को परिभाषित करें

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

क्रॉपिंग के लिए एक नया बाउंडिंग बॉक्स परिभाषित करें। सुनिश्चित करें कि नए मान प्रारंभिक बाउंडिंग बॉक्स के भीतर हैं।

## चरण 5: काटें और बचाएं

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

नए बाउंडिंग बॉक्स का उपयोग करके ईपीएस छवि को क्रॉप करें और इसे आउटपुट स्ट्रीम में सहेजें।

विभिन्न आकार बदलने वाले परिदृश्यों के लिए इन चरणों को दोहराएं।

## ईपीएस छवियों का आकार बदलना

### इंच में आकार बदलें

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

ईपीएस छवि का आकार बदलें और इसे इंच में निर्दिष्ट आयामों के साथ सहेजें।

### मिलीमीटर में आकार बदलें

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

ईपीएस छवि का आकार बदलें और इसे मिलीमीटर में निर्दिष्ट आयामों के साथ सहेजें।

### प्रतिशत में आकार बदलें

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

ईपीएस छवि का आकार बदलें और इसे निर्दिष्ट आयामों के साथ प्रतिशत में सहेजें।

## निष्कर्ष

बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.Page का उपयोग करके EPS छवियों को कैसे क्रॉप और आकार दिया जाए। अब, अपनी छवि हेरफेर क्षमताओं को बढ़ाएं और अपने .NET अनुप्रयोगों को अगले स्तर पर लाएं।

## पूछे जाने वाले प्रश्न

### Q1: क्या मैं अन्य छवि प्रारूपों के साथ .NET के लिए Aspose.Page का उपयोग कर सकता हूँ?

A1: Aspose.Page मुख्य रूप से EPS छवियों पर केंद्रित है, लेकिन Aspose विभिन्न प्रारूपों के लिए विभिन्न लाइब्रेरी प्रदान करता है। विशिष्ट प्रारूपों के लिए उनके दस्तावेज़ की जाँच करें।

### Q2: मैं .NET के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 ए2: विजिट करें[इस लिंक](https://purchase.aspose.com/temporary-license/) परीक्षण के लिए अस्थायी लाइसेंस प्राप्त करना।

### Q3: क्या छवि आकार की कोई सीमाएँ हैं जिन्हें मैं .NET के लिए Aspose.Page के साथ संसाधित कर सकता हूँ?

A3: Aspose.Page को विभिन्न आकारों की छवियों को संभालने के लिए डिज़ाइन किया गया है। हालाँकि, छवि की जटिलता के आधार पर प्रदर्शन भिन्न हो सकता है।

### Q4: क्या Aspose.Page चर्चाओं के लिए कोई सामुदायिक मंच है?

 A4: हां, आप Aspose.Page समुदाय से जुड़ सकते हैं[यहाँ](https://forum.aspose.com/c/page/39).

### Q5: मुझे .NET के लिए Aspose.Page के लिए विस्तृत दस्तावेज़ कहां मिल सकते हैं?

 A5: दस्तावेज़ देखें[यहाँ](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
