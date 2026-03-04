---
date: 2025-12-23
description: Aspose.Page का उपयोग करके जावा में आसानी से **XPS को PNG में बदलें**।
  यह गाइड दिखाता है कि कैसे XPS को इमेज फ़ाइलों में रेंडर किया जाए, एक विश्वसनीय,
  डेवलपर‑फ्रेंडली समाधान के साथ।
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: जावा में XPS को PNG में बदलें
url: /hi/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में XPS को PNG में परिवर्तित करें

## परिचय
सॉफ़्टवेयर विकास की गतिशील दुनिया में **XPS को PNG में परिवर्तित करने** (XML Paper Specification से Portable Network Graphics) की आवश्यकता अक्सर उत्पन्न होती है। इस कार्य को जावा में सहजता से पूरा करने के लिए Aspose.Page एक शक्तिशाली समाधान प्रदान करता है। इस ट्यूटोरियल में हम Aspose.Page for Java का उपयोग करके XPS को PNG में परिवर्तित करने की प्रक्रिया को चरण‑बद्ध तरीके से समझेंगे।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी परिवर्तन को संभालती है?** Aspose.Page for Java  
- **कौन‑से फ़ॉर्मेट शामिल हैं?** XPS (स्रोत) → PNG (आउटपुट)  
- **उत्पादन के लिए लाइसेंस चाहिए?** हाँ, एक व्यावसायिक लाइसेंस आवश्यक है  
- **क्या मैं इमेज रेज़ोल्यूशन सेट कर सकता हूँ?** हाँ, `PngSaveOptions.setResolution()` का उपयोग करके  
- **क्या विशिष्ट पृष्ठ चुनना संभव है?** बिल्कुल – विकल्प ऑब्जेक्ट में पेज नंबर प्रदान करें  

## XPS को PNG में क्यों परिवर्तित करें?
XPS को इमेज फ़ाइलों में रेंडर करना तब उपयोगी होता है जब आपको दस्तावेज़ वेब पर दिखाने, रिपोर्ट में एम्बेड करने या प्रीव्यू के लिए थंबनेल बनाने की आवश्यकता होती है। PNG लॉसलेस कंप्रेशन और व्यापक ब्राउज़र समर्थन प्रदान करता है, जिससे यह XPS सामग्री के उच्च‑गुणवत्ता दृश्य प्रतिनिधित्व के लिए आदर्श विकल्प बनता है।

## पूर्वापेक्षाएँ
ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित स्थापित हैं:
1. **Java Development Kit (JDK):** सुनिश्चित करें कि आपके सिस्टम पर JDK स्थापित है।  
2. **Aspose.Page for Java:** Aspose.Page लाइब्रेरी डाउनलोड और इंस्टॉल करें। आप डाउनलोड लिंक [यहाँ](https://releases.aspose.com/page/java/) पा सकते हैं।  
3. **Integrated Development Environment (IDE):** IntelliJ IDEA या Eclipse जैसे जावा‑संगत IDE चुनें।  

## Java में XPS को PNG में कैसे परिवर्तित करें
नीचे एक चरण‑बद्ध गाइड दिया गया है जो **XPS दस्तावेज़ों को PNG इमेज में परिवर्तित** करने की प्रक्रिया को समझाता है, साथ ही आप सीधे अपने प्रोजेक्ट में कॉपी कर सकने वाले कोड स्निपेट्स भी शामिल हैं।

### पैकेज इम्पोर्ट करें
अपने जावा प्रोजेक्ट में Aspose.Page की कार्यक्षमताओं को उपयोग करने के लिए आवश्यक पैकेज इम्पोर्ट करें। अपने जावा फ़ाइल की शुरुआत में निम्नलिखित इम्पोर्ट स्टेटमेंट जोड़ें:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### चरण 1: दस्तावेज़ डायरेक्टरी सेट करें
उस फ़ोल्डर को परिभाषित करें जिसमें आपका स्रोत XPS फ़ाइल है और जहाँ PNG फ़ाइलें सहेजी जाएँगी।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### चरण 2: XPS दस्तावेज़ लोड करें
एक `XpsDocument` इंस्टेंस बनाएँ जो स्रोत XPS फ़ाइल को लोड करे।

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### चरण 3: विकल्प प्रारंभ करें
PNG आउटपुट विकल्पों को कॉन्फ़िगर करें। यहाँ आप स्मूदिंग, रेज़ोल्यूशन सेट कर सकते हैं और यह निर्धारित कर सकते हैं कि कौन‑से पृष्ठ रेंडर किए जाएँ।

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### चरण 4: रेंडरिंग डिवाइस बनाएं
एक `ImageDevice` बनाएँ जो रेंडर की गई इमेज डेटा को रखेगा।

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### चरण 5: सहेजें और इटरेट करें
XPS दस्तावेज़ को रेंडर करें, फिर प्रत्येक उत्पन्न PNG बाइट एरे को डिस्क पर फ़ाइल में लिखें।

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

इन चरणों का पालन करके आप **XPS को इमेज** फ़ाइलों में PNG फ़ॉर्मेट में आसानी से रेंडर कर सकते हैं, Aspose.Page for Java का उपयोग करके।

## निष्कर्ष
संक्षेप में, Aspose.Page for Java XPS से PNG में परिवर्तन प्रक्रिया को सरल बनाता है, जिससे डेवलपर्स को एक विश्वसनीय और कुशल टूल मिलता है। इस लाइब्रेरी को अपने जावा प्रोजेक्ट में शामिल करें और दस्तावेज़ प्रबंधन कार्यों को सहज बनाएं।

## अतिरिक्त अक्सर पूछे जाने वाले प्रश्न

**प्रश्न:** क्या मैं XPS फ़ाइल के केवल चयनित पृष्ठों को ही परिवर्तित कर सकता हूँ?  
**उत्तर:** बिल्कुल। `PngSaveOptions` में `setPageNumbers` मेथड का उपयोग करके आप रेंडर करने वाले पृष्ठ निर्दिष्ट कर सकते हैं।

**प्रश्न:** उच्च‑गुणवत्ता PNG के लिए कौन‑सा इमेज रेज़ोल्यूशन सुझाया जाता है?  
**उत्तर:** 300 dpi का रेज़ोल्यूशन गुणवत्ता और फ़ाइल आकार के बीच अच्छा संतुलन प्रदान करता है, लेकिन आप `options.setResolution()` के माध्यम से इसे समायोजित कर सकते हैं।

**प्रश्न:** क्या API बड़े दस्तावेज़ों के लिए मल्टी‑थ्रेडेड परिवर्तन का समर्थन करता है?  
**उत्तर:** हां, आप परिवर्तन लॉजिक को समानांतर थ्रेड्स में चलाकर प्रत्येक पृष्ठ या दस्तावेज़ के भाग को अलग‑अलग प्रोसेस कर सकते हैं।

**प्रश्न:** बहुत बड़े XPS फ़ाइलों को परिवर्तित करते समय मेमोरी उपयोग को कैसे नियंत्रित करूँ?  
**उत्तर:** पृष्ठों को क्रमिक रूप से प्रोसेस करें और प्रत्येक लिखने के बाद `FileOutputStream` को रिलीज़ करें, जैसा कि नमूना कोड में दिखाया गया है।

**प्रश्न:** उत्पन्न PNG फ़ाइलों में कस्टम मेटाडेटा जोड़ने का कोई तरीका है?  
**उत्तर:** जबकि `PngSaveOptions` सीधे मेटाडेटा फ़ील्ड प्रदान नहीं करता, आप मानक इमेज लाइब्रेरीज़ का उपयोग करके PNG को पोस्ट‑प्रोसेस कर मेटाडेटा एम्बेड कर सकते हैं।

---

**अंतिम अपडेट:** 2025-12-23  
**परीक्षित संस्करण:** Aspose.Page for Java 24.12 (नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}