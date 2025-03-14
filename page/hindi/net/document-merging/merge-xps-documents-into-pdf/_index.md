---
title: .NET के लिए Aspose.Page के साथ XPS दस्तावेज़ों को PDF में मर्ज करें
linktitle: XPS दस्तावेज़ों को पीडीएफ में मर्ज करें
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page का उपयोग करके आसानी से XPS दस्तावेज़ों को उच्च-गुणवत्ता वाले PDF में मर्ज करें। सहज दस्तावेज़ रूपांतरण अनुभव के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 11
url: /hi/net/document-merging/merge-xps-documents-into-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Page के साथ XPS दस्तावेज़ों को PDF में मर्ज करें

## परिचय

दस्तावेज़ प्रसंस्करण के लगातार विकसित हो रहे परिदृश्य में, .NET के लिए Aspose.Page XPS दस्तावेज़ों को पीडीएफ प्रारूप में निर्बाध रूप से विलय करने के लिए एक शक्तिशाली उपकरण के रूप में उभरता है। यह ट्यूटोरियल आपको प्रक्रिया के माध्यम से मार्गदर्शन करेगा, एक सुचारू और प्रभावी निष्पादन सुनिश्चित करने के लिए प्रत्येक चरण का विवरण देगा।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET के लिए Aspose.Page: सुनिश्चित करें कि आपके पास Aspose.Page लाइब्रेरी स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).

- दस्तावेज़ फ़ाइलें: XPS दस्तावेज़ रखें (`input.xps`) आपकी निर्दिष्ट निर्देशिका में तैयार है।

## नामस्थान आयात करें

अपने .NET प्रोजेक्ट में, Aspose.Page के साथ काम करने के लिए आवश्यक नेमस्पेस शामिल करें:

```csharp
using Aspose.Page.XPS;
```

यह चरण सुनिश्चित करता है कि आपके पास दस्तावेज़ रूपांतरण के लिए आवश्यक कक्षाओं और विधियों तक पहुंच है।

## चरण 1: स्ट्रीम प्रारंभ करें

```csharp
// एक्सस्टार्ट:3
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
// पीडीएफ आउटपुट स्ट्रीम आरंभ करें
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// XPS इनपुट स्ट्रीम प्रारंभ करें
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

इस चरण में XPS और PDF फ़ाइलों के लिए इनपुट और आउटपुट स्ट्रीम सेट करना शामिल है। सुनिश्चित करें कि सही पथ और फ़ाइल नाम का उपयोग किया गया है।

## चरण 2: एक्सपीएस दस्तावेज़ लोड करें

```csharp
// एक्सस्टार्ट:4
// स्ट्रीम के रूप में XPS दस्तावेज़ लोड करें
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// या XPS दस्तावेज़ को सीधे फ़ाइल से लोड करें। तब किसी xpsStream की आवश्यकता नहीं है।
//XpsDocument दस्तावेज़ = नया XpsDocument(inputFileName, नया XpsLoadOptions());
// ExEnd:4
```

 यहां, हम XPS दस्तावेज़ को इसमें लोड करते हैं`XpsDocument` वस्तु, इसे आगे की प्रक्रिया के लिए तैयार करना।

## चरण 3: सहेजें विकल्प आरंभ करें

```csharp
// एक्सस्टार्ट:5
// आवश्यक मापदंडों के साथ विकल्प ऑब्जेक्ट को आरंभ करें।
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// ExEnd:5
```

 अनुकूलित करें`PdfSaveOptions` आपकी प्राथमिकताओं के आधार पर ऑब्जेक्ट, छवि संपीड़न, पाठ संपीड़न और पृष्ठ संख्या जैसे पैरामीटर निर्दिष्ट करता है।

## चरण 4: रेंडरिंग डिवाइस बनाएं

```csharp
// एक्सस्टार्ट:6
// पीडीएफ प्रारूप के लिए रेंडरिंग डिवाइस बनाएं
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice` XPS दस्तावेज़ को पीडीएफ प्रारूप में प्रस्तुत करने के लिए जिम्मेदार उपकरण है।

## चरण 5: दस्तावेज़ सहेजें

```csharp
// एक्सस्टार्ट:7
document.Save(device, options);
// ExEnd:7
```

अंत में, रेंडरिंग डिवाइस और निर्दिष्ट विकल्पों का उपयोग करके दस्तावेज़ को सहेजें।

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके XPS दस्तावेज़ों को PDF में सफलतापूर्वक मर्ज कर दिया है। यह निर्बाध प्रक्रिया दस्तावेज़ की गुणवत्ता और स्वरूपण के संरक्षण को सुनिश्चित करती है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं एकाधिक XPS फ़ाइलों को एक ही PDF में मर्ज कर सकता हूँ?

 A1: हाँ, आप कर सकते हैं। बस समायोजित करें`PageNumbers` में पैरामीटर`PdfSaveOptions` विभिन्न XPS फ़ाइलों से वांछित पृष्ठ शामिल करने के लिए।

### Q2: क्या .NET के लिए Aspose.Page के लिए एक अस्थायी लाइसेंस उपलब्ध है?

 उ2: हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/) परीक्षण प्रयोजनों के लिए.

### Q3: क्या दस्तावेज़ रूपांतरण के लिए Aspose.Page का उपयोग करते समय फ़ाइल आकार पर कोई सीमाएँ हैं?

A3: .NET के लिए Aspose.Page फ़ाइल आकार पर सख्त सीमाएं नहीं लगाता है, लेकिन उचित फ़ाइल आकार के साथ इष्टतम प्रदर्शन प्राप्त किया जाता है।

### Q4: क्या मैं आउटपुट पीडीएफ को और अधिक अनुकूलित कर सकता हूं, जैसे वॉटरमार्क या एनोटेशन जोड़ना?

A4: हाँ, .NET के लिए Aspose.Page PDF हेरफेर के लिए व्यापक सुविधाएँ प्रदान करता है। उन्नत अनुकूलन विकल्पों के लिए दस्तावेज़ की जाँच करें।

### Q5: क्या .NET के लिए Aspose.Page क्रॉस-प्लेटफ़ॉर्म विकास का समर्थन करता है?

A5: हां, .NET के लिए Aspose.Page को विभिन्न प्लेटफार्मों पर निर्बाध रूप से काम करने के लिए डिज़ाइन किया गया है।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
