---
title: Aspose.Page के साथ पोस्टस्क्रिप्ट (PS) पर टेक्सचर टाइलिंग पैटर्न लागू करें
linktitle: पोस्टस्क्रिप्ट (पीएस) पर टेक्सचर टाइलिंग पैटर्न लागू करें
second_title: Aspose.Page .NET API
description: .NET के लिए Aspose.Page का उपयोग करके टेक्सचर टाइलिंग पैटर्न के साथ अपने पोस्टस्क्रिप्ट (PS) दस्तावेज़ों को बेहतर बनाएं। रचनात्मक स्पर्श के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 10
url: /hi/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ पोस्टस्क्रिप्ट (PS) पर टेक्सचर टाइलिंग पैटर्न लागू करें

## परिचय

.NET के लिए Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट (PS) दस्तावेज़ में टेक्सचर टाइलिंग पैटर्न कैसे लागू करें, इस चरण-दर-चरण ट्यूटोरियल में आपका स्वागत है। Aspose.Page एक शक्तिशाली लाइब्रेरी है जो आपको विभिन्न दस्तावेज़ प्रारूपों के साथ काम करने की अनुमति देती है, और इस ट्यूटोरियल में, हम यह पता लगाएंगे कि टेक्सचर टाइलिंग पैटर्न जोड़कर अपने PS दस्तावेज़ों को कैसे बढ़ाया जाए।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- [विजुअल स्टूडियो](https://visualstudio.microsoft.com/) आपकी मशीन पर स्थापित.
- सी# प्रोग्रामिंग का बुनियादी ज्ञान।
-  डाउनलोड करें और इंस्टॉल करें[.NET लाइब्रेरी के लिए Aspose.Page](https://releases.aspose.com/page/net/).
- बनावट पैटर्न के लिए एक छवि फ़ाइल (उदाहरण के लिए, "TestTexture.bmp")।

## नामस्थान आयात करें

अपने C# कोड में, सुनिश्चित करें कि आप आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

आइए प्रक्रिया में आपका मार्गदर्शन करने के लिए दिए गए उदाहरण को कई चरणों में विभाजित करें।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
```

"आपकी दस्तावेज़ निर्देशिका" को उस पथ से बदलना सुनिश्चित करें जहां आप अपना पीएस दस्तावेज़ सहेजना चाहते हैं।

## चरण 2: पीएस दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं

```csharp
// पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // A4 आकार के साथ सेव विकल्प बनाएं
    PsSaveOptions options = new PsSaveOptions();

    // नया 1-पृष्ठ वाला PS दस्तावेज़ बनाएँ
    PsDocument document = new PsDocument(outPsStream, options, false);
```

यह चरण पीएस दस्तावेज़ के लिए आउटपुट स्ट्रीम सेट करता है, जिसमें दस्तावेज़ का आकार परिभाषित करना भी शामिल है।

## चरण 3: टेक्सचर टाइलिंग पैटर्न लागू करें

```csharp
// छवि फ़ाइल से एक बिटमैप ऑब्जेक्ट बनाएं
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // छवि से बनावट ब्रश बनाएं
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //पैटर्न में X दिशा में स्केलिंग जोड़ें
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // इस टेक्सचर ब्रश को वर्तमान पेंट के रूप में सेट करें
    document.SetPaint(brush);
}
```

इस चरण में एक छवि से एक बनावट ब्रश बनाना और इसे दस्तावेज़ के लिए वर्तमान पेंट के रूप में सेट करना शामिल है।

## चरण 4: आयत पथ बनाएं और भरें

```csharp
// आयताकार पथ बनाएं
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// आयत भरें
document.Fill(path);
```

यहां, हम एक आयत पथ को परिभाषित करते हैं और इसे पहले से सेट बनावट ब्रश से भरते हैं।

## चरण 5: स्ट्रोक सेट करें और ड्रा करें

```csharp
// वर्तमान पेंट प्राप्त करें
Brush paint = document.GetPaint();

// लाल स्ट्रोक सेट करें
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// आयत को स्ट्रोक करें
document.Draw(path);
```

इस चरण में स्ट्रोक गुण सेट करना और उल्लिखित आयत बनाना शामिल है।

## चरण 6: टेक्स्ट को बनावट पैटर्न के साथ भरें और रेखांकित करें

```csharp
// टेक्स्ट को बनावट पैटर्न से भरें
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// बनावट पैटर्न के साथ पाठ की रूपरेखा तैयार करें
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

अंत में, हम आपके दस्तावेज़ की दृश्य अपील को बढ़ाते हुए, बनावट पैटर्न के साथ टेक्स्ट को भरते हैं और रेखांकित करते हैं।

## चरण 7: दस्तावेज़ सहेजें और बंद करें

```csharp
// वर्तमान पृष्ठ बंद करें
document.ClosePage();

// दस्तावेज़ सहेजें
document.Save();
```

परिवर्तनों को लागू करने के लिए वर्तमान पृष्ठ को बंद करना और दस्तावेज़ को सहेजना सुनिश्चित करें।

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट दस्तावेज़ में टेक्सचर टाइलिंग पैटर्न लागू करना सफलतापूर्वक सीख लिया है। अपने पीएस दस्तावेज़ों को और अधिक अनुकूलित करने के लिए विभिन्न छवियों और पैटर्न के साथ प्रयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं बनावट पैटर्न के लिए अन्य छवि प्रारूपों का उपयोग कर सकता हूँ?

A1: हां, Aspose.Page विभिन्न छवि प्रारूपों का समर्थन करता है। पुस्तकालय दस्तावेज़ीकरण के साथ अनुकूलता सुनिश्चित करें।

### Q2: क्या Aspose.Page .NET कोर के साथ संगत है?

A2: हाँ, Aspose.Page .NET Framework और .NET Core दोनों के साथ संगत है।

### Q3: मैं बनावट वाले आयत का आकार कैसे समायोजित कर सकता हूं?

 A3: में आयाम संशोधित करें`RectangleF` पथ निर्माण के दौरान पैरामीटर।

### Q4: क्या मैं एक ही दस्तावेज़ में एकाधिक बनावट पैटर्न जोड़ सकता हूँ?

उ4: हां, आप विभिन्न छवियों और पथों के साथ प्रक्रिया को दोहरा सकते हैं।

### Q5: मुझे अतिरिक्त संसाधन और सहायता कहां मिल सकती है?

 A5: पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक समर्थन के लिए और अन्वेषण करें[प्रलेखन](https://reference.aspose.com/page/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
