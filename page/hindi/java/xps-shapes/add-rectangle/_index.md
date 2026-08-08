---
date: 2026-04-24
description: Aspose.Page का उपयोग करके Java XPS में आयत का रंग सेट करना और आयत जोड़ना
  सीखें। यह गाइड Java में आयत जोड़ने और आयत की स्ट्रोक बदलने को कवर करता है।
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: जावा XPS में आयत जोड़ें
second_title: Aspose.Page Java API
title: जावा XPS में आयत का रंग सेट करें और आयत जोड़ें
url: /hi/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा XPS में आयत का रंग सेट करें और आयत जोड़ें

## परिचय
इस गाइड में, आप **set rectangle color** और **add a rectangle** को Java XPS में Aspose.Page लाइब्रेरी का उपयोग करके कैसे सेट करें, यह सीखेंगे। चाहे आप रिपोर्ट के लिए सरल आकार बनाना चाहते हों या जटिल वेक्टर ग्राफिक्स बनाना चाहते हों, आयत की स्टाइलिंग में महारत हासिल करने से आपको अपने XPS दस्तावेज़ों पर सटीक नियंत्रण मिलता है।  

## त्वरित उत्तर
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Page for Java  
- **क्या मैं आयत की स्ट्रोक बदल सकता हूँ?** हाँ, `setStroke` और `setStrokeThickness` का उपयोग करके  
- **क्या CMYK कलर प्रोफ़ाइल समर्थित है?** बिल्कुल – आप नीचे दिखाए अनुसार ICC प्रोफ़ाइल लोड कर सकते हैं  
- **उत्पादन के लिए लाइसेंस चाहिए?** हाँ, गैर‑इवैल्यूएशन उपयोग के लिए एक व्यावसायिक लाइसेंस आवश्यक है  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** आमतौर पर बुनियादी आयत के लिए 10 मिनट से कम  

## **set rectangle color** क्या है?
आयत का रंग सेट करना का अर्थ है फ़िल या स्ट्रोक रंग को परिभाषित करना, जिससे आकार अंतिम XPS दस्तावेज़ में उसी रंग में रेंडर होगा। Aspose.Page के साथ आप RGB, CMYK, या कस्टम ICC कलर प्रोफ़ाइल का उपयोग करके सटीक रंग मिलान प्राप्त कर सकते हैं।

## Aspose.Page को **add rectangle java** और **change rectangle stroke** के लिए क्यों उपयोग करें?
- **Full‑featured API** – सॉलिड कलर और ग्रेडिएंट दोनों का समर्थन करता है।  
- **Cross‑platform** – किसी भी Java रनटाइम पर बिना नेटिव डिपेंडेंसी के काम करता है।  
- **Rich geometry support** – जटिल पाथ बनाएं, ट्रांसफ़ॉर्मेशन लागू करें, और स्ट्रोक थिकनेस को आसानी से मैनेज करें।  

## आवश्यकताएँ
कोड में जाने से पहले सुनिश्चित करें कि आपके पास हैं:

- Java प्रोग्रामिंग का बुनियादी ज्ञान।  
- Aspose.Page लाइब्रेरी स्थापित। यदि नहीं, तो इसे [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) से डाउनलोड करें।  
- एक कार्यशील Java विकास वातावरण (IDE, JDK, आदि)।  

## पैकेज आयात करें
शुरू करने के लिए, आवश्यक पैकेज को अपने Java प्रोजेक्ट में इम्पोर्ट करें। सुनिश्चित करें कि Aspose.Page लाइब्रेरी आपके क्लासपाथ में सही ढंग से जोड़ी गई है। यहाँ एक बुनियादी उदाहरण है:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

अब, हम उदाहरण को कई चरणों में विभाजित करेंगे ताकि **add a rectangle** और **set its color** को Java XPS में लागू किया जा सके।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
`"Your Document Directory"` को उस पूर्ण पथ से बदलें जहाँ आप XPS फ़ाइलें पढ़ना/लिखना चाहते हैं।

## चरण 2: नया XPS दस्तावेज़ बनाएं
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
यह पंक्ति एक नया XPS दस्तावेज़ इनिशियलाइज़ करती है जिसमें हमारे आकार रखे जाएंगे।

## चरण 3: CMYK ठोस रंग स्ट्रोक वाली आयत जोड़ें
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
यह चरण एक **stroked rectangle** को CMYK ठोस रंग के साथ जोड़ता है। `setStroke` मेथड आयत की रूपरेखा का रंग निर्धारित करता है, जबकि `setStrokeThickness` लाइन की चौड़ाई को नियंत्रित करता है—**changing rectangle stroke** के लिए बिल्कुल उपयुक्त।

### प्रो टिप:
यदि आप RGB रंग पसंद करते हैं, तो `createColor` कॉल को `doc.createColor(0, 0, 255)` से बदलें ताकि सॉलिड ब्लू फ़िल मिल सके।

## चरण 4: परिणामी XPS दस्तावेज़ सहेजें
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
अंत में, XPS दस्तावेज़ को डिस्क पर सहेजें। फ़ाइल `AddRectangle_out.xps` अब एक ऐसी आयत रखती है जिसका रंग और स्ट्रोक आपने परिभाषित किया है।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|----------|
| **आयत दिखाई नहीं दे रही** | पाथ जियोमेट्री गलत या स्ट्रोक थिकनेस 0 पर सेट | पाथ स्ट्रिंग (`"M 20,10 L 220,10 220,100 20,100 Z"`) की जाँच करें और सुनिश्चित करें कि `setStrokeThickness` 0 से बड़ा है। |
| **गलत रंग** | ऐसा ICC प्रोफ़ाइल उपयोग किया गया जो इच्छित कलर स्पेस से मेल नहीं खाता | RGB के लिए `doc.createColor(r, g, b)` उपयोग करें या ICC फ़ाइल पाथ को दोबारा जाँचें। |
| **फ़ाइल नहीं सहेजी गई** | `dataDir` गैर‑मौजूद फ़ोल्डर की ओर इशारा कर रहा है या लिखने की अनुमति नहीं है | फ़ोल्डर को पहले बनाएं या लिखने योग्य स्थान चुनें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्र:** *क्या मैं एक ही XPS दस्तावेज़ में कई आयतें जोड़ सकता हूँ?*  
**उ:** हाँ। प्रत्येक आयत के लिए जियोमेट्री निर्माण और स्टाइलिंग चरणों को दोहराएँ।

**प्र:** *मैं स्ट्रोक के बजाय आयत का फ़िल रंग कैसे बदलूँ?*  
**उ:** `path.setFill(...)` का उपयोग करके सॉलिड कलर ब्रश सेट करें, ठीक उसी तरह जैसे `setStroke` उपयोग किया जाता है।

**प्र:** *क्या Aspose.Page जटिल XPS दस्तावेज़ हेरफेर के लिए उपयुक्त है?*  
**उ:** बिल्कुल। लाइब्रेरी ग्रेडिएंट, ट्रांसफ़ॉर्मेशन, एम्बेडेड फ़ॉन्ट जैसी उन्नत सुविधाओं का समर्थन करती है।

**प्र:** *अतिरिक्त उदाहरण और समुदाय समर्थन कहाँ मिल सकता है?*  
**उ:** अधिक कोड सैंपल और सहयोग के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) देखें।

**प्र:** *क्या मैं खरीदने से पहले Aspose.Page आज़मा सकता हूँ?*  
**उ:** हाँ, आप API क्षमताओं का मूल्यांकन करने के लिए एक [free trial](https://releases.aspose.com/) ले सकते हैं।

---

**अंतिम अपडेट:** 2026-04-24  
**परीक्षण किया गया:** Aspose.Page for Java 24.12  
**लेखक:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}