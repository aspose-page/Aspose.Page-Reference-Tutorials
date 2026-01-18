---
date: 2026-01-18
description: Aspose.Page for .NET का उपयोग करके पोस्टस्क्रिप्ट दस्तावेज़ .NET बनाना
  और आयतें जोड़ना सीखें। कोड उदाहरणों के साथ चरण‑दर‑चरण मार्गदर्शिका।
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Postscript दस्तावेज़ .net बनाएं – Aspose.Page के साथ आयत जोड़ें
url: /hi/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET के साथ PostScript (PS) में आयत जोड़ें

## परिचय

यदि आप **create postscript document .net** बनाना चाहते हैं, तो Aspose.Page PostScript फ़ाइलों को संभालने के लिए एक शक्तिशाली समाधान प्रदान करता है। इस ट्यूटोरियल में, हम आपको Aspose.Page for .NET का उपयोग करके PostScript दस्तावेज़ में आयतें जोड़ने के चरण दिखाएंगे, जिससे आप समृद्ध ग्राफ़िक्स जेनरेशन के लिए एक ठोस आधार प्राप्त करेंगे।

## त्वरित उत्तर
- **मुझे कौन सी लाइब्रेरी चाहिए?** Aspose.Page for .NET.
- **क्या मैं शून्य से एक PostScript दस्तावेज़ बना सकता हूँ?** हाँ – API आपको प्रोग्रामेटिक रूप से PS फ़ाइलें बनाने देती है।
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **क्या विकास के लिए लाइसेंस चाहिए?** परीक्षण के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है।
- **इम्प्लीमेंटेशन में कितना समय लगता है?** बुनियादी आकारों के लिए आमतौर पर 10 मिनट से कम।

## PostScript दस्तावेज़ .net बनाना क्या है?
.NET में PostScript दस्तावेज़ बनाना का अर्थ है Aspose.Page API का उपयोग करके प्रोग्रामेटिक रूप से एक .ps फ़ाइल उत्पन्न करना, जिसमें पेज सामग्री—टेक्स्ट, ग्राफ़िक्स या शैप्स—का वर्णन होता है। यह तरीका सर्वर‑साइड ग्राफ़िक्स जेनरेशन, स्वचालित रिपोर्ट निर्माण, या किसी भी स्थिति के लिए आदर्श है जहाँ आउटपुट फ़ॉर्मेट पर सटीक नियंत्रण आवश्यक हो।

## Aspose.Page for .NET का उपयोग क्यों करें?
- **ग्राफ़िक्स पर पूर्ण नियंत्रण** – आकार बनाएं, रंग सेट करें, और स्ट्रोक लागू करें बिना लो‑लेवल PS सिंटैक्स से निपटे।
- **क्रॉस‑प्लेटफ़ॉर्म** – Windows, Linux, और macOS रनटाइम पर काम करता है।
- **कोई बाहरी निर्भरताएँ नहीं** – लाइब्रेरी सभी PS जेनरेशन को आंतरिक रूप से संभालती है।
- **समृद्ध दस्तावेज़ीकरण और उदाहरण** – जल्दी से शुरू करें।

## पूर्वापेक्षाएँ

- **Aspose.Page for .NET लाइब्रेरी** – [here](https://releases.aspose.com/page/net/) से डाउनलोड और इंस्टॉल करें।
- **डेवलपमेंट एनवायरनमेंट** – Visual Studio, VS Code, या कोई भी .NET‑compatible IDE।

## नेमस्पेस इम्पोर्ट करें

कोड लिखना शुरू करने से पहले, आवश्यक क्लासेज़ को उजागर करने वाले नेमस्पेस इम्पोर्ट करें:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

अब हम उदाहरण को स्पष्ट, क्रमांकित चरणों में विभाजित करते हैं।

## चरण 1: अपने दस्तावेज़ डायरेक्टरी सेट करें

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

यह स्ट्रीम **AddRectangle_outPS.ps** की ओर इशारा करती है। आवश्यकता अनुसार फ़ाइल का नाम बदलें या स्थान बदलें।

## चरण 3: सेव ऑप्शन सेट करें और PS दस्तावेज़ बनाएं

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

यहाँ हम Aspose.Page को A4 पेज साइज उपयोग करने और एक‑पेज दस्तावेज़ बनाने के लिए निर्देश देते हैं।

## चरण 4: एक भरी हुई आयत जोड़ें

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

हम (250, 100) पर चौड़ाई 150 और ऊँचाई 100 की आयत परिभाषित करते हैं, एक ऑरेंज ब्रश सेट करते हैं, और आकार को भरते हैं।

## चरण 5: एक आउटलाइन वाली आयत जोड़ें

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

दूसरी आयत पेज के नीचे बनाई जाती है, इस बार लाल 3‑पॉइंट स्ट्रोक के साथ।

## चरण 6: पेज को बंद करें और दस्तावेज़ सहेजें

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

पेज को बंद करने से ड्राइंग अंतिम रूप लेती है, और `Save()` PS फ़ाइल को डिस्क पर लिखता है।

## सामान्य समस्याएँ और सुझाव
- **गलत फ़ाइल पाथ** – सुनिश्चित करें कि `dataDir` पाथ सेपरेटर (`\\` या `/`) के साथ समाप्त हो या `Path.Combine` का उपयोग करें।
- **लाइसेंस गायब** – प्रोडक्शन एनवायरनमेंट में, दस्तावेज़ बनाने से पहले अपना Aspose लाइसेंस लागू करें ताकि इवैल्युएशन वाटरमार्क न आए।
- **रंग की दृश्यता** – यदि आयत खाली दिखे, तो ब्रश या पेन के रंग पेज बैकग्राउंड के साथ कंट्रास्ट में हैं या नहीं, जांचें।

## अक्सर पूछे जाने वाले प्रश्न

**प्र:** क्या मैं आयतों के रंग कस्टमाइज़ कर सकता हूँ?  
**उ:** बिल्कुल। `SolidBrush` और `Pen` कंस्ट्रक्टर्स में `Color.Orange` या `Color.Red` मानों को अपनी पसंद के किसी भी `System.Drawing.Color` में बदलें।

**प्र:** क्या Aspose.Page अन्य दस्तावेज़ फ़ॉर्मेट के साथ संगत है?  
**उ:** हाँ। PostScript के अलावा, Aspose.Page XPS और EPS जेनरेशन को भी समर्थन देता है।

**प्र:** मैं उसी दस्तावेज़ में टेक्स्ट कैसे जोड़ सकता हूँ?  
**उ:** `TextFragment` क्लास का उपयोग करके इच्छित निर्देशांक पर टेक्स्ट रखें, फिर `document.Draw(textFragment)` कॉल करें।

**प्र:** अतिरिक्त उदाहरण और पूर्ण API रेफ़रेंस कहाँ मिलेंगे?  
**उ:** दस्तावेज़ीकरण [here](https://reference.aspose.com/page/net/) देखें और [Aspose.Page forum](https://forum.aspose.com/c/page/39) में समुदाय से जुड़ें।

**प्र:** क्या मैं खरीदने से पहले Aspose.Page आज़मा सकता हूँ?  
**उ:** हाँ, मुफ्त ट्रायल [here](https://releases.aspose.com/) से डाउनलोड करें। विस्तारित मूल्यांकन के लिए एक [temporary license](https://purchase.aspose.com/temporary-license/) पर विचार करें।

---

**अंतिम अपडेट:** 2026-01-18  
**परीक्षित संस्करण:** Aspose.Page 24.12 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}