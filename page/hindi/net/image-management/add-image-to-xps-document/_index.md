---
title: .NET के लिए Aspose.Page के साथ XPS दस्तावेज़ में छवि जोड़ें
linktitle: XPS दस्तावेज़ में छवि जोड़ें
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page के साथ XPS दस्तावेज़ों में छवियों के निर्बाध एकीकरण का अन्वेषण करें। सहज विकास अनुभव के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 11
url: /hi/net/image-management/add-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Page के साथ XPS दस्तावेज़ में छवि जोड़ें

## परिचय

.NET विकास की दुनिया में, XPS दस्तावेज़ों में छवियों को शामिल करना एक सामान्य आवश्यकता है। .NET के लिए Aspose.Page इस प्रक्रिया को सरल बनाता है, XPS दस्तावेज़ों में आसानी से हेरफेर करने और बढ़ाने के लिए एक शक्तिशाली टूलकिट की पेशकश करता है। यह ट्यूटोरियल आपको .NET के लिए Aspose.Page का उपयोग करके XPS दस्तावेज़ में एक छवि जोड़ने के चरणों के माध्यम से मार्गदर्शन करेगा।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1.  .NET लाइब्रेरी के लिए Aspose.Page: लाइब्रेरी को यहां से डाउनलोड और इंस्टॉल करें[Aspose.Page .NET दस्तावेज़ीकरण](https://reference.aspose.com/page/net/).

2. विकास परिवेश: एक .NET विकास परिवेश स्थापित करें, जैसे विज़ुअल स्टूडियो।

3. नमूना छवि: एक नमूना छवि फ़ाइल रखें (उदाहरण के लिए, "QL_logo_color.tif") जिसे आप XPS दस्तावेज़ में जोड़ना चाहते हैं।

## नामस्थान आयात करें

अपने .NET प्रोजेक्ट में आवश्यक नामस्थान आयात करके प्रारंभ करें। ये नामस्थान .NET के लिए Aspose.Page द्वारा प्रदान की गई सुविधाओं का उपयोग करने के लिए महत्वपूर्ण हैं।

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

अपनी दस्तावेज़ निर्देशिका का पथ निर्दिष्ट करके प्रारंभ करें। यह चरण सुनिश्चित करता है कि आपका प्रोजेक्ट जानता है कि फ़ाइलों को कहाँ ढूँढ़ना और सहेजना है।

```csharp
// एक्सस्टार्ट:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

## चरण 2: एक्सपीएस दस्तावेज़ बनाएं

.NET के लिए Aspose.Page का उपयोग करके एक नया XPS दस्तावेज़ बनाएं।

```csharp
// एक्सस्टार्ट:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

## चरण 3: XPS दस्तावेज़ में छवि जोड़ें

अब, छवि को XPS दस्तावेज़ में जोड़ें। इस उदाहरण में, हम "QL_logo_color.tif" नामक एक नमूना छवि का उपयोग करेंगे।

```csharp
// एक्सस्टार्ट:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

## चरण 4: परिणामी XPS दस्तावेज़ सहेजें

जोड़ी गई छवि के साथ XPS दस्तावेज़ सहेजें।

```csharp
// एक्सस्टार्ट:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

अब आपने .NET के लिए Aspose.Page का उपयोग करके XPS दस्तावेज़ में सफलतापूर्वक एक छवि जोड़ दी है!

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया कि XPS दस्तावेज़ों में छवियों को सहजता से शामिल करने के लिए .NET के लिए Aspose.Page का लाभ कैसे उठाया जाए। यह चरण-दर-चरण मार्गदर्शिका आपकी .NET विकास क्षमताओं को बढ़ाते हुए, एक सहज एकीकरण प्रक्रिया सुनिश्चित करती है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या .NET के लिए Aspose.Page नवीनतम .NET फ्रेमवर्क संस्करणों के साथ संगत है?

 A1: .NET के लिए Aspose.Page को नवीनतम रिलीज़ सहित .NET फ्रेमवर्क संस्करणों की एक विस्तृत श्रृंखला के साथ संगत होने के लिए डिज़ाइन किया गया है। को देखें[प्रलेखन](https://reference.aspose.com/page/net/) विशिष्ट विवरण के लिए.

### Q2: क्या मैं Windows और Linux दोनों परिवेशों में .NET के लिए Aspose.Page का उपयोग कर सकता हूँ?

A2: हां, .NET के लिए Aspose.Page प्लेटफ़ॉर्म-स्वतंत्र है, जो इसे विंडोज़ और लिनक्स दोनों वातावरणों में उपयोग के लिए उपयुक्त बनाता है।

### Q3: क्या .NET के लिए Aspose.Page के लिए कोई लाइसेंसिंग विकल्प हैं?

 उ3: हां, आप लाइसेंसिंग विकल्प तलाश सकते हैं और खरीदारी कर सकते हैं[यहाँ](https://purchase.aspose.com/buy).

### Q4: क्या .NET के लिए Aspose.Page का कोई निःशुल्क परीक्षण उपलब्ध है?

 A4: हां, आप एक्सेस करके .NET के लिए Aspose.Page को निःशुल्क आज़मा सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/).

### Q5: मैं .NET के लिए Aspose.Page के लिए कहां सहायता मांग सकता हूं या समुदाय से जुड़ सकता हूं?

 A5: पर जाएँ[.NET फोरम के लिए Aspose.Page](https://forum.aspose.com/c/page/39) समुदाय से जुड़ने और समर्थन प्राप्त करने के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
