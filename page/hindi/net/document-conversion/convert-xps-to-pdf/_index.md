---
title: .NET के लिए Aspose.Page के साथ XPS को PDF में बदलें
linktitle: एक्सपीएस को पीडीएफ में बदलें
second_title: Aspose.Page .NET API
description: Aspose.Page के साथ आसानी से XPS को .NET में PDF में बदलें। लाइब्रेरी डाउनलोड करें, दस्तावेज़ देखें और निःशुल्क परीक्षण प्राप्त करें।
weight: 11
url: /hi/net/document-conversion/convert-xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Page के साथ XPS को PDF में बदलें

## परिचय

इस ट्यूटोरियल में, हम .NET लाइब्रेरी के लिए शक्तिशाली Aspose.Page का उपयोग करके XPS (XML पेपर स्पेसिफिकेशन) दस्तावेज़ों को पीडीएफ (पोर्टेबल दस्तावेज़ प्रारूप) में परिवर्तित करने की प्रक्रिया के बारे में विस्तार से जानेंगे। .NET के लिए Aspose.Page XPS फ़ाइलों के साथ काम करने के लिए सुविधाओं का एक मजबूत सेट प्रदान करता है, जो डेवलपर्स को विभिन्न अनुकूलन विकल्पों के साथ उन्हें पीडीएफ प्रारूप में सहजता से परिवर्तित करने में सक्षम बनाता है।

## आवश्यक शर्तें

इससे पहले कि हम इस रूपांतरण यात्रा को शुरू करें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

-  .NET लाइब्रेरी के लिए Aspose.Page: सुनिश्चित करें कि आपके विकास परिवेश में .NET लाइब्रेरी के लिए Aspose.Page स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose.पेज दस्तावेज़ीकरण](https://reference.aspose.com/page/net/).

- विकास वातावरण: विजुअल स्टूडियो या किसी अन्य संगत आईडीई के साथ एक .NET विकास वातावरण स्थापित करें।

- एक्सपीएस दस्तावेज़: वह एक्सपीएस दस्तावेज़ तैयार करें जिसे आप पीडीएफ में बदलना चाहते हैं। यह निर्दिष्ट निर्देशिका में संग्रहीत आपकी नमूना XPS फ़ाइल हो सकती है।

## नामस्थान आयात करें

कोड में गोता लगाने से पहले, आइए हमारे कोड में .NET कार्यात्मकताओं के लिए Aspose.Page को सुलभ बनाने के लिए आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Page.XPS;
```

## चरण 1: दस्तावेज़ निर्देशिका प्रारंभ करें

```csharp
string dataDir = "Your Document Directory";
```

"आपकी दस्तावेज़ निर्देशिका" को अपने XPS दस्तावेज़ वाली निर्देशिका के पथ से बदलें।

## चरण 2: पीडीएफ और एक्सपीएस स्ट्रीम आरंभ करें

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

आउटपुट पीडीएफ फाइल और इनपुट एक्सपीएस फाइल दोनों के लिए स्ट्रीम खोलें। सुनिश्चित करें कि आपके पास उपयुक्त फ़ाइल पथ सेट हैं।

## चरण 3: एक्सपीएस दस्तावेज़ लोड करें

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

.NET लाइब्रेरी के लिए Aspose.Page का उपयोग करके XPS दस्तावेज़ लोड करें।

## चरण 4: पीडीएफ सेव विकल्प प्रारंभ करें

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

पीडीएफ सेव विकल्प सेट करें, जिसमें जेपीईजी गुणवत्ता स्तर, छवि संपीड़न, पाठ संपीड़न और विशिष्ट पृष्ठ संख्या जैसे पैरामीटर शामिल हों।

## चरण 5: पीडीएफ रेंडरिंग डिवाइस बनाएं

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

.NET लाइब्रेरी के लिए Aspose.Page का उपयोग करके पीडीएफ प्रारूप के लिए एक रेंडरिंग डिवाइस बनाएं।

## चरण 6: दस्तावेज़ को पीडीएफ में सहेजें

```csharp
document.Save(device, options);
```

निर्दिष्ट रेंडरिंग डिवाइस और विकल्पों का उपयोग करके XPS दस्तावेज़ को पीडीएफ में सहेजें।

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके एक XPS दस्तावेज़ को सफलतापूर्वक PDF में परिवर्तित कर लिया है। यह बहुमुखी लाइब्रेरी डेवलपर्स को विभिन्न दस्तावेज़ प्रारूपों को सहजता से संभालने के लिए एक शक्तिशाली टूलसेट प्रदान करती है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं .NET के लिए Aspose.Page का उपयोग करके एकाधिक XPS फ़ाइलों को एक ही PDF में परिवर्तित कर सकता हूँ?

A1: हां, आप कई XPS फ़ाइलों को लूप कर सकते हैं और उन्हें एक ही पीडीएफ में मर्ज करने के लिए समान चरणों का पालन कर सकते हैं।

### Q2: क्या .NET के लिए Aspose.Page द्वारा समर्थित अन्य आउटपुट प्रारूप हैं?

A2: हां, .NET के लिए Aspose.Page TIFF, JPEG, PNG और अन्य सहित विभिन्न आउटपुट स्वरूपों का समर्थन करता है।

### Q3: मैं परिवर्तित पीडीएफ दस्तावेज़ की उपस्थिति को कैसे अनुकूलित कर सकता हूं?

A3: वांछित स्वरूप प्राप्त करने के लिए आप विकल्प ऑब्जेक्ट पैरामीटर, जैसे छवि संपीड़न और पाठ संपीड़न, को बदल सकते हैं।

### Q4: क्या .NET के लिए Aspose.Page का कोई परीक्षण संस्करण उपलब्ध है?

 A4: हाँ, आप निःशुल्क परीक्षण प्राप्त करके .NET के लिए Aspose.Page की क्षमताओं का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).

### Q5: मुझे .NET के लिए Aspose.Page के लिए सामुदायिक समर्थन कहां मिल सकता है?

 A5: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक चर्चा और समर्थन के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
