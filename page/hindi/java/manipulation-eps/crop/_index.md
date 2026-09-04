---
date: 2026-09-04
description: Aspose.Page का उपयोग करके Java में EPS फ़ाइलों को क्रॉप करके EPS फ़ाइल
  आकार कम करना सीखें – एक चरण‑दर‑चरण गाइड जो दिखाता है कि eps कैसे क्रॉप करें, eps
  इमेज को क्रॉप करें और eps फ़ाइल को ट्रिम करें।
keywords:
- reduce eps file size
- how to crop eps
- Aspose.Page Java
- EPS cropping Java
lastmod: 2026-09-04
linktitle: Java में EPS फ़ाइल को क्रॉप करें
og_description: Aspose.Page का उपयोग करके Java में EPS फ़ाइलों को क्रॉप करके EPS फ़ाइल
  आकार कम करना सीखें – कोड और टिप्स के साथ एक त्वरित गाइड।
og_image_alt: 'Guide: cropping EPS files in Java to reduce file size with Aspose.Page'
og_title: Java में EPS फ़ाइलों को क्रॉप करके EPS फ़ाइल आकार कम कैसे करें
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  headline: How to crop EPS files in Java to reduce EPS file size
  type: TechArticle
- description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  name: How to crop EPS files in Java to reduce EPS file size
  steps:
  - name: set document directory and input stream
    text: Here we point the code to the folder that holds our source EPS file and
      open a stream for reading it.
  - name: initialize PsDocument object
    text: The `PsDocument` class represents an EPS file in memory, allowing you to
      read and modify its properties. The object gives you access to the original
      bounding box and other metadata.
  - name: extract initial bounding box
    text: Extracting the original bounding box gives you the coordinates of the current
      visible area – handy for deciding how much you need to trim.
  - name: create output stream
    text: We open a stream where the cropped EPS will be written.
  - name: define new bounding box and crop
    text: The `cropEps` method trims the document to a new bounding box and writes
      the result to an output stream. Provide the four coordinates (lower‑left x,
      lower‑left y, upper‑right x, upper‑right y) that define the area you want to
      keep. The method performs the cropping and writes the result to `output_cr
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works with Java 8 and any later version.
    question: Is Aspose.Page compatible with Java 8?
  - answer: Absolutely. A commercial license is required for production deployments.
      You can obtain one [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: Visit the official [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for discussions, code samples, and troubleshooting tips.
    question: Where can I find additional resources and community support?
  - answer: Yes, you can download a free trial of Aspose.Page from the releases page
      [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is there a free trial available for testing?
  - answer: A temporary license can be requested from the licensing portal [temporary
      license request page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for short‑term evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- reduce eps file size
- Aspose.Page
- Java EPS processing
- crop EPS
title: Java में EPS फ़ाइलों को क्रॉप करके EPS फ़ाइल आकार कम कैसे करें
url: /hi/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में EPS फ़ाइलों को क्रॉप करके EPS फ़ाइल आकार कम कैसे करें

## परिचय
यदि आपको Java एप्लिकेशन में प्रोग्रामेटिक रूप से **crop EPS** फ़ाइलों को क्रॉप करना है और **reduce EPS file size** करना है, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम Aspose.Page for Java लाइब्रेरी का उपयोग करके EPS इमेज को क्रॉप करने की पूरी प्रक्रिया को समझेंगे। गाइड के अंत तक आप समझेंगे कि EPS को क्रॉप करना क्यों महत्वपूर्ण है, आवश्यक कोड देखेंगे, और इसे अपने प्रोजेक्ट्स में इंटीग्रेट करने के लिए तैयार होंगे।

## त्वरित उत्तर
- **Java में EPS क्रॉपिंग को संभालने वाली लाइब्रेरी कौन सी है?** Aspose.Page for Java.  
- **एक बेसिक क्रॉप को लागू करने में कितना समय लगता है?** लगभग 5‑10 मिनट।  
- **क्या विकास के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक फ्री ट्रायल काम करता है; प्रोडक्शन के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **कौन से Java संस्करण समर्थित हैं?** Java 8 और उसके बाद के संस्करण।  
- **क्या मैं कोई कस्टम बाउंडिंग बॉक्स परिभाषित कर सकता हूँ?** हाँ – आप आवश्यक निर्देशांक प्रदान करते हैं।

## EPS क्रॉपिंग क्या है और इसे क्यों उपयोग करें?
**EPS क्रॉपिंग एक नया बाउंडिंग बॉक्स बनाता है जो EPS फ़ाइल के दृश्यमान क्षेत्र को परिभाषित करता है।**  
EPS फ़ाइल को क्रॉप करने से अनावश्यक व्हाइटस्पेस हट जाता है और ग्राफ़िक को उस क्षेत्र तक सीमित किया जाता है जिसकी आपको वास्तव में आवश्यकता है, जिससे सीधे **reduce EPS file size** होता है और PDF या रिपोर्ट जैसे डाउनस्ट्रीम दस्तावेज़ों में लेआउट स्थिरता में सुधार होता है।

## EPS फ़ाइलों को क्यों क्रॉप करें?
EPS फ़ाइलों को क्रॉप करने से आप **shrink file size by up to 30 %** कर सकते हैं, अतिरिक्त मार्जिन हटाते हैं, और बैच प्रोसेसिंग पाइपलाइन के लिए ग्राफ़िक्स को मानकीकृत करते हैं। यह विशेष रूप से उपयोगी है जब आपको कई EPS एसेट्स को एक ही PDF में एम्बेड करना हो या जब आप लो‑पावर डिवाइसों पर रेंडरिंग को तेज़ करना चाहते हों।

## आवश्यकताएँ
Before we dive into the code, make sure you have:

- **Aspose.Page for Java** लाइब्रेरी स्थापित करें – इसे आधिकारिक पेज से डाउनलोड करें [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** 8 या उसके बाद का संस्करण अपने मशीन पर स्थापित हो।  
- **एक फ़ोल्डर** जहाँ आप अपनी इनपुट EPS (`input.eps`) और परिणामी क्रॉप्ड फ़ाइल (`output_crop.eps`) को स्टोर कर सकें।

## पैकेज इम्पोर्ट करें
सबसे पहले, आवश्यक Java क्लासेस को इम्पोर्ट करें। यह स्निपेट मूल ट्यूटोरियल जैसा ही रहेगा:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

## Java में EPS इमेज को कैसे क्रॉप करें
अपने स्रोत EPS को लोड करें, नया बाउंडिंग बॉक्स परिभाषित करें, और क्रॉपिंग API को कॉल करें – पूरी प्रक्रिया पाँच संक्षिप्त चरणों में पूरी होती है।

### चरण 1: दस्तावेज़ डायरेक्टरी और इनपुट स्ट्रीम सेट करें
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
यहाँ हम कोड को उस फ़ोल्डर की ओर इंगित करते हैं जहाँ हमारा स्रोत EPS फ़ाइल स्थित है और इसे पढ़ने के लिए एक स्ट्रीम खोलते हैं।

### चरण 2: PsDocument ऑब्जेक्ट को इनिशियलाइज़ करें
`PsDocument` क्लास मेमोरी में EPS फ़ाइल का प्रतिनिधित्व करती है, जिससे आप उसकी प्रॉपर्टीज़ को पढ़ और संशोधित कर सकते हैं।  
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
यह ऑब्जेक्ट आपको मूल बाउंडिंग बॉक्स और अन्य मेटाडेटा तक पहुँच प्रदान करता है।

### चरण 3: प्रारंभिक बाउंडिंग बॉक्स निकालें
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
मूल बाउंडिंग बॉक्स को निकालने से आपको वर्तमान दृश्यमान क्षेत्र के निर्देशांक मिलते हैं – यह तय करने में मददगार है कि आपको कितना ट्रिम करना है।

### चरण 4: आउटपुट स्ट्रीम बनाएं
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
हम एक स्ट्रीम खोलते हैं जहाँ क्रॉप्ड EPS लिखा जाएगा।

### चरण 5: नया बाउंडिंग बॉक्स परिभाषित करें और क्रॉप करें
`cropEps` मेथड दस्तावेज़ को नए बाउंडिंग बॉक्स तक ट्रिम करता है और परिणाम को आउटपुट स्ट्रीम में लिखता है।  
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
वह चार निर्देशांक (निचला‑बायाँ x, निचला‑बायाँ y, ऊपरी‑दायाँ x, ऊपरी‑दायाँ y) प्रदान करें जो आप जिस क्षेत्र को रखना चाहते हैं उसे परिभाषित करते हैं। मेथड क्रॉपिंग करता है और परिणाम को `output_crop.eps` में लिखता है।

## सामान्य समस्याएँ और समाधान
- **गलत निर्देशांक:** EPS पॉइंट्स (1/72 इंच) का उपयोग करता है। यदि क्रॉप गलत दिख रहा है, तो यूनिट कन्वर्ज़न दोबारा जांचें।  
- **फ़ाइल नहीं मिली त्रुटियाँ:** सुनिश्चित करें कि `dataDir` उचित पाथ सेपरेटर (`/` या `\`) के साथ समाप्त हो।  
- **लाइसेंस अपवाद:** वैध लाइसेंस के बिना कोड चलाने से आउटपुट में वॉटरमार्क जुड़ सकता है। प्रोडक्शन उपयोग से पहले अपना टेम्पररी या परमानेंट लाइसेंस लागू करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Page Java 8 के साथ संगत है?**  
A: हाँ, Aspose.Page Java 8 और उसके बाद के सभी संस्करणों के साथ काम करता है।

**Q: क्या मैं Aspose.Page को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?**  
A: बिल्कुल। प्रोडक्शन डिप्लॉयमेंट के लिए एक कमर्शियल लाइसेंस आवश्यक है। आप इसे यहाँ से प्राप्त कर सकते हैं [Aspose purchase page](https://purchase.aspose.com/buy).

**Q: अतिरिक्त संसाधन और समुदाय समर्थन कहाँ मिल सकते हैं?**  
A: चर्चा, कोड सैंपल और ट्रबलशूटिंग टिप्स के लिए आधिकारिक [Aspose.Page forum](https://forum.aspose.com/c/page/39) पर जाएँ।

**Q: क्या परीक्षण के लिए फ्री ट्रायल उपलब्ध है?**  
A: हाँ, आप रिलीज़ पेज से Aspose.Page का फ्री ट्रायल डाउनलोड कर सकते हैं [Aspose.Page releases page](https://releases.aspose.com/).

**Q: शॉर्ट‑टर्म इवैल्यूएशन के लिए टेम्पररी लाइसेंस कैसे प्राप्त करें?**  
A: टेम्पररी लाइसेंस लाइसेंसिंग पोर्टल से अनुरोध किया जा सकता है [temporary license request page](https://purchase.aspose.com/temporary-license/).

## निष्कर्ष
अब आप जानते हैं **how to crop EPS** फ़ाइलों को Java में Aspose.Page का उपयोग करके **reduce EPS file size** करने के लिए। एक कस्टम बाउंडिंग बॉक्स परिभाषित करके और `cropEps` को कॉल करके, आप कुछ ही कोड लाइनों से अनावश्यक मार्जिन को ट्रिम या EPS ग्राफ़िक के विशिष्ट भागों को अलग कर सकते हैं। इस स्निपेट को अपने बड़े डॉक्यूमेंट‑प्रोसेसिंग पाइपलाइन में इंटीग्रेट करें ताकि EPS मैनिपुलेशन, **crop EPS image** एसेट्स, और **trim EPS file** कंटेंट को प्रभावी रूप से ऑटोमेट किया जा सके।

---

**अंतिम अपडेट:** 2026-09-04  
**परीक्षण किया गया:** Aspose.Page for Java 24.11  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल्स

- [Java में Aspose.Page के साथ EPS फ़ाइलों को री-साइज़ कैसे करें](/page/java/manipulation-eps/resize/)
- [Aspose.Page Java के साथ EPS को PNG में कनवर्ट करें (Metered License)](/page/java/license-management/set-metered-license/)
- [Aspose Page Java ट्यूटोरियल – EPS फ़ाइलों में XMP मेटाडेटा जोड़ें](/page/java/xmp-metadata-manipulation/add-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}