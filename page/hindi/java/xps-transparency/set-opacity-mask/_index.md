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

# Aspose.Page Java का इस्तेमाल करके Java XPS में Opacity Mask सेट करें

## परिचय
हमारे बड़े गाइड **aspose page java** opacity masks में आपका स्वागत है। इस ट्यूटोरियल में आप बताएंगे कि कैसे एक XPS डॉक्यूमेंट बनाएं, एक कैनवास ऐड करें, और एक इनकम पर opacity mask लगाएं—सब कुछ ताकतवर Aspose.Page Java API के साथ। आखिर तक आप ऐसे opacity mask इनकम जोड़ पाएंगे जो आपके XPS सर्वर को एक परफ़ेक्ट, अर्ध-पारदर्शी रूप देगा।

## क्विक जवाब
- **एक opacity mask क्या करता है?** यह एक साइज़ के लिए अलग-अलग लेवल तय करता है, जिससे नीचे की चीज़ दिखती है।
- **कौन सी लाइब्रेरी ज़रूरी है?** Aspose.Page for Java (aspose page java)।
- **क्या मुझे लाइसेंस चाहिए?** टेस्ट के लिए एक टेम्पररी लाइसेंस काम करता है; प्रोडक्शन के लिए पूरा लाइसेंस ज़रूरी है।
- **कोड की कितनी लाइनें चाहिए?** लगभग 20 Java लाइनें और कुछ सेटअप कॉलम।
- **क्या मैं एक ही मास्क को कई तरह से इस्तेमाल कर सकता हूँ?** हाँ, आप एक ही ImageBrush को कई तरीकों से इस्तेमाल कर सकते हैं।

## XPS में Opacity Mask क्या है?
Opacity mask एक बिटमैप या वेक्टर है जो किसी आकार के हर पिक्सेल की अल्फा (पारदर्शिता) को कंट्रोल करता है। जब इसे एक Volume पर लगाया जाता है, तो Volume के कुछ हिस्से पूरी तरह से अपारदर्शी, कुछ हिस्से अंशतः सही, और कुछ हिस्से पूरी तरह से सही हो जाते हैं, जिससे परिष्कार दृश्य प्रभाव बनता है।

## Opacity Masks के लिए Aspose.Page Java का इस्तेमाल क्यों करें?
- **Java में Full .NET‑style API** – सहज ऑब्जेक्ट मॉडल।
- **कोई बाहरी निर्भरता नहीं** – शुद्ध Java के साथ काम करता है।
- **High‑fidelity rendering** – masks XPS स्पेसिफिकेशन्स के अनुसार बिल्कुल रेंडर होते हैं।
- **क्रॉस-प्लेटफ़ॉर्म** – Windows, Linux, या macOS पर बिना बदलाव के चलता है।

## ज़रूरतें
शुरू करने से पहले यह पक्का करें कि आपके पास है:
- Java प्रोग्रामिंग की बुनियादी समझ।
- Aspose.Page for Java लाइब्रेरी इंस्टॉल करें। आप इसे **[यहाँ](https://releases.aspose.com/page/java/)** डाउनलोड कर सकते हैं।
- Aspose.Page के लिए वैध लाइसेंस। अगर आपके पास नहीं है, तो **[यहाँ](https://purchase.aspose.com/temporary-license/)** एक अस्थायी लाइसेंस लें।
- एक डेवलपमेंट माहौल जो Java एप्लिकेशन को कंपाइल और रन कर सके (जैसे IntelliJ IDEA, Eclipse, या VS Code)।

## पैकेज इंपोर्ट करें
Aspose.Page लाइब्रेरी से आवश्यक क्लासेज़ को इम्पोर्ट करें। यह सुनिश्चित करता है कि API आपके प्रोजेक्ट में उपलब्ध हो।

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
## स्टेप-बाय-स्टेप गाइड

### स्टेप 1: एक नया XPS डॉक्यूमेंट बनाएं
एक नया XPS दस्तावेज़ बनाएं जो सभी ग्राफ़िक्स को रखेगा।

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### स्टेप 2: एक कैनवस जोड़ें
कैनवास XPS पेज के भीतर एक ड्रॉइंग सतह के रूप में कार्य करता है।

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### स्टेप 3: एक रेक्टेंगल जोड़ें और एक सॉलिड फिल लगाएं
यहाँ हम एक आयत पाथ बनाते हैं और उसे ठोस लाल रंग से भरते हैं। यह आयत बाद में opacity mask प्राप्त करेगी।

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### स्टेप 4: इमेजब्रश का इस्तेमाल करके ओपेसिटी मास्क जोड़ें
हम एक TIFF इमेज लोड करते हैं, स्रोत और लक्ष्य आयतें निर्धारित करते हैं, और ब्रश को टाइल मोड पर सेट करते हैं ताकि आवश्यक होने पर mask दोहराया जा सके।

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### स्टेप 5: रिजल्टेंट XPS डॉक्यूमेंट सेव करें
अंत में, दस्तावेज़ को डिस्क पर सहेजें। आउटपुट फ़ाइल में वह आयत होगी जिसमें लागू किया गया opacity mask होगा।

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

इन चरणों को ध्यानपूर्वक पालन करें ताकि आप अपने Java XPS दस्तावेज़ में **add opacity mask** कार्यक्षमता को Aspose.Page के साथ सम्मिलित कर सकें।

## आम दिक्कतें और समस्याएँ
- **इमेज नहीं मिली** – यह पक्का करें कि `dataDir` सही फ़ोल्डर की ओर इशारा कर रहा है और `R08SY_NN.tif` मौजूद है।
- **Mask सॉलिड दिख रहा है** – जाँचें कि सोर्स इमेज में असल में अलग-अलग अल्फ़ा मान हैं; पूरी तरह अपारदर्शी इमेज ट्रांसफर नहीं दिखाएगी।
- **Tile mode लागू नहीं हो रहा** – टाइलिंग दिखने के लिए टारगेट वॉल्यूम सोर्स वॉल्यूम से छोटी होनी चाहिए।

## अक्सर पूछे जाने वाले सवाल

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