---
title: .NET के लिए Aspose.Page के साथ XPS दस्तावेज़ में आयत जोड़ें
linktitle: XPS दस्तावेज़ में आयत जोड़ें
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page के साथ दस्तावेज़ निर्माण बढ़ाएँ। इस चरण-दर-चरण ट्यूटोरियल में जानें कि XPS दस्तावेज़ों में आयत कैसे जोड़ें।
weight: 13
url: /hi/net/drawing-shapes/add-rectangle-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Page के साथ XPS दस्तावेज़ में आयत जोड़ें

## परिचय

.NET के लिए Aspose.Page एक शक्तिशाली लाइब्रेरी है जो .NET अनुप्रयोगों में XPS (XML पेपर विशिष्टता) दस्तावेज़ों के साथ काम करने के लिए विभिन्न प्रकार की सुविधाएँ प्रदान करती है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.Page का उपयोग करके XPS दस्तावेज़ में एक आयत जोड़ने पर ध्यान केंद्रित करेंगे। अपनी दस्तावेज़ निर्माण प्रक्रिया को बेहतर बनाने के लिए इस चरण-दर-चरण मार्गदर्शिका का पालन करें।

## आवश्यक शर्तें

इस ट्यूटोरियल को शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1.  .NET लाइब्रेरी के लिए Aspose.Page: सुनिश्चित करें कि आपके विकास परिवेश में .NET लाइब्रेरी के लिए Aspose.Page स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).

2. दस्तावेज़ निर्देशिका: एक निर्देशिका सेट करें जहाँ आप अपने XPS दस्तावेज़ संग्रहीत करना चाहते हैं।

## नामस्थान आयात करें

अपने .NET एप्लिकेशन में, Aspose.Page कार्यात्मकताओं का उपयोग करने के लिए आवश्यक नामस्थान शामिल करें।

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

```csharp
// एक्सस्टार्ट:3
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## चरण 2: एक नया XPS दस्तावेज़ बनाएँ

```csharp
// एक्सस्टार्ट:4
// नया XPS दस्तावेज़ बनाएं
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## चरण 3: एक आयत जोड़ें

```csharp
// एक्सस्टार्ट:5
// निचले बाएँ भाग में CMYK (नीला) ठोस रंग का स्ट्रोक किया हुआ आयत
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

## चरण 4: दस्तावेज़ सहेजें

```csharp
// एक्सस्टार्ट:6
// परिणामी XPS दस्तावेज़ सहेजें
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके XPS दस्तावेज़ में सफलतापूर्वक एक आयत जोड़ा है।

## निष्कर्ष

.NET के लिए Aspose.Page दस्तावेज़ हेरफेर कार्यों को सरल बनाता है, जिससे डेवलपर्स को आसानी से XPS दस्तावेज़ बनाने और संशोधित करने की अनुमति मिलती है। यह चरण-दर-चरण मार्गदर्शिका दर्शाती है कि अपने XPS दस्तावेज़ में एक आयत कैसे जोड़ें, जो आगे की खोज के लिए एक ठोस आधार प्रदान करता है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.Page सभी .NET अनुप्रयोगों के साथ संगत है?

A1: हां, Aspose.Page को सभी .NET अनुप्रयोगों के साथ निर्बाध रूप से काम करने के लिए डिज़ाइन किया गया है।

### Q2: मुझे .NET के लिए Aspose.Page का दस्तावेज़ कहां मिल सकता है?

 A2: दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/page/net/).

### Q3: क्या मैं खरीदने से पहले .NET के लिए Aspose.Page को मुफ़्त में आज़मा सकता हूँ?

 उ3: हाँ, आप निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q4: मैं .NET के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 ए4: विजिट करें[इस लिंक](https://purchase.aspose.com/temporary-license/) अस्थायी लाइसेंस प्राप्त करने के लिए.

### Q5: मैं सामुदायिक समर्थन कहां प्राप्त कर सकता हूं या .NET के लिए Aspose.Page से संबंधित प्रश्न कहां पूछ सकता हूं?

 A5: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक समर्थन के लिए.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
