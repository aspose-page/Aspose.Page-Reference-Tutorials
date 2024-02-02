---
title: Aspose.Page .NET के साथ पोस्टस्क्रिप्ट (PS) में डायगोनल ग्रेडिएंट जोड़ें
linktitle: पोस्टस्क्रिप्ट में विकर्ण ग्रेडिएंट जोड़ें (पीएस)
second_title: Aspose.Page .NET API
description: Aspose.Page के साथ .NET में पोस्टस्क्रिप्ट दस्तावेज़ों में विकर्ण ग्रेडिएंट जोड़ने की सरलता का अन्वेषण करें। गतिशील दृश्य तत्वों के साथ अपनी परियोजनाओं को उन्नत करें।
type: docs
weight: 10
url: /hi/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
---
## परिचय

पोस्टस्क्रिप्ट (पीएस) दस्तावेज़ में एक विकर्ण ढाल जोड़ने से आपकी परियोजनाओं में दृश्य अपील और रचनात्मकता आ सकती है। .NET के लिए Aspose.Page इस सुविधा को आपके अनुप्रयोगों में एकीकृत करने के लिए एक सहज समाधान प्रदान करता है। इस ट्यूटोरियल में, हम आपको चरण दर चरण Aspose.Page का उपयोग करके PS दस्तावेज़ में एक विकर्ण ग्रेडिएंट जोड़ने की प्रक्रिया के बारे में मार्गदर्शन करेंगे।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET लाइब्रेरी के लिए Aspose.Page: सुनिश्चित करें कि आपके पास .NET लाइब्रेरी के लिए Aspose.Page स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/net/).

- दस्तावेज़ निर्देशिका: अपने दस्तावेज़ों के लिए एक निर्देशिका सेट करें जहां आउटपुट पीएस फ़ाइल सहेजी जाएगी।

अब, आइए चरण-दर-चरण मार्गदर्शिका पर आगे बढ़ें।

## नामस्थान आयात करें

सबसे पहले, अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करना सुनिश्चित करें। Aspose.Page कार्यात्मकताओं के साथ काम करने के लिए ये नामस्थान महत्वपूर्ण हैं।

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
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## चरण 2: A4 आकार के साथ सेव विकल्प बनाएं

```csharp
	//A4 आकार के साथ सेव विकल्प बनाएं
	PsSaveOptions options = new PsSaveOptions();
```

## चरण 3: एक नया 1-पृष्ठ पीएस दस्तावेज़ बनाएँ

```csharp
	// नया 1-पृष्ठ वाला PS दस्तावेज़ बनाएँ
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## चरण 4: आयत पैरामीटर्स को परिभाषित करें

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## चरण 5: ग्राफ़िक्स पथ बनाएँ

```csharp
	//पहले आयत से ग्राफ़िक्स पथ बनाएँ
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## चरण 6: लीनियर ग्रेडिएंट ब्रश बनाएं

```csharp
	//सीमा, प्रारंभ और अंत रंगों के रूप में आयत के साथ रैखिक ग्रेडिएंट ब्रश बनाएं
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## चरण 7: ब्रश के लिए ट्रांसफ़ॉर्म बनाएं

```csharp
	//ब्रश के लिए एक ट्रांसफ़ॉर्म बनाएं. X और Y स्केल घटक क्रमशः आयत की चौड़ाई और ऊंचाई के बराबर होने चाहिए।
	// अनुवाद घटक आयत के ऑफसेट हैं
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## चरण 8: ब्रश पर परिवर्तन लागू करें

```csharp
	//आवश्यक आयत में दृश्यमान रंग परिवर्तन प्राप्त करने के लिए ग्रेडिएंट घुमाएं, फिर स्केल करें और अनुवाद करें
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## चरण 9: ट्रांसफ़ॉर्म को ब्रश पर सेट करें

```csharp
	//परिवर्तन सेट करें
	brush.Transform = brushTransform;
```

## चरण 10: पेंट सेट करें और आयत भरें

```csharp
	//पेंट सेट करें
	document.SetPaint(brush);

	//आयत भरें
	document.Fill(path);
```

## चरण 11: वर्तमान पृष्ठ बंद करें

```csharp
	//वर्तमान पृष्ठ बंद करें
	document.ClosePage();
```

## चरण 12: दस्तावेज़ सहेजें

```csharp
	//दस्तावेज़ सहेजें
	document.Save();
}
// ExEnd:1
```

इन चरणों का पालन करके, आप .NET के लिए Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट दस्तावेज़ में सफलतापूर्वक एक विकर्ण ग्रेडिएंट जोड़ देंगे।

## निष्कर्ष

अपने पीएस दस्तावेज़ों को विकर्ण ग्रेडिएंट के साथ बढ़ाने से आपकी परियोजनाएँ दृष्टिगत रूप से आकर्षक और गतिशील बन सकती हैं। .NET के लिए Aspose.Page इस प्रक्रिया को सरल बनाता है, जिससे डेवलपर्स आसानी से इस सुविधा को अपने अनुप्रयोगों में एकीकृत कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.Page सभी .NET फ्रेमवर्क के साथ संगत है?

A1: Aspose.Page विभिन्न .NET फ्रेमवर्क का समर्थन करता है, जो विकास परिवेशों की एक विस्तृत श्रृंखला के साथ अनुकूलता सुनिश्चित करता है।

### Q2: क्या मैं Aspose.Page में ग्रेडिएंट रंगों को कस्टमाइज़ कर सकता हूँ?

A2: हाँ, Aspose.Page आपके प्रोजेक्ट की आवश्यकताओं के अनुसार ग्रेडिएंट रंगों को चुनने और अनुकूलित करने में लचीलापन प्रदान करता है।

### Q3: क्या Aspose.Page के लिए कोई परीक्षण संस्करण उपलब्ध है?

 उ3: हां, आप परीक्षण संस्करण डाउनलोड करके Aspose.Page की सुविधाओं का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).

### Q4: मैं Aspose.Page के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 A4: Aspose.Page के लिए एक अस्थायी लाइसेंस प्राप्त करें[यहाँ](https://purchase.aspose.com/temporary-license/) अतिरिक्त सुविधाओं को अनलॉक करने के लिए.

### Q5: मुझे Aspose.Page के लिए सामुदायिक समर्थन कहां मिल सकता है?

 A5: Aspose.Page समुदाय के साथ जुड़ें[मंच](https://forum.aspose.com/c/page/39) सहायता और चर्चा के लिए.