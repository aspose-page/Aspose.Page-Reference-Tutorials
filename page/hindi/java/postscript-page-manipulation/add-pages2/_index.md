---
date: 2026-02-18
description: Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट दस्तावेज़ों में कस्टम पेज
  आकार सेट करना और पेज जोड़ना सीखें। सहज दस्तावेज़ संचालन के लिए हमारे चरण‑दर‑चरण
  गाइड का पालन करें।
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page जावा ट्यूटोरियल – पोस्टस्क्रिप्ट में पेज जोड़ते समय कस्टम पेज आकार
  सेट करें
url: /hi/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java ट्यूटोरियल – PostScript में पेज जोड़ते समय कस्टम पेज साइज सेट करना

## परिचय
आधुनिक Java एप्लिकेशन में, PostScript आउटपुट के लिए **कस्टम पेज साइज सेट करना** अक्सर आवश्यक होता है—चाहे आप इनवॉइस, टिकट या कस्टम ग्राफ़िक्स बना रहे हों। इस ट्यूटोरियल में आप सीखेंगे कि **प्रत्येक पेज के लिए कस्टम पेज साइज कैसे सेट करें**, कई पेज जोड़ें, और अंत में **एक PostScript फ़ाइल जेनरेट करें** जो आपके लेआउट की सटीक जरूरतों को पूरा करे। हम कोड को चरण‑दर‑चरण समझेंगे ताकि आप इसे अपने प्रोजेक्ट में जल्दी से लागू कर सकें।

## त्वरित उत्तर
- **क्या मैं प्रत्येक पेज के लिए अलग-अलग पेज साइज सेट कर सकता हूँ?** हाँ, आप `document.openPage(width, height)` का उपयोग करके कस्टम डाइमेंशन के साथ पेज खोल सकते हैं।  
- **क्या प्रोडक्शन उपयोग के लिए लाइसेंस चाहिए?** गैर‑इवैल्यूएशन डिप्लॉयमेंट के लिए एक वैध Aspose.Page लाइसेंस आवश्यक है।  
- **कौन से Java संस्करण समर्थित हैं?** लाइब्रेरी Java 8 और उसके बाद के संस्करणों के साथ काम करती है।  
- **क्या API थ्रेड‑सेफ़ है?** Document इंस्टेंस थ्रेड‑सेफ़ नहीं हैं; प्रत्येक थ्रेड के लिए एक अलग `PsDocument` बनाएं।  
- **PostScript फ़ाइल का आकार कितना बड़ा हो सकता है?** Aspose.Page मल्टी‑मेगाबाइट फ़ाइलों को कुशलता से संभालता है; मेमोरी उपयोग कंटेंट के आधार पर बढ़ता है, पेज काउंट नहीं।  
- **क्या मैं open page width/height ओवरलोड का उपयोग कर सकता हूँ?** बिल्कुल—`openPage(double width, double height)` आपको पॉइंट्स में कोई भी डाइमेंशन निर्दिष्ट करने देता है।  

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास:

- Java प्रोग्रामिंग की बुनियादी समझ।  
- आपके प्रोजेक्ट में Aspose.Page for Java जोड़ा गया हो (Maven/Gradle या मैनुअल JAR)।  
- एक Java डेवलपमेंट एनवायरनमेंट (IDE, JDK 8+)।  

## इम्पोर्ट पैकेजेज
शुरू करने के लिए, Aspose.Page लाइब्रेरी से आवश्यक क्लासेज इम्पोर्ट करें।

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## चरण 1: एक मल्टीपेज्ड PostScript दस्तावेज़ बनाएं
पहले, एक नया `PsDocument` बनाएं जिसे कई पेजों के लिए कॉन्फ़िगर किया गया हो। यह आउटपुट स्ट्रीम सेट करता है और लाइब्रेरी को बताता है कि हम एक मल्टीपेज फ़ाइल पर काम करेंगे।

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## चरण 2: पहले पेज में सामग्री जोड़ें
डॉक्यूमेंट तैयार होने के बाद, आप पहले पेज में आवश्यक कोई भी सामग्री जोड़ सकते हैं। जब काम हो जाए, तो पेज को बंद करके उसकी सामग्री को लॉक कर दें।

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## कस्टम पेज साइज कैसे सेट करें
यदि डिफ़ॉल्ट पेज साइज आपकी जरूरतों को पूरा नहीं करता, तो आप नया पेज खोलते समय **कस्टम पेज साइज सेट** कर सकते हैं। यह रसीद, लेबल या किसी भी गैर‑स्टैंडर्ड लेआउट के लिए उपयोगी है।

## चरण 3: अलग साइज के साथ दूसरा पेज जोड़ें
नीचे हम दूसरा पेज खोलते हैं और स्पष्ट रूप से कस्टम चौड़ाई और ऊँचाई (पॉइंट्स में) प्रदान करते हैं। यह दर्शाता है कि व्यक्तिगत पेजों के लिए **विभिन्न पेज साइज** कैसे सेट करें, जिससे आप एक ही दस्तावेज़ में कई साइज का उपयोग कर सकें।

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## चरण 4: दस्तावेज़ को सहेजें
अंत में, दस्तावेज़ को सहेजकर बदलावों को स्थायी बनाएं। सभी पेज—जिसमें कस्टम साइज वाले पेज भी शामिल हैं—आउटपुट फ़ाइल में लिखे जाएंगे।

```java
// Save the document
document.save();
```

इन चरणों का पालन करके, आप Aspose.Page का उपयोग करके Java PostScript दस्तावेज़ में पेज जोड़ सकते हैं और **कस्टम पेज साइज सेट** कर सकते हैं, जिससे प्रत्येक पेज के लेआउट पर पूर्ण नियंत्रण मिलता है।

## कस्टम पेज साइज सेट करने के लिए Aspose.Page का उपयोग क्यों करें?
- **सटीकता:** डाइमेंशन पॉइंट्स में परिभाषित होते हैं, इसलिए आपको पेज की चौड़ाई और ऊँचाई पर पूर्ण नियंत्रण मिलता है।  
- **लचीलापन:** एक ही PostScript फ़ाइल में **विभिन्न पेज साइज** को मिलाकर उपयोग कर सकते हैं।  
- **प्रदर्शन:** लाइब्रेरी कंटेंट को सीधे आउटपुट फ़ाइल में स्ट्रीम करती है, जिससे बड़े‑पैमाने पर **PostScript फ़ाइल जेनरेट** करने के परिदृश्य में उपयुक्त बनती है।  
- **समृद्ध API:** ग्राफ़िक्स ड्रॉ करना, इमेज एम्बेड करना, और टेक्स्ट जोड़ना—all while respecting the custom dimensions you set.  

## सामान्य समस्याएँ और समाधान
| Issue | Solution |
|-------|----------|
| **Page dimensions appear swapped** | याद रखें कि `openPage(width, height)` में पहले चौड़ाई और फिर ऊँचाई (दोनों पॉइंट्स में) अपेक्षित है। |
| **Content overflows the page** | `PsGraphics` कोऑर्डिनेट सिस्टम का उपयोग करके तत्वों को कस्टम बाउंड्स के भीतर रखें, या अपने ड्रॉइंग को स्केल करें। |
| **Out‑of‑memory errors on huge documents** | जैसा दिखाया गया है, सीधे `FileOutputStream` में लिखकर स्ट्रीमिंग सक्षम करें, और बड़े इमेज को एक बार में मेमोरी में लोड करने से बचें। |

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं एक ही PostScript दस्तावेज़ में विभिन्न साइज के पेज जोड़ सकता हूँ?
हाँ, इस ट्यूटोरियल में दिखाए अनुसार आप मल्टीपेज्ड PostScript दस्तावेज़ में विभिन्न साइज के पेज जोड़ सकते हैं।  

### क्या पेज जोड़ने की संख्या पर कोई सीमा है?
Aspose.Page व्यावहारिक रूप से अनिश्चित संख्या में पेज जोड़ने का समर्थन करता है।  

### क्या मैं पेजों में कस्टम कंटेंट, जैसे इमेज या ग्राफ़िक्स, जोड़ सकता हूँ?
बिल्कुल! Aspose.Page आपको टेक्स्ट, इमेज और अन्य ग्राफ़िकल एलिमेंट्स जोड़ने की अनुमति देता है।  

### क्या Aspose.Page बड़े दस्तावेज़ों को संभालने के लिए उपयुक्त है?
हाँ, Aspose.Page छोटे और बड़े दोनों प्रकार के दस्तावेज़ों को आसानी से संभालने के लिए डिज़ाइन किया गया है।  

### Aspose.Page के लिए अतिरिक्त संसाधन और सपोर्ट कहाँ मिल सकते हैं?
[Aspose.Page documentation](https://reference.aspose.com/page/java/) देखें, या समुदाय समर्थन के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) पर जाएँ।  

**Additional Q&A**

**Q:** *PostScript पेज पर ड्रॉ करते समय कौन‑से इमेज फ़ॉर्मेट सपोर्टेड हैं?*  
**A:** आप PNG, JPEG, BMP, और GIF इमेज को सीधे ड्रॉइंग API का उपयोग करके एम्बेड कर सकते हैं।  

**Q:** *दस्तावेज़ की डिफ़ॉल्ट DPI कैसे बदलूँ?*  
**A:** `PsDocument` बनाने से पहले `PsSaveOptions.setResolution(int dpi)` सेट करें।  

**Q:** *क्या मैं PostScript फ़ाइल को पासवर्ड से एन्क्रिप्ट कर सकता हूँ?*  
**A:** PostScript स्वयं एन्क्रिप्शन को सपोर्ट नहीं करता, लेकिन आप आउटपुट को PDF में रैप करके आवश्यक सुरक्षा सेटिंग्स लागू कर सकते हैं।  

**अंतिम अपडेट:** 2026-02-18  
**परीक्षित संस्करण:** Aspose.Page for Java 24.10  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}