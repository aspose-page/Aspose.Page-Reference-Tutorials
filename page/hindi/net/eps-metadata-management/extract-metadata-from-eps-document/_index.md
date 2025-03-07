---
title: .NET के लिए Aspose.Page के साथ EPS दस्तावेज़ से मेटाडेटा निकालें
linktitle: ईपीएस दस्तावेज़ से मेटाडेटा निकालें
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page के साथ EPS दस्तावेज़ संगठन को बेहतर बनाएं। बेहतर पहुंच और सूचना पुनर्प्राप्ति के लिए आसानी से मेटाडेटा जोड़ें।
weight: 18
url: /hi/net/eps-metadata-management/extract-metadata-from-eps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Page के साथ EPS दस्तावेज़ से मेटाडेटा निकालें

## परिचय

डिजिटल दस्तावेज़ों के लगातार विकसित हो रहे परिदृश्य में, मेटाडेटा सामग्री, इसकी उत्पत्ति और अन्य आवश्यक विवरणों के बारे में जानकारी प्रदान करने में महत्वपूर्ण भूमिका निभाता है। .NET के लिए Aspose.Page डेवलपर्स को EPS (एनकैप्सुलेटेड पोस्टस्क्रिप्ट) दस्तावेजों में मेटाडेटा को सहजता से जोड़ने का अधिकार देता है, जिससे उनकी पहुंच और उपयोगिता बढ़ जाती है।

## आवश्यक शर्तें

इससे पहले कि हम चरण-दर-चरण मार्गदर्शिका में गहराई से उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET लाइब्रेरी के लिए Aspose.Page: .NET लाइब्रेरी के लिए Aspose.Page को यहां से डाउनलोड और इंस्टॉल करें।[यहाँ](https://releases.aspose.com/page/net/).
- दस्तावेज़ निर्देशिका: एक निर्देशिका स्थापित करें जहाँ आपके ईपीएस दस्तावेज़ संग्रहीत हैं।

## नामस्थान आयात करें

अपने .NET प्रोजेक्ट में, Aspose.Page की क्षमताओं का लाभ उठाने के लिए आवश्यक नेमस्पेस शामिल करें। निम्नलिखित नामस्थान आयात करें:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

आइए ईपीएस दस्तावेज़ में मेटाडेटा जोड़ने की प्रक्रिया को कई चरणों में विभाजित करें:

## चरण 1: ईपीएस फ़ाइल इनपुट स्ट्रीम प्रारंभ करें

```csharp
// एक्सस्टार्ट:3
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:3
```

## चरण 2: एक्सएमपी मेटाडेटा प्राप्त करें

```csharp
// एक्सस्टार्ट:4
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

## चरण 3: मेटाडेटा मान जांचें और सेट करें

पीएस मेटाडेटा टिप्पणियों से निकाले गए मेटाडेटा मानों की जांच करें और नए एक्सएमपी मेटाडेटा में सेट करें।

### क्रिएटरटूल मूल्य प्राप्त करें

```csharp
// एक्सस्टार्ट:5
if (xmp.Contains("xmp:CreatorTool"))
    Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());
// ExEnd:5
```

### CreateDate मान प्राप्त करें

```csharp
// एक्सस्टार्ट:6
if (xmp.Contains("xmp:CreateDate"))
    Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());
// ExEnd:6
```

### प्रारूप मान प्राप्त करें

```csharp
// एक्सस्टार्ट:7
if (xmp.Contains("dc:format"))
    Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());
// ExEnd:7
```

### शीर्षक मान प्राप्त करें

```csharp
// एक्सस्टार्ट:8
if (xmp.Contains("dc:title"))
    Console.WriteLine("Title: " + xmp["dc:title"].ToArray()[0].ToStringValue());
// ExEnd:8
```

### निर्माता मूल्य प्राप्त करें

```csharp
// एक्सस्टार्ट:9
if (xmp.Contains("dc:creator"))
    Console.WriteLine("Creator: " + xmp["dc:creator"].ToArray()[0].ToStringValue());
// ExEnd:9
```

### मेटाडेटाडेट मान प्राप्त करें

```csharp
// एक्सस्टार्ट:10
if (xmp.Contains("xmp:MetadataDate"))
    Console.WriteLine("MetadataDate: " + xmp["xmp:MetadataDate"].ToStringValue());
// ExEnd:10
```

## चरण 4: ईपीएस फ़ाइल को नए एक्सएमपी मेटाडेटा के साथ सहेजें

```csharp
// एक्सस्टार्ट:11
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
// ExEnd:11
```

## निष्कर्ष

ईपीएस दस्तावेजों में मेटाडेटा जोड़ना उनके संगठन और पहुंच को बढ़ाने में एक महत्वपूर्ण कदम है। .NET के लिए Aspose.Page के साथ, यह प्रक्रिया सुव्यवस्थित और कुशल हो जाती है, जिससे डेवलपर्स आसानी से मेटाडेटा प्रबंधित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं एक साथ कई ईपीएस दस्तावेज़ों में मेटाडेटा जोड़ सकता हूँ?

उ1: हां, आप ईपीएस दस्तावेज़ों के संग्रह के माध्यम से पुनरावृति कर सकते हैं और प्रत्येक फ़ाइल में मेटाडेटा निष्कर्षण और जोड़ने की प्रक्रिया लागू कर सकते हैं।

### Q2: क्या EPS दस्तावेज़ों के आकार पर कोई सीमाएँ हैं जिन्हें .NET के लिए Aspose.Page संभाल सकता है?

A2: .NET के लिए Aspose.Page को विभिन्न आकारों के EPS दस्तावेज़ों को संभालने के लिए डिज़ाइन किया गया है। हालाँकि, असाधारण बड़ी फ़ाइलों के लिए मेमोरी उपयोग की निगरानी करने की अनुशंसा की जाती है।

### Q3: क्या XMP मेटाडेटा सभी EPS दस्तावेज़ों के लिए मानकीकृत है?

A3: XMP मेटाडेटा एक मानक संरचना का अनुसरण करता है, लेकिन इसकी सामग्री निर्माता और दस्तावेज़ के निर्माण के दौरान प्रदान की गई जानकारी के आधार पर भिन्न हो सकती है।

### Q4: क्या मैं विशिष्ट आवश्यकताओं के अनुरूप मेटाडेटा फ़ील्ड को अनुकूलित कर सकता हूँ?

A4: हाँ, .NET के लिए Aspose.Page आपके एप्लिकेशन की आवश्यकताओं के अनुसार मेटाडेटा फ़ील्ड को अनुकूलित करने में लचीलापन प्रदान करता है।

### Q5: मैं मेटाडेटा जोड़ने की प्रक्रिया के दौरान त्रुटियों को कैसे संभाल सकता हूं?

A5: मेटाडेटा निष्कर्षण और परिवर्धन प्रक्रिया के दौरान किसी भी संभावित त्रुटि को संबोधित करने के लिए अपने कोड में उचित अपवाद प्रबंधन सुनिश्चित करें।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
