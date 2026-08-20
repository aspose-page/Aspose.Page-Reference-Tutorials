---
date: 2026-03-16
description: जानेँ कि Aspose.Page का उपयोग करके जावा में XPS दस्तावेज़ों में छवि कैसे
  जोड़ें। यह गाइड आपको जल्दी से छवियों को जोड़ने की प्रक्रिया दिखाता है।
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: asp asp – Aspose.Page के साथ Java XPS दस्तावेज़ों में इमेज जोड़ें
url: /hi/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp asp – Aspose.Page के साथ Java XPS दस्तावेज़ों में इमेज जोड़ें

XPS फ़ाइलों में इमेज जोड़ना Java डेवलपर्स के लिए अक्सर आवश्यक होता है जो रिपोर्ट, इनवॉइस, या किसी भी विज़ुअल दस्तावेज़ को समृद्ध करना चाहते हैं। इस ट्यूटोरियल में आप **इमेज कैसे जोड़ें** को XPS दस्तावेज़ में जोड़ना सीखेंगे, Aspose.Page for Java लाइब्रेरी का उपयोग करके, और आप देखेंगे कि **asp asp** दृष्टिकोण प्रक्रिया को विश्वसनीय और तेज़ क्यों बनाता है। हम प्रत्येक चरण को चलेंगे, समझाएंगे कि प्रत्येक पंक्ति क्यों महत्वपूर्ण है, और सामान्य समस्याओं से बचने के लिए व्यावहारिक टिप्स देंगे।

## Quick Answers
- **कौनसी लाइब्रेरी चाहिए?** Aspose.Page for Java  
- **क्या मैं कई इमेज जोड़ सकता हूँ?** Yes – repeat the image‑adding steps for each picture  
- **समर्थित इमेज फ़ॉर्मेट?** TIFF, JPEG, PNG, GIF (and others supported by .NET)  
- **क्या मुझे लाइसेंस चाहिए?** A free trial works for evaluation; a commercial license is required for production  
- **आम तौर पर कार्यान्वयन समय?** About 10‑15 minutes for a basic image insertion  

## asp asp: XPS दस्तावेज़ों में इमेज जोड़ना

## Aspose.Page for Java क्या है?
Aspose.Page एक समर्पित API है जो आपको Microsoft XPS Viewer की आवश्यकता के बिना XPS (XML Paper Specification) दस्तावेज़ बनाने, संपादित करने और रेंडर करने देता है। यह XPS मार्कअप के लो‑लेवल विवरणों को एब्स्ट्रैक्ट करता है, जिससे आप अपने दस्तावेज़ों के विज़ुअल लेआउट पर ध्यान केंद्रित कर सकते हैं।

## Why add images to XPS?
- **पेशेवर लुक:** लोगो, चार्ट या उत्पाद फ़ोटो जैसी इमेज आपके दस्तावेज़ों को एक परिष्कृत रूप देती हैं।  
- **ब्रांड स्थिरता:** अपने कंपनी के लोगो को एम्बेड करने से सुनिश्चित होता है कि प्रत्येक जेनरेटेड इनवॉइस या रिपोर्ट में आपका ब्रांड दिखे।  
- **डायनेमिक कंटेंट:** आप रनटाइम पर प्रोग्रामेटिकली QR कोड, बारकोड, या उपयोगकर्ता‑जनित ग्राफ़िक्स डाल सकते हैं।

## Introduction
XPS दस्तावेज़ों में इमेज जोड़ना कई Java एप्लिकेशनों में एक सामान्य आवश्यकता है, जो रिपोर्ट जेनरेशन से लेकर दस्तावेज़ प्रोसेसिंग तक होती है। Aspose.Page for Java इस कार्य को सरल बनाता है, प्रभावी मेथड्स प्रदान करके जिससे इमेज को आपके XPS फ़ाइलों में सहजता से इंटीग्रेट किया जा सके। इस ट्यूटोरियल में, हम दिखाएंगे कि Aspose.Page for Java का उपयोग करके XPS दस्तावेज़ में इमेज कैसे जोड़ें।

## Prerequisites
ट्यूटोरियल में डुबने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित प्रीरेक्विज़िट्स मौजूद हैं:
1. **Aspose.Page for Java Library** – Aspose.Page for Java लाइब्रेरी को [website](https://releases.aspose.com/page/java/) से डाउनलोड और इंस्टॉल करें।  
2. **Java Development Environment** – सुनिश्चित करें कि आपके मशीन पर Java विकास वातावरण सेट अप है।  

अब, चलिए अगले चरणों की ओर बढ़ते हैं।

## Import Packages
अपने Java प्रोजेक्ट में, आवश्यक Aspose.Page for Java पैकेज इम्पोर्ट करें ताकि आवश्यक क्लासेज़ और मेथड्स तक पहुंच सकें।

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## Step 1: Set Up Document Directory
उस पथ को परिभाषित करें जहाँ आपका दस्तावेज़ डायरेक्टरी रहेगा, जहाँ XPS दस्तावेज़ और इमेज फ़ाइलें संग्रहीत होंगी।

```java
String dataDir = "Your Document Directory";
```

## Step 2: Create a New XPS Document
निम्नलिखित कोड स्निपेट का उपयोग करके एक नया XPS दस्तावेज़ इनिशियलाइज़ करें:

```java
XpsDocument doc = new XpsDocument();
```

## Step 3: Add Image to XPS Document
इमेज जोड़ने के लिए, XPS दस्तावेज़ में एक पाथ बनाएं, और प्रदान की गई इमेज फ़ाइल और कॉर्डिनेट्स का उपयोग करके इमेज ब्रश सेट करें।

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## Step 4: Save Resultant XPS Document
संशोधित XPS दस्तावेज़ को आपके निर्दिष्ट डायरेक्टरी में सेव करें।

```java
doc.save(dataDir + "AddImage_out.xps");
```

इन चरणों को दोहराएँ ताकि अधिक इमेज जोड़ सकें या अपने प्रोजेक्ट की आवश्यकताओं के अनुसार मौजूदा इमेज को कस्टमाइज़ कर सकें।

## Common Issues and Solutions
- **इमेज खिंची हुई दिख रही है:** Verify that the source rectangle (`new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f)`) matches the actual dimensions of your image. Adjust the destination rectangle to maintain the aspect ratio.  
- **वॉटरमार्क दिख रहा है:** If you run the code without a valid license, Aspose adds a watermark. Activate your license early in the application to avoid this.  
- **FileNotFoundException:** Ensure `dataDir` points to the correct folder and that the image file name (`QL_logo_color.tif`) matches the file on disk.  

## Conclusion
बधाई हो! आपने सफलतापूर्वक Aspose.Page for Java का उपयोग करके XPS दस्तावेज़ में **इमेज कैसे जोड़ें** सीख लिया है। यह कौशल आपके Java एप्लिकेशनों और दस्तावेज़ों की विज़ुअल अपील को बढ़ाने में अत्यंत मूल्यवान है। **asp asp** पैटर्न का पालन करके, आप इस उदाहरण को आसानी से विस्तारित कर कई ग्राफ़िक्स जोड़ सकते हैं, उन्हें डायनामिकली स्केल कर सकते हैं, या यहां तक कि तुरंत चार्ट जेनरेट कर सकते हैं।

### Frequently Asked Questions
### क्या मैं Aspose.Page for Java का उपयोग करके एक ही XPS दस्तावेज़ में कई इमेज जोड़ सकता हूँ?
हाँ, आप इस ट्यूटोरियल में बताए गए चरणों को प्रत्येक इमेज के लिए दोहराकर कई इमेज जोड़ सकते हैं।

### Aspose.Page for Java द्वारा कौनसे इमेज फ़ॉर्मेट समर्थित हैं?
Aspose.Page for Java विभिन्न इमेज फ़ॉर्मेट्स को सपोर्ट करता है, जिसमें TIFF, JPEG, PNG, और GIF शामिल हैं।

### क्या Aspose.Page for Java का ट्रायल वर्ज़न उपलब्ध है?
हाँ, आप [this link](https://releases.aspose.com/) से Aspose.Page for Java का मुफ्त ट्रायल प्राप्त कर सकते हैं।

### मैं Aspose.Page for Java के लिए टेम्पररी लाइसेंस कैसे प्राप्त कर सकता हूँ?
आप [this link](https://purchase.aspose.com/temporary-license/) से टेम्पररी लाइसेंस प्राप्त कर सकते हैं।

### मैं Aspose.Page for Java से संबंधित अतिरिक्त सपोर्ट या मुद्दों पर चर्चा कहाँ कर सकता हूँ?
सहायता प्राप्त करने, अनुभव साझा करने, और Aspose.Page समुदाय से जुड़ने के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) पर जाएँ।

---

**Last Updated:** 2026-03-16  
**परीक्षण किया गया:** Aspose.Page for Java 23.12 (latest at time of writing)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}