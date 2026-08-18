---
date: 2026-02-23
description: PostScript फ़ाइलों में ग्रेडिएंट कैसे जोड़ें, A4 पेज आकार के साथ PostScript
  फ़ाइल को सहेजें, और Aspose.Page for .NET का उपयोग करके आयत के ग्रेडिएंट को भरें।
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Aspose.Page .NET के साथ PostScript (PS) में ग्रेडिएंट – डायगोनल ग्रेडिएंट कैसे
  जोड़ें
url: /hi/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

}}.

Let's craft.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ग्रेडिएंट कैसे जोड़ें: Aspose.Page .NET के साथ PostScript (PS) में डायगोनल ग्रेडिएंट

## परिचय

PostScript (PS) दस्तावेज़ में एक डायगोनल ग्रेडिएंट जोड़ने से दृश्य आकर्षण में काफी सुधार हो सकता है, विशेष रूप से जब आपको तकनीकी रिपोर्ट, ब्रोशर, या ग्राफ़िक्स‑इंटेंसिव एप्लिकेशन में **how to add gradient** प्रभाव चाहिए। इस ट्यूटोरियल में आप देखेंगे कि PostScript फ़ाइल में ग्रेडिएंट कैसे जोड़ें, A4 पेज आकार सेट करें, और Aspose.Page for .NET का उपयोग करके एक आयत को स्मूथ रंग परिवर्तन से भरें।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for .NET  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **क्या मैं ग्रेडिएंट की दिशा बदल सकता हूँ?** हाँ – कोड में दिखाए अनुसार ब्रश ट्रांसफ़ॉर्म को घुमाएँ  
- **परिणाम को कैसे सहेजूँ?** `PsDocument.Save()` का उपयोग करें जो PostScript फ़ाइल को डिस्क पर लिखता है  
- **उत्पादन के लिए लाइसेंस आवश्यक है?** हाँ, एक कमर्शियल लाइसेंस पूरी कार्यक्षमता अनलॉक करता है  

## PostScript में डायगोनल ग्रेडिएंट क्या है?

डायगोनल ग्रेडिएंट एक रैखिक रंग परिवर्तन है जो किसी आकार के पार एक कोण (आमतौर पर 45°) पर चलता है। PostScript में यह `LinearGradientBrush` को एक कस्टम ट्रांसफ़ॉर्मेशन मैट्रिक्स के साथ लागू करके प्राप्त किया जाता है जो ग्रेडिएंट को घुमाता, स्केल करता और ट्रांसलेट करता है ताकि इच्छित आयत से मेल खाए।

## ग्रेडिएंट फ़िल्स के लिए Aspose.Page क्यों उपयोग करें?

Aspose.Page लो‑लेवल PostScript कमांड्स को एब्स्ट्रैक्ट करता है, जिससे आप परिचित .NET ग्राफ़िक्स ऑब्जेक्ट्स के साथ काम कर सकते हैं। आप जटिल फ़िल्स बना सकते हैं, पेज डाइमेंशन सेट कर सकते हैं, और सीधे **save PostScript file** में एक्सपोर्ट कर सकते हैं बिना कच्चे PS सिंटैक्स को संभाले।

## पूर्वापेक्षाएँ

- **Aspose.Page for .NET Library** – इसे [यहाँ](https://releases.aspose.com/page/net/) से डाउनलोड करें।  
- **Document Directory** – वह फ़ोल्डर जहाँ उत्पन्न `*.ps` फ़ाइल लिखी जाएगी।

अब जब बुनियादी बातें कवर हो गई हैं, चलिए कार्यान्वयन को चरण‑दर‑चरण देखते हैं।

## नेमस्पेस इम्पोर्ट करें

पहले उन नेमस्पेस को इम्पोर्ट करें जो आपको EPS डिवाइस, ड्रॉइंग यूटिलिटीज़, और I/O क्लासेज़ तक पहुँच प्रदान करते हैं।

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## चरण 1: PostScript दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं (Create PostScript Document)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## चरण 2: A4 पेज आकार सेट करें (Save Options)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## चरण 3: नया 1‑पेज वाला PS दस्तावेज़ बनाएं

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## चरण 4: आयत पैरामीटर परिभाषित करें

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## चरण 5: ग्राफ़िक्स पाथ बनाएं

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## चरण 6: लीनियर ग्रेडिएंट ब्रश बनाएं (Fill Rectangle Gradient)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## चरण 7: ब्रश के लिए ट्रांसफ़ॉर्म बनाएं

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## चरण 8: ब्रश पर ट्रांसफ़ॉर्मेशन लागू करें (Rotate, Scale, Translate)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## चरण 9: ब्रश पर ट्रांसफ़ॉर्म सेट करें

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## चरण 10: पेंट सेट करें और आयत को भरें

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## चरण 11: वर्तमान पेज बंद करें

```csharp
	//Close current page
	document.ClosePage();
```

## चरण 12: दस्तावेज़ सहेजें (Save PostScript File)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## PostScript फ़ाइल कैसे सहेजें

`PsDocument.Save()` कॉल पूरी‑तरह से निर्मित PostScript सामग्री को उस स्ट्रीम में लिखता है जिसे आपने **चरण 1** में खोला था। `using` ब्लॉक समाप्त होने के बाद, फ़ाइल `DiagonaGradient_outPS.ps` निर्दिष्ट डायरेक्टरी में उपलब्ध होगी।

## सामान्य उपयोग केस

- **तकनीकी दस्तावेज़ीकरण** जहाँ हल्का बैकग्राउंड शेडिंग चाहिए।  
- **मार्केटिंग ब्रोशर** जहाँ डायगोनल ग्रेडिएंट आधुनिक लुक जोड़ता है।  
- **ऑटोमेटेड रिपोर्ट जेनरेटर** जो ऑन‑द‑फ़्लाई प्रिंटेबल PS फ़ाइलें बनाते हैं।

## ट्रबलशूटिंग और टिप्स

- **गलत रंग** – `LinearGradientBrush` को पास किए गए ARGB मानों को दोबारा जांचें।  
- **ग्रेडिएंट दिखाई नहीं दे रहा** – सुनिश्चित करें कि ट्रांसफ़ॉर्म मैट्रिक्स सही ढंग से घुमाता और स्केल करता है; `Rotate(-45)` कॉल डायगोनल कोण सेट करता है।  
- **फ़ाइल नहीं बन रही** – पुष्टि करें कि `dataDir` मौजूदा फ़ोल्डर की ओर इशारा कर रहा है और एप्लिकेशन के पास लिखने की अनुमति है।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या Aspose.Page सभी .NET फ्रेमवर्क के साथ संगत है?**  
उत्तर: Aspose.Page .NET Framework 4.5+ से लेकर .NET 6+ तक के विस्तृत संस्करणों को समर्थन देता है, जिससे व्यापक संगतता मिलती है।

**प्रश्न: क्या मैं Aspose.Page में ग्रेडिएंट रंगों को कस्टमाइज़ कर सकता हूँ?**  
उत्तर: हाँ, आप `LinearGradientBrush` बनाते समय कोई भी ARGB रंग निर्दिष्ट कर सकते हैं, जिससे प्रारंभिक और अंतिम ह्यूज़ पर पूर्ण नियंत्रण मिलता है।

**प्रश्न: क्या Aspose.Page के लिए ट्रायल संस्करण उपलब्ध है?**  
उत्तर: हाँ, आप ट्रायल संस्करण को [यहाँ](https://releases.aspose.com/) डाउनलोड करके Aspose.Page की सुविधाओं का अन्वेषण कर सकते हैं।

**प्रश्न: मैं Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
उत्तर: मूल्यांकन के दौरान अतिरिक्त क्षमताएँ अनलॉक करने के लिए Aspose.Page का अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) प्राप्त करें।

**प्रश्न: Aspose.Page के लिए समुदाय समर्थन कहाँ मिल सकता है?**  
उत्तर: सहायता और चर्चा के लिए Aspose.Page समुदाय के साथ [फ़ोरम](https://forum.aspose.com/c/page/39) पर जुड़ें।

---

**अंतिम अपडेट:** 2026-02-23  
**परीक्षित संस्करण:** Aspose.Page for .NET (नवीनतम स्थिर रिलीज)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}