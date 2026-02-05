---
date: 2026-02-05
description: Aspose.Page for Java का उपयोग करके EPS को PNG में कैसे सहेजें और मीटरड
  लाइसेंस को कॉन्फ़िगर करना सीखें। पूर्ण कोड उदाहरण के साथ चरण‑दर‑चरण गाइड।
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Aspose.Page Java (मेटर्ड लाइसेंस) के साथ EPS को PNG में सहेजें
url: /hi/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java (Metered License) के साथ EPS को PNG के रूप में सहेजें

## परिचय
यदि आपको Java एप्लिकेशन में **save EPS as PNG** करने की आवश्यकता है और लाइसेंसिंग को बिना झंझट के प्रबंधित करना चाहते हैं, तो आप सही जगह पर हैं। यह ट्यूटोरियल आपको Aspose.Page के लिए मेटर्ड लाइसेंस को कॉन्फ़िगर करने, PostScript (EPS) फ़ाइल को लोड करने और उसे PNG इमेज में परिवर्तित करने की प्रक्रिया दिखाता है—स्पष्ट, छोटे‑छोटे चरणों के साथ जिसे आप तुरंत फॉलो कर सकते हैं। अंत तक आप यह भी समझेंगे कि **render EPS to PNG** को प्रभावी ढंग से कैसे किया जाता है और **write PNG file Java** कोड कैसे लिखा जाता है जो प्रोडक्शन वातावरण में काम करता है।

## त्वरित उत्तर
- **save EPS as PNG** का क्या अर्थ है? यह एक वेक्टर EPS फ़ाइल को रास्टर PNG इमेज में परिवर्तित करता है।  
- **Metered लाइसेंस** क्यों उपयोग करें? यह आपको केवल उन पेजों के लिए भुगतान करने देता है जिन्हें आप प्रोसेस करते हैं, जिससे बदलते वर्कलोड के लिए यह आदर्श है।  
- क्या मुझे इंटरनेट कनेक्शन चाहिए? नहीं, मेटर्ड कीज़ स्थानीय रूप से वैलिडेट की जाती हैं।  
- कौन सा Java संस्करण आवश्यक है? Java 8 या उससे ऊपर।  
- सेटअप में कितना समय लगेगा? बेसिक इम्प्लीमेंटेशन के लिए लगभग 10 मिनट।

## “save EPS as PNG” क्या है?
EPS को PNG के रूप में सहेजना एक स्केलेबल Encapsulated PostScript दस्तावेज़ को व्यापक रूप से समर्थित बिटमैप फ़ॉर्मेट में बदलता है। PNG ट्रांसपैरेंसी को बनाए रखता है और लॉसलैस कम्प्रेशन प्रदान करता है, जिससे यह वेब ग्राफिक्स, थंबनेल और प्रिंट प्रीव्यू के लिए आदर्श है।

## Aspose.Page के साथ EPS को PNG में रेंडर क्यों करें?
- **Pure Java API** – कोई नेटिव डिपेंडेंसी नहीं, इसलिए आप इसे किसी भी JVM‑सपोर्टेड वातावरण में चला सकते हैं।  
- **High fidelity rendering** – वेक्टर ग्राफिक्स को सटीक रूप से रास्टराइज़ किया जाता है, लाइन क्वालिटी बनी रहती है।  
- **Metered licensing** – आप केवल वही भुगतान करते हैं जो आप कन्वर्ट करते हैं, जिससे लागत पूर्वानुमानित रहती है।  
- **Multiple output options** – PNG के अलावा आप JPEG, TIFF आदि भी जेनरेट कर सकते हैं, जिससे विभिन्न प्रोजेक्ट्स के लिए लचीलापन मिलता है।

## आवश्यकताएँ
- Java प्रोग्रामिंग का बुनियादी ज्ञान।  
- Aspose.Page लाइब्रेरी स्थापित है – इसे [यहाँ](https://releases.aspose.com/page/java/) से डाउनलोड करें।  
- मेटर्ड पब्लिक और प्राइवेट कीज़, जिन्हें आप अपने Aspose अकाउंट के माध्यम से प्राप्त कर सकते हैं।

## पैकेज इम्पोर्ट करें
पहले, उन क्लासेज़ को इम्पोर्ट करें जिनकी हमें आवश्यकता होगी। कोड ब्लॉक को बिल्कुल उसी तरह रखें जैसा दिखाया गया है ताकि कोड बिना बदलाव के कम्पाइल हो सके।

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Aspose.Page Java का उपयोग करके EPS को PNG के रूप में सहेजने का तरीका
नीचे चरण‑दर‑चरण गाइड है जो लाइसेंसिंग, लोडिंग, रेंडरिंग और अंतिम PNG फ़ाइल लिखने को संयोजित करता है।

### चरण 1: डॉक्यूमेंट और इमेज फॉर्मेट को इनिशियलाइज़ करें
यहाँ हम मेटर्ड कीज़ सेट करते हैं और आउटपुट फॉर्मेट (PNG) को परिभाषित करते हैं। यह **save EPS as PNG** ऑपरेशन की बुनियाद है।

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

### चरण 2: PostScript इनपुट स्ट्रीम को इनिशियलाइज़ करें
उस EPS फ़ाइल को खोलें जिसे आप कन्वर्ट करना चाहते हैं। स्ट्रीम डॉक्यूमेंट को Aspose.Page में फीड करती है।

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### चरण 3: डॉक्यूमेंट लाइसेंस की जाँच करें
प्रोसेसिंग शुरू करने से पहले हमेशा यह सत्यापित करें कि मेटर्ड लाइसेंस सही ढंग से लागू हुआ है।

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### चरण 4: ऑप्शन्स और इमेज डिवाइस को इनिशियलाइज़ करें
एक ऑप्शन्स ऑब्जेक्ट बनाएं जो कन्वर्ज़न सेटिंग्स को नियंत्रित करता है और वह डिवाइस जो रेंडर की गई इमेज प्राप्त करेगा।

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### चरण 5: EPS फ़ाइल को इमेज के रूप में सहेजें
यह मुख्य **save EPS as PNG** कॉल है। डॉक्यूमेंट को कॉन्फ़िगर किए गए ऑप्शन्स के साथ इमेज डिवाइस में रेंडर किया जाता है।

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### चरण 6: इमेज बाइट्स प्राप्त करें और सहेजें
डिवाइस से PNG बाइट्स निकालें और उन्हें डिस्क पर फ़ाइल में लिखें। यह चरण दिखाता है कि **write PNG file Java** को सुरक्षित रूप से कैसे किया जाता है।

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
| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| **License not recognized** | कीज़ गलत हैं या गलत क्रम में रखी गई हैं। | सार्वजनिक/निजी की स्ट्रिंग्स को दोबारा जाँचें और सुनिश्चित करें कि `setMeteredKey` को किसी भी डॉक्यूमेंट प्रोसेसिंग से पहले कॉल किया गया है। |
| **Output file is empty** | `device.getImagesBytes()` ने `null` लौटाया। | यह सत्यापित करें कि EPS फ़ाइल वैध है और `ImageSaveOptions` शून्य‑साइज़ कैनवास पर सेट नहीं है। |
| **OutOfMemoryError on large EPS** | बड़े वेक्टर फ़ाइलों को रेंडर करने में बहुत मेमोरी लगती है। | पेज‑दर‑पेज प्रोसेस करें या JVM हीप (`-Xmx2g`) बढ़ाएँ। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: मैं मेटर्ड पब्लिक और प्राइवेट कीज़ कैसे प्राप्त करूँ?**  
A: आप इन कीज़ को अपने Aspose अकाउंट के माध्यम से प्राप्त कर सकते हैं।

**Q: क्या Aspose.Page लाइब्रेरी मुफ्त है?**  
A: Aspose.Page दोनों—फ्री ट्रायल और पेड—वर्ज़न प्रदान करता है। फ्री ट्रायल के लिए [यहाँ](https://releases.aspose.com/) जाएँ।

**Q: क्या मैं Aspose.Page को वाणिज्यिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.Page के पास कमर्शियल लाइसेंस उपलब्ध हैं। आप इन्हें [यहाँ](https://purchase.aspose.com/buy) खरीद सकते हैं।

**Q: अतिरिक्त डॉक्यूमेंटेशन कहाँ मिल सकता है?**  
A: डॉक्यूमेंटेशन के लिए [यहाँ](https://reference.aspose.com/page/java/) देखें।

**Q: अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A: अस्थायी लाइसेंस आप [यहाँ](https://purchase.aspose.com/temporary-license/) से ले सकते हैं।

**Q: यदि मुझे मल्टी‑पेज EPS फ़ाइल को कन्वर्ट करना हो तो क्या करें?**  
A: `device.getImagesBytes()` का उपयोग करके प्रत्येक पेज पर लूप करें और प्रत्येक बाइट एरे को अलग‑अलग PNG फ़ाइल में लिखें।

**Q: क्या मैं PNG क्वालिटी या कलर डेप्थ बदल सकता हूँ?**  
A: हाँ, `ImageSaveOptions` को कॉन्फ़िगर करें (जैसे `options.setCompressionLevel(...)`) `document.save(...)` कॉल करने से पहले।

---

**अंतिम अपडेट:** 2025-12-03  
**परिक्षण किया गया:** Aspose.Page 24.12 for Java  
**लेखक:** Aspose  

**अंतिम अपडेट:** 2026-02-05  
**परिक्षण किया गया:** Aspose.Page 24.12 for Java (latest)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}