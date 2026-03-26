---
date: 2026-03-26
description: Aspose.Page का उपयोग करके .NET में टेक्सचर टाइलिंग पैटर्न के साथ पोस्टस्क्रिप्ट
  दस्तावेज़ बनाना सीखें। अपने PS फ़ाइलों में समृद्ध टेक्सचर जोड़ने के लिए हमारी चरण‑दर‑चरण
  गाइड का पालन करें।
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: टेक्सचर टाइलिंग के साथ पोस्टस्क्रिप्ट .NET दस्तावेज़ बनाएं
url: /hi/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# टेक्सचर टाइलिंग के साथ PostScript .NET दस्तावेज़ बनाएं

## कैसे बनाएं PostScript दस्तावेज़ .NET में टेक्सचर टाइलिंग के साथ

इस ट्यूटोरियल में आप सीखेंगे कि **PostScript दस्तावेज़ .NET** कैसे बनाएं और Aspose.Page लाइब्रेरी का उपयोग करके उसमें टेक्सचर टाइलिंग पैटर्न जोड़ें। हम प्रत्येक चरण को विस्तार से बताएंगे, प्रोजेक्ट सेटअप से लेकर टेक्सचर ब्रश के साथ टेक्स्ट को फ़िल और स्ट्रोक करने तक, ताकि आप कुछ ही मिनटों में आकर्षक PS फ़ाइलें बना सकें।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी उपयोग की जाती है?** Aspose.Page for .NET  
- **क्या .NET Core का उपयोग कर सकता हूँ?** हाँ, लाइब्रेरी .NET Core और .NET 5/6 को सपोर्ट करती है  
- **टेक्सचर के लिए कौन से इमेज फ़ॉर्मेट काम करेंगे?** System.Drawing द्वारा समर्थित कोई भी फ़ॉर्मेट (BMP, PNG, JPEG, आदि)  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बेसिक उदाहरण के लिए लगभग 10‑15 मिनट  
- **क्या लाइसेंस चाहिए?** परीक्षण के लिए फ्री ट्रायल चल सकता है; प्रोडक्शन के लिए लाइसेंस आवश्यक है  

## पूर्वापेक्षाएँ

- आपके मशीन पर स्थापित [Visual Studio](https://visualstudio.microsoft.com/)  
- C# प्रोग्रामिंग का बेसिक ज्ञान  
- [Aspose.Page for .NET लाइब्रेरी](https://releases.aspose.com/page/net/) डाउनलोड और इंस्टॉल करें  
- टेक्सचर पैटर्न के लिए एक इमेज फ़ाइल (उदा., **TestTexture.bmp**)  

## नेमस्पेस इम्पोर्ट करें

अपने C# फ़ाइल में आवश्यक नेमस्पेस इम्पोर्ट करें ताकि कंपाइलर को उन टाइप्स का पता चल सके जिन्हें हम उपयोग करेंगे:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## चरण 1: दस्तावेज़ डायरेक्टरी सेट करें

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

**Your Document Directory** को उस फ़ोल्डर से बदलें जहाँ आप जनरेटेड PS फ़ाइल को सेव करना चाहते हैं।

## चरण 2: PS दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

यह ब्लॉक फ़ाइल स्ट्रीम खोलता है, पेज साइज (डिफ़ॉल्ट रूप से A4) कॉन्फ़िगर करता है, और एक नया **PsDocument** इंस्टेंस बनाता है जिस पर हम ड्रॉ करेंगे।

## चरण 3: टेक्सचर टाइलिंग पैटर्न लागू करें

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

यहाँ हम बिटमैप लोड करते हैं, उसे **TextureBrush** में रैप करते हैं, वैकल्पिक रूप से क्षैतिज रूप से स्ट्रेच करते हैं, और **PsDocument** को बताते हैं कि आगे की ड्रॉइंग ऑपरेशन्स में इस ब्रश का उपयोग करे।

## चरण 4: रेक्टेंगल पाथ बनाएं और फ़िल करें

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

एक साधा रेक्टेंगल परिभाषित किया गया है और पहले सेट किए गए टेक्सचर ब्रश से फ़िल किया गया है।

## चरण 5: स्ट्रोक सेट करें और ड्रॉ करें

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

हम वर्तमान पेंट (टेक्सचर ब्रश) प्राप्त करते हैं, आउटलाइन के लिए एक लाल पेन बनाते हैं, और रेक्टेंगल की बॉर्डर ड्रॉ करते हैं।

## चरण 6: टेक्सचर पैटर्न के साथ टेक्स्ट को फ़िल और स्ट्रोक करें

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

यह चरण **fill and stroke text** क्षमता को दर्शाता है: अक्षर “ABC” टेक्सचर ब्रश से फ़िल होते हैं और फिर आउटलाइन होते हैं, जिससे एक प्रभावशाली विज़ुअल इफ़ेक्ट मिलता है।

## चरण 7: दस्तावेज़ को सेव और क्लोज करें

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

पेज को क्लोज करने से ड्रॉइंग कमांड्स फाइनल हो जाते हैं, और `Save()` पोस्टस्क्रिप्ट फ़ाइल को डिस्क पर लिखता है।

## सामान्य समस्याएँ और समाधान

- **टेक्सचर गलत तरीके से स्ट्रेच हो रहा है** – स्केलिंग को X/Y दिशा में नियंत्रित करने के लिए `Matrix` वैल्यूज़ समायोजित करें।  
- **इमेज नहीं मिली** – सुनिश्चित करें कि `dataDir` सही फ़ोल्डर की ओर इशारा कर रहा है और फ़ाइल नाम बिल्कुल समान है, केस सहित।  
- **रंग गलत दिख रहे हैं** – याद रखें कि PostScript डिवाइस‑इंडिपेंडेंट कलर स्पेस उपयोग करता है; सुनिश्चित करें कि आप सही `Color` ऑब्जेक्ट्स उपयोग कर रहे हैं।

## अक्सर पूछे जाने वाले प्रश्न

**प्र:** क्या मैं टेक्सचर पैटर्न के लिए अन्य इमेज फ़ॉर्मेट उपयोग कर सकता हूँ?  
**उ:** हाँ, `System.Drawing.Bitmap` द्वारा समर्थित कोई भी फ़ॉर्मेट (BMP, PNG, JPEG, GIF, आदि) काम करेगा।

**प्र:** क्या Aspose.Page .NET Core के साथ संगत है?  
**उ:** बिल्कुल। लाइब्रेरी .NET Framework, .NET Core, और .NET 5/6 पर चलती है।

**प्र:** टेक्सचर वाले रेक्टेंगल का आकार कैसे बदलूँ?  
**उ:** रेक्टेंगल‑क्रिएशन चरण में `RectangleF` वैल्यूज़ को बदलें (उदा., `new RectangleF(0, 0, 300, 150)`)।

**प्र:** क्या एक ही दस्तावेज़ में कई टेक्सचर पैटर्न लागू कर सकता हूँ?  
**उ:** हाँ। बस एक नया `TextureBrush` अलग इमेज के साथ बनाएं और अगली शैप या टेक्स्ट ड्रॉ करने से पहले `SetPaint` फिर से कॉल करें।

**प्र:** और उदाहरण तथा API रेफ़रेंस कहाँ मिलेंगे?  
**उ:** समुदाय सहायता के लिए [Aspose.Page Forum](https://forum.aspose.com/c/page/39) देखें और विस्तृत API उपयोग के लिए आधिकारिक [documentation](https://reference.aspose.com/page/net/) देखें।

## निष्कर्ष

अब आप जानते हैं कि **PostScript दस्तावेज़ .NET** कैसे बनाएं और टेक्सचर टाइलिंग पैटर्न लागू करें, जिसमें **fill and stroke text** भी शामिल है। विभिन्न इमेज, स्केलिंग मैट्रिक्स, और ड्रॉइंग प्रिमिटिव्स के साथ प्रयोग करें ताकि रिपोर्ट, फ़्लायर या किसी भी ग्राफ़िक‑हैवी आउटपुट के लिए कस्टम‑स्टाइल्ड PS फ़ाइलें बना सकें।

---

**अंतिम अपडेट:** 2026-03-26  
**टेस्टेड विद:** Aspose.Page 24.11 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}