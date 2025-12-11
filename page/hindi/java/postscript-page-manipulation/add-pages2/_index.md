---
date: 2025-12-11
description: Aspose.Page का उपयोग करके जावा पोस्टस्क्रिप्ट दस्तावेज़ों में कस्टम पेज
  आकार सेट करना और पेज जोड़ना सीखें। सहज दस्तावेज़ संचालन के लिए हमारी चरण‑दर‑चरण
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

# Aspose.Page Java ट्यूटोरियल – PostScript में पेज जोड़ते समय कस्टम पेज साइज सेट करें

## परिचय
आधुनिक Java अनुप्रयोगों में, **कस्टम पेज साइज सेट करना** अक्सर आवश्यक होता है—चाहे आप इनवॉइस, टिकट या कस्टम ग्राफिक्स बना रहे। Aspose.Page for Java इस कार्य को सरल बनाता है। इस ट्यूटोरियल में आप सीखेंगे कि कैसे PostScript दस्तावेज़ में पेज जोड़ें और कस्टम पेज साइज सेट करें, चरण दर चरण, ताकि आप हर बार बिल्कुल सही लेआउट बना सकें।

## त्वरित उत्तर
- **क्या मैं प्रत्येक पेज के लिए अलग-अलग पेज साइज सेट कर सकता हूँ?** हाँ, आप `document.openPage(width, height)` का उपयोग करके कस्टम आयामों के साथ पेज खोल सकते हैं।  
- **क्या उत्पादन उपयोग के लिए लाइसेंस चाहिए?** गैर‑मूल्यांकन डिप्लॉयमेंट के लिए एक वैध Aspose.Page लाइसेंस आवश्यक है।  
- **कौन से Java संस्करण समर्थित हैं?** यह लाइब्रेरी Java 8 और उसके बाद के संस्करणों के साथ काम करती है।  
- **क्या API थ्रेड‑सेफ है?** Document इंस्टेंस थ्रेड‑सेफ नहीं हैं; प्रत्येक थ्रेड के लिए अलग `PsDocument` बनाएं।  
- **PostScript फ़ाइल कितनी बड़ी हो सकती है?** Aspose.Page मल्टी‑मेगाबाइट फ़ाइलों को कुशलता से संभालता है; मेमोरी उपयोग सामग्री के अनुसार बढ़ता है, पेज गिनती के अनुसार नहीं।

## पूर्वापेक्षाएँ
- Java प्रोग्रामिंग की बुनियादी समझ।  
- अपने प्रोजेक्ट में Aspose.Page for Java जोड़ें (Maven/Gradle या मैन्युअल JAR)।  
- Java विकास पर्यावरण (IDE, JDK 8+)।  

## पैकेज इम्पोर्ट करें
शुरू करने के लिए, Aspose.Page लाइब्रेरी से आवश्यक क्लासेज़ इम्पोर्ट करें।

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## चरण 1: मल्टीपेज़ PostScript दस्तावेज़ बनाएं
सबसे पहले, एक नया `PsDocument` बनाएं जो कई पेजों के लिए कॉन्फ़िगर किया गया हो। यह आउटपुट स्ट्रीम सेट करता है और लाइब्रेरी को बताता है कि हम एक मल्टीपेज़ फ़ाइल के साथ काम करेंगे।

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
दस्तावेज़ तैयार होने पर, आप पहले पेज में आवश्यक कोई भी सामग्री जोड़ सकते हैं। समाप्त होने पर, पेज को बंद करके उसकी सामग्री को लॉक कर दें।

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## कस्टम पेज साइज कैसे सेट करें
यदि डिफ़ॉल्ट पेज साइज आपकी आवश्यकता नहीं है, तो आप नया पेज खोलते समय **कस्टम पेज साइज सेट** कर सकते हैं। यह रसीदों, लेबल या किसी भी गैर‑मानक लेआउट के लिए उपयोगी है।

## चरण 3: अलग साइज के साथ दूसरा पेज जोड़ें
नीचे हम दूसरा पेज खोलते हैं और स्पष्ट रूप से कस्टम चौड़ाई और ऊँचाई (पॉइंट्स में) प्रदान करते हैं। यह व्यक्तिगत पेजों के लिए कस्टम पेज साइज सेट करने का तरीका दर्शाता है।

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## चरण 4: दस्तावेज़ को सहेजें
अंत में, दस्तावेज़ को सहेजकर परिवर्तन को स्थायी बनाएं। सभी पेज—जिसमें कस्टम साइज वाले पेज भी शामिल हैं—आउटपुट फ़ाइल में लिखे जाते हैं।

```java
// Save the document
document.save();
```

इन चरणों का पालन करके, आप Aspose.Page का उपयोग करके Java PostScript दस्तावेज़ में पेज जोड़ सकते हैं और **कस्टम पेज साइज सेट** कर सकते हैं, जिससे आपको प्रत्येक पेज के लेआउट पर पूर्ण नियंत्रण मिलता है।

## निष्कर्ष
Aspose.Page for Java PostScript दस्तावेज़ों को संभालने के लिए एक मजबूत, डेवलपर‑मित्र API प्रदान करता है। अब आप जानते हैं कि कई पेज कैसे जोड़ें, कस्टम आयाम कैसे लागू करें, और परिणाम को कैसे सहेजें—जिससे आप किसी भी Java‑आधारित समाधान के लिए सटीक रूप से स्वरूपित आउटपुट उत्पन्न कर सकें।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं एक ही PostScript दस्तावेज़ में विभिन्न आकार के पेज जोड़ सकता हूँ?
हाँ, इस ट्यूटोरियल में दिखाए अनुसार, आप मल्टीपेज़ PostScript दस्तावेज़ में विभिन्न आकार के पेज जोड़ सकते हैं।

### क्या पेजों की संख्या पर कोई सीमा है?
Aspose.Page एक दस्तावेज़ में लगभग असीमित संख्या में पेज जोड़ने का समर्थन करता है।

### क्या मैं पेजों में कस्टम सामग्री, जैसे छवियां या ग्राफ़िक्स, जोड़ सकता हूँ?
बिल्कुल! Aspose.Page आपको टेक्स्ट, छवियां और अन्य ग्राफ़िकल तत्वों सहित विविध प्रकार की सामग्री जोड़ने की अनुमति देता है।

### क्या Aspose.Page बड़े दस्तावेज़ों को संभालने के लिए उपयुक्त है?
हाँ, Aspose.Page को छोटे और बड़े दोनों दस्तावेज़ों को आसानी से और कुशलता से संभालने के लिए डिज़ाइन किया गया है।

### मैं Aspose.Page के अतिरिक्त संसाधन और समर्थन कहाँ पा सकता हूँ?
Explore the [Aspose.Page दस्तावेज़ीकरण](https://reference.aspose.com/page/java/), or visit the [Aspose.Page फ़ोरम](https://forum.aspose.com/c/page/39) for community support.  

**अतिरिक्त प्रश्नोत्तर**

**Q:** *PostScript पेज पर ड्रॉ करने के समय कौन से इमेज फ़ॉर्मेट्स समर्थित हैं?*  
**A:** आप ड्रॉइंग API का उपयोग करके सीधे PNG, JPEG, BMP, और GIF इमेज एम्बेड कर सकते हैं।  

**Q:** *दस्तावेज़ के लिए डिफ़ॉल्ट DPI कैसे बदलूँ?*  
**A:** `PsDocument` बनाने से पहले `PsSaveOptions.setResolution(int dpi)` सेट करें।  

**Q:** *क्या मैं PostScript फ़ाइल को पासवर्ड से एन्क्रिप्ट कर सकता हूँ?*  
**A:** PostScript स्वयं एन्क्रिप्शन को सपोर्ट नहीं करता, लेकिन आप आउटपुट को PDF में रैप करके आवश्यक होने पर सुरक्षा सेटिंग्स लागू कर सकते हैं।

---

**अंतिम अपडेट:** 2025-12-11  
**परीक्षण किया गया:** Aspose.Page for Java 24.10  
**लेखक:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
