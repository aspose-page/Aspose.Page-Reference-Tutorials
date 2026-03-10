---
date: 2026-02-25
description: Aspose.Page for .NET का उपयोग करके पोस्टस्क्रिप्ट दस्तावेज़ों को रैखिक
  ग्रेडिएंट आयत के साथ सुधारें। ग्रेडिएंट फ़िल टेक्स्ट और आउटलाइन टेक्स्ट ग्रेडिएंट
  सीखने के लिए हमारी चरण‑दर‑चरण गाइड का पालन करें।
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Aspose.Page के साथ PostScript (PS) में एक रैखिक ग्रेडिएंट आयत जोड़ें
url: /hi/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ PostScript (PS) में Linear Gradient Rectangle जोड़ें

## Introduction

Aspose.Page for .NET का उपयोग करके PostScript (PS) दस्तावेज़ों में **linear gradient rectangle** जोड़ने पर इस व्यापक ट्यूटोरियल में आपका स्वागत है। Aspose.Page एक शक्तिशाली लाइब्रेरी है जो आपको विभिन्न फ़ॉर्मैट में दस्तावेज़ बनाने, संशोधित करने और रेंडर करने देती है, और आज हम आपके PS फ़ाइलों में आकर्षक ग्रेडिएंट लाने पर ध्यान देंगे।

### Quick Answers

- **linear gradient rectangle क्या करता है?** यह एक आयताकार क्षेत्र को एक तरफ से दूसरी तरफ़ तक एक सुगम रंग परिवर्तन के साथ भरता है।  
- **कौन सा API ग्रेडिएंट फ़िल टेक्स्ट को संभालता है?** `LinearGradientBrush` को `SetPaint` और `FillAndStrokeText` के साथ मिलाकर।  
- **क्या मैं ग्रेडिएंट के साथ टेक्स्ट का आउटलाइन बना सकता हूँ?** हाँ—`SetStroke` को ग्रेडिएंट ब्रश के साथ उपयोग करें और `OutlineText` को कॉल करें।  
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** गैर‑मूल्यांकन उपयोग के लिए एक व्यावसायिक Aspose.Page लाइसेंस आवश्यक है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7।

## Prerequisites

शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:

- Aspose.Page for .NET लाइब्रेरी: सुनिश्चित करें कि लाइब्रेरी आपके प्रोजेक्ट में रेफ़रेंस की गई है। आप इसे [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) से डाउनलोड कर सकते हैं।
- Document Directory: डिस्क पर एक फ़ोल्डर बनाएं जहाँ उत्पन्न PS फ़ाइल सहेजी जाएगी और कोड में **“Your Document Directory”** को उस पथ से बदलें।

## Import Namespaces

शुरू करने के लिए, उन namespaces को आयात करें जो आपको ड्रॉइंग और PS‑विशिष्ट क्लासेज़ तक पहुँच प्रदान करते हैं:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## What Is a Linear Gradient Rectangle?

**linear gradient rectangle** बस एक आयताकार आकार है जिसका अंदरूनी भाग linear gradient से रंगा जाता है—रंग एक सीधी रेखा के साथ सुगमता से बदलते हैं, आमतौर पर बाएँ से दाएँ (क्षैतिज) या ऊपर से नीचे (ऊर्ध्वाधर)। Aspose.Page में आप इसे `GraphicsPath` (जो आयत को परिभाषित करता है) को `LinearGradientBrush` (जो रंग परिवर्तन को वर्णित करता है) के साथ मिलाकर प्राप्त करते हैं।

## Why Use Gradient Fill Text and Outline Text Gradient?

- **दृश्य आकर्षण:** Gradient‑filled टेक्स्ट रिपोर्ट, इनवॉइस या प्रमोशनल सामग्री में गहराई और आधुनिक शैली जोड़ता है।  
- **ब्रांड संगतता:** सटीक ARGB मानों के साथ कॉर्पोरेट रंगों को मिलाएँ।  
- **बहुमुखीता:** वही ब्रश आकार भरने, टेक्स्ट भरने और आउटलाइन ग्रेडिएंट्स के लिए पुनः उपयोग किया जा सकता है, जिससे कोड दोहराव कम होता है।

## Step 1: Set Up the Document

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 2: Define Gradient Rectangle and Colors

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Step 3: Set Transform for Brush

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Step 4: Set Paint and Fill the Rectangle

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## How to Apply Gradient Fill Text

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Using Outline Text Gradient

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Step 7: Close the Current Page and Save the Document

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

बधाई हो! आपने सफलतापूर्वक एक PostScript दस्तावेज़ में **linear gradient rectangle** जोड़ा है और वही ब्रश **gradient fill text** तथा **outline text gradient** के लिए उपयोग किया है।

## Common Use Cases & Tips

- **रिपोर्ट हेडर:** सेक्शन शीर्षकों को उजागर करने के लिए बड़े टेक्स्ट ब्लॉकों को ग्रेडिएंट से भरें।  
- **ब्रांड लोगो:** सुसंगत ब्रांडिंग के लिए लोगो आकारों को ग्रेडिएंट फ़िल आकारों से पुनः बनाएं।  
- **प्रो टिप:** कई ड्रॉइंग कॉल्स के लिए वही `LinearGradientBrush` इंस्टेंस पुनः उपयोग करें ताकि आकार और टेक्स्ट में रंग पूरी तरह संरेखित रहें।

## Frequently Asked Questions

### Q1: क्या मैं आयत के अलावा अन्य आकारों पर ग्रेडिएंट लागू कर सकता हूँ?

**A:** हाँ, आप `GraphicsPath` द्वारा परिभाषित किसी भी आकार पर ग्रेडिएंट लागू कर सकते हैं। `document.Fill(path)` कॉल करने से पहले बस सर्कल, पॉलीगॉन या कस्टम पाथ जोड़ें।

### Q2: मैं ग्रेडिएंट रंगों को कैसे बदल सकता हूँ?

**A:** `LinearGradientBrush` बनाते समय `Color.FromArgb` मानों को बदलें। पहला रंग प्रारंभ है, दूसरा ग्रेडिएंट का अंत।

### Q3: क्या Aspose.Page विभिन्न दस्तावेज़ फ़ॉर्मैट्स के साथ संगत है?

**A:** बिल्कुल। Aspose.Page XPS, PS, PDF और कई अन्य वेक्टर फ़ॉर्मैट्स को सपोर्ट करता है। पूर्ण सूची के लिए आधिकारिक दस्तावेज़ देखें।

### Q4: क्या मैं Aspose.Page को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?

**A:** हाँ, व्यावसायिक लाइसेंस उपलब्ध है। विवरण के लिए खरीद पेज देखें: [here](https://purchase.aspose.com/buy).

### Q5: मैं समुदाय समर्थन कहाँ पा सकता हूँ?

**A:** Aspose.Page कम्युनिटी फ़ोरम में शामिल हों: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**अंतिम अपडेट:** 2026-02-25  
**परीक्षित संस्करण:** Aspose.Page 24.10 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}