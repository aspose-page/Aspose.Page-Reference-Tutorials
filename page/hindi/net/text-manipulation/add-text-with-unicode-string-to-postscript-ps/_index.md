---
date: 2026-03-21
description: Aspose.Page for .NET का उपयोग करके C# में यूनिकोड टेक्स्ट के साथ पोस्टस्क्रिप्ट
  दस्तावेज़ बनाना सीखें – दस्तावेज़ प्रबंधन को बेहतर बनाने का एक तेज़ तरीका।
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: Unicode टेक्स्ट के साथ C# में PostScript दस्तावेज़ बनाएं – Aspose.Page
url: /hi/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ PostScript (PS) में यूनिकोड स्ट्रिंग के साथ टेक्स्ट जोड़ें

## परिचय

यदि आपको **create a PostScript document C#** बनाना है और यूनिकोड अक्षर एम्बेड करने हैं, तो Aspose.Page for .NET प्रक्रिया को सरल बनाता है। इस ट्यूटोरियल में हम एक पूर्ण, व्यावहारिक उदाहरण के माध्यम से दिखाएंगे कि कैसे जापानी टेक्स्ट (या कोई भी यूनिकोड स्ट्रिंग) को PS फ़ाइल में जोड़ें, कस्टम फ़ॉन्ट चुनें, और परिणाम को सहेजें। अंत तक, आपके पास एक पुन: उपयोग योग्य स्निपेट होगा जिसे आप किसी भी C# प्रोजेक्ट में डाल सकते हैं।

## त्वरित उत्तर
- **यह ट्यूटोरियल क्या कवर करता है?** Unicode टेक्स्ट को Aspose.Page का उपयोग करके C# में PostScript फ़ाइल में जोड़ना।
- **कौन‑सी लाइब्रेरी आवश्यक है?** Aspose.Page for .NET (नवीनतम संस्करण)।
- **क्या मुझे विशेष फ़ॉन्ट चाहिए?** कोई भी TrueType/OpenType फ़ॉन्ट जो वांछित यूनिकोड रेंज को सपोर्ट करता हो, जैसे *Arial Unicode MS*।
- **कोड की कितनी पंक्तियाँ हैं?** लगभग 30 पंक्तियाँ, स्पष्ट चरणों में विभाजित।
- **क्या लाइसेंस आवश्यक है?** मूल्यांकन के लिए एक अस्थायी लाइसेंस काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।

## “create postscript document c#” क्या है?

C# में PostScript दस्तावेज़ बनाना मतलब प्रोग्रामेटिक रूप से एक .ps फ़ाइल उत्पन्न करना है जो PostScript भाषा विनिर्देशों का पालन करती है। Aspose.Page निम्न‑स्तरीय विवरणों को अमूर्त बनाता है, जिससे आप टेक्स्ट, ग्राफ़िक्स और फ़ॉन्ट जैसे कंटेंट पर ध्यान केंद्रित कर सकते हैं।

## Unicode टेक्स्ट के लिए Aspose.Page क्यों उपयोग करें?

- **Full Unicode support** – किसी भी भाषा के अक्षरों को बिना मैनुअल एन्कोडिंग के रेंडर करता है।
- **Device‑independent** – वही कोड PS, EPS, और PDF आउटपुट के लिए काम करता है।
- **No external dependencies** – लाइब्रेरी फ़ॉन्ट लोडिंग और ग्लिफ़ मैपिंग को आंतरिक रूप से संभालती है।

## पूर्वापेक्षाएँ

- C# और .NET विकास की बुनियादी समझ।
- Aspose.Page for .NET लाइब्रेरी स्थापित हो। आप इसे [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) से डाउनलोड कर सकते हैं।
- एक फ़ोल्डर जिसमें आप उपयोग करने वाले फ़ॉन्ट हों (जैसे *Arial Unicode MS*)।

## नेमस्पेस इम्पोर्ट करें

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## चरण 1: दस्तावेज़ डायरेक्टरी और फ़ॉन्ट फ़ोल्डर सेट अप करें

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## चरण 2: PostScript दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## चरण 3: कस्टम फ़ॉन्ट के साथ यूनिकोड टेक्स्ट जोड़ें

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## चरण 4: वर्तमान पेज बंद करें

```csharp
document.ClosePage();
```

## चरण 5: दस्तावेज़ को अंतिम रूप दें और सहेजें

```csharp
document.Save();
```

## सामान्य समस्याएँ और समाधान

- **Font not found** – सुनिश्चित करें कि `AdditionalFontsFolders` पथ .ttf/.otf फ़ाइलों वाले फ़ोल्डर की ओर इशारा कर रहा है और फ़ॉन्ट नाम बिल्कुल मेल खाता हो।
- **Garbage characters** – पुष्टि करें कि स्रोत स्ट्रिंग आपके C# स्रोत फ़ाइल में UTF‑8 के रूप में एन्कोडेड है (यदि आवश्यक हो तो `#pragma warning disable 1591` उपयोग करें)।
- **File not created** – `dataDir` पर लिखने की अनुमति जांचें और सुनिश्चित करें कि स्ट्रीम सही तरीके से डिस्पोज़ हो रहा है (`using` ब्लॉक इसे संभालता है)।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Page for .NET को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?**  
A: Aspose.Page मुख्यतः .NET के लिए डिज़ाइन किया गया है, लेकिन जावा के समकक्ष उपलब्ध हैं।

**Q: Aspose.Page for .NET के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A: अस्थायी लाइसेंस प्राप्त करने के लिए [Temporary License](https://purchase.aspose.com/temporary-license/) पर जाएँ।

**Q: Aspose.Page चर्चाओं के लिए कोई कम्युनिटी फ़ोरम है?**  
A: हाँ, कम्युनिटी सपोर्ट के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) पर जाएँ।

**Q: Aspose.Page for .NET किन फ़ॉर्मैट्स के साथ काम कर सकता है?**  
A: Aspose.Page विभिन्न फ़ॉर्मैट्स को सपोर्ट करता है, जैसे XPS, PS, EPS, PDF, और अधिक।

**Q: क्या मैं जोड़े गए टेक्स्ट की उपस्थिति को कस्टमाइज़ कर सकता हूँ?**  
A: हाँ, आप Aspose.Page में टेक्स्ट के फ़ॉन्ट, आकार, रंग और अन्य गुणों को कस्टमाइज़ कर सकते हैं।

## निष्कर्ष

इस ट्यूटोरियल में हमने दिखाया कि कैसे **create a PostScript document C#** बनाकर Aspose.Page का उपयोग करके यूनिकोड टेक्स्ट एम्बेड किया जा सकता है। ऊपर दिए गए चरणों का पालन करके आप किसी भी .NET एप्लिकेशन में बहुभाषी टेक्स्ट रेंडरिंग को जल्दी से इंटीग्रेट कर सकते हैं, जिससे आपको दस्तावेज़ निर्माण और लेआउट पर पूर्ण नियंत्रण मिलता है।

---

**अंतिम अपडेट:** 2026-03-21  
**परीक्षण किया गया:** Aspose.Page 24.11 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}