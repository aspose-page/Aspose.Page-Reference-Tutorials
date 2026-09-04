---
date: 2026-06-30
description: Aspose.Page for .NET का उपयोग करके PostScript दस्तावेज़ .NET कैसे बनाएं
  और Rectangle जोड़ें, यह सीखें। कोड नमूनों के साथ चरण-दर-चरण गाइड।
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: PostScript (PS) में Rectangle जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: PostScript दस्तावेज़ .NET बनाएं – Aspose.Page के साथ Rectangle जोड़ें
url: /hi/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET के साथ PostScript (PS) में आयत जोड़ें

## परिचय

Aspose.Page for .NET एक लाइब्रेरी है जो प्रोग्रामेटिक रूप से PostScript, EPS, और XPS फ़ाइलों का निर्माण और हेरफेर सक्षम करती है। यदि आप **create postscript document .net** की तलाश में हैं, तो यह ट्यूटोरियल Aspose.Page का उपयोग करके PostScript दस्तावेज़ में आयतें जोड़ने की प्रक्रिया दिखाता है, जिससे आपको अधिक समृद्ध ग्राफ़िक्स जनरेशन के लिए एक ठोस आधार मिलता है।

## त्वरित उत्तर
- **मुझे कौनसी लाइब्रेरी चाहिए?** Aspose.Page for .NET.  
- **क्या मैं शून्य से PostScript दस्तावेज़ बना सकता हूँ?** Yes – the API lets you build PS files programmatically.  
- **कौनसे .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **क्या विकास के लिए लाइसेंस चाहिए?** A free trial works for testing; a license is required for production.  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** Typically under 10 minutes for basic shapes.

## Postscript दस्तावेज़ .net बनाना क्या है?
PostScript दस्तावेज़ .net बनाना का मतलब है .NET में प्रोग्रामेटिक रूप से एक `.ps` फ़ाइल उत्पन्न करना जो पृष्ठ सामग्री—टेक्स्ट, ग्राफ़िक्स, या आकार—को Aspose.Page API का उपयोग करके वर्णित करती है। यह तरीका सर्वर‑साइड ग्राफ़िक्स जनरेशन, स्वचालित रिपोर्ट निर्माण, या किसी भी स्थिति के लिए आदर्श है जहाँ आपको आउटपुट फ़ॉर्मेट पर सटीक नियंत्रण चाहिए।

## Aspose.Page for .NET का उपयोग क्यों करें?
Aspose.Page **30+ ग्राफ़िक्स प्रिमिटिव्स** का समर्थन करता है और पूरी दस्तावेज़ को मेमोरी में लोड किए बिना **500 MB** तक की फ़ाइलें उत्पन्न कर सकता है, जिससे Windows, Linux, और macOS पर उच्च‑प्रदर्शन रेंडरिंग मिलती है। यह आपको आकार, रंग, और स्ट्रोक पर पूर्ण नियंत्रण देता है जबकि लो‑लेवल PostScript कोड लिखने की आवश्यकता नहीं रहती।

- **ग्राफ़िक्स पर पूर्ण नियंत्रण** – लो‑लेवल PS सिंटैक्स से निपटे बिना आकार बनाएं, रंग सेट करें, और स्ट्रोक लागू करें।  
- **क्रॉस‑प्लेटफ़ॉर्म** – Windows, Linux, और macOS रनटाइम पर काम करता है।  
- **कोई बाहरी निर्भरताएँ नहीं** – लाइब्रेरी सभी PS जनरेशन आंतरिक रूप से संभालती है।  
- **समृद्ध दस्तावेज़ीकरण और उदाहरण** – जल्दी से शुरू करें।

## पूर्वापेक्षाएँ

- **Aspose.Page for .NET लाइब्रेरी** – [here](https://releases.aspose.com/page/net/) से डाउनलोड और इंस्टॉल करें।  
- **डेवलपमेंट एनवायरनमेंट** – Visual Studio, VS Code, या कोई भी .NET‑compatible IDE।

## नामस्थान आयात करें

`Aspose.Page` नामस्थान उन कोर क्लासों को उजागर करता है जिनकी आपको आवश्यकता होगी, जैसे `Document`, `Page`, `SolidBrush`, और `Pen`। कोडिंग शुरू करने से पहले इसे आयात करें।

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

अब चलिए उदाहरण को स्पष्ट, क्रमांकित चरणों में विभाजित करते हैं।

## चरण 1: अपने दस्तावेज़ निर्देशिका सेट करें

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

`"Your Document Directory"` को उस फ़ोल्डर से बदलें जहाँ आप परिणामी PS फ़ाइल सहेजना चाहते हैं।

## चरण 2: PostScript दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

यह स्ट्रीम **AddRectangle_outPS.ps** की ओर इशारा करती है। आवश्यकता अनुसार फ़ाइल का नाम बदलने या स्थान बदलने में संकोच न करें।

## चरण 3: सहेजने के विकल्प सेट करें और PS दस्तावेज़ बनाएं

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

यहाँ हम Aspose.Page को A4 पेज आकार उपयोग करने और एक‑पृष्ठ दस्तावेज़ बनाने के लिए कहते हैं।

## चरण 4: भरी हुई आयत जोड़ें

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

हम (250, 100) पर एक आयत परिभाषित करते हैं जिसकी चौड़ाई 150 और ऊँचाई 100 है, एक नारंगी ब्रश सेट करते हैं, और आकार को भरते हैं।

## चरण 5: रूपरेखा वाली आयत जोड़ें

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

पृष्ठ के नीचे एक दूसरी आयत बनाई गई है, इस बार लाल 3‑पॉइंट स्ट्रोक के साथ।

## चरण 6: पृष्ठ बंद करें और दस्तावेज़ सहेजें

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

पृष्ठ को बंद करने से ड्राइंग समाप्त होती है, और `Save()` PS फ़ाइल को डिस्क पर लिखता है।

## Postscript दस्तावेज़ .net कैसे बनाएं?
`Document` Aspose.Page में PostScript फ़ाइल का प्रतिनिधित्व करने वाली मुख्य क्लास है। `SaveOptions` दस्तावेज़ के पृष्ठ आकार और आउटपुट फ़ॉर्मेट जैसी सेटिंग्स निर्दिष्ट करता है। `Document` ऑब्जेक्ट लोड करें, A4 पेज के लिए `SaveOptions` कॉन्फ़िगर करें, अपने आकार `SolidBrush` या `Pen` से बनाएं, फिर `document.Save()` कॉल करें—पूरा वर्कफ़्लो केवल कुछ कोड लाइनों में संभव है और किसी भी समर्थित .NET रनटाइम पर चलता है। यह पैटर्न आपको कच्चे PS सिंटैक्स को छुए बिना पूर्णतः अनुपालन PostScript फ़ाइलें उत्पन्न करने देता है।

## Postscript फ़ाइल कैसे उत्पन्न करें
Aspose.Page की `SaveOptions` क्लास का उपयोग करके आउटपुट फ़ॉर्मेट को PostScript (`SaveFormat.PS`) के रूप में निर्दिष्ट करें। लाइब्रेरी सामग्री को सीधे फ़ाइल या मेमोरी स्ट्रीम में स्ट्रीम करती है, जिससे आप बड़ी दस्तावेज़ों को कुशलता से उत्पन्न कर सकते हैं बिना अत्यधिक मेमोरी उपयोग के।

## सामान्य समस्याएँ और सुझाव

- **गलत फ़ाइल पथ** – सुनिश्चित करें कि `dataDir` पाथ सेपरेटर (`\\` या `/`) के साथ समाप्त हो या `Path.Combine` का उपयोग करें।  
- **लाइसेंस अनुपलब्ध** – प्रोडक्शन वातावरण में दस्तावेज़ बनाने से पहले अपना Aspose लाइसेंस लागू करें ताकि इवैल्यूएशन वॉटरमार्क न आए।  
- **रंग दृश्यता** – यदि आयत खाली दिखे, तो ब्रश या पेन के रंग पृष्ठ पृष्ठभूमि के साथ कंट्रास्ट में हैं या नहीं, जांचें।

## अक्सर पूछे जाने वाले प्रश्न

**Q:** क्या मैं आयतों के रंग कस्टमाइज़ कर सकता हूँ?  
**A:** बिल्कुल। `SolidBrush` और `Pen` कंस्ट्रक्टर्स में `Color.Orange` या `Color.Red` मानों को अपनी पसंद के किसी भी `System.Drawing.Color` में बदलें।

**Q:** क्या Aspose.Page अन्य दस्तावेज़ फ़ॉर्मेट्स के साथ संगत है?  
**A:** हां। PostScript के अलावा, Aspose.Page XPS और EPS जनरेशन को भी समर्थन देता है।

**Q:** मैं उसी दस्तावेज़ में टेक्स्ट कैसे जोड़ सकता हूँ?  
**A:** `TextFragment` क्लास का उपयोग करके इच्छित कॉर्डिनेट्स पर टेक्स्ट रखें, फिर `document.Draw(textFragment)` कॉल करें।

**Q:** अतिरिक्त उदाहरण और पूर्ण API रेफ़रेंस कहाँ मिल सकते हैं?  
**A:** डॉक्यूमेंटेशन [here](https://reference.aspose.com/page/net/) देखें और समुदाय में शामिल हों [Aspose.Page forum](https://forum.aspose.com/c/page/39) पर।

**Q:** क्या मैं खरीदने से पहले Aspose.Page आज़मा सकता हूँ?  
**A:** हां, एक मुफ्त ट्रायल [here](https://releases.aspose.com/) से डाउनलोड करें। विस्तारित मूल्यांकन के लिए, एक [temporary license](https://purchase.aspose.com/temporary-license/) पर विचार करें।

**अंतिम अपडेट:** 2026-06-30  
**परीक्षण किया गया:** Aspose.Page 24.12 for .NET  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Page for .NET के साथ PostScript दस्तावेज़ कैसे बनाएं](/page/net/document-creation/create-postscript-document/)
- [Aspose.Page के साथ PostScript (PS) दस्तावेज़ में इमेज जोड़ें](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Aspose.Page के साथ PostScript (PS) दस्तावेज़ में टेक्स्ट जोड़ें](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}