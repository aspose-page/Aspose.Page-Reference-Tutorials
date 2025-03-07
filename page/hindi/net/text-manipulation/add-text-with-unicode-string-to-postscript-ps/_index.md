---
title: Aspose.Page के साथ पोस्टस्क्रिप्ट (PS) में यूनिकोड स्ट्रिंग के साथ टेक्स्ट जोड़ें
linktitle: पोस्टस्क्रिप्ट (पीएस) में यूनिकोड स्ट्रिंग के साथ टेक्स्ट जोड़ें
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट फ़ाइलों में यूनिकोड टेक्स्ट जोड़ने का तरीका जानें। आसानी से दस्तावेज़ हेरफेर बढ़ाएँ।
weight: 11
url: /hi/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ पोस्टस्क्रिप्ट (PS) में यूनिकोड स्ट्रिंग के साथ टेक्स्ट जोड़ें

## परिचय

दस्तावेज़ हेरफेर के क्षेत्र में, .NET के लिए Aspose.Page एक मजबूत लाइब्रेरी के रूप में सामने आता है जो डेवलपर्स को विभिन्न दस्तावेज़ प्रारूप बनाने, संपादित करने और परिवर्तित करने का अधिकार देता है। इसकी शक्तिशाली विशेषताओं में से एक पोस्टस्क्रिप्ट (पीएस) फ़ाइलों में यूनिकोड स्ट्रिंग्स का उपयोग करके टेक्स्ट जोड़ने की क्षमता है। इस ट्यूटोरियल में, हम इस कार्य को पूरा करने के लिए चरण-दर-चरण मार्गदर्शिका का पता लगाएंगे, जो Aspose.Page के साथ काम करने वाले डेवलपर्स के लिए एक सहज अनुभव प्रदान करेगा।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

- C# प्रोग्रामिंग भाषा का कार्यसाधक ज्ञान।
-  .NET लाइब्रेरी के लिए Aspose.Page स्थापित किया गया। आप इसे यहां से डाउनलोड कर सकते हैं[.NET दस्तावेज़ीकरण के लिए Aspose.Page](https://reference.aspose.com/page/net/).
- आवश्यक कॉन्फ़िगरेशन के साथ एक विकास वातावरण स्थापित किया गया।

## नामस्थान आयात करें

अपने C# कोड में, .NET कार्यात्मकताओं के लिए Aspose.Page का उपयोग करने के लिए आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## चरण 1: दस्तावेज़ निर्देशिका और फ़ॉन्ट फ़ोल्डर सेट करें

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## चरण 2: पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // A4 आकार के साथ सेव विकल्प बनाएं
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (अतिरिक्त विकल्प यहां सेट किए जा सकते हैं)
    
    // नया 1-पृष्ठ वाला PS दस्तावेज़ बनाएँ
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (आगे के चरण नीचे बताए जाएंगे)
    
    // दस्तावेज़ सहेजें
    document.Save();
}
```

## चरण 3: कस्टम फ़ॉन्ट के साथ यूनिकोड टेक्स्ट जोड़ें

```csharp
string str = "試してみます.";  // यूनिकोड पाठ
int fontSize = 48;

// टेक्स्ट भरने के लिए कस्टम फ़ॉन्ट का उपयोग करना
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## चरण 4: वर्तमान पृष्ठ बंद करें

```csharp
document.ClosePage();
```

## चरण 5: दस्तावेज़ को अंतिम रूप दें और सहेजें

```csharp
document.Save();
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट दस्तावेज़ में यूनिकोड टेक्स्ट जोड़ने की प्रक्रिया के बारे में जाना है। इसकी शक्तिशाली क्षमताओं का लाभ उठाते हुए, डेवलपर्स लचीलापन और सटीकता सुनिश्चित करते हुए अपने दस्तावेज़ हेरफेर वर्कफ़्लो को बढ़ा सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Page का उपयोग कर सकता हूँ?

A1: Aspose.Page मुख्य रूप से .NET के लिए डिज़ाइन किया गया है, लेकिन Java के लिए अन्य संस्करण भी उपलब्ध हैं।

### Q2: मैं .NET के लिए Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त करूं?

 ए2: विजिट करें[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) अस्थायी लाइसेंस प्राप्त करने के लिए.

### Q3: क्या Aspose.Page चर्चाओं के लिए कोई सामुदायिक मंच है?

 A3: हाँ, पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक समर्थन के लिए.

### Q4: .NET के लिए Aspose.Page किन प्रारूपों के साथ काम कर सकता है?

A4: Aspose.Page XPS, PS, EPS, PDF और अन्य सहित विभिन्न प्रारूपों का समर्थन करता है।

### Q5: क्या मैं जोड़े गए टेक्स्ट के स्वरूप को अनुकूलित कर सकता हूँ?

A5: हाँ, आप Aspose.Page में टेक्स्ट के फ़ॉन्ट, आकार, रंग और अन्य गुणों को अनुकूलित कर सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
