---
title: Aspose.Page के साथ XPS दस्तावेज़ में पारदर्शी ऑब्जेक्ट जोड़ें
linktitle: XPS दस्तावेज़ में पारदर्शी ऑब्जेक्ट जोड़ें
second_title: Aspose.Page .NET API
description: Aspose.Page का उपयोग करके .NET में XPS दस्तावेज़ों में पारदर्शी ऑब्जेक्ट जोड़ने का तरीका जानें। चरण-दर-चरण मार्गदर्शन के साथ दृश्य अपील बढ़ाएँ।
weight: 11
url: /hi/net/transparency-effects/add-transparent-object-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ XPS दस्तावेज़ में पारदर्शी ऑब्जेक्ट जोड़ें

## परिचय

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Page का उपयोग करके XPS दस्तावेज़ में पारदर्शी ऑब्जेक्ट कैसे जोड़ें। एक्सपीएस दस्तावेज़ों में पारदर्शिता दृश्य अपील को बढ़ा सकती है और जानकारी को प्रभावी ढंग से संप्रेषित कर सकती है। हम स्पष्टता और समझने में आसानी सुनिश्चित करते हुए प्रक्रिया को प्रबंधनीय चरणों में विभाजित करेंगे।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET के लिए Aspose.Page: सुनिश्चित करें कि आपके पास .NET के लिए Aspose.Page लाइब्रेरी स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[.NET दस्तावेज़ीकरण के लिए Aspose.Page](https://reference.aspose.com/page/net/).

## नामस्थान आयात करें

आरंभ करने के लिए, अपने प्रोजेक्ट में आवश्यक नामस्थान शामिल करें:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

अब, चरण-दर-चरण मार्गदर्शिका के साथ आगे बढ़ें।

## चरण 1: एक नया XPS दस्तावेज़ बनाएँ

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
// नया XPS दस्तावेज़ बनाएं
XpsDocument doc = new XpsDocument();
```

यह कोड .NET के लिए Aspose.Page का उपयोग करके एक नया XPS दस्तावेज़ प्रारंभ करता है।

## चरण 2: पारदर्शिता प्रदर्शित करें

```csharp
// सिर्फ पारदर्शिता प्रदर्शित करने के लिए
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

ये पंक्तियाँ दस्तावेज़ में पारदर्शिता के प्रभाव को प्रदर्शित करने के लिए पारदर्शी पथ बनाती हैं।

## चरण 3: बंद आयत ज्यामिति के साथ एक पथ बनाएं

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

यहां, हम एक बंद आयत ज्यामिति के साथ एक पथ बनाते हैं, इसे भरने के लिए एक नीला ठोस ब्रश सेट करते हैं, और इसे वर्तमान पृष्ठ में जोड़ते हैं।

## चरण 4: पथ और रंगों में हेरफेर करें

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

यह चरण दर्शाता है कि पथों में कैसे हेरफेर किया जा सकता है, और रंग कैसे बदले जा सकते हैं।

## चरण 5: पथों को क्लोन करें और रूपांतरित करें

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

पथों को क्लोन करना और रूपांतरित करना, क्लोन पथ का रंग बदलना और बदलना।

## चरण 6: पथों को दोहराएं और संशोधित करें

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

संशोधनों के साथ पिछले पथ के आधार पर एक नया पथ बनाते हुए प्रक्रिया को दोहराएं।

## चरण 7: अपारदर्शिता प्रबंधित करें

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

प्रदर्शित करें कि विभिन्न पथों के लिए अपारदर्शिता को स्वतंत्र रूप से कैसे प्रबंधित किया जा सकता है।

## चरण 8: एक्सपीएस दस्तावेज़ सहेजें

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

अंत में, परिणामी XPS दस्तावेज़ को लागू पारदर्शिता के साथ सहेजें।

## निष्कर्ष

.NET के लिए Aspose.Page का उपयोग करके XPS दस्तावेज़ों में पारदर्शी ऑब्जेक्ट जोड़ना दृश्य प्रस्तुतियों को बढ़ाने का एक बहुमुखी तरीका प्रदान करता है। वांछित प्रभाव प्राप्त करने के लिए विभिन्न ज्यामितियों, रंगों और अपारदर्शिताओं के साथ प्रयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं XPS दस्तावेज़ में किसी ऑब्जेक्ट पर पारदर्शिता लागू कर सकता हूँ?

A1: हां, XPS दस्तावेज़ में पथ, आकार और छवियों जैसी विभिन्न वस्तुओं पर पारदर्शिता लागू की जा सकती है।

### Q2: मैं किसी विशिष्ट तत्व की अपारदर्शिता को कैसे समायोजित कर सकता हूँ?

A2: आप किसी विशिष्ट तत्व की पारदर्शिता को समायोजित करने के लिए भरण या स्ट्रोक की अपारदर्शिता संपत्ति सेट कर सकते हैं।

### Q3: क्या Aspose.Page .NET कोर के साथ संगत है?

A3: हाँ, Aspose.Page .NET कोर का समर्थन करता है, जो क्रॉस-प्लेटफ़ॉर्म विकास को सक्षम करता है।

### Q4: क्या मैं Aspose.Page का उपयोग करके XPS दस्तावेज़ों को अन्य प्रारूपों में निर्यात कर सकता हूँ?

A4: Aspose.Page पीडीएफ और छवियों सहित विभिन्न प्रारूपों में XPS दस्तावेज़ों को निर्यात करने की कार्यक्षमता प्रदान करता है।

### Q5: मुझे अतिरिक्त सहायता और सामुदायिक चर्चाएँ कहाँ मिल सकती हैं?

 A5: अतिरिक्त सहायता और सामुदायिक चर्चाओं के लिए, पर जाएँ[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
