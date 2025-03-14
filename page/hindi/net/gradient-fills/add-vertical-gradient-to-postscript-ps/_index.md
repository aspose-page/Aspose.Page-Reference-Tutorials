---
title: Aspose.Page के साथ पोस्टस्क्रिप्ट (PS) में वर्टिकल ग्रेडिएंट जोड़ें
linktitle: पोस्टस्क्रिप्ट (PS) में वर्टिकल ग्रेडिएंट जोड़ें
second_title: Aspose.Page .NET API
description: Aspose.Page का उपयोग करके .NET में पोस्टस्क्रिप्ट (PS) दस्तावेज़ों में दृश्यमान रूप से आकर्षक लंबवत ग्रेडिएंट जोड़ने का तरीका जानें। इस चरण-दर-चरण मार्गदर्शिका के साथ अपने दस्तावेज़ निर्माण को उन्नत बनाएं।
weight: 14
url: /hi/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ पोस्टस्क्रिप्ट (PS) में वर्टिकल ग्रेडिएंट जोड़ें

## परिचय

दस्तावेज़ हेरफेर और निर्माण के क्षेत्र में, .NET के लिए Aspose.Page डेवलपर्स के लिए एक शक्तिशाली उपकरण के रूप में सामने आता है। यह ट्यूटोरियल आपको .NET के लिए Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट (PS) दस्तावेज़ में एक वर्टिकल ग्रेडिएंट जोड़ने की प्रक्रिया में मार्गदर्शन करेगा। इस गाइड के अंत तक, आपको इस आकर्षक प्रभाव को प्राप्त करने के लिए आवश्यक कदमों की स्पष्ट समझ हो जाएगी।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित स्थान हैं:

-  .NET के लिए Aspose.Page: सुनिश्चित करें कि आपके पास Aspose.Page लाइब्रेरी स्थापित है। आप आवश्यक संसाधन और दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/page/net/).

- विकास वातावरण: .NET विकास के लिए एक एकीकृत विकास वातावरण (आईडीई) सहित एक उपयुक्त विकास वातावरण स्थापित करें।

- बुनियादी समझ: स्ट्रीम, ग्राफिक्स पथ और रंग हेरफेर के साथ काम करने सहित .NET विकास की बुनियादी बातों से खुद को परिचित करें।

## नामस्थान आयात करें

अपने C# प्रोजेक्ट में, अपनी कोड फ़ाइल की शुरुआत में आवश्यक नामस्थान शामिल करें:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

अपनी दस्तावेज़ निर्देशिका का पथ निर्दिष्ट करके प्रारंभ करें। यह वह स्थान है जहां आपका PS दस्तावेज़ सहेजा जाएगा।

```csharp
string dataDir = "Your Document Directory";
```

## चरण 2: पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं

फ़ाइलस्ट्रीम क्लास का उपयोग करके पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम जेनरेट करें।

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## चरण 3: सेव विकल्प और पीएस दस्तावेज़ बनाएं

A4 आकार के साथ सेव विकल्प बनाएं और एक नया 1-पृष्ठ वाला PS दस्तावेज़ प्रारंभ करें।

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## चरण 4: आयत आयाम परिभाषित करें

आयत के आयाम और स्थिति निर्दिष्ट करें जहां ऊर्ध्वाधर ढाल लागू की जाएगी।

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## चरण 5: ग्राफ़िक्स पथ बनाएँ

परिभाषित आयत से एक ग्राफ़िक्स पथ बनाएँ।

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## चरण 6: इंटरपोलेशन रंगों को परिभाषित करें

ग्रेडिएंट के लिए इंटरपोलेशन रंगों और स्थितियों की एक श्रृंखला स्थापित करें।

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## चरण 7: लीनियर ग्रेडिएंट ब्रश बनाएं

सीमा, आरंभ और अंत रंगों के रूप में आयत के साथ एक रेखीय ग्रेडिएंट ब्रश बनाएं।

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## चरण 8: ब्रश ट्रांसफ़ॉर्म सेट करें

ब्रश के लिए एक ट्रांसफ़ॉर्म स्थापित करें, यह सुनिश्चित करते हुए कि X और Y स्केल घटक आयत की चौड़ाई और ऊंचाई से मेल खाते हैं।

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## चरण 9: पेंट सेट करें और आयत भरें

दस्तावेज़ के लिए पेंट सेट करें, और पहले से परिभाषित आयत भरें।

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## चरण 10: वर्तमान पृष्ठ बंद करें और दस्तावेज़ सहेजें

वर्तमान पृष्ठ बंद करें और पोस्टस्क्रिप्ट दस्तावेज़ सहेजें।

```csharp
document.ClosePage();
document.Save();
```

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके एक पोस्टस्क्रिप्ट दस्तावेज़ में सफलतापूर्वक एक लंबवत ग्रेडिएंट जोड़ा है। अपने दस्तावेज़ों में विभिन्न दृश्य प्रभाव प्राप्त करने के लिए विभिन्न मापदंडों और रंगों के साथ प्रयोग करें।

## निष्कर्ष

इस ट्यूटोरियल में, हमने वर्टिकल ग्रेडिएंट्स को शामिल करके आपके पोस्टस्क्रिप्ट दस्तावेज़ों को बढ़ाने की प्रक्रिया का पता लगाया। .NET के लिए Aspose.Page इस तरह के हेरफेर के लिए एक सहज वातावरण प्रदान करता है, जो डेवलपर्स को सहजता से आश्चर्यजनक दस्तावेज़ बनाने के लिए सशक्त बनाता है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं एक ही दस्तावेज़ के विभिन्न क्षेत्रों में एकाधिक ग्रेडिएंट लागू कर सकता हूँ?

A1: हाँ, आप कर सकते हैं। बस प्रत्येक क्षेत्र के लिए उसके विशिष्ट आयामों और रंग योजना के साथ चरणों को दोहराएं।

### Q2: मैं इस कोड को अपने मौजूदा .NET प्रोजेक्ट में कैसे एकीकृत कर सकता हूं?

A2: कोड को अपनी प्रोजेक्ट फ़ाइल में कॉपी और पेस्ट करें और सुनिश्चित करें कि आपके पास Aspose.Page लाइब्रेरी संदर्भित है।

### Q3: क्या .NET के लिए Aspose.Page में अन्य ग्रेडिएंट प्रकार उपलब्ध हैं?

A3: Aspose.Page रेडियल और पथ ग्रेडिएंट सहित विभिन्न ग्रेडिएंट प्रकारों का समर्थन करता है। अधिक विवरण के लिए दस्तावेज़ देखें।

### Q4: क्या मैं व्यावसायिक परियोजनाओं के लिए Aspose.Page का उपयोग कर सकता हूँ?

 उ4: हाँ, आप कर सकते हैं। मिलने जाना[यहाँ](https://purchase.aspose.com/buy) लाइसेंसिंग विकल्पों का पता लगाने के लिए।

### Q5: क्या Aspose.Page के लिए कोई सामुदायिक मंच है जहां मैं मदद मांग सकता हूं?

 ए5: निश्चित रूप से! की ओर जाएं[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) अन्य डेवलपर्स से जुड़ने और सहायता प्राप्त करने के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
