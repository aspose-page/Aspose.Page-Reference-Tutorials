---
date: 2026-03-26
description: Aspose.Page का उपयोग करके .NET में PostScript दस्तावेज़ बनाना और एक पारदर्शी
  छवि जोड़ना सीखें। यह चरण‑दर‑चरण गाइड आवश्यकताएँ, कोड और सुझावों को कवर करता है।
linktitle: Add Transparent Image to PostScript (PS)
second_title: Aspose.Page .NET API
title: पारदर्शी छवि के साथ .NET में पोस्टस्क्रिप्ट दस्तावेज़ बनाएं (Aspose.Page)
url: /hi/net/transparency-effects/add-transparent-image-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create PostScript document .NET with transparent image (Aspose.Page)

## Introduction

इस ट्यूटोरियल में आप **कैसे .NET में PostScript दस्तावेज़ बनाते हैं** और Aspose.Page for .NET का उपयोग करके एक पारदर्शी PNG एम्बेड करते हैं, यह सीखेंगे। पारदर्शी इमेज़ जोड़ने से आप अधिक समृद्ध, लेयर‑डेड ग्राफ़िक्स बना सकते हैं—वॉटरमार्क, ओवरले, या UI मॉक‑अप्स के लिए PS फ़ाइल में बिल्कुल उपयुक्त। हम हर कदम को विस्तार से बताएँगे, पर्यावरण सेट‑अप से लेकर अपारदर्शी और पारदर्शी दोनों इमेज़ को रेंडर करने तक।

## Quick Answers
- **Aspose.Page क्या करता है?** यह .NET में PostScript (PS) और XPS दस्तावेज़ बनाने, संपादित करने और रेंडर करने के लिए एक पूर्ण‑फ़ीचर API प्रदान करता है।  
- **क्या मैं पारदर्शी PNG जोड़ सकता हूँ?** हाँ—पारदर्शिता नियंत्रित करने के लिए `DrawTransparentImage` का उपयोग करें।  
- **कौन‑से .NET संस्करण समर्थित हैं?** सभी नवीनतम .NET Framework, .NET Core, और .NET 5/6 रिलीज़।  
- **क्या लाइसेंस की आवश्यकता है?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बेसिक उदाहरण के लिए लगभग 10‑15 मिनट।

## Prerequisites

शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

- **Aspose.Page for .NET** – इसे [download link](https://releases.aspose.com/page/net/) से डाउनलोड करें।  
- एक फ़ोल्डर जहाँ आप PS दस्तावेज़ और एम्बेड करने वाली इमेज़ रखेंगे।  
- एक ट्रांस्लूसेंट PNG (जैसे `mask1.png`) जो पारदर्शी लेयर के रूप में उपयोग होगी।

## Import Namespaces

सबसे पहले उन नेमस्पेस को इम्पोर्ट करें जिनमें वह क्लासेज़ हैं जिनकी हमें आवश्यकता होगी। इससे हमें PS दस्तावेज़ मॉडल, ग्राफ़िक्स यूटिलिटीज़, और बेसिक .NET ड्रॉइंग टाइप्स तक पहुँच मिलती है।

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up Your Document Directory

स्रोत इमेज़ और आउटपुट PS फ़ाइल के पाथ को परिभाषित करें। प्लेसहोल्डर को अपने मशीन के वास्तविक पाथ से बदलें।

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Step 2: Create Output Stream for PostScript Document

हम जनरेट किए गए PS कंटेंट को एक फ़ाइल स्ट्रीम में लिखेंगे। यह स्ट्रीम बाद में `PsDocument` कंस्ट्रक्टर को पास किया जाता है।

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTransparentImage_outPS.ps", FileMode.Create))
{
    // Your code for the next steps will go here.
}
```

## Step 3: Set Save Options and Background Color

`PsSaveOptions` को कॉन्फ़िगर करें ताकि फ़ाइल कैसे सेव होगी, यह निर्धारित हो सके। पारदर्शी एलिमेंट्स के पीछे एक ठोस कैनवास चाहिए तो बैकग्राउंड कलर सेट करना उपयोगी होता है।

```csharp
PsSaveOptions options = new PsSaveOptions();
options.BackgroundColor = Color.FromArgb(211, 8, 48);
```

## Step 4: Create a New 1‑Paged PS Document

स्ट्रीम और ऊपर परिभाषित विकल्पों का उपयोग करके दस्तावेज़ बनाएँ। `false` फ़्लैग Aspose.Page को स्ट्रीम को स्वचालित रूप से बंद करने से रोकता है।

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 5: Write Graphics Save and Translate

ड्रॉ करने से पहले, हम वर्तमान ग्राफ़िक्स स्टेट को सेव करते हैं और ओरिजिन को ट्रांसलेट करते हैं ताकि हमारी इमेज़ पेज पर इच्छित स्थान पर दिखाई दे।

```csharp
document.WriteGraphicsSave();
document.Translate(20, 100);
```

## How to add transparent image to a PostScript document

### Step 6: Add Opaque RGB Image

पहले हम वही PNG को सामान्य अपारदर्शी इमेज़ के रूप में जोड़ते हैं। यह बाद में पारदर्शिता लागू करने पर दृश्य अंतर को दर्शाता है।

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 100, 0), Color.Empty);
}
```

### Step 7: Add Transparent Image

अब हम `DrawTransparentImage` का उपयोग करके PNG को एक अपारदर्शिता मान के साथ रेंडर करते हैं। तीसरा पैरामीटर (`255`) पूर्ण अपारदर्शिता दर्शाता है; कम मान पारदर्शिता बढ़ाते हैं। यहाँ हम **.NET में इमेज़ पारदर्शिता सेट** करते हैं।

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawTransparentImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 350, 0), 255);
}
```

> **Pro tip:** इमेज़ को 50 % पारदर्शी बनाने के लिए `255` के बजाय `128` पास करें।

## Step 8: Write Graphics Restore and Close Page

ड्रॉ करने के बाद, पिछले ग्राफ़िक्स स्टेट को रिस्टोर करें और पेज को बंद करके कंटेंट को फाइनल करें।

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## Step 9: Save the Document

अंत में, PS फ़ाइल को डिस्क पर सेव करें।

```csharp
document.Save();
```

इन चरणों को फॉलो करके आपने **.NET में PostScript दस्तावेज़ बनाया** है जिसमें एक अपारदर्शी और एक पारदर्शी इमेज़ दोनों हैं, जिससे **C# में पारदर्शी इमेज़ ड्रॉ करना** Aspose.Page के साथ संभव हो गया।

## Why use Aspose.Page for transparency effects?

- **Full control** ग्राफ़िक्स स्टेट, मैट्रिसेज़, और अपारदर्शिता स्तरों पर।  
- **No external dependencies**—सभी चीज़ें शुद्ध .NET कोड के भीतर चलती हैं।  
- **Cross‑platform** सपोर्ट आपको Windows, Linux, या macOS पर PS फ़ाइलें जनरेट करने की अनुमति देता है।

## Common Pitfalls & Troubleshooting

| Issue | Solution |
|-------|----------|
| इमेज़ `DrawTransparentImage` के बाद भी पूरी तरह अपारदर्शी दिखती है | सुनिश्चित करें कि अल्फ़ा वैल्यू (तीसरा आर्ग्युमेंट) `255` से कम है। |
| PS फ़ाइल में खाली पेज दिख रहा है | बैकग्राउंड कलर सेट है या नहीं, और स्ट्रीम पाथ सही है, यह जाँचें। |
| Exception “File not found” | `dataDir` और यह कि `mask1.png` उस फ़ोल्डर में मौजूद है, दोबारा जाँचें। |

## Frequently Asked Questions

**Q: क्या मैं PNG के अलावा अन्य इमेज फ़ॉर्मेट का उपयोग पारदर्शिता के लिए कर सकता हूँ?**  
A: हाँ—Aspose.Page PNG, GIF, और TIFF को पारदर्शी रेंडरिंग के लिए सपोर्ट करता है।

**Q: क्या Aspose.Page नवीनतम .NET फ्रेमवर्क के साथ संगत है?**  
A: बिल्कुल। लाइब्रेरी को नियमित रूप से .NET 6, .NET 7 और उससे आगे के संस्करणों के लिए अपडेट किया जाता है।

**Q: क्या मैं मौजूदा PS दस्तावेज़ में पारदर्शिता लागू कर सकता हूँ?**  
A: हाँ। `PsDocument` से दस्तावेज़ खोलें, नया पेज जोड़ें या मौजूदा को संशोधित करें, फिर वही `DrawTransparentImage` तरीका अपनाएँ।

**Q: सामान्य ग्राफ़िक्स लाइब्रेरी की तुलना में Aspose.Page के क्या फायदे हैं?**  
A: यह विशेष रूप से PS/XPS के लिए बनाया गया है, जिससे वेक्टर ग्राफ़िक्स, फ़ॉन्ट और इमेज़ हैंडलिंग पर सटीक नियंत्रण मिलता है, बिना पूर्ण रेंडरिंग इंजन की आवश्यकता के।

**Q: क्या पारदर्शिता स्तर पर कोई सीमा है?**  
A: नहीं। आप `0` (पूरी तरह पारदर्शी) से `255` (पूरी तरह अपारदर्शी) तक कोई भी अल्फ़ा वैल्यू सेट कर सकते हैं।

## Conclusion

हमने दिखाया कि **.NET में PostScript दस्तावेज़ कैसे बनाते हैं** और Aspose.Page का उपयोग करके अपारदर्शी और पारदर्शी दोनों इमेज़ एम्बेड करते हैं। यह तकनीक प्रोग्रामेटिक रूप से C# से जटिल दस्तावेज़ लेआउट, वॉटरमार्किंग, और लेयर‑डेड ग्राफ़िक्स बनाने के द्वार खोलती है।

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}