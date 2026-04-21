---
date: 2026-01-02
description: जावा XPS दस्तावेज़ों में पारदर्शिता जोड़ना सीखें Aspose.Page का उपयोग
  करके। शानदार दृश्य प्रभावों के साथ पारदर्शी वस्तुएँ जोड़ने के लिए हमारे चरण‑दर‑चरण
  मार्गदर्शक का पालन करें।
linktitle: Add Transparent Object in Java XPS
second_title: Aspose.Page Java API
title: जावा XPS दस्तावेज़ों में पारदर्शिता कैसे जोड़ें
url: /hi/java/xps-transparency/add-transparent-object/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS डॉक्यूमेंट्स में ट्रांसपेरेंसी कैसे जोड़ें

## इंट्रोडक्शन
अगर आप अपने Java XPS डॉक्यूमेंट्स में **ट्रांसपेरेंसी कैसे जोड़ें** जोड़ना चाहते हैं और उन्हें एक आधुनिक, परतदार लुक देना चाहते हैं, तो Aspose.Page for Java इसे सरल बनाता है। इस ट्यूटोरियल में हम सभी ज़रूरी स्टेप्स को कवर करेंगे—पर्यावरण सेटअप से लेकर पारदर्शी पाथ बनाने, अपारदर्शिता (opacity) को कंट्रोल करने, और अंत में परिणाम को सहेजने तक। अंत तक, आप किसी भी XPS ऑब्जेक्ट में कॉन्फिडेंस के साथ ट्रांसफर जोड़ कैलिबर।

## क्विक आंसर्स
- **कौन सी लाइब्रेरी ज़रूरी है?** Aspose.Page for Java
- **क्या मैं प्रोग्रामेटिकली ओपेसिटी कंट्रोल कर सकता हूँ?** हाँ, ब्रश पर `setOpacity` मेथड के ज़रिए।
- **क्या मुझे प्रोडक्शन के लिए लाइसेंस चाहिए?** नॉन-इवैल्यूएशन इस्तेमाल के लिए कमर्शियल लाइसेंस ज़रूरी है।
- **कौन सा Java वर्जन सपोर्टेड है?** Java8 और उसके बाद का।
- **क्या आउटपुट स्टैंडर्ड XPS व्यूअर्स के साथ कम्पैटिबल है?** बिल्कुल—स्टैंडर्ड व्यूअर्स ट्रांसपेरेंसी को सही तरीके से रेंडर करते हैं।

## XPS में ट्रांसपेरेंसी क्या है?

आपको ऑब्जेक्ट्स को अलग-अलग अपारदर्शिता के साथ रेंडर करने की अनुमति देती है, जिससे बैकग्राउंड के एलिमेंट दिखेंगे। यह इम्पैक्ट वॉटरमार्क, ओवरले ग्राफ़िक्स, या किसी भी डिज़ाइन में उपयोगी है जहाँ परतदार विज़ुअलता पढ़ने को मिलती है।

## ट्रांसपेरेंसी जोड़ने के लिए Aspose.Page का इस्तेमाल क्यों करें?
- **ज्योमेट्री, ब्रश और ट्रांसफ़ॉर्म पर पूरा कंट्रोल**।
- **कोई बाहरी डिपेंडेंसी नहीं**—सब कुछ API के अंदर हैंडल किया जाता है।
- **क्रॉस-प्लेटफ़ॉर्म** सपोर्ट, इसलिए वही कोड Windows, Linux और macOS पर काम करता है।

## ज़रूरी शर्तें
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

- एक Java डेवलपमेंट एनवायरनमेंट (JDK8+)।
- Aspose.Page for Java लाइब्रेरी इंस्टॉल है। आप इसे ऑफिशियल साइट [यहां](https://releases.aspose.com/page/java/) से डाउनलोड कर सकते हैं।

## पैकेज इंपोर्ट करें
अपने Java प्रोजेक्ट में आवश्यक Aspose.Page पैकेज इम्पोर्ट करें ताकि आप पारदर्शी ऑब्जेक्ट जोड़ना शुरू कर सकें। अपने Java फ़ाइल की शुरुआत में निम्नलिखित लाइनों को शामिल करें:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.Color;
```

अब, उदाहरण कोड को कई चरणों में विभाजित करते हैं।

## स्टेप 1: डॉक्यूमेंट को इनिशियलाइज़ करें
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize document
XpsDocument doc = new XpsDocument();
```
सबसे पहले अपने दस्तावेज़ को सेट अप करें और वह डायरेक्टरी निर्दिष्ट करें जहाँ आपका XPS दस्तावेज़ सहेजा जाएगा।

## स्टेप 2: ट्रांसपेरेंट ऑब्जेक्ट्स बनाएँ
```java
// Just to demonstrate transparency
doc.addPath(doc.createPathGeometry("M120,0 H400 v1000 H120")).setFill(doc.createSolidColorBrush(Color.GRAY));
doc.addPath(doc.createPathGeometry("M300,120 h600 V420 h-600")).setFill(doc.createSolidColorBrush(Color.GRAY));
```
यहाँ हम दो ग्रे पाथ बनाते हैं जो बाद में जोड़ने वाले पारदर्शी आकारों के लिए बैकड्रॉप के रूप में काम करेंगे।

## स्टेप 3: फिल्ड पाथ्स जोड़ें
```java
// Create path with closed rectangle geometry
XpsPath path1 = doc.createPath(doc.createPathGeometry("M20,20 h200 v200 h-200 z"));
// Set blue solid brush to fill path1
path1.setFill(doc.createSolidColorBrush(Color.BLUE));
// Add it to the current page
XpsPath path2 = doc.add(path1);
```
इस चरण में हम एक ठोस नीला आयत बनाते हैं और उसे पेज पर रखते हैं। यह आयत बाद में पारदर्शी आकारों द्वारा ओवरलैप किया जाएगा, जिससे प्रभाव प्रदर्शित होगा।

## स्टेप 4: ट्रांसपेरेंसी में बदलाव करें
```java
// path1 and path2 are the same as long as path1 hasn't been placed inside any other element
path2.setFill(doc.createSolidColorBrush(Color.GREEN));
// Now add path2 once again. Now path2 has a parent, so path3 won't be the same as path2.
XpsPath path3 = doc.add(path2);
path3.setRenderTransform(doc.createMatrix(1, 0, 0, 1, 0, 300));
path3.setFill(doc.createSolidColorBrush(Color.RED));
```
यहाँ हम डुप्लिकेट पाथ का फ़िल कलर बदलते हैं और एक ट्रांसलेशन ट्रांसफ़ॉर्म लागू करते हैं। यह दर्शाता है कि जब ऑब्जेक्ट एक ही पैरेंट एलिमेंट साझा करते हैं तो पारदर्शिता कैसे इंटरैक्ट करती है।

## स्टेप 5: पाथ्स को डुप्लिकेट और मॉडिफाई करें
```java
// Create new path4 with path2's geometry
XpsPath path4 = doc.addPath(path2.getData());
path4.setRenderTransform(doc.createMatrix(1, 0, 0, 1, 300, 0));
path4.setFill(doc.createSolidColorBrush(Color.BLUE));
// Add path4 once again.
XpsPath path5 = doc.add(path4);
path5.setRenderTransform(path5.getRenderTransform().deepClone());
path5.getRenderTransform().translate(0, 300);
path5.getFill().setOpacity(0.8f);
```
हम मौजूदा पाथ को क्लोन करते हैं, उसे स्थानांतरित करते हैं, और उसकी अपारदर्शिता को 0.8 (80 % अपारदर्शी) सेट करते हैं। यह चरण दिखाता है कि आप जियोमेट्री को पुन: उपयोग कर सकते हैं और प्रत्येक इंस्टेंस के लिए पारदर्शिता को कस्टमाइज़ कर सकते हैं।

## स्टेप 6: डॉक्यूमेंट को सेव करें
```java
// Save the modified document
doc.save(dataDir + "WorkingWithTransparency_out.xps");
```
अंत में, हम XPS फ़ाइल को सहेजते हैं। परिणामस्वरूप फ़ाइल को किसी भी XPS व्यूअर में खोलें और परतदार पारदर्शिता को क्रिया में देखें।

## आम दिक्कतें और टिप्स
- **ओपेसिटी दिख नहीं रही?** पक्का करें कि आप ऐसा ब्रश इस्तेमाल कर रहे हैं जो ओपेसिटी को सपोर्ट करता हो (जैसे, `createSolidColorBrush`)।

- **ट्रांसफ़ॉर्म लागू नहीं हुआ?** डॉक्यूमेंट में पाथ जोड़ने से **पहले** पक्का कर लें कि आप `setRenderTransform` को कॉल कर रहे हैं।

- **परफ़ॉर्मेंस टिप:** मेमोरी ओवरहेड कम करने के लिए कई एक जैसे शेप बनाते समय ज्योमेट्री ऑब्जेक्ट का दोबारा इस्तेमाल करें।

## अक्सर पूछे जाने वाले सवाल
### सवाल: क्या मैं रेक्टेंगल के अलावा दूसरे शेप पर भी ट्रांसपेरेंसी लगा सकता हूँ?

जवाब: हाँ, आप दी गई ज्योमेट्री का इस्तेमाल करके अलग-अलग शेप पर ट्रांसपेरेंसी लगा सकते हैं।

### सवाल: मैं किसी ऑब्जेक्ट का ट्रांसपेरेंसी लेवल कैसे कंट्रोल कर सकता हूँ?

जवाब: ट्रांसपेरेंसी लेवल कंट्रोल करने के लिए फ़िल की ओपेसिटी प्रॉपर्टी को एडजस्ट करें।

### सवाल: क्या Aspose.Page प्रोफ़ेशनल डॉक्यूमेंट बनाने के लिए सही है?

जवाब: बिल्कुल! Aspose.Page प्रोफ़ेशनल डॉक्यूमेंट मैनिपुलेशन के लिए मज़बूत फ़ीचर देता है।

### सवाल: क्या मैं Aspose.Page को दूसरी Java लाइब्रेरी के साथ इंटीग्रेट कर सकता हूँ?
जवाब: हाँ, Aspose.Page को ज़्यादा फंक्शनैलिटी के लिए दूसरी Java लाइब्रेरी के साथ आसानी से इंटीग्रेट किया जा सकता है।
### सवाल: मुझे Aspose.Page के लिए और उदाहरण और सपोर्ट कहाँ मिल सकता है?
जवाब: कम्युनिटी सपोर्ट के लिए [Aspose.Page Java Forum](https://forum.aspose.com/c/page/39) पर जाएँ और [यहाँ](https://reference.aspose.com/page/java/) डॉक्यूमेंटेशन देखें।

---

**पिछला अपडेट:** 2026-01-02
**इसके साथ टेस्ट किया गया:** Java 24.12 के लिए Aspose.Page
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}