---
date: 2026-01-07
description: Aspose.Page का उपयोग करके .NET में XPS दस्तावेज़ बनाना सीखें। यह गाइड
  इमेज‑भरे ग्लिफ़ और विदेशी छवियों को जोड़कर अधिक समृद्ध दस्तावेज़ दृश्य प्रदान करता
  है।
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Aspose.Page के साथ .NET में XPS दस्तावेज़ बनाएं – इमेज़‑फ़िल्ड ग्लिफ़ और विदेशी
  इमेज
url: /hi/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create XPS document .NET with Aspose.Page – Image Filled Glyph & Foreign Image

## Introduction

यदि आपको **create XPS document .NET** एप्लिकेशन बनाना है जो परिष्कृत और पेशेवर दिखें, तो Aspose.Page आपको सीधे glyph में इमेज एम्बेड करने और दस्तावेज़ों में ग्राफ़िक संसाधनों को पुन: उपयोग करने के उपकरण देता है। इस ट्यूटोरियल में हम दो XPS फ़ाइलें बनाएँगे, glyph को इमेज ब्रश से भरेंगे, और फिर उस ब्रश को दूसरी फ़ाइल में पुन: उपयोग करेंगे। अंत तक आप समझेंगे कि यह तरीका मेमोरी बचाता है, स्टाइलिंग को सरल बनाता है, और रिपोर्ट, इनवॉइस या किसी भी प्रिंटेबल कंटेंट के लिए रचनात्मक संभावनाएँ खोलता है।

## Quick Answers
- **इस ट्यूटोरियल में क्या कवर किया गया है?** Aspose.Page for .NET के साथ इमेज‑filled glyphs जोड़ना और उन्हें XPS दस्तावेज़ों में पुन: उपयोग करना।  
- **कौन सा मुख्य कीवर्ड लक्षित है?** `create xps document .net`.  
- **पूर्वापेक्षाएँ?** .NET विकास पर्यावरण, Aspose.Page for .NET, और आपके XPS फ़ाइलों के लिए एक फ़ोल्डर।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** कार्यशील प्रोटोटाइप के लिए लगभग 10‑15 मिनट।  
- **क्या मैं अन्य इमेज फ़ॉर्मेट उपयोग कर सकता हूँ?** हाँ – कोई भी फ़ॉर्मेट जो .NET के `System.Drawing.Image` द्वारा समर्थित है।

## Prerequisites

कोड में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित तैयार हैं:

- **Aspose.Page for .NET** – नवीनतम लाइब्रेरी [here](https://releases.aspose.com/page/net/) से डाउनलोड करें।  
- **Development Environment** – Visual Studio 2022 (या कोई भी IDE जो .NET 6+ को सपोर्ट करता हो)।  
- **Document Directory** – अपने मशीन पर एक फ़ोल्डर बनाएँ जहाँ इनपुट इमेज और जेनरेटेड XPS फ़ाइलें रखी जाएँगी; हम इसे स्निपेट्स में **Your Document Directory** कहेंगे।

## Import Namespaces

XPS ऑब्जेक्ट्स और ड्राइंग यूटिलिटीज़ के साथ काम करने के लिए आवश्यक नेमस्पेसेज़ को इम्पोर्ट करें।

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step‑by‑Step Guide

### Step 1: Create the First XPS Document

हम एक खाली XPS दस्तावेज़ बनाते हैं जो इमेज‑filled glyph को होस्ट करेगा।

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Step 2: Add Glyphs to the First Document

अब एक glyph (एक टेक्स्ट कैरेक्टर) जोड़ें जिसे बाद में इमेज ब्रश से भरेंगे।

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Step 3: Fill Glyphs with an Image Brush

यहाँ हम अपने डेटा डायरेक्टरी में स्थित TIFF फ़ाइल से `ImageBrush` बनाते हैं और उसे glyph पर लागू करते हैं। ब्रश को टाइल मोड पर सेट किया गया है ताकि यदि glyph का क्षेत्र इमेज साइज से बड़ा हो तो इमेज दोहराया जाए।

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Step 4: Create the Second XPS Document

अब हम दूसरा XPS दस्तावेज़ बनाते हैं जो पहले वाले से glyph स्टाइल और इमेज ब्रश को पुन: उपयोग करेगा।

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Step 5: Add Glyphs with the Font from the First Document

दूसरे दस्तावेज़ में glyph जोड़ते हैं, पहले दस्तावेज़ के बिल्कुल वही फ़ॉन्ट ऑब्जेक्ट पुन: उपयोग करके। इससे दोनों फ़ाइलों में विज़ुअल कंसिस्टेंसी बनी रहती है।

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Step 6: Create an Image Brush from the Fill of the First Document

इमेज को फिर से लोड करने के बजाय, हम `glyphs1` से ब्रश को क्लोन करके `glyphs2` को असाइन करते हैं। यह दर्शाता है कि आप **create XPS document .NET** वर्कफ़्लो को कैसे संसाधनों को कुशलता से साझा करने के लिए बना सकते हैं।

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Step 7: Save the Documents

अंत में दोनों XPS फ़ाइलों को डिस्क पर सेव करें। अब आप उन्हें किसी भी XPS व्यूअर से खोलकर इमेज‑filled glyph इफ़ेक्ट देख सकते हैं।

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Why use image‑filled glyphs when you create XPS document .NET?

- **Visual Impact** – साधारण टेक्स्ट को ग्राफ़िक‑रिच एलिमेंट्स में बदलें बिना पूरे पेज को रास्टराइज़ किए।  
- **Resource Reuse** – ब्रश और फ़ॉन्ट को कई दस्तावेज़ों में साझा करें, जिससे मेमोरी फुटप्रिंट घटे।  
- **Flexibility** – टाइल, स्ट्रेच या रोटेट करें इमेज ब्रश को कस्टम पैटर्न या ब्रांडिंग के लिए।

## Common Issues & Tips

- **File Path Errors** – सुनिश्चित करें कि `dataDir` अंत में सही पाथ सेपरेटर (`\` या `/`) रखता हो आपके OS के अनुसार।  
- **Unsupported Image Formats** – Aspose.Page TIFF, PNG, और JPEG के साथ सबसे अच्छा काम करता है। अन्य फ़ॉर्मेट को उपयोग से पहले कन्वर्ट करें।  
- **TileMode Not Applied** – `TileMode` सेट करने से पहले `XpsImageBrush` में कास्ट करना न भूलें; अन्यथा प्रॉपर्टी इग्नोर हो जाएगी।

## Frequently Asked Questions

### Q1: Can I use different image formats for filling glyphs?

**A:** हाँ, Aspose.Page TIFF, PNG, JPEG, BMP, और GIF को सपोर्ट करता है। बस `CreateImageBrush` कॉल में सही फ़ाइल एक्सटेंशन दें।

### Q2: How can I customize the appearance of glyphs further?

**A:** `XpsGlyphs` की अतिरिक्त प्रॉपर्टीज़ जैसे `Opacity`, `RenderTransform`, और `Stroke` को एक्सप्लोर करें ताकि रेंडरिंग को फाइन‑ट्यून किया जा सके।

### Q3: Is Aspose.Page suitable for handling large document sets?

**A:** बिल्कुल। लाइब्रेरी हाई‑परफ़ॉर्मेंस परिदृश्यों के लिए ऑप्टिमाइज़्ड है और बैच जॉब्स में हजारों XPS फ़ाइलों को प्रोसेस कर सकती है।

### Q4: Can I apply different styles to individual glyphs?

**A:** हाँ। प्रत्येक `XpsGlyphs` इंस्टेंस का अपना फ़िल, स्ट्रोक, और ट्रांसफ़ॉर्मेशन हो सकता है, जिससे आपको ग्रैन्युलर कंट्रोल मिलता है।

### Q5: What are the benefits of using Aspose.Page over other document processing tools?

**A:** Aspose.Page एक पूर्ण, लाइसेंस‑फ्री API प्रदान करता है XPS निर्माण, मैनिपुलेशन, और कन्वर्ज़न के लिए, विस्तृत डॉक्यूमेंटेशन और 24/7 सपोर्ट के साथ।

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}