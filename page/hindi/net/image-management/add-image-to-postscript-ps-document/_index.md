---
date: 2026-02-28
description: Aspose.Page for .NET का उपयोग करके PostScript दस्तावेज़ में छवि कैसे
  जोड़ें, सीखें। यह गाइड यह भी बताता है कि कैसे बिटमैप को PS में डालें और आवश्यकता
  पड़ने पर PS से छवियों को निकालें।
linktitle: Add Image to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Aspose.Page के साथ PostScript (PS) दस्तावेज़ में छवि कैसे जोड़ें
url: /hi/net/image-management/add-image-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript (PS) दस्तावेज़ में छवि कैसे जोड़ें Aspose.Page के साथ

## PostScript (PS) दस्तावेज़ में छवि कैसे जोड़ें

इस ट्यूटोरियल में, आप **how to add image** को PostScript (PS) दस्तावेज़ में Aspose.Page for .NET लाइब्रेरी का उपयोग करके सीखेंगे। चाहे आप प्रिंटेबल फ्लायर्स, तकनीकी ड्रॉइंग्स, या कस्टम रिपोर्ट तैयार कर रहे हों, ग्राफिक्स को सीधे PS फ़ाइलों में एम्बेड करने से दृश्य गुणवत्ता में काफी सुधार हो सकता है। हम प्रत्येक चरण को विस्तार से समझाएंगे, प्रत्येक लाइन का महत्व बताएंगे, और आपको ऐसे टिप्स देंगे जिन्हें आप भविष्य के प्रोजेक्ट्स में पुनः उपयोग कर सकते हैं।

## त्वरित उत्तर
- **मुझे कौन सी लाइब्रेरी चाहिए?** Aspose.Page for .NET (latest version)
- **क्या मैं ps में bitmap डाल सकता हूँ?** हाँ – `DrawImage` को `Bitmap` ऑब्जेक्ट के साथ उपयोग करें
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बेसिक इमेज के लिए आमतौर पर 10 मिनट से कम
- **क्या मुझे लाइसेंस चाहिए?** ट्रायल मूल्यांकन के लिए काम करता है; प्रोडक्शन के लिए कमर्शियल लाइसेंस आवश्यक है
- **क्या मैं बाद में ps से छवियों को निकाल सकता हूँ?** बिल्कुल – Aspose.Page एक्सट्रैक्शन API भी प्रदान करता है

## पूर्वापेक्षाएँ

कोड में डुबकी लगाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- Aspose.Page for .NET लाइब्रेरी: Aspose.Page for .NET लाइब्रेरी को [here](https://releases.aspose.com/page/net/) से डाउनलोड और इंस्टॉल करें।
- Document Directory: अपने सिस्टम पर एक डायरेक्टरी बनाएं जहाँ आप दस्तावेज़ और इमेज फ़ाइलें स्टोर करेंगे।

## नेमस्पेस इम्पोर्ट करें

अपने प्रोजेक्ट में आवश्यक नेमस्पेस इम्पोर्ट करके शुरू करें। ये नेमस्पेस आपको .NET एप्लिकेशन में Aspose.Page की कार्यक्षमता उपयोग करने में सक्षम बनाते हैं:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## चरण 1: दस्तावेज़ डायरेक्टरी सेट अप करें

अपने दस्तावेज़ों के लिए एक समर्पित डायरेक्टरी सुनिश्चित करें। नीचे दिए गए कोड स्निपेट में `"Your Document Directory"` को अपनी दस्तावेज़ डायरेक्टरी के पाथ से बदलें।

```csharp
string dataDir = "Your Document Directory";
```

## चरण 2: PS दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं

PostScript दस्तावेज़ के लिए एक आउटपुट स्ट्रीम सेट अप करें। यह स्ट्रीम संशोधित दस्तावेज़ को सेव करने के लिए उपयोग होगी।

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddImage_outPS.ps", FileMode.Create))
```

## चरण 3: सेव ऑप्शन बनाएं

PS दस्तावेज़ के लिए सेव ऑप्शन बनाएं, जिसमें पेज साइज जैसी वांछित सेटिंग्स निर्दिष्ट हों।

```csharp
PsSaveOptions options = new PsSaveOptions();
```

## चरण 4: PS दस्तावेज़ बनाएं

एक नया 1‑पेज वाला PS दस्तावेज़ इनिशियलाइज़ करें, और ग्राफ़िक्स ऑपरेशन्स के लिए तैयार रहें।

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
document.WriteGraphicsSave();
document.Translate(100, 100);
```

## चरण 5: PS दस्तावेज़ में Bitmap डालें

इमेज फ़ाइल से एक `Bitmap` ऑब्जेक्ट लोड करें और ट्रांसफ़ॉर्मेशन लागू करें। यह **how to add image** का मुख्य भाग है – हम bitmap को PS कैनवास पर ड्रॉ करते हैं।

```csharp
using (Bitmap image = new Bitmap(dataDir + "TestImage Format24bppRgb.jpg"))
{
    System.Drawing.Drawing2D.Matrix transform = new System.Drawing.Drawing2D.Matrix();
    transform.Translate(35, 300);
    transform.Scale(3, 3);
    transform.Rotate(-45);
    
    document.DrawImage(image, transform, Color.Empty);
}
```

> **Pro tip:** `Translate`, `Scale`, और `Rotate` मानों को समायोजित करके छवि को ठीक उसी स्थान और आकार में रखें जहाँ आपको चाहिए।

## चरण 6: ग्राफ़िक्स ऑपरेशन्स को फाइनलाइज़ करें

ग्राफ़िक्स ऑपरेशन्स को समाप्त करें और वर्तमान पेज को बंद करें।

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## चरण 7: दस्तावेज़ को सेव करें

संशोधित PS दस्तावेज़ को सेव करें।

```csharp
document.Save();
```

## PS दस्तावेज़ से छवियों को निकालने का तरीका

यदि बाद में आपको ग्राफ़िक्स पुनः प्राप्त करने की आवश्यकता हो, तो Aspose.Page `PsDocument.ExtractImages` जैसी एक्सट्रैक्शन मेथड्स प्रदान करता है। जबकि यह ट्यूटोरियल इन्सर्शन पर केंद्रित है, वही लाइब्रेरी आपको **extract images from ps** फ़ाइलों को पुनः उपयोग या विश्लेषण के लिए निकालने की सुविधा देती है।

## सामान्य समस्याएँ और समाधान

| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| छवि विकृत दिख रही है | गलत स्केलिंग मैट्रिक्स | `Scale` मानों को दोबारा जांचें; मूल आकार के लिए समान स्केलिंग (जैसे `Scale(1,1)`) उपयोग करें |
| आउटपुट फ़ाइल खाली है | स्ट्रीम फ़्लश नहीं हुई | सुनिश्चित करें कि `document.Save()` `using` ब्लॉक के अंदर कॉल किया गया है |
| असमर्थित छवि फ़ॉर्मेट | Bitmap फ़ाइल को लोड नहीं कर पा रहा है | इमेज को JPEG, PNG, BMP, या GIF जैसे समर्थित फ़ॉर्मेट में बदलें |

## निष्कर्ष

बधाई हो! आपने Aspose.Page for .NET का उपयोग करके PostScript दस्तावेज़ में **how to add image** सफलतापूर्वक सीख लिया है। अब आपके पास ग्राफ़िक्स इन्सर्ट करने की ठोस नींव है, और आप यह भी जानते हैं कि आवश्यकता पड़ने पर **extract images from ps** और **insert bitmap into ps** कैसे किया जाता है। कई इमेज, विभिन्न ट्रांसफ़ॉर्मेशन या कस्टम ड्रॉइंग कमांड्स के साथ प्रयोग करने में संकोच न करें ताकि आप समृद्ध, प्रिंटेबल कंटेंट बना सकें।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं Aspose.Page का उपयोग करके एक ही PS दस्तावेज़ में कई इमेज जोड़ सकता हूँ?

A1: हाँ, आप कर सकते हैं। बस दस्तावेज़ के भीतर इमेज जोड़ने के चरणों को दोहराएँ।

### Q2: Aspose.Page for .NET कौन-कौन से इमेज फ़ॉर्मेट सपोर्ट करता है?

A2: Aspose.Page for .NET JPEG, PNG, BMP, और GIF सहित विभिन्न इमेज फ़ॉर्मेट को सपोर्ट करता है।

### Q3: इमेज के आकार पर कोई सीमा है क्या?

A3: आकार सीमा PS दस्तावेज़ की विशिष्टताओं और सिस्टम संसाधनों पर निर्भर करती है। Aspose.Page बहुत बड़े इमेज को भी संभाल सकता है।

### Q4: क्या मैं इमेज पर अतिरिक्त इफ़ेक्ट्स जैसे फ़िल्टर या ओवरले लगा सकता हूँ?

A4: हाँ, Aspose.Page इमेज को दस्तावेज़ में जोड़ने से पहले विभिन्न ट्रांसफ़ॉर्मेशन और इफ़ेक्ट्स लागू करने की अनुमति देता है।

### Q5: मैं PS दस्तावेज़ से इमेज कैसे निकाल सकता हूँ?

A5: Aspose.Page for .NET PS दस्तावेज़ों से इमेज निकालने के मेथड्स प्रदान करता है। विस्तृत जानकारी के लिए डॉक्यूमेंटेशन देखें।

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Page for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}