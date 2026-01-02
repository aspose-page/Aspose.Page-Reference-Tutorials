---
date: 2026-01-02
description: Aspose.Page Java के साथ XPS दस्तावेज़ों में अपारदर्शिता मास्क कैसे जोड़ें,
  सीखें। अपारदर्शिता मास्क आयत बनाने और दृश्य गुणवत्ता को बढ़ाने के लिए चरण-दर-चरण
  गाइड।
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: Aspose.Page Java का उपयोग करके Java XPS में अपारदर्शिता मास्क सेट करें
url: /hi/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java का उपयोग करके Java XPS में Opacity Mask सेट करें

## Introduction
हमारे व्यापक गाइड **aspose page java** opacity masks में आपका स्वागत है। इस ट्यूटोरियल में आप सीखेंगे कि कैसे एक XPS दस्तावेज़ बनाएं, एक कैनवास जोड़ें, और एक आयत पर opacity mask लागू करें—सब कुछ शक्तिशाली Aspose.Page Java API के साथ। अंत तक आप ऐसे opacity mask आयतें जोड़ पाएंगे जो आपके XPS फ़ाइलों को एक परिष्कृत, अर्ध‑पारदर्शी रूप देंगे।

## Quick Answers
- **एक opacity mask क्या करता है?** यह एक आकार के लिए विभिन्न पारदर्शिता स्तर निर्धारित करता है, जिससे नीचे की सामग्री दिखाई देती है।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java (aspose page java)।  
- **क्या मुझे लाइसेंस चाहिए?** परीक्षण के लिए एक अस्थायी लाइसेंस काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **कोड की कितनी पंक्तियाँ चाहिए?** लगभग 20 Java पंक्तियाँ plus कुछ सेटअप स्टेटमेंट्स।  
- **क्या मैं एक ही mask को कई आकारों पर पुन: उपयोग कर सकता हूँ?** हाँ, आप एक ही ImageBrush को कई पाथ्स में असाइन कर सकते हैं।

## What is an Opacity Mask in XPS?
Opacity mask एक bitmap या vector है जो किसी आकार के प्रत्येक पिक्सेल की अल्फा (पारदर्शिता) को नियंत्रित करता है। जब इसे एक आयत पर लागू किया जाता है, तो आयत के कुछ हिस्से पूरी तरह अपारदर्शी, कुछ हिस्से अंशतः पारदर्शी, और कुछ हिस्से पूरी तरह पारदर्शी हो जाते हैं, जिससे परिष्कृत दृश्य प्रभाव बनते हैं।

## Why Use Aspose.Page Java for Opacity Masks?
- **Full .NET‑style API in Java** – सहज ऑब्जेक्ट मॉडल।  
- **No external dependencies** – शुद्ध Java के साथ काम करता है।  
- **High‑fidelity rendering** – masks XPS स्पेसिफिकेशन के अनुसार बिल्कुल रेंडर होते हैं।  
- **Cross‑platform** – Windows, Linux, या macOS पर बिना बदलाव के चलाता है।

## Prerequisites
शुरू करने से पहले सुनिश्चित करें कि आपके पास है:
- Java प्रोग्रामिंग की बुनियादी समझ।  
- Aspose.Page for Java लाइब्रेरी स्थापित। आप इसे **[यहाँ](https://releases.aspose.com/page/java/)** डाउनलोड कर सकते हैं।  
- Aspose.Page के लिए वैध लाइसेंस। यदि आपके पास नहीं है, तो **[यहाँ](https://purchase.aspose.com/temporary-license/)** एक अस्थायी लाइसेंस प्राप्त करें।  
- एक विकास वातावरण जो Java एप्लिकेशन को कंपाइल और रन कर सके (जैसे IntelliJ IDEA, Eclipse, या VS Code)।

## Import Packages
Aspose.Page लाइब्रेरी से आवश्यक क्लासेज़ को इम्पोर्ट करें। यह सुनिश्चित करता है कि API आपके प्रोजेक्ट में उपलब्ध हो।

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Step‑by‑Step Guide

### Step 1: Create a New XPS Document
एक नया XPS दस्तावेज़ बनाएं जो सभी ग्राफ़िक्स को रखेगा।

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Step 2: Add a Canvas
कैनवास XPS पेज के भीतर एक ड्रॉइंग सतह के रूप में कार्य करता है।

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Step 3: Add a Rectangle and Apply a Solid Fill
यहाँ हम एक आयत पाथ बनाते हैं और उसे ठोस लाल रंग से भरते हैं। यह आयत बाद में opacity mask प्राप्त करेगी।

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Step 4: Add Opacity Mask Using an ImageBrush
हम एक TIFF इमेज लोड करते हैं, स्रोत और लक्ष्य आयतें निर्धारित करते हैं, और ब्रश को टाइल मोड पर सेट करते हैं ताकि आवश्यक होने पर mask दोहराया जा सके।

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Step 5: Save the Resultant XPS Document
अंत में, दस्तावेज़ को डिस्क पर सहेजें। आउटपुट फ़ाइल में वह आयत होगी जिसमें लागू किया गया opacity mask होगा।

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

इन चरणों को ध्यानपूर्वक पालन करें ताकि आप अपने Java XPS दस्तावेज़ में **add opacity mask** कार्यक्षमता को Aspose.Page के साथ सम्मिलित कर सकें।

## Common Issues & Troubleshooting
- **इमेज नहीं मिली** – सुनिश्चित करें कि `dataDir` सही फ़ोल्डर की ओर इशारा कर रहा है और `R08SY_NN.tif` मौजूद है।  
- **Mask ठोस दिख रहा है** – जाँचें कि स्रोत इमेज में वास्तव में विभिन्न अल्फा मान हैं; पूरी तरह अपारदर्शी इमेज पारदर्शिता नहीं दिखाएगी।  
- **Tile mode लागू नहीं हो रहा** – टाइलिंग दिखने के लिए लक्ष्य आयत स्रोत आयत से छोटी होनी चाहिए।

## Frequently Asked Questions

**Q: क्या Aspose.Page सभी Java विकास वातावरणों के साथ संगत है?**  
A: हाँ, Aspose.Page विभिन्न Java IDEs और बिल्ड टूल्स के साथ सहजता से काम करने के लिए डिज़ाइन किया गया है।

**Q: क्या मैं Aspose.Page बिना लाइसेंस के उपयोग कर सकता हूँ?**  
A: आप लाइब्रेरी का मूल्यांकन अस्थायी लाइसेंस के साथ कर सकते हैं, लेकिन उत्पादन उपयोग के लिए पूर्ण लाइसेंस आवश्यक है।

**Q: ट्रायल संस्करण में कोई सीमाएँ हैं क्या?**  
A: ट्रायल में आकार या फीचर प्रतिबंध हो सकते हैं; विस्तृत जानकारी के लिए आधिकारिक दस्तावेज़ देखें।

**Q: Aspose.Page के लिए समर्थन कैसे प्राप्त करूँ?**  
A: समुदाय सहायता के लिए **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** देखें या प्रीमियम सहायता के लिए लाइसेंस खरीदें।

**Q: क्या Aspose.Page के लिए मनी‑बैक गारंटी है?**  
A: रिफंड नीतियों की जानकारी के लिए **[purchase page](https://purchase.aspose.com/buy)** देखें।

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.Page Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}