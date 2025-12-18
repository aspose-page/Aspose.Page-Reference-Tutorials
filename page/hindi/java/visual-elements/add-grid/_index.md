---
date: 2025-12-18
description: Aspose.Page के साथ जावा XPS दस्तावेज़ों में ग्रिड जोड़ना और पारदर्शी
  आयत जोड़ना सीखें। XPS दस्तावेज़ को कुशलतापूर्वक सहेजने के लिए चरण‑दर‑चरण मार्गदर्शिका।
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: जावा में विज़ुअल ब्रश का उपयोग करके ग्रिड कैसे जोड़ें
url: /hi/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में विज़ुअल ब्रश का उपयोग करके ग्रिड कैसे जोड़ें

## Introduction
यदि आप अपने जावा‑जनित XPS दस्तावेज़ों में **how to add grid** तत्व जोड़ने की तलाश में हैं, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम आपको विज़ुअल ब्रश के साथ ग्रिड जोड़ने, एक पारदर्शी आयत को लेयर करने, और अंत में Aspose.Page Java API का उपयोग करके **save XPS document** करने की प्रक्रिया दिखाएंगे। अंत तक आपके पास एक परिष्कृत दृश्य होगा जिसे रिपोर्ट, इनवॉइस या किसी भी दस्तावेज‑भारी एप्लिकेशन में पुनः उपयोग किया जा सकता है।

## Quick Answers
- **What does a Visual Brush do?** यह एक परिभाषित क्षेत्र को पुन: उपयोग योग्य विज़ुअल सामग्री से पेंट करता है, जो ग्रिड जैसे दोहराव वाले पैटर्न के लिए उपयुक्त है।  
- **Can I change the grid color?** हाँ – ब्रश की solid‑color सेटिंग्स को संशोधित करें।  
- **How do I add a transparent rectangle on top of the grid?** एक सॉलिड रंग से भरे पाथ पर `setOpacity` का उपयोग करें।  
- **What method saves the file?** `doc.save(...)` XPS फ़ाइल को डिस्क पर लिखता है।  
- **Do I need a license?** उत्पादन उपयोग के लिए एक अस्थायी या पूर्ण लाइसेंस आवश्यक है।

## What is a Visual Brush Grid?
विज़ुअल ब्रश आपको एक छोटा विज़ुअल (ग्रिड पैटर्न) परिभाषित करने और फिर उसे बड़े क्षेत्र में टाइल करने की अनुमति देता है। यह प्रत्येक लाइन को अलग‑अलग ड्रॉ करने की तुलना में मेमोरी‑कुशल है और पिक्सेल‑परफेक्ट दोहराव प्रदान करता है।

## Why use Aspose.Page for this task?
- **Cross‑platform** – वह किसी भी OS पर काम करता है जो जावा को सपोर्ट करता है।  
- **High‑fidelity rendering** – रंग, अपारदर्शिता और टाइलिंग पर सटीक नियंत्रण।  
- **No external dependencies** – सब कुछ Aspose.Page लाइब्रेरी के माध्यम से संभाला जाता है।

## Prerequisites
शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

- बेसिक जावा प्रोग्रामिंग ज्ञान।  
- Aspose.Page लाइब्रेरी स्थापित – आप इसे [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) से डाउनलोड कर सकते हैं।  
- आपके विकास मशीन पर JDK 8 या बाद का संस्करण स्थापित।

## Import Packages
पहले, आवश्यक क्लासेस को इम्पोर्ट करें ताकि कंपाइलर को पता चले कि हम कौन‑से टाइप उपयोग करेंगे:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Step‑by‑Step Guide

### Step 1: Set Up Your Project
एक नया `XpsDocument` इंस्टेंस बनाएं और उस फ़ोल्डर की ओर इशारा करें जहाँ आप आउटपुट फ़ाइल सहेजना चाहते हैं।

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Step 2: Create a Magenta Grid Visual Brush
हम एक छोटा मैजेंटा आकार परिभाषित करते हैं जिसे ग्रिड क्षेत्र में टाइल किया जाएगा।

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Step 3: Define Geometry for the Grid Brush
उस आयताकार क्षेत्र को सेट करें जो टाइल किए गए विज़ुअल को प्राप्त करेगा।

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Step 4: Create a New Canvas for the Document
दस्तावेज़ में एक कैनवास जोड़ें और उसे उस स्थान पर रखें जहाँ ग्रिड दिखाई देगा।

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Step 5: Add the Grid to the Canvas
विज़ुअल ब्रश को ज्योमेट्री पर लागू करें, जिससे टाइलिंग सक्षम हो जाएगी।

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Step 6: Add a Transparent Red Rectangle (Secondary Feature)
यहाँ हम ग्रिड के ऊपर **add transparent rectangle** को प्रदर्शित करते हैं ताकि जोर दिया जा सके।

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Step 7: Save the Resulting XPS Document
अंत में, दस्तावेज़ को डिस्क पर लिखें—यह **save XPS document** चरण है।

```java
doc.save(dataDir + "AddGrid_out.xps");
```

इन चरणों का पालन करें, और आपके पास एक प्रोफ़ेशनल‑लुकिंग ग्रिड होगा जिसमें पारदर्शी ओवरले होगा, सभी प्रोग्रामेटिक रूप से जेनरेटेड।

## Common Issues & Tips

- **Incorrect tile size:** सुनिश्चित करें कि ब्रश के लिए उपयोग किया गया `Rectangle2D` इच्छित दोहराव आकार से मेल खाता है; अन्यथा पैटर्न खिंचा हुआ दिख सकता है।  
- **Opacity not applied:** याद रखें कि आप जिस पाथ को पारदर्शी बनाना चाहते हैं, उस पर `setOpacity` कॉल करें; यह ब्रश को प्रभावित नहीं करेगा।  
- **File not saved:** पुष्टि करें कि `dataDir` एक मौजूदा फ़ोल्डर की ओर इशारा कर रहा है और आपके एप्लिकेशन के पास लिखने की अनुमति है।

## Frequently Asked Questions

**Q: Is Aspose.Page suitable for professional document generation?**  
A: हाँ, Aspose.Page एक मजबूत लाइब्रेरी है जो जावा में उच्च‑गुणवत्ता वाले XPS और PDF जेनरेशन के लिए डिज़ाइन की गई है।

**Q: Can I customize the grid colors using Visual Brush?**  
A: बिल्कुलश के `setFill` कॉल में `createColor` पैरामीटर को किसी भी RGBA मान में बदलें।

**Q: Where can I find additional support for Aspose.Page?**  
A: समुदाय सहायता और आधिकारिक उत्तरों के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) देखें।

**Q: Is there a free trial available for Aspose.Page?**  
A: हाँ, आप सभी फीचर्स को आज़माने के लिए [free trial](https://releases.aspose.com/) तक पहुँच सकते हैं।

**Q: How can I obtain a temporary license for testing?**  
A: विकास और मूल्यांकन के लिए काम करने वाला [temporary license](https://purchase.aspose.com/temporary-license/) प्राप्त करें।

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}