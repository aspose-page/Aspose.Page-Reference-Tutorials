---
date: 2026-04-30
description: Aspose.Page Java का उपयोग करके XPS दस्तावेज़ जावा कैसे बनाएं और एक अपारदर्शिता
  मास्क जोड़ें, सीखें। कोड उदाहरणों के साथ चरण‑दर‑चरण गाइड।
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Java XPS में अपारदर्शिता मास्क सेट करें
second_title: Aspose.Page Java API
title: Java में XPS दस्तावेज़ बनाएं – Aspose.Page के साथ अपारदर्शिता मास्क सेट करें
url: /hi/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS में Opacity Mask सेट करें Aspose.Page Java का उपयोग करके

## परिचय
इस ट्यूटोरियल में आप **create XPS document Java** फ़ाइलें बनाएँगे और सीखेंगे कि कैसे एक opacity mask लागू किया जाए जो आपके ग्राफ़िक्स को एक पॉलिश्ड, अर्ध‑पारदर्शी लुक देता है। हम पूरी प्रक्रिया को चरण‑दर‑चरण देखेंगे—XPS दस्तावेज़ को इनिशियलाइज़ करने से, कैनवास जोड़ने, आयत ड्रॉ करने, और इमेज‑आधारित opacity mask संलग्न करने तक—Aspose.Page Java API का उपयोग करके। अंत तक, आप प्रोग्रामेटिकली प्रोफेशनल XPS फ़ाइलें जेनरेट कर सकेंगे और आवश्यक किसी भी आकार पर मास्क को पुनः उपयोग कर सकेंगे।

## त्वरित उत्तर
- **एक opacity mask क्या करता है?** यह एक आकार के लिए विभिन्न पारदर्शिता स्तरों को परिभाषित करता है, जिससे नीचे की सामग्री दिख सके।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java (aspose page java).  
- **क्या मुझे लाइसेंस चाहिए?** परीक्षण के लिए एक टेम्पररी लाइसेंस काम करता है; प्रोडक्शन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **कोड की कितनी पंक्तियाँ?** लगभग 20 पंक्तियों का Java कोड प्लस कुछ सेटअप स्टेटमेंट्स।  
- **क्या मैं कई आकारों पर मास्क को पुनः उपयोग कर सकता हूँ?** हाँ, आप समान `ImageBrush` को कई पाथ्स पर असाइन कर सकते हैं।

## XPS में Opacity Mask क्या है?
एक opacity mask एक बिटमैप या वेक्टर होता है जो किसी आकार में प्रत्येक पिक्सेल की अल्फा (पारदर्शिता) को नियंत्रित करता है। जब इसे आयत पर लागू किया जाता है, तो आयत के कुछ हिस्से पूरी तरह अपारदर्शी, कुछ हिस्से अंशतः पारदर्शी, और कुछ हिस्से पूरी तरह पारदर्शी हो जाते हैं, जिससे अतिरिक्त ड्रॉइंग लेयर के बिना जटिल दृश्य प्रभाव बनते हैं।

## क्यों उपयोग करें Aspose.Page Java को **create XPS document java** बनाने के लिए?
- **Pure Java API** – कोई नेटिव डिपेंडेंसी नहीं, इसलिए वही कोड Windows, Linux, या macOS पर चलता है।  
- **Full XPS spec compliance** – मास्क XPS मानक द्वारा परिभाषित अनुसार बिल्कुल रेंडर होते हैं।  
- **Object‑oriented design** – .NET के समान, जिससे यदि आपने अन्य भाषाओं में Aspose इस्तेमाल किया है तो इसे सीखना आसान है।  
- **High performance** – बड़े दस्तावेज़ों और बैच प्रोसेसिंग के लिए ऑप्टिमाइज़्ड।

## सामान्य उपयोग केस
- **Watermarking** – पृष्ठों पर अर्ध‑पारदर्शी लोगो लागू करें।  
- **Dynamic theming** – जेनरेटेड रिपोर्ट्स में UI तत्वों की दृश्य शैली बदलें।  
- **Print‑ready previews** – प्रिंटर को भेजने से पहले विभिन्न opacity के साथ डिज़ाइन कैसे दिखेगा, यह दिखाएँ।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:
- Java प्रोग्रामिंग की बुनियादी समझ।  
- Aspose.Page for Java लाइब्रेरी स्थापित है। आप इसे **[यहाँ](https://releases.aspose.com/page/java/)** डाउनलोड कर सकते हैं।  
- Aspose.Page के लिए एक वैध लाइसेंस। यदि आपके पास नहीं है, तो एक टेम्पररी लाइसेंस **[यहाँ](https://purchase.aspose.com/temporary-license/)** प्राप्त करें।  
- एक विकास वातावरण जो Java एप्लिकेशन को कंपाइल और रन कर सके (जैसे IntelliJ IDEA, Eclipse, या VS Code)।

## पैकेज इम्पोर्ट करें
सबसे पहले Aspose.Page लाइब्रेरी से आवश्यक क्लासेज़ इम्पोर्ट करें। यह सुनिश्चित करता है कि API आपके प्रोजेक्ट में उपलब्ध हो।

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## चरण‑दर‑चरण गाइड

### चरण 1: नया XPS दस्तावेज़ बनाएं
सबसे पहले, एक नया XPS दस्तावेज़ बनाएं जो हमारे सभी ग्राफ़िक्स को रखेगा।

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### चरण 2: एक कैनवास जोड़ें
कैनवास XPS पेज के भीतर एक ड्रॉइंग सतह के रूप में कार्य करता है।

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### चरण 3: आयत जोड़ें और सॉलिड फ़िल लागू करें
यहाँ हम एक आयत पाथ बनाते हैं और उसे सॉलिड लाल फ़िल देते हैं। यह आयत बाद में opacity mask प्राप्त करेगी।

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### चरण 4: ImageBrush का उपयोग करके Opacity Mask जोड़ें
हम एक TIFF इमेज लोड करते हैं, स्रोत और गंतव्य आयतें परिभाषित करते हैं, और ब्रश को टाइल मोड पर सेट करते हैं ताकि आवश्यक होने पर मास्क दोहराया जा सके।

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### चरण 5: परिणामी XPS दस्तावेज़ सहेजें
अंत में, दस्तावेज़ को डिस्क पर सहेजें। आउटपुट फ़ाइल में लागू किए गए opacity mask वाली आयत होगी।

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

इन चरणों को सावधानीपूर्वक पालन करें ताकि आप Aspose.Page का उपयोग करके अपने Java XPS दस्तावेज़ में **add opacity mask** कार्यक्षमता को सम्मिलित कर सकें।

## सामान्य समस्याएँ और ट्रबलशूटिंग
- **Image not found** – सुनिश्चित करें कि `dataDir` सही फ़ोल्डर की ओर इशारा कर रहा है और `R08SY_NN.tif` मौजूद है।  
- **Mask appears solid** – सुनिश्चित करें कि स्रोत इमेज में वास्तव में विभिन्न अल्फा मान हैं; पूरी तरह अपारदर्शी इमेज पारदर्शिता नहीं दिखाएगी।  
- **Tile mode not respected** – टाइलिंग दिखाने के लिए गंतव्य आयत स्रोत आयत से छोटी होनी चाहिए।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Page सभी Java विकास वातावरणों के साथ संगत है?**  
A: हाँ, Aspose.Page विभिन्न Java IDEs और बिल्ड टूल्स के साथ सहजता से काम करने के लिए डिज़ाइन किया गया है।

**Q: क्या मैं Aspose.Page को बिना लाइसेंस के उपयोग कर सकता हूँ?**  
A: आप लाइब्रेरी का मूल्यांकन टेम्पररी लाइसेंस के साथ कर सकते हैं, लेकिन प्रोडक्शन उपयोग के लिए पूर्ण लाइसेंस आवश्यक है।

**Q: क्या ट्रायल संस्करण में कोई सीमाएँ हैं?**  
A: ट्रायल में आकार या फीचर प्रतिबंध हो सकते हैं; विवरण के लिए आधिकारिक दस्तावेज़ देखें।

**Q: मैं Aspose.Page के लिए समर्थन कैसे प्राप्त कर सकता हूँ?**  
A: समुदाय सहायता के लिए **[Aspose.Page फ़ोरम](https://forum.aspose.com/c/page/39)** पर जाएँ या प्रीमियम सहायता के लिए लाइसेंस खरीदें।

**Q: क्या Aspose.Page के लिए मनी‑बैक गारंटी है?**  
A: रिफंड नीतियों की जानकारी के लिए **[purchase page](https://purchase.aspose.com/buy)** देखें।

---

**अंतिम अपडेट:** 2026-04-30  
**परीक्षित संस्करण:** Aspose.Page Java 24.11 (latest at time of writing)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}