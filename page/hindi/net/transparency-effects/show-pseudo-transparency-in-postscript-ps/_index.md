---
title: Aspose.Page के साथ पोस्टस्क्रिप्ट (पीएस) में छद्म पारदर्शिता दिखाएं
linktitle: पोस्टस्क्रिप्ट में छद्म पारदर्शिता दिखाएं (पीएस)
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page के साथ पोस्टस्क्रिप्ट में छद्म पारदर्शिता की शक्ति का अन्वेषण करें। दृश्यात्मक रूप से आश्चर्यजनक दस्तावेज़ों के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 13
url: /hi/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---
## परिचय

क्या आप छद्म पारदर्शिता को शामिल करके अपने पोस्टस्क्रिप्ट (पीएस) दस्तावेज़ों की दृश्य अपील को बढ़ाना चाहते हैं? .NET के लिए Aspose.Page इस प्रभाव को सहजता से प्राप्त करने के लिए एक शक्तिशाली समाधान प्रदान करता है। इस चरण-दर-चरण ट्यूटोरियल में, हम आपको Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट में छद्म पारदर्शिता दिखाने की प्रक्रिया के माध्यम से मार्गदर्शन करेंगे।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- .NET के लिए Aspose.Page: सुनिश्चित करें कि आपके पास .NET के लिए Aspose.Page लाइब्रेरी स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose.पेज दस्तावेज़ीकरण](https://reference.aspose.com/page/net/).

- दस्तावेज़ निर्देशिका: अपने पोस्टस्क्रिप्ट दस्तावेज़ों को संग्रहीत करने के लिए एक निर्देशिका सेट करें।

अब जब आपके पास अपने शस्त्रागार में आवश्यक उपकरण हैं, तो आइए जानें कि Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट में छद्म पारदर्शिता कैसे प्रदर्शित की जाए।

## नामस्थान आयात करें

उदाहरण पर ध्यान देने से पहले, सुनिश्चित करें कि आप आवश्यक नामस्थान आयात कर लें:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## चरण 1: पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं

```csharp
// एक्सस्टार्ट:1
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
//पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//A4 आकार के साथ सेव विकल्प बनाएं
	PsSaveOptions options = new PsSaveOptions();

	// नया 1-पृष्ठ वाला PS दस्तावेज़ बनाएँ
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## चरण 2: अपारदर्शी ग्रेडिएंट भरण के साथ आयत बनाएं

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

## चरण 3: पारभासी ग्रेडिएंट भरण के साथ आयत बनाएं

```csharp
	offsetX = 350;

	//पहले आयत से ग्राफ़िक्स पथ बनाएँ
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//रैखिक ग्रेडिएंट ब्रश रंग बनाएं जिनकी पारदर्शिता 255 नहीं, बल्कि 150 और 50 हो। इसलिए यह पारभासी हैं।
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## चरण 4: वर्तमान पृष्ठ बंद करें और दस्तावेज़ सहेजें

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

इन चरणों का पालन करके, आप .NET के लिए Aspose.Page का उपयोग करके अपने पोस्टस्क्रिप्ट दस्तावेज़ों में छद्म पारदर्शिता को सहजता से एकीकृत कर सकते हैं।

## निष्कर्ष

अंत में, .NET के लिए Aspose.Page आपके पोस्टस्क्रिप्ट दस्तावेज़ों के दृश्य तत्वों को बढ़ाने का एक सीधा और कुशल तरीका प्रदान करता है। ऊपर उल्लिखित चरण छद्म पारदर्शिता को शामिल करने के लिए एक स्पष्ट मार्ग प्रदान करते हैं, जिससे आप दृश्यमान आश्चर्यजनक आउटपुट बना सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.Page .NET के सभी संस्करणों के साथ संगत है?

A1: .NET के लिए Aspose.Page, .NET फ्रेमवर्क के विभिन्न संस्करणों के साथ संगत है, जो लचीलापन और एकीकरण में आसानी सुनिश्चित करता है।

### Q2: क्या मैं आयतों के अलावा अन्य आकृतियों पर छद्म पारदर्शिता लागू कर सकता हूँ?

A2: हाँ, ग्राफ़िक्सपाथ को तदनुसार समायोजित करके समान सिद्धांतों को अन्य आकृतियों पर लागू किया जा सकता है।

### Q3: मुझे अतिरिक्त उदाहरण और दस्तावेज़ कहां मिल सकते हैं?

 ए3: अन्वेषण करें[Aspose.पेज दस्तावेज़ीकरण](https://reference.aspose.com/page/net/) व्यापक उदाहरणों और विस्तृत दस्तावेज़ीकरण के लिए।

### Q4: क्या Aspose.Page के लिए कोई निःशुल्क परीक्षण उपलब्ध है?

 A4: हां, आप Aspose.Page के निःशुल्क परीक्षण तक पहुंच सकते हैं[इस लिंक](https://releases.aspose.com/).

### Q5: मैं Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 ए5: विजिट करें[इस लिंक](https://purchase.aspose.com/temporary-license/) Aspose.Page के लिए एक अस्थायी लाइसेंस प्राप्त करने के लिए।