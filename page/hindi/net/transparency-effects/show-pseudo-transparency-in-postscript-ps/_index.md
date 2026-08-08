---
date: 2026-03-29
description: C# में एक रैखिक ग्रेडिएंट ब्रश का उपयोग करके Aspose.Page for .NET के
  साथ पोस्टस्क्रिप्ट में छद्म‑पारदर्शिता कैसे बनाएं, सीखें।
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: पीएस में स्यूडो‑ट्रांसपेरेंसी के लिए C# में लीनियर ग्रेडिएंट ब्रश
url: /hi/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# पोस्टस्क्रिप्ट (PS) में छद्म‑पारदर्शिता के लिए C# में रैखिक ग्रेडिएंट ब्रश

## परिचय

यदि आपको अपने पोस्टस्क्रिप्ट (PS) फ़ाइलों में एक सूक्ष्म पारदर्शी प्रभाव जोड़ना है, तो **linear gradient brush C#** बिल्कुल उपयुक्त उपकरण है। Aspose.Page for .NET आयतों को अपारदर्शी और अर्धपारदर्शी ग्रेडिएंट फ़िल्स के साथ पेंट करना आसान बनाता है, जिससे आपके दस्तावेज़ों को आधुनिक, परतदार लुक मिलता है। इस ट्यूटोरियल में हम C# में रैखिक ग्रेडिएंट ब्रश का उपयोग करके छद्म‑पारदर्शिता बनाने के लिए आवश्यक सटीक चरणों को समझेंगे।

## त्वरित उत्तर
- **रैखिक ग्रेडिएंट ब्रश प्रदान करने वाली लाइब्रेरी कौन सी है?** Aspose.Page for .NET
- **ग्रेडिएंट बनाने वाली ग्राफ़िक्स क्लास कौन सी है?** `LinearGradientBrush`
- **क्या मैं प्रत्येक रंग की अपारदर्शिता नियंत्रित कर सकता हूँ?** हाँ, `Color.FromArgb(alpha, …)` का उपयोग करके
- **उत्पादन के लिए क्या मुझे लाइसेंस चाहिए?** एक वैध Aspose.Page लाइसेंस आवश्यक है
- **समर्थित .NET संस्करण?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## C# में रैखिक ग्रेडिएंट ब्रश क्या है?

`LinearGradientBrush` एक GDI+ ऑब्जेक्ट है जो दो रंगों के बीच एक सीधी रेखा के साथ सुगम संक्रमण पेंट करता है। जब आप प्रत्येक रंग के लिए अल्फा चैनल (0‑255) निर्दिष्ट करते हैं, तो आप अर्धपारदर्शी ग्रेडिएंट बना सकते हैं—जो पोस्टस्क्रिप्ट में छद्म‑पारदर्शिता के लिए बिल्कुल आवश्यक है।

## छद्म‑पारदर्शिता के लिए C# में रैखिक ग्रेडिएंट ब्रश क्यों उपयोग करें?

- **सूक्ष्म‑स्तर की अपारदर्शिता नियंत्रण:** प्रत्येक रंग के अल्फा को समायोजित करके वांछित पारदर्शिता स्तर प्राप्त करें।  
- **डिवाइस‑स्वतंत्र रेंडरिंग:** ब्रश स्क्रीन, PDF, EPS, और PS आउटपुट पर समान रूप से काम करता है।  
- **सरल API:** C# कोड की कुछ पंक्तियों से पेशेवर‑स्तर के दृश्य प्रभाव प्राप्त होते हैं।

## आवश्यकताएँ

कोड में जाने से पहले, सुनिश्चित करें कि आपके पास है:

- Aspose.Page for .NET स्थापित है। आप इसे [Aspose.Page documentation](https://reference.aspose.com/page/net/) से डाउनलोड कर सकते हैं।
- एक लिखने योग्य फ़ोल्डर जहाँ उत्पन्न पोस्टस्क्रिप्ट दस्तावेज़ सहेजा जाएगा।

अब जब आपके पास आवश्यक उपकरण हैं, चलिए छद्म‑पारदर्शी आयतें बनाना शुरू करते हैं।

## नेमस्पेस आयात करें

Before we begin, import the namespaces that contain the classes we’ll use:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## चरण 1: पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं

हम एक फ़ाइल स्ट्रीम बनाकर शुरू करते हैं जो परिणामी PS फ़ाइल को रखेगा, फिर `PsDocument` को प्रारंभ करते हैं।

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## चरण 2: **अपारदर्शी** ग्रेडिएंट फ़िल के साथ एक आयत बनाएं

यहाँ हम एक `LinearGradientBrush` बनाते हैं जिसकी रंग पूरी तरह अपारदर्शी (alpha = 255) हैं। यह आयत पृष्ठभूमि परत के रूप में कार्य करेगी।

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## चरण 3: **अर्धपारदर्शी** ग्रेडिएंट फ़िल के साथ एक आयत बनाएं

अब हम एक **linear gradient brush C#** का उपयोग करते हैं जहाँ अल्फा मान 255 से कम होते हैं (उदाहरण के लिए 150 और 50)। इससे आयत आंशिक रूप से पारदर्शी बनती है, जिससे छद्म‑पारदर्शिता प्रभाव प्राप्त होता है।

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## चरण 4: पृष्ठ बंद करें और दस्तावेज़ सहेजें

अंत में हम पृष्ठ को समाप्त करते हैं और PS फ़ाइल को डिस्क पर लिखते हैं।

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

इन चार चरणों का पालन करके आप अपारदर्शी और अर्धपारदर्शी आयतों को सहजता से मिश्रित कर सकते हैं, जिससे किसी भी पोस्टस्क्रिप्ट आउटपुट में विश्वसनीय छद्म‑पारदर्शी प्रभाव बनता है।

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|----------------|-----|
| रंग पूरी तरह अपारदर्शी दिखते हैं | अल्फा मान गलती से 255 सेट किया गया | `alpha` < 255 के साथ `Color.FromArgb(alpha, …)` का उपयोग करें |
| ग्रेडिएंट गलत तरीके से विस्तारित है | गलत ट्रांसफ़ॉर्मेशन मैट्रिक्स | मैट्रिक्स पैरामीटर को आयत के आयामों से मिलान करें |
| आउटपुट फ़ाइल खाली है | स्ट्रीम बंद नहीं हुई या `Save()` कॉल नहीं किया गया | `document.ClosePage()` और `document.Save()` को `using` ब्लॉक के भीतर निष्पादित किया गया है, यह सुनिश्चित करें |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Page सभी .NET संस्करणों के साथ संगत है?**  
A: Aspose.Page for .NET विभिन्न .NET फ्रेमवर्क संस्करणों के साथ संगत है, जिससे लचीलापन और आसान एकीकरण सुनिश्चित होता है।

**Q: क्या मैं आयतों के अलावा अन्य आकारों पर भी छद्म‑पारदर्शिता लागू कर सकता हूँ?**  
A: हाँ, समान सिद्धांतों को `GraphicsPath` को उचित रूप से समायोजित करके किसी भी आकार पर लागू किया जा सकता है।

**Q: मैं अतिरिक्त उदाहरण और दस्तावेज़ कहाँ पा सकता हूँ?**  
A: व्यापक उदाहरणों और विस्तृत API संदर्भों के लिए [Aspose.Page documentation](https://reference.aspose.com/page/net/) देखें।

**Q: क्या Aspose.Page के लिए कोई मुफ्त ट्रायल उपलब्ध है?**  
A: हाँ, आप [इस लिंक](https://releases.aspose.com/) से Aspose.Page का मुफ्त ट्रायल प्राप्त कर सकते हैं।

**Q: मैं Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?**  
A: Aspose.Page के लिए अस्थायी लाइसेंस प्राप्त करने हेतु [इस लिंक](https://purchase.aspose.com/temporary-license/) पर जाएँ।

---

**अंतिम अपडेट:** 2026-03-29  
**परीक्षण किया गया:** Aspose.Page 24.11 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}