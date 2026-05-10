---
date: 2026-02-13
description: Aspose.Page का उपयोग करके जावा में पोस्टस्क्रिप्ट ग्रेडिएंट बनाना सीखें।
  यह चरण‑दर‑चरण गाइड आपको दिखाता है कि कैसे आसानी से अपने पोस्टस्क्रिप्ट दस्तावेज़ों
  में एक लंबवत ग्रेडिएंट जोड़ें।
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: जावा में पोस्टस्क्रिप्ट ग्रेडिएंट बनाएं – वर्टिकल ग्रेडिएंट जोड़ें
url: /hi/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create PostScript Gradient in Java – Add Vertical Gradient

## Introduction
इस व्यापक ट्यूटोरियल में, आप **Java में PostScript ग्रेडिएंट बनाने** के बारे में सीखेंगे, Aspose.Page for Java का उपयोग करके। एक वर्टिकल ग्रेडिएंट जोड़ने से आपके दस्तावेज़ अधिक जीवंत और पेशेवर दिखेंगे, और कुछ ही लाइनों के कोड से आप शानदार दृश्य प्रभाव प्राप्त कर सकते हैं। हम आपको प्रत्येक चरण के माध्यम से ले जाएंगे, यह समझाएंगे कि प्रत्येक भाग क्यों महत्वपूर्ण है, और सामान्य समस्याओं से बचने के लिए व्यावहारिक टिप्स देंगे। इस गाइड के अंत तक आप ऐसे PostScript फ़ाइलें जनरेट करने में सक्षम हो जाएंगे जिनमें सुगम, आँख‑को आकर्षित करने वाले वर्टिकल रंग परिवर्तन हों।

## Quick Answers
- **What library is needed?** Aspose.Page for Java  
- **Can I customize colors?** Yes, any `java.awt.Color` can be used  
- **Is rotation supported?** Yes, you can rotate the gradient with an `AffineTransform`  
- **What output format is produced?** A standard PostScript (.ps) file  
- **Do I need a license for production?** Yes, a commercial license is required  

## Why add a vertical gradient to a PostScript document?
वर्टिकल ग्रेडिएंट आपके पृष्ठों में गहराई जोड़ते हैं बिना फ़ाइल आकार बढ़ाए। ये निम्नलिखित के लिए आदर्श हैं:

* रिपोर्ट हेडर या फुटर जो सूक्ष्म बैकग्राउंड स्प्लैश चाहते हैं।  
* तकनीकी मैनुअल या व्हाइट‑पेपर में सेक्शन को हाइलाइट करना।  
* चार्ट, डायग्राम, या प्रोमोशनल फ़्लायर को आधुनिक लुक देना।

क्योंकि ग्रेडिएंट वेक्टर रूप में परिभाषित होता है, आउटपुट किसी भी रिज़ॉल्यूशन पर स्पष्ट रहता है।

## Prerequisites
ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ मौजूद हों:
- आपके मशीन पर Java Development Kit (JDK) स्थापित हो।  
- Aspose.Page for Java लाइब्रेरी। आप इसे [here](https://releases.aspose.com/page/java/) से डाउनलोड कर सकते हैं।

## Import Packages
अपने Java प्रोजेक्ट में, आवश्यक पैकेज इम्पोर्ट करें ताकि आप शुरू कर सकें:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

अब, चलिए वर्टिकल ग्रेडिएंट जोड़ने की प्रक्रिया को चरण‑दर‑चरण देखते हैं।

## How to create PostScript gradient in Java
नीचे एक चरण‑बद्ध गाइड दिया गया है जो दिखाता है कि **Java में PostScript ग्रेडिएंट कैसे बनाएं** Aspose.Page API का उपयोग करके।

### Step 1: Set up Your Document Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Step 2: Create Output Stream for PostScript Document
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Step 3: Create Save Options with A4 Size
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Step 4: Create a New PS Document
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Step 5: Create a Rectangle
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Step 6: Set Up Colors and Fractions for the Gradient
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Step 7: Create the Gradient Transform
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Step 8: Create Vertical Linear Gradient Paint
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Step 9: Set Paint and Fill the Rectangle
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Step 10: Close Current Page and Save the Document
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

बधाई हो! आपने सफलतापूर्वक अपने Java PostScript दस्तावेज़ में Aspose.Page for Java का उपयोग करके वर्टिकल ग्रेडिएंट जोड़ दिया है।

## Common Issues and Solutions
- **Gradient appears flat:** Ensure the `AffineTransform` scaling matches the rectangle dimensions.  
- **Colors look washed out:** Verify you are using the correct `ColorSpaceType` (SRGB) and that the fractions array is ordered from 0.0 to 1.0.  
- **File not generated:** Check that the output directory (`dataDir`) exists and the application has write permissions.  

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other Java libraries?
Yes, Aspose.Page for Java is designed to work seamlessly with other Java libraries.

### Is there a free trial available for Aspose.Page for Java?
Yes, you can get a free trial [here](https://releases.aspose.com/).

### Where can I find additional documentation?
Detailed documentation is available [here](https://reference.aspose.com/page/java/).

### How can I purchase Aspose.Page for Java?
You can purchase Aspose.Page for Java [here](https://purchase.aspose.com/buy).

### Is there a forum for Aspose.Page discussions?
Yes, you can join the community forum [here](https://forum.aspose.com/c/page/39).

## Additional Frequently Asked Questions

**Q: Can I create other gradient directions (horizontal, diagonal)?**  
A: Absolutely. Adjust the start and end points in `LinearGradientPaint` and modify the rotation angle in the `AffineTransform`.

**Q: Does this work with PDF output as well?**  
A: The same gradient logic can be applied when saving to PDF by using `PdfSaveOptions` instead of `PsSaveOptions`.

**Q: How do I change the gradient size dynamically?**  
A: Calculate the rectangle dimensions at runtime and pass those values to both the `Rectangle2D` and the `AffineTransform` constructor.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Page for Java 24.11 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}