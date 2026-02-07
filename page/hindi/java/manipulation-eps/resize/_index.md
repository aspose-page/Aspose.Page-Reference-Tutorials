---
date: 2026-02-07
description: जावा में EPS फ़ाइलों को री‑साइज़ करना और Aspose.Page का उपयोग करके EPS
  आयाम बदलना सीखें। यह चरण‑दर‑चरण गाइड आपको दिखाता है कि पॉइंट्स, इंच, मिलीमीटर या
  प्रतिशत के साथ EPS को कैसे री‑साइज़ किया जाए।
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Aspose.Page के साथ जावा में EPS फ़ाइलों का आकार कैसे बदलें
url: /hi/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में Aspose.Page के साथ EPS फ़ाइलों को री‑साइज़ कैसे करें

## Introduction
यदि आप प्रोग्रामेटिक रूप से **EPS को री‑साइज़ करने का विश्वसनीय तरीका** खोज रहे हैं, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम Aspose.Page लाइब्रेरी का उपयोग करके Java में EPS इमेज को री‑साइज़ करने की प्रक्रिया को चरण‑दर‑चरण समझेंगे। चाहे आपको आकार को दोगुना करना हो, किसी विशिष्ट माप में घटाना हो, या प्रतिशत के आधार पर काम करना हो, नीचे दिए गए कदम आपको आउटपुट डायमेंशन पर पूर्ण नियंत्रण देंगे। **EPS को री‑साइज़ करने का तरीका** समझना आवश्यक है जब आपको विभिन्न प्रिंट लेआउट या स्क्रीन रिज़ॉल्यूशन के लिए ग्राफ़िक्स को अनुकूलित करना हो।

## Quick Answers
- **What library is needed?** Aspose.Page for Java  
- **Can I resize using points, inches, or millimeters?** हाँ – API सभी तीन यूनिट्स और प्रतिशत दोनों को सपोर्ट करता है।  
- **Do I need a license for development?** परीक्षण के लिए फ्री ट्रायल काम करता है; प्रोडक्शन के लिए लाइसेंस आवश्यक है।  
- **What Java version is required?** Java 8 या बाद का संस्करण।  
- **Is the code thread‑safe?** प्रत्येक `PsDocument` इंस्टेंस अलग है, इसलिए आप फ़ाइलों को समानांतर में प्रोसेस कर सकते हैं।  

## What is EPS and Why Resize It?
Encapsulated PostScript (EPS) एक लोकप्रिय वेक्टर ग्राफ़िक्स फ़ॉर्मेट है जो प्रकाशन और प्रिंटिंग में उपयोग होता है। कभी‑कभी मूल EPS फ़ाइल का आकार आपके लक्ष्य आउटपुट से मेल नहीं खाता – उदाहरण के लिए, 72 pts पर डिज़ाइन किया गया लोगो बड़े ब्रोशर के लिए 144 pts चाहिए हो सकता है। **EPS को री‑साइज़ करने का तरीका** जानने से आप वेक्टर क्वालिटी को बनाए रखते हुए किसी भी वर्कफ़्लो के लिए डायमेंशन को अनुकूलित कर सकते हैं।

## Why Use Aspose.Page for Resizing EPS?
- **Full‑control over units** – पॉइंट्स, इंच, मिलीमीटर या प्रतिशत।  
- **No external dependencies** – शुद्ध Java API, कोई नेटिव लाइब्रेरी नहीं।  
- **High performance** – सर्वर पर बैच प्रोसेसिंग के लिए उपयुक्त।  
- **Preserves vector fidelity** – आउटपुट स्केलेबल रहता है, रास्टराइज़ेशन नहीं होता।  

## Prerequisites
कोड में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हों:

- आपके मशीन पर Java Development Kit (JDK) स्थापित हो।  
- Aspose.Page for Java लाइब्रेरी। आप इसे **[here](https://releases.aspose.com/page/java/)** से डाउनलोड कर सकते हैं।  
- Java प्रोग्रामिंग की बुनियादी समझ।  

## Import Packages
अपने Java प्रोजेक्ट में आवश्यक इम्पोर्ट्स शामिल करें ताकि आप Aspose.Page ऑब्जेक्ट्स और स्टैंडर्ड I/O स्ट्रीम्स के साथ काम कर सकें।

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## How to Change EPS Dimensions with Different Units
लाइब्रेरी आपको **EPS डायमेंशन बदलने** की सुविधा देती है, बस उपयुक्त `Units` एनेम को चुनें। नीचे हम पॉइंट्स, इंच, मिलीमीटर और प्रतिशत के लिए वही पाँच‑स्टेप पैटर्न दिखाएंगे। केवल `resizeEps` को पास किया गया यूनिट बदलता है।

## How to Resize EPS Using Points
नीचे एक पूर्ण, चरण‑दर‑चरण उदाहरण है जो पॉइंट्स को माप इकाई के रूप में उपयोग करके EPS फ़ाइल का आकार दोगुना करता है।

### Step 1: Set up the input stream
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Step 2: Initialize the `PsDocument` object
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Step 3: Extract the current size of the EPS image
```java
Dimension oldSize = doc.extractEpsSize();
```

### Step 4: Create an output stream for the resized file
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Step 5: Resize and save the EPS using points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## How to Resize EPS Using Inches
उसी पाँच‑स्टेप पैटर्न को लागू करें; केवल `Units.Points` को `Units.Inches` से बदलें और स्केलिंग फ़ैक्टर को इच्छित इंच मान के अनुसार समायोजित करें।

## How to Resize EPS Using Millimeters
फिर से वही कदम अपनाएँ, लेकिन यूनिट को `Units.Millimeters` में बदलें। यह तब उपयोगी होता है जब आपको प्रिंट वर्कफ़्लो के लिए मीट्रिक‑आधारित डायमेंशन चाहिए हों।

## How to Resize EPS Using Percentages
प्रतिशत‑आधारित स्केलिंग के लिए यूनिट को `Units.Percent` रखें। मूल चौड़ाई और ऊँचाई को इच्छित प्रतिशत (जैसे 0.5 = 50 % कमी) से गुणा करें।

## Common Pitfalls & Tips
- **Always close streams** – प्रोडक्शन कोड में स्ट्रीम्स को `try‑with‑resources` में रैप करें ताकि फ़ाइल लॉक न हों।  
- **Preserve aspect ratio** – जब तक आप जानबूझकर विकृति नहीं चाहते, चौड़ाई और ऊँचाई दोनों को समान फ़ैक्टर से गुणा करें।  
- **Check DPI** – री‑साइज़ करने से DPI नहीं बदलता; यदि अलग DPI चाहिए तो री‑साइज़ के बाद अलग से समायोजित करें।  
- **Thread safety** – प्रत्येक थ्रेड के लिए नया `PsDocument` बनाएं; एक ही इंस्टेंस को साझा करने से अनपेक्षित परिणाम मिल सकते हैं।  

## Frequently Asked Questions

**Q: Can I use this library for other image formats?**  
A: नहीं, Aspose.Page केवल PostScript और EPS फ़ाइलों के लिए विशेषीकृत है।

**Q: Is there a free trial available for Aspose.Page for Java?**  
A: हाँ, आप फ्री ट्रायल **[here](https://releases.aspose.com/)** पर एक्सप्लोर कर सकते हैं।

**Q: Where can I find additional help and discussions?**  
A: समुदाय समर्थन के लिए **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** देखें।

**Q: How can I obtain a temporary license?**  
A: आप अस्थायी लाइसेंस **[here](https://purchase.aspose.com/temporary-license/)** से प्राप्त कर सकते हैं।

**Q: Are there any example projects available?**  
A: हाँ, दस्तावेज़ीकरण **[here](https://reference.aspose.com/page/java/)** में देखें।

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}