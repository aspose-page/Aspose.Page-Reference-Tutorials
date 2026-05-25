---
date: 2026-01-20
description: Aspose.Page for .NET का उपयोग करके XPS दस्तावेज़ों को उच्च‑गुणवत्ता वाले
  PDFs में मर्ज करते हुए PDF में पेज नंबर आसानी से जोड़ें। XPS को PDF में बदलने के
  लिए हमारा चरण‑बद्ध मार्गदर्शक देखें।
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: PDF में पेज नंबर जोड़ें – Aspose.Page का उपयोग करके XPS को PDF में मर्ज करें
url: /hi/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF में पेज नंबर जोड़ें – XPS को PDF में मर्ज करें Aspose.Page का उपयोग करके

## परिचय

यदि आपको XPS फ़ाइलों को मर्ज करते समय **add page numbers PDF** की आवश्यकता है, तो Aspose.Page for .NET प्रक्रिया को बेहद आसान बना देता है। इस ट्यूटोरियल में हम एक पूर्ण, प्रोडक्शन‑रेडी उदाहरण के माध्यम से चलेंगे जो XPS दस्तावेज़ को उच्च‑गुणवत्ता वाले PDF में बदलता है, आपको इमेज कॉम्प्रेशन को नियंत्रित करने देता है, और अंतिम PDF में स्वचालित रूप से पेज नंबर जोड़ता है। अंत तक आपके पास एक पुन: उपयोग योग्य स्निपेट होगा जिसे आप किसी भी C# प्रोजेक्ट में डाल सकते हैं।

## त्वरित उत्तर

- **क्या मैं XPS को PDF में मर्ज करते समय पेज नंबर जोड़ सकता हूँ?** हाँ – `PdfSaveOptions.PageNumbers` प्रॉपर्टी ठीक यही करती है।  
- **कौन सी लाइब्रेरी रूपांतरण संभालती है?** Aspose.Page for .NET.  
- **क्या प्रोडक्शन उपयोग के लिए लाइसेंस चाहिए?** एक वैध Aspose.Page लाइसेंस आवश्यक है; परीक्षण के लिए एक अस्थायी लाइसेंस उपलब्ध है।  
- **कौन‑से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, और .NET 5/6+.  
- **क्या हाई‑क्वालिटी इमेज आउटपुट संभव है?** बिल्कुल – `JpegQualityLevel` को 100 सेट करें और `PdfImageCompression.Jpeg` चुनें।

## पूर्वापेक्षाएँ

ट्यूटोरियल में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- Aspose.Page for .NET: सुनिश्चित करें कि आपके पास Aspose.Page लाइब्रेरी स्थापित है। आप इसे [here](https://releases.aspose.com/page/net/) से डाउनलोड कर सकते हैं।

- दस्तावेज़ फ़ाइलें: अपने निर्दिष्ट डायरेक्टरी में XPS दस्तावेज़ (`input.xps`) तैयार रखें।

## नेमस्पेस इम्पोर्ट करें

अपने .NET प्रोजेक्ट में, Aspose.Page के साथ काम करने के लिए आवश्यक नेमस्पेस शामिल करें:

```csharp
using Aspose.Page.XPS;
```

यह कदम सुनिश्चित करता है कि आपके पास दस्तावेज़ रूपांतरण के लिए आवश्यक क्लास और मेथड्स तक पहुँच है।

## XPS दस्तावेज़ों को मर्ज करते समय PDF में पेज नंबर कैसे जोड़ें

`PdfSaveOptions.PageNumbers` कलेक्शन आपको यह निर्दिष्ट करने देता है कि आउटपुट PDF में कौन‑से पेज (या पेज रेंज) दिखेंगे। इसे इच्छित पेज नंबरों से भरने पर Aspose.Page स्वचालित रूप से सही क्रमांक जोड़ देता है।

### चरण 1: स्ट्रीम्स को इनिशियलाइज़ करें

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

यह कदम XPS और PDF फ़ाइलों के लिए इनपुट और आउटपुट स्ट्रीम्स सेट अप करने से संबंधित है। सही पाथ और फ़ाइल नामों का उपयोग सुनिश्चित करें।

### चरण 2: XPS दस्तावेज़ लोड करें

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

यहाँ हम XPS दस्तावेज़ को `XpsDocument` ऑब्जेक्ट में लोड करते हैं, जिससे आगे की प्रोसेसिंग के लिए तैयार हो जाता है।

### चरण 3: सेव ऑप्शन्स को इनिशियलाइज़ करें (XPS को PDF में मर्ज करें)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

अपनी पसंद के अनुसार `PdfSaveOptions` ऑब्जेक्ट को कस्टमाइज़ करें, जिसमें इमेज कॉम्प्रेशन, टेक्स्ट कॉम्प्रेशन, और **page numbers** जैसे पैरामीटर शामिल हों जो अंतिम PDF में दिखेंगे। `JpegQualityLevel` को 100 सेट करने से **high quality PDF images** सुनिश्चित होते हैं।

### चरण 4: रेंडरिंग डिवाइस बनाएं

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice` वह टूल है जो XPS दस्तावेज़ को PDF फॉर्मेट में रेंडर करने के लिए ज़िम्मेदार है।

### चरण 5: दस्तावेज़ को सहेजें (C# XPS से PDF)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

अंत में, रेंडरिंग डिवाइस और निर्दिष्ट विकल्पों का उपयोग करके दस्तावेज़ को सहेजें। आउटपुट PDF में चयनित पेज स्वचालित रूप से जोड़े गए पेज नंबरों के साथ होंगे।

## इस रूपांतरण के लिए Aspose.Page का उपयोग क्यों करें?

- **विश्वसनीयता** – जटिल XPS फीचर्स को बिना गुणवत्ता खोए संभालता है।  
- **प्रदर्शन** – स्ट्रीम‑आधारित प्रोसेसिंग पूरी फ़ाइलों को मेमोरी में लोड करने से बचाती है।  
- **लचीलापन** – इमेज क्वालिटी, कॉम्प्रेशन, और पेज नंबरिंग पर सूक्ष्म नियंत्रण।  
- **क्रॉस‑प्लेटफ़ॉर्म** – .NET Core के साथ Windows, Linux, और macOS पर काम करता है।

## सामान्य समस्याएँ और समाधान

| समस्या | समाधान |
|-------|----------|
| **आउटपुट PDF खाली है** | जांचें कि XPS फ़ाइल पाथ सही है और फ़ाइल करप्ट नहीं है। |
| **पेज नंबर नहीं दिख रहे हैं** | सुनिश्चित करें कि `PageNumbers` सही ज़ीरो‑बेस्ड पेज इंडेक्स पर सेट है (उदा., `new int[] {1,2,6}`)। |
| **कम गुणवत्ता वाली इमेजेज** | `JpegQualityLevel` बढ़ाएँ और `PdfImageCompression.Jpeg` चुनें। |
| **बड़े XPS फ़ाइलें मेमोरी पर दबाव डालती हैं** | XPS को छोटे हिस्सों में प्रोसेस करें या एप्लिकेशन की मेमोरी सीमा बढ़ाएँ। |

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं कई XPS फ़ाइलों को एक ही PDF में मर्ज कर सकता हूँ?

A1: हाँ, आप कर सकते हैं। बस `PdfSaveOptions` में `PageNumbers` पैरामीटर को समायोजित करें ताकि विभिन्न XPS फ़ाइलों से इच्छित पेज शामिल हों, या प्रत्येक XPS को क्रमिक रूप से लोड करें और उसी `PdfDevice` पर `document.Save` कॉल करें।

### Q2: क्या Aspose.Page for .NET के लिए एक अस्थायी लाइसेंस उपलब्ध है?

A2: हाँ, आप परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

### Q3: क्या Aspose.Page का उपयोग करके दस्तावेज़ रूपांतरण में फ़ाइल आकार पर कोई सीमाएँ हैं?

A3: Aspose.Page for .NET फ़ाइल आकार पर सख्त सीमाएँ नहीं लगाता, लेकिन उचित आकार की फ़ाइलों के साथ सर्वोत्तम प्रदर्शन मिलता है। बहुत बड़े XPS दस्तावेज़ों के लिए, मेमोरी खपत कम करने हेतु उन्हें स्ट्रीम में प्रोसेस करने पर विचार करें।

### Q4: क्या मैं आउटपुट PDF को आगे कस्टमाइज़ कर सकता हूँ, जैसे वाटरमार्क या एनोटेशन जोड़ना?

A4: हाँ, Aspose.Page for .NET PDF मैनिपुलेशन के लिए व्यापक सुविधाएँ प्रदान करता है। रूपांतरण के बाद, आप Aspose.PDF लाइब्रेरी का उपयोग करके वाटरमार्क, एनोटेशन या अन्य सुधार जोड़ सकते हैं।

### Q5: क्या Aspose.Page for .NET क्रॉस‑प्लेटफ़ॉर्म विकास का समर्थन करता है?

A5: हाँ, Aspose.Page for .NET विभिन्न प्लेटफ़ॉर्म, जैसे Windows, Linux, और macOS, पर .NET Core या .NET 5/6 के साथ सहजता से काम करने के लिए डिज़ाइन किया गया है।

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}