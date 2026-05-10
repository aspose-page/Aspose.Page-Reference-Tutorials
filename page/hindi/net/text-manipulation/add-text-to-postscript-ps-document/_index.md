---
date: 2026-03-21
description: Aspose.Page for .NET का उपयोग करके PS दस्तावेज़ों में टेक्स्ट भरना और
  जोड़ना सीखें। कोड उदाहरणों के साथ चरण‑दर‑चरण गाइड।
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Aspose.Page के साथ PostScript (PS) दस्तावेज़ों में टेक्स्ट कैसे भरें
url: /hi/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ PostScript (PS) दस्तावेज़ों में टेक्स्ट कैसे भरें

## परिचय

यदि आपको PostScript (PS) फ़ाइल के भीतर **टेक्स्ट कैसे भरें** की आवश्यकता है, तो Aspose.Page for .NET इसे सरल बनाता है। चाहे आप रिपोर्ट, इनवॉइस, या कस्टम ग्राफ़िक्स बना रहे हों, टेक्स्ट जोड़ना और उसका स्टाइलिंग करना एक मुख्य आवश्यकता है। इस ट्यूटोरियल में हम पूरे प्रक्रिया को चरण‑दर‑चरण समझेंगे—पर्यावरण सेटअप से लेकर अंतिम PS दस्तावेज़ को सहेजने तक—ताकि आप अपने .NET एप्लिकेशन में PS फ़ाइलों में टेक्स्ट जोड़ने में आत्मविश्वास महसूस करें।

## त्वरित उत्तर
- **“fill text” का क्या अर्थ है?** यह अक्षरों को एक ठोस ब्रश का उपयोग करके रेंडर करता है, ग्लीफ़्स को सीधे पृष्ठ पर पेंट करता है।  
- **क्या मैं कस्टम फ़ॉन्ट्स का उपयोग कर सकता हूँ?** हां—Aspose.Page `add custom font ps` फीचर के माध्यम से कस्टम फ़ॉन्ट्स को सपोर्ट करता है।  
- **मैं PS दस्तावेज़ को कैसे सहेजूँ?** पेज बंद करने के बाद `document.Save()` कॉल करें; यह फ़ाइल को डिस्क पर लिखता है (`save ps document`).  
- **क्या “fill and stroke text” समर्थित है?** बिल्कुल; दोनों फ़िल और आउटलाइन लागू करने के लिए `FillAndStrokeText` का उपयोग करें।  
- **कौन से .NET संस्करण आवश्यक हैं?** कोई भी .NET Framework 4.5+ या .NET Core/5/6+ रनटाइम।

## PS दस्तावेज़ में “टेक्स्ट कैसे भरें” क्या है?

टेक्स्ट भरना मतलब अक्षरों को बिना आउटलाइन के एक ठोस रंग (या ब्रश) से पेंट करना है। PostScript में, यह `fill` ऑपरेटर के समान है। Aspose.Page इसे `FillText` और `FillAndStrokeText` जैसी उपयोग‑में‑आसान मेथड्स में सारांशित करता है।

## कस्टम फ़ॉन्ट ps जोड़ने के लिए Aspose.Page क्यों उपयोग करें?

- **पूर्ण फ़ॉन्ट समर्थन** – सिस्टम फ़ॉन्ट्स और बाहरी TrueType/OpenType फ़ॉन्ट्स तुरंत काम करते हैं।  
- **सटीक पोजिशनिंग** – आप X/Y कॉर्डिनेट्स, आकार, और शैली को नियंत्रित करते हैं।  
- **समृद्ध स्टाइलिंग** – “fill and stroke text” जैसे प्रभावों के लिए फ़िल, स्ट्रोक, और पेन को मिलाएँ।  
- **क्रॉस‑प्लेटफ़ॉर्म** – वही API के साथ Windows, Linux, और macOS पर काम करता है।

## पूर्वापेक्षाएँ

- **Aspose.Page for .NET** – लाइब्रेरी को [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/) से डाउनलोड करें।  
- **Document Directory** – आपके मशीन पर एक फ़ोल्डर जहाँ स्रोत और आउटपुट PS फ़ाइलें रहेंगी (कोड में *Your Document Directory* कहा गया है)।  
- **Fonts Folder** – एक सब‑फ़ोल्डर जिसमें आप उपयोग करने वाले कस्टम फ़ॉन्ट्स हों।

## नेमस्पेस इम्पोर्ट करें

पहले, आवश्यक नेमस्पेस इम्पोर्ट करें ताकि कंपाइलर को पता हो कि हम जिन क्लासेज़ का उपयोग करेंगे, वे कहाँ हैं:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## चरण‑दर‑चरण गाइड

### चरण 1: PS दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं  

हम एक `FileStream` खोलते हैं जो जनरेटेड PS फ़ाइल को रखेगा, `PsSaveOptions` को हमारे कस्टम फ़ॉन्ट्स फ़ोल्डर की ओर इंगित करने के लिए कॉन्फ़िगर करते हैं, और एक `PsDocument` बनाते हैं।

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **प्रो टिप:** `using` ब्लॉक को रखें ताकि स्ट्रीम स्वचालित रूप से बंद हो जाए, जो PS फ़ाइल को भी अंतिम रूप देता है (`save ps document`).

### चरण 2: सिस्टम फ़ॉन्ट के साथ टेक्स्ट भरें  

यहाँ हम बिल्ट‑इन *Times New Roman* फ़ॉन्ट का उपयोग करके बुनियादी **टेक्स्ट कैसे भरें** ऑपरेशन दिखाते हैं।

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### चरण 3: कस्टम फ़ॉन्ट के साथ टेक्स्ट भरें  

यदि आपको विशिष्ट लुक चाहिए, तो `ExternalFontCache.FetchDrFont` का उपयोग करके फ़ॉन्ट्स फ़ोल्डर से कस्टम फ़ॉन्ट लोड करें। यह **add custom font ps** आवश्यकता को पूरा करता है।

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### चरण 4: सिस्टम फ़ॉन्ट के साथ टेक्स्ट को आउटलाइन (स्ट्रोक) करें  

आउटलाइनिंग ग्लीफ़ की रूपरेखा खींचती है। “fill and stroke” प्रभाव के लिए इसे फ़िल के साथ मिलाएँ।

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **यह क्यों महत्वपूर्ण है:** `FillAndStrokeText` कॉल दिखाता है कि कैसे एक ही चरण में **fill and stroke text** किया जाए, जिससे आपको अधिक समृद्ध टाइपोग्राफिक नियंत्रण मिलता है।

### चरण 5: कस्टम फ़ॉन्ट के साथ टेक्स्ट को आउटलाइन करें  

एक ही आउटलाइन तकनीक किसी भी लोड किए गए कस्टम फ़ॉन्ट के साथ काम करती है।

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### चरण 6: पेज बंद करें और दस्तावेज़ सहेजें  

समाप्त करना सरल है: वर्तमान पेज को बंद करें और `Save()` को कॉल करके PS फ़ाइल को डिस्क पर लिखें।

```csharp
document.ClosePage();
document.Save();
}
```

> **परिणाम:** आपको *Your Document Directory* में `AddText_outPS.ps` मिलेगा, जिसमें सिस्टम और कस्टम फ़ॉन्ट्स के साथ रेंडर किया गया दोनों फ़िल और स्ट्रोक किया हुआ टेक्स्ट होगा।

## सामान्य समस्याएँ और समाधान

| समस्या | समाधान |
|-------|----------|
| **कस्टम फ़ॉन्ट नहीं मिला** | सुनिश्चित करें कि फ़ॉन्ट फ़ाइल (.ttf/.otf) `AdditionalFontsFolders` द्वारा संदर्भित फ़ोल्डर में मौजूद है। |
| **टेक्स्ट गलत स्थान पर दिखाई देता है** | `FillText`/`OutlineText` को पास किए गए X/Y कॉर्डिनेट्स को समायोजित करें। याद रखें कि PostScript पॉइंट्स (1/72 इंच) का उपयोग करता है। |
| **रंग अलग दिख रहे हैं** | सुनिश्चित करें कि आप सही `Color` मानों के साथ `SolidBrush` या `Pen` का उपयोग कर रहे हैं। |
| **दस्तावेज़ सहेजा नहीं जा रहा** | पुष्टि करें कि `using` ब्लॉक बिना अपवाद के पूरा हो रहा है और एप्लिकेशन को लक्ष्य फ़ोल्डर में लिखने की अनुमति है। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Page को अन्य .NET लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
उत्तर: हाँ, Aspose.Page अन्य .NET घटकों के साथ सहजता से एकीकृत होता है, जिससे आप एक ही समाधान में PDF, इमेज, या चार्ट लाइब्रेरीज़ को संयोजित कर सकते हैं।

**प्रश्न: क्या इस प्रक्रिया के लिए कस्टम फ़ॉन्ट्स आवश्यक हैं?**  
उत्तर: जबकि सिस्टम फ़ॉन्ट्स ठीक काम करते हैं, कस्टम फ़ॉन्ट्स आपको पूर्ण डिजाइन स्वतंत्रता देते हैं और जब ब्रांड‑विशिष्ट टाइपोग्राफी की आवश्यकता हो तो उपयोगी होते हैं।

**प्रश्न: क्या Aspose.Page बड़े‑पैमाने पर दस्तावेज़ प्रोसेसिंग के लिए उपयुक्त है?**  
उत्तर: बिल्कुल। लाइब्रेरी उच्च‑थ्रूपुट परिदृश्यों के लिए अनुकूलित है और हजारों PS फ़ाइलों को कुशलता से संभाल सकती है।

**प्रश्न: क्या मैं PS दस्तावेज़ में टेक्स्ट की स्थिति बदल सकता हूँ?**  
उत्तर: निश्चित रूप से—सिर्फ `FillText` या `OutlineText` कॉल में संख्यात्मक X/Y मान बदलें।

**प्रश्न: Aspose.Page‑संबंधी प्रश्नों के लिए मैं कहां सहायता प्राप्त कर सकता हूँ?**  
उत्तर: समुदाय से जुड़ने और विशेषज्ञ मदद पाने के लिए [Aspose.Page Forum](https://forum.aspose.com/c/page/39) पर जाएँ।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2026-03-21  
**परीक्षित संस्करण:** Aspose.Page 24.11 for .NET  
**लेखक:** Aspose