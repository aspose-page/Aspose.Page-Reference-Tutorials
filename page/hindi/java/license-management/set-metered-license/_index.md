---
date: 2025-12-03
description: Aspose.Page for Java का उपयोग करके EPS को PNG के रूप में सहेजना सीखें
  और मीटर लाइसेंस को कॉन्फ़िगर करें। पूर्ण कोड उदाहरण के साथ चरण‑दर‑चरण गाइड।
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Aspose.Page Java (Metered License) के साथ EPS को PNG के रूप में सहेजें
url: /hi/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java (Metered License) के साथ EPS को PNG में सहेजें

## परिचय
यदि आपको Java एप्लिकेशन में **EPS को PNG में सहेजना** है और लाइसेंसिंग को आसान तरीके से प्रबंधित करना चाहते हैं, तो आप सही जगह पर हैं। यह ट्यूटोरियल आपको Aspose.Page के लिए मीटरड लाइसेंस कॉन्फ़िगर करने, PostScript (EPS) फ़ाइल लोड करने, और उसे PNG इमेज में बदलने की स्पष्ट, छोटे‑छोटे चरणों के माध्यम से ले जाता है।

## त्वरित उत्तर
- **“EPS को PNG में सहेजना” का क्या अर्थ है?** यह एक वेक्टर EPS फ़ाइल को रास्टर PNG इमेज में बदलता है।  
- **मीटरड लाइसेंस क्यों उपयोग करें?** यह आपको केवल उन पृष्ठों के लिए भुगतान करने देता है जिन्हें आप प्रोसेस करते हैं, जिससे बदलते वर्कलोड के लिए यह आदर्श है।  
- **क्या इंटरनेट कनेक्शन आवश्यक है?** नहीं, मीटरड कुंजियों की वैधता स्थानीय रूप से जाँचती है।  
- **कौन सा Java संस्करण आवश्यक है?** Java 8 या उससे ऊपर।  
- **सेटअप में कितना समय लगेगा?** बुनियादी इम्प्लीमेंटेशन के लिए लगभग 10 मिनट।

## “EPS को PNG में सहेजना” क्या है?
EPS को PNG में सहेजना एक स्केलेबल Encapsulated PostScript दस्तावेज़ को व्यापक रूप से समर्थित बिटमैप फ़ॉर्मेट में बदलता है। PNG पारदर्शिता को बनाए रखता है और लॉसलेस कम्प्रेशन प्रदान करता है, जिससे यह वेब ग्राफ़िक्स, थंबनेल और प्रिंट प्रीव्यू के लिए आदर्श है।

## इस कार्य के लिए Aspose.Page क्यों उपयोग करें?
- **शुद्ध Java API** – कोई नेटिव डिपेंडेंसी नहीं।  
- **उच्च सटीकता** – वेक्टर ग्राफ़िक्स सटीक रूप से रेंडर होते हैं।  
- **मीटरड लाइसेंसिंग** – आप केवल वही भुगतान करते हैं जो आप कन्वर्ट करते हैं।  
- **कई आउटपुट फ़ॉर्मेट का समर्थन** – PNG, JPEG, TIFF, आदि।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- Java प्रोग्रामिंग का बुनियादी ज्ञान।  
- Aspose.Page लाइब्रेरी स्थापित – इसे [here](https://releases.aspose.com/page/java/) से डाउनलोड करें।  
- मीटरड पब्लिक और प्राइवेट कुंजियाँ, जिन्हें आप अपने Aspose खाते से प्राप्त कर सकते हैं।

## पैकेज इम्पोर्ट करें
पहले, उन क्लासों को इम्पोर्ट करें जिनकी हमें आवश्यकता होगी। कोड को बिना बदलाव के कंपाइल करने के लिए इम्पोर्ट ब्लॉक को बिल्कुल जैसा है वैसा ही रखें।

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## चरण 1: डॉक्यूमेंट और इमेज फ़ॉर्मेट इनिशियलाइज़ करें
यहाँ हम मीटरड कुंजियों को सेट करते हैं और आउटपुट फ़ॉर्मेट (PNG) को परिभाषित करते हैं। यह **EPS को PNG में सहेजना** ऑपरेशन की नींव है।

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

## चरण 2: PostScript इनपुट स्ट्रीम इनिशियलाइज़ करें
उस EPS फ़ाइल को खोलें जिसे आप कन्वर्ट करना चाहते हैं। स्ट्रीम डॉक्यूमेंट को Aspose.Page में फीड करती है।

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## चरण 3: डॉक्यूमेंट लाइसेंस जांचें
प्रोसेसिंग से पहले हमेशा यह सत्यापित करें कि मीटरड लाइसेंस सही ढंग से लागू हुआ है।

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## चरण 4: ऑप्शन्स और इमेज डिवाइस इनिशियलाइज़ करें
वह ऑप्शन्स ऑब्जेक्ट बनाएं जो कन्वर्ज़न सेटिंग्स को नियंत्रित करता है और वह डिवाइस जो रेंडर की गई इमेज प्राप्त करेगा।

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## चरण 5: EPS फ़ाइल को इमेज के रूप में सहेजें
यह मुख्य **EPS को PNG में सहेजना** कॉल है। डॉक्यूमेंट को हमने कॉन्फ़िगर किए गए ऑप्शन्स के साथ इमेज डिवाइस में रेंडर किया जाता है।

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## चरण 6: इमेज बाइट्स प्राप्त करें और सहेजें
डिवाइस से PNG बाइट्स निकालें और उन्हें डिस्क पर फ़ाइल में लिखें।

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|------|--------|
| **लाइसेंस पहचान नहीं रहा** | कुंजियाँ गलत हैं या गलत क्रम में रखी गई हैं। | पब्लिक/प्राइवेट कुंजी स्ट्रिंग्स को दोबारा जांचें और सुनिश्चित करें कि `setMeteredKey` किसी भी डॉक्यूमेंट प्रोसेसिंग से पहले कॉल किया गया है। |
| **आउटपुट फ़ाइल खाली है** | `device.getImagesBytes()` ने `null` लौटाया। | यह सत्यापित करें कि EPS फ़ाइल वैध है और `ImageSaveOptions` शून्य‑साइज़ कैनवास पर सेट नहीं है। |
| **बड़ी EPS पर OutOfMemoryError** | बड़े वेक्टर फ़ाइलों को रेंडर करने में बहुत मेमोरी लगती है। | पृष्ठों को एक‑एक करके प्रोसेस करें या JVM हीप (`-Xmx2g`) बढ़ाएँ। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: मीटरड पब्लिक और प्राइवेट कुंजियाँ कैसे प्राप्त करें?**  
उत्तर: आप इन्हें अपने Aspose खाते से प्राप्त कर सकते हैं।

**प्रश्न: क्या Aspose.Page लाइब्रेरी मुफ्त है?**  
उत्तर: Aspose.Page में फ्री ट्रायल और पेड दोनों संस्करण उपलब्ध हैं। फ्री ट्रायल के लिए [here](https://releases.aspose.com/) देखें।

**प्रश्न: क्या मैं Aspose.Page को वाणिज्यिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?**  
उत्तर: हाँ, Aspose.Page के पास वाणिज्यिक लाइसेंस उपलब्ध हैं। आप इन्हें [here](https://purchase.aspose.com/buy) से खरीद सकते हैं।

**प्रश्न: अतिरिक्त दस्तावेज़ीकरण कहाँ मिल सकता है?**  
उत्तर: दस्तावेज़ीकरण के लिए [here](https://reference.aspose.com/page/java/) देखें।

**प्रश्न: अस्थायी लाइसेंस कैसे प्राप्त करें?**  
उत्तर: अस्थायी लाइसेंस आप [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

---

**अंतिम अपडेट:** 2025-12-03  
**टेस्टेड संस्करण:** Aspose.Page 24.12 for Java  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}