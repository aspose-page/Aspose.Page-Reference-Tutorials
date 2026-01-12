---
date: 2026-01-12
description: Aspose.Page for .NET का उपयोग करके PostScript फ़ाइल को सहेजना और PostScript
  दस्तावेज़ बनाना सीखें, और गतिशील ग्राफ़िक्स के लिए कई रूपांतरण लागू करें।
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: Aspose.Page ट्रांसफ़ॉर्मेशन (.NET) के साथ PostScript फ़ाइल सहेजें
url: /hi/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Transformations (.NET) के साथ PostScript फ़ाइल सहेजें

## Introduction

इस ट्यूटोरियल में आप सीखेंगे कि **PostScript फ़ाइल को कैसे सहेजें** जबकि आप Aspose.Page for .NET के साथ काम कर रहे हों। हम एक PostScript दस्तावेज़ बनाने, ट्रांसलेशन, स्केलिंग, रोटेशन और शीयरिंग जैसे कई ट्रांसफ़ॉर्मेशन लागू करने, और अंत में परिणाम को सहेजने की प्रक्रिया को चरण‑बद्ध रूप से देखेंगे। अंत तक आप प्रोग्रामेटिक रूप से डायनामिक ग्राफ़िक्स बनाने में सहज हो जाएंगे और जानेंगे कि ग्राफ़िक्स स्टेट में प्रत्येक ट्रांसफ़ॉर्मेशन को कहाँ रखना है।

## Quick Answers
- **मैं क्या बना सकता हूँ?** एक पूरी तरह से फीचर वाला PostScript दस्तावेज़ जिसमें परिवर्तित ग्राफ़िक्स होते हैं।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for .NET (आधिकारिक साइट से डाउनलोड योग्य)।  
- **फ़ाइल को कैसे सहेजें?** ग्राफ़िक्स स्टेट्स को कॉन्फ़िगर करने के बाद `PsDocument.Save()` का उपयोग करें।  
- **क्या मैं कई ट्रांसफ़ॉर्मेशन लागू कर सकता हूँ?** हाँ – उन्हें `Transform` या क्रमिक कॉल्स के साथ संयोजित करें।  
- **क्या लाइसेंस आवश्यक है?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।

## What is a “save postscript file” operation?

PostScript फ़ाइल को सहेजना मतलब है कि मेमोरी में बनाए गए ड्रॉइंग कमांड्स को डिस्क पर `.ps` फ़ाइल के रूप में स्थायी बनाना। इस फ़ाइल को कोई भी PostScript इंटरप्रेटर, प्रिंटर या व्यूअर रेंडर कर सकता है।

## Why use Aspose.Page for .NET to create postscript document?

Aspose.Page एक हाई‑लेवल, डिवाइस‑इंडिपेंडेंट API प्रदान करता है जो लो‑लेवल PostScript सिंटैक्स को एब्स्ट्रैक्ट करता है। आपको मिलता है:

- पाथ, ब्रश, और ट्रांसफ़ॉर्मेशन के लिए स्ट्रॉन्गली‑टाइप्ड C# ऑब्जेक्ट्स।  
- ग्राफ़िक्स स्टेट स्टैक (save/restore) का स्वचालित प्रबंधन।  
- मैन्युअल गणनाओं के बिना जटिल ट्रांसफ़ॉर्मेशन मैट्रिक्स के लिए पूर्ण समर्थन।  

## Prerequisites

शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

- **Aspose.Page for .NET** लाइब्रेरी को अपने प्रोजेक्ट में इंटीग्रेट करें। इसे [download link](https://releases.aspose.com/page/net/) से प्राप्त करें।  
- एक लिखने योग्य फ़ोल्डर जहाँ उत्पन्न `.ps` फ़ाइल संग्रहीत होगी। कोड में प्लेसहोल्डर पाथ को अपने वास्तविक डायरेक्टरी से बदलें।

## Import Namespaces

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

अब हम प्रत्येक ट्रांसफ़ॉर्मेशन को चरण‑बद्ध रूप से देखेंगे।

## No Transformations

### Step 1: Create Output Stream

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

यह स्निपेट एक **PostScript दस्तावेज़** बनाता है जिसमें एक एकल नारंगी आयत है और **PostScript फ़ाइल** को बिना किसी ट्रांसफ़ॉर्मेशन के सहेजता है।

## Translation

### Step 1: Save Graphics State

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

ग्राफ़िक्स स्टेट को सहेजने से आप वस्तुओं को स्थानांतरित करने के बाद वापस लौट सकते हैं।

### Step 2: Translate Graphics State

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

यह ट्रांसलेशन इस कॉल के बाद ड्रॉ की गई सभी वस्तुओं को 250 यूनिट दाईं ओर ले जाता है।

### Step 3: Fill Rectangle with Translation Transformation

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

अब एक नीली आयत नारंगी आयत के 250 पॉइंट दाईं ओर दिखाई देती है।

### Step 4: Restore Graphics State

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

रीस्टोर करने से कॉर्डिनेट सिस्टम अपनी मूल स्थिति में लौट आता है, इसलिए आगे की ड्रॉइंग ट्रांसलेशन से प्रभावित नहीं होती।

## Scaling

> *You can follow the same pattern—save state, apply `Scale`, draw, then restore.*  
> **Pro tip:** Use non‑uniform scaling (`Scale(sx, sy)`) to stretch objects only in one direction.

## Rotation

> *Rotate around the origin or a custom pivot point using `Rotate(angle)`.*
> **Pro tip:** Combine `Translate` before rotation to rotate around a specific point.

## Shearing

> *Shear transformations (`Shear(shx, shy)`) slant shapes, useful for italic effects.*

## Complex Transformations

> *For advanced scenarios, build a custom `Matrix` and pass it to `Transform(matrix)`.*
> This is where you **apply multiple transformations** in a single step.

## Conclusion

आपने सीखा कि **PostScript फ़ाइल को कैसे सहेजें**, **PostScript दस्तावेज़ कैसे बनाएं**, और **Aspose.Page for .NET** का उपयोग करके **कई ट्रांसफ़ॉर्मेशन कैसे लागू करें**। विभिन्न ट्रांसफ़ॉर्मेशन क्रमों के साथ प्रयोग करें, उन्हें संयोजित करें, और देखें कि ग्राफ़िक्स कैसे विकसित होते हैं।

## Frequently Asked Questions

**Q: How can I apply multiple transformations to a single object?**  
A: Use the `Transform` method with a custom `Matrix` that combines translation, scaling, rotation, or shearing in the order you need.

**Q: Can I preview the transformations before saving the document?**  
A: Yes—render the `PsDocument` to an image or use a PostScript viewer to inspect the output before calling `Save()`.

**Q: Is it possible to apply transformations to specific elements in a document?**  
A: Absolutely. Save the graphics state before drawing the element, apply the desired transformation, draw, then restore the state.

**Q: Are there any performance considerations when dealing with complex transformations?**  
A: Complex matrices increase CPU work. Keep transformations as simple as possible and reuse saved states when drawing many similar objects.

**Q: How can I get support or seek assistance for Aspose.Page-related queries?**  
A: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community help, or contact Aspose support directly.

---

**Last Updated:** 2026-01-12  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}