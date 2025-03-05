---
title: Aspose.Page के साथ पोस्टस्क्रिप्ट (PS) में क्षैतिज ग्रेडिएंट जोड़ें
linktitle: पोस्टस्क्रिप्ट में क्षैतिज ग्रेडिएंट जोड़ें (PS)
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page का उपयोग करके आश्चर्यजनक क्षैतिज ग्रेडिएंट के साथ पोस्टस्क्रिप्ट दस्तावेज़ों को बेहतर बनाएं। निर्बाध कार्यान्वयन के लिए हमारे चरण-दर-चरण ट्यूटोरियल का पालन करें।
type: docs
weight: 12
url: /hi/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
---
## परिचय

.NET के लिए Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट (PS) दस्तावेज़ों में क्षैतिज ग्रेडिएंट जोड़ने पर इस व्यापक ट्यूटोरियल में आपका स्वागत है। Aspose.Page एक शक्तिशाली लाइब्रेरी है जो विभिन्न प्रारूपों में दस्तावेज़ हेरफेर की सुविधा प्रदान करती है, डेवलपर्स को दस्तावेज़ों को निर्बाध रूप से बनाने, संशोधित करने और प्रस्तुत करने के लिए आवश्यक उपकरण प्रदान करती है।

इस ट्यूटोरियल में, हम आकर्षक क्षैतिज ग्रेडिएंट्स को शामिल करके आपके पोस्टस्क्रिप्ट दस्तावेज़ों को बढ़ाने पर ध्यान केंद्रित करेंगे। हम आपको प्रक्रिया के प्रत्येक चरण के बारे में बताएंगे, यह सुनिश्चित करते हुए कि आप कार्यान्वयन की ठोस समझ प्राप्त करें।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET लाइब्रेरी के लिए Aspose.Page: सुनिश्चित करें कि आपके पास .NET लाइब्रेरी के लिए Aspose.Page आपके विकास परिवेश में एकीकृत है। आप इसे यहां से डाउनलोड कर सकते हैं[.NET दस्तावेज़ीकरण के लिए Aspose.Page](https://reference.aspose.com/page/net/).

- दस्तावेज़ निर्देशिका: अपने दस्तावेज़ों को संग्रहीत करने के लिए एक निर्देशिका सेट करें, और दिए गए कोड में "आपकी दस्तावेज़ निर्देशिका" को वास्तविक पथ से बदलें।

अब, आइए देखें कि पोस्टस्क्रिप्ट दस्तावेज़ में चरण दर चरण क्षैतिज ग्रेडिएंट कैसे जोड़ें।

## नामस्थान आयात करें

शुरू करने से पहले, Aspose.Page द्वारा प्रदान की गई कार्यक्षमताओं तक पहुंचने के लिए आवश्यक नामस्थान आयात करना आवश्यक है। अपने कोड की शुरुआत में निम्नलिखित नामस्थान जोड़ें:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## चरण 1: दस्तावेज़ सेट करें

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";

// पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // A4 आकार के साथ सेव विकल्प बनाएं
    PsSaveOptions options = new PsSaveOptions();

    // नया 1-पृष्ठ वाला PS दस्तावेज़ बनाएँ
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## चरण 2: ग्रेडिएंट आयत और रंगों को परिभाषित करें

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // पहले आयत से ग्राफ़िक्स पथ बनाएँ
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    //सीमा, प्रारंभ और अंत रंगों के रूप में आयत के साथ रैखिक ग्रेडिएंट ब्रश बनाएं
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## चरण 3: ब्रश के लिए ट्रांसफ़ॉर्म सेट करें

```csharp
    // ब्रश के लिए एक ट्रांसफ़ॉर्म बनाएं. X और Y स्केल घटक क्रमशः आयत की चौड़ाई और ऊंचाई के बराबर होने चाहिए।
    // अनुवाद घटक आयत के ऑफसेट हैं
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // परिवर्तन सेट करें
    brush.Transform = brushTransform;
```

## चरण 4: पेंट सेट करें और आयत भरें

```csharp
    // पेंट सेट करें
    document.SetPaint(brush);

    // आयत भरें
    document.Fill(path);
```

## चरण 5: टेक्स्ट को ग्रेडिएंट से भरें

```csharp
    // टेक्स्ट को ग्रेडिएंट से भरें
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## चरण 6: स्ट्रोक और आउटलाइन टेक्स्ट सेट करें

```csharp
    // वर्तमान स्ट्रोक सेट करें
    document.SetStroke(new Pen(brush, 5));
    // ग्रेडिएंट के साथ पाठ की रूपरेखा बनाएं
    document.OutlineText("ABC", font, 200, 400);
```

## चरण 7: वर्तमान पृष्ठ बंद करें और दस्तावेज़ सहेजें

```csharp
    // वर्तमान पृष्ठ बंद करें
    document.ClosePage();

    // दस्तावेज़ सहेजें
    document.Save();
}
```

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट दस्तावेज़ में एक क्षैतिज ग्रेडिएंट सफलतापूर्वक जोड़ दिया है।

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET लाइब्रेरी के लिए Aspose.Page का उपयोग करके आपके पोस्टस्क्रिप्ट दस्तावेज़ों को क्षैतिज ग्रेडिएंट के साथ बढ़ाने की प्रक्रिया को कवर किया है। चरण-दर-चरण मार्गदर्शिका का पालन करके, आपने दस्तावेज़ हेरफेर के लिए इस शक्तिशाली उपकरण का लाभ उठाने में मूल्यवान अंतर्दृष्टि प्राप्त की है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं आयतों के अलावा अन्य आकृतियों पर ग्रेडिएंट लागू कर सकता हूँ?

 A1: हां, आप Aspose.Page का उपयोग करके विभिन्न आकृतियों में ग्रेडिएंट लागू कर सकते हैं। संशोधित करें`GraphicsPath` आपके विशिष्ट आकार के अनुरूप रचना।

### Q2: मैं ग्रेडिएंट रंग कैसे बदल सकता हूँ?

 A2: समायोजित करें`Color.FromArgb` मूल्यों में`LinearGradientBrush` वांछित ग्रेडिएंट रंग प्राप्त करने के लिए तात्कालिकता।

### Q3: क्या Aspose.Page विभिन्न दस्तावेज़ प्रारूपों के साथ संगत है?

A3: Aspose.Page XPS, PS, PDF और अन्य सहित विभिन्न दस्तावेज़ प्रारूपों का समर्थन करता है। विस्तृत सूची के लिए दस्तावेज़ देखें।

### Q4: क्या मैं व्यावसायिक परियोजनाओं के लिए Aspose.Page का उपयोग कर सकता हूँ?

 A4: हां, Aspose.Page वाणिज्यिक लाइसेंसिंग विकल्पों के साथ आता है। मिलने जाना[यहाँ](https://purchase.aspose.com/buy) जानकारी के लिए।

### Q5: क्या Aspose.Page उपयोगकर्ताओं के लिए कोई सामुदायिक मंच है?

 A5: हाँ, Aspose.Page समुदाय में शामिल हों[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) अन्य उपयोगकर्ताओं से जुड़ने और सहायता प्राप्त करने के लिए।