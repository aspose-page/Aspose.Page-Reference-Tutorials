---
date: 2026-03-03
description: Aspose.Page for .NET का उपयोग करके कस्टम पेज साइज सेट करना और PostScript
  दस्तावेज़ में दूसरा PS पेज जोड़ना सीखें।
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Aspose.Page के साथ PS दस्तावेज़ में कस्टम पेज आकार सेट करें
url: /hi/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ PostScript (PS) दस्तावेज़ में पृष्ठ जोड़ें

## परिचय

.NET विकास में, **कस्टम पेज आकार सेट** करने और PostScript (PS) दस्तावेज़ में **दूसरा PS पेज जोड़ने** की क्षमता आपको उत्पन्न प्रिंट, रिपोर्ट या ग्राफ़िक्स के लेआउट पर सूक्ष्म नियंत्रण देती है। Aspose.Page for .NET इस कार्य को साफ़, ऑब्जेक्ट‑ओरिएंटेड API के साथ सरल बनाता है। इस ट्यूटोरियल में आप सीखेंगे कि कैसे एक मल्टी‑पेज PS फ़ाइल बनाएं, प्रत्येक पेज के लिए कस्टम आकार निर्धारित करें, और परिणाम को सहेजें—सिर्फ कुछ ही C# कोड लाइनों के साथ।

## त्वरित उत्तर
- **क्या मैं कस्टम पेज आकार सेट कर सकता हूँ?** हाँ – पेज खोलते समय चौड़ाई और ऊँचाई पास करें।  
- **मैं दूसरा PS पेज कैसे जोड़ूँ?** `document.OpenPage(width, height)` को दूसरी बार कॉल करें।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **क्या मुझे लाइसेंस चाहिए?** परीक्षण के लिए एक अस्थायी लाइसेंस काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **मैं Aspose.Page कहाँ डाउनलोड कर सकता हूँ?** नीचे दिए गए आधिकारिक डाउनलोड पेज से।

## आवश्यकताएँ

इस ट्यूटोरियल को शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित उपलब्ध हों:

- .NET विकास का कार्यात्मक ज्ञान।  
- आपके मशीन पर Visual Studio स्थापित हो।  
- Aspose.Page for .NET लाइब्रेरी, जिसे आप [here](https://releases.aspose.com/page/net/) से डाउनलोड कर सकते हैं।  
- परीक्षण के लिए आपका पसंदीदा दस्तावेज़ डायरेक्टरी।

## नेमस्पेस आयात करें

Aspose.Page द्वारा प्रदान की गई कार्यक्षमताओं तक पहुँचने के लिए अपने प्रोजेक्ट में आवश्यक नेमस्पेस शामिल करना सुनिश्चित करें। दिए गए उदाहरण में नेमस्पेस अप्रत्यक्ष रूप से शामिल हैं, लेकिन अपने प्रोजेक्ट संरचना के आधार पर दोबारा जाँचें और आवश्यक समायोजन करें।

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## चरण 1: अपना प्रोजेक्ट सेट अप करें

Visual Studio में एक नया .NET प्रोजेक्ट बनाएं और आवश्यक कॉन्फ़िगरेशन सेट करें। अपने प्रोजेक्ट में Aspose.Page लाइब्रेरी को रेफ़रेंस करना न भूलें।

## कस्टम पेज आकार सेट करें और दूसरा PS पेज जोड़ें

यह अनुभाग दर्शाता है कि **प्रत्येक पेज के लिए कस्टम पेज आकार** कैसे सेट करें और उसी दस्तावेज़ में **दूसरा PS पेज** कैसे जोड़ें।

### चरण 2: दस्तावेज़ को इनिशियलाइज़ करें

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### चरण 3: पहला पेज जोड़ें (डिफ़ॉल्ट आकार)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### चरण 4: अलग (कस्टम) आकार के साथ दूसरा पेज जोड़ें

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### चरण 5: दस्तावेज़ सहेजें

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

इन चरणों को सावधानीपूर्वक पालन करें, और आप Aspose.Page for .NET का उपयोग करके PostScript दस्तावेज़ में **कस्टम पेज आकार सेट** करने और **दूसरा PS पेज** जोड़ने में सफल होंगे।

## यह क्यों महत्वपूर्ण है

- **सटीक लेआउट** – कस्टम पेज आयाम आपको प्रिंटर विशिष्टताओं से मेल खाने या अनोखे ब्रोशर फ़ॉर्मेट बनाने की अनुमति देते हैं।  
- **एकाधिक पेज** – दूसरा पेज (या अधिक) जोड़ने से बाहरी मर्जिंग टूल्स की आवश्यकता के बिना मल्टी‑पेज रिपोर्ट बन सकती है।  
- **क्रॉस‑प्लेटफ़ॉर्म** – उत्पन्न PS फ़ाइल को किसी भी PostScript‑संगत डिवाइस पर रेंडर किया जा सकता है या बाद में PDF में परिवर्तित किया जा सकता है।

## सामान्य समस्याएँ एवं ट्रबलशूटिंग

- **गलत पाथ** – सुनिश्चित करें कि `dataDir` पाथ सेपरेटर पर समाप्त हो या `Path.Combine` का उपयोग करें।  
- **लाइसेंस समस्याएँ** – वैध लाइसेंस न होने पर लाइब्रेरी वॉटरमार्क जोड़ सकती है या पेज गिनती सीमित कर सकती है।  
- **इकाई भ्रम** – चौड़ाई और ऊँचाई पॉइंट्स में मापी जाती है (1 पॉइंट = 1/72 इंच)। अनुसार समायोजित करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q1: क्या Aspose.Page विभिन्न दस्तावेज़ फ़ॉर्मेट्स के साथ संगत है?**  
A1: Aspose.Page मुख्यतः PostScript दस्तावेज़ हेरफेर पर केंद्रित है। अन्य फ़ॉर्मेट्स के लिए आप विशिष्ट आवश्यकताओं के अनुसार Aspose लाइब्रेरीज़ का उपयोग कर सकते हैं।

**Q2: क्या मैं Aspose.Page में पेज आकार को कस्टमाइज़ कर सकता हूँ?**  
A2: बिल्कुल! ट्यूटोरियल में दिखाए अनुसार आप प्रत्येक पेज के लिए अपनी आवश्यकताओं के अनुसार अलग आकार निर्दिष्ट कर सकते हैं।

**Q3: अधिक उदाहरण और दस्तावेज़ीकरण कहाँ मिल सकता है?**  
A3: व्यापक जानकारी और विभिन्न उदाहरणों के लिए [documentation](https://reference.aspose.com/page/net/) देखें।

**Q4: Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A4: परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस प्राप्त करने हेतु [this link](https://purchase.aspose.com/temporary-license/) पर जाएँ।

**Q5: समुदाय समर्थन या प्रश्न पूछने के लिए कहाँ जा सकता हूँ?**  
A5: अन्य डेवलपर्स से जुड़ने, अनुभव साझा करने और सहायता प्राप्त करने के लिए [Aspose.Page community forum](https://forum.aspose.com/c/page/39) में शामिल हों।

---

**अंतिम अपडेट:** 2026-03-03  
**परीक्षण किया गया:** Aspose.Page 24.11 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}