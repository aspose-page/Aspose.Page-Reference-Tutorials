---
title: .NET के लिए Aspose.Page के साथ पोस्टस्क्रिप्ट (PS) में आयत जोड़ें
linktitle: पोस्टस्क्रिप्ट में आयत जोड़ें (पीएस)
second_title: Aspose.Page .NET API
description: Aspose.Page के साथ .NET में दस्तावेज़ निर्माण बढ़ाएँ। चरण-दर-चरण पोस्टस्क्रिप्ट (PS) फ़ाइलों में आयत जोड़ना सीखें।
weight: 12
url: /hi/net/drawing-shapes/add-rectangle-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Page के साथ पोस्टस्क्रिप्ट (PS) में आयत जोड़ें

## परिचय

यदि आप .NET में अपनी दस्तावेज़ निर्माण क्षमताओं को बढ़ाना चाहते हैं, तो Aspose.Page पोस्टस्क्रिप्ट दस्तावेज़ों को संभालने के लिए एक शक्तिशाली समाधान प्रदान करता है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट दस्तावेज़ में आयत जोड़ने की प्रक्रिया में आपका मार्गदर्शन करेंगे।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET लाइब्रेरी के लिए Aspose.Page: .NET लाइब्रेरी के लिए Aspose.Page को यहां से डाउनलोड और इंस्टॉल करें।[यहाँ](https://releases.aspose.com/page/net/).

- विकास परिवेश: सुनिश्चित करें कि आपकी मशीन पर .NET विकास परिवेश स्थापित है।

## नामस्थान आयात करें

कोडिंग शुरू करने से पहले, आवश्यक कक्षाओं और विधियों तक पहुँचने के लिए आवश्यक नामस्थान आयात करना सुनिश्चित करें:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

अब, आइए उदाहरण को कई चरणों में विभाजित करें:

## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें

```csharp
// एक्सस्टार्ट:1
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
```

इस चरण में, "आपकी दस्तावेज़ निर्देशिका" को उस पथ से बदलें जहां आप अपना पोस्टस्क्रिप्ट दस्तावेज़ सहेजना चाहते हैं।

## चरण 2: पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं

```csharp
//पोस्टस्क्रिप्ट दस्तावेज़ के लिए आउटपुट स्ट्रीम बनाएं
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

यहां, हम पोस्टस्क्रिप्ट दस्तावेज़ के लिए एक आउटपुट स्ट्रीम बनाते हैं और फ़ाइल नाम ("AddRectangel_outPS.ps") निर्दिष्ट करते हैं। अपनी प्राथमिकताओं के अनुसार फ़ाइल का नाम और स्थान समायोजित करें।

## चरण 3: सेव विकल्प सेट करें और पीएस दस्तावेज़ बनाएं

```csharp
//A4 आकार के साथ सेव विकल्प बनाएं
PsSaveOptions options = new PsSaveOptions();

// नया 1-पृष्ठ वाला PS दस्तावेज़ बनाएँ
PsDocument document = new PsDocument(outPsStream, options, false);
```

वांछित पृष्ठ आकार (इस मामले में A4) निर्दिष्ट करते हुए, सेव विकल्प सेट करें। फिर, एक नया एकल-पृष्ठ वाला पोस्टस्क्रिप्ट दस्तावेज़ बनाएं।

## चरण 4: आयत जोड़ें और भरें

```csharp
//पहले आयत से ग्राफ़िक्स पथ बनाएँ
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//पेंट सेट करें
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//आयत भरें
document.Fill(path);
```

यहां, हम पहले आयत का प्रतिनिधित्व करने वाला एक ग्राफिक्स पथ बनाते हैं, पेंट का रंग सेट करते हैं (इस मामले में, नारंगी), और आयत को भरते हैं।

## चरण 5: एक और आयत और स्ट्रोक जोड़ें

```csharp
//दूसरे आयत से ग्राफ़िक्स पथ बनाएँ
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//स्ट्रोक सेट करें
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//आयत को स्ट्रोक (रूपरेखा) करें
document.Draw(path);
```

पिछले चरण के समान, हम दूसरे आयत के लिए एक ग्राफिक्स पथ बनाते हैं, स्ट्रोक रंग (3 की मोटाई के साथ लाल) सेट करते हैं, और आयत की रूपरेखा तैयार करते हैं।

## चरण 6: पृष्ठ बंद करें और दस्तावेज़ सहेजें

```csharp
//वर्तमान पृष्ठ बंद करें
document.ClosePage();

//दस्तावेज़ सहेजें
document.Save();
```

अंत में, वर्तमान पृष्ठ को बंद करें और संपूर्ण दस्तावेज़ को सहेजें।

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Page का उपयोग करके पोस्टस्क्रिप्ट दस्तावेज़ में आयतों को सफलतापूर्वक जोड़ दिया है। इस ट्यूटोरियल में आपके विकास परिवेश को स्थापित करने से लेकर अंतिम दस्तावेज़ को सहेजने तक, आवश्यक चरणों को शामिल किया गया है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं आयतों के रंगों को अनुकूलित कर सकता हूँ?

A1: हाँ, आप पैरामीटर्स को समायोजित करके रंगों को अनुकूलित कर सकते हैं`SolidBrush` और`Pen` कक्षाएं.

### Q2: क्या Aspose.Page अन्य दस्तावेज़ प्रारूपों के साथ संगत है?

A2: हां, Aspose.Page XPS और पोस्टस्क्रिप्ट सहित विभिन्न दस्तावेज़ प्रारूपों का समर्थन करता है।

### Q3: मैं दस्तावेज़ में टेक्स्ट कैसे जोड़ सकता हूँ?

 A3: आप इसका उपयोग कर सकते हैं`TextFragment` अपने दस्तावेज़ में टेक्स्ट जोड़ने के लिए Aspose.Page में क्लास।

### Q4: मुझे अतिरिक्त उदाहरण और दस्तावेज़ कहां मिल सकते हैं?

 A4: दस्तावेज़ का अन्वेषण करें[यहाँ](https://reference.aspose.com/page/net/) और विजिट करें[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक समर्थन के लिए.

### Q5: क्या मैं खरीदने से पहले Aspose.Page आज़मा सकता हूँ?

 A5: हाँ, आप निःशुल्क परीक्षण संस्करण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/) , और विस्तारित उपयोग के लिए, एक पर विचार करें[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
