---
date: 2026-08-13
description: Aspose.Page का उपयोग करके .NET अनुप्रयोगों में EPS मान बदलना सीखें, जिसमें
  चरण-दर-चरण XMP मेटाडेटा अपडेट शामिल हैं।
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: मान बदलें
og_description: Aspose.Page change eps values ट्यूटोरियल आपको .NET का उपयोग करके EPS
  फ़ाइलों के भीतर XMP मेटाडेटा को संशोधित करने का तरीका दिखाता है। निर्माता, शीर्षक
  और संशोधित तिथि को तुरंत अपडेट करने के लिए चरण-दर-चरण गाइड का पालन करें।
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page के साथ .NET में EPS मान बदलने का ट्यूटोरियल
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page के साथ .NET में EPS मान बदलें – ट्यूटोरियल
url: /hi/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page के साथ .NET में EPS मान बदलें – ट्यूटोरियल

## परिचय

इस ट्यूटोरियल में आप सीखेंगे कि **aspose.page change eps values** को कैसे EPS फ़ाइल में एम्बेडेड XMP मेटाडेटा को संपादित करके बदल सकते हैं। चाहे आपको निर्माता का नाम अपडेट करना हो, शीर्षक समायोजित करना हो, या संशोधित तिथि को सही करना हो, Aspose.Page for .NET आपको एक साफ़, कोड‑फ़र्स्ट API प्रदान करता है जो Windows, Linux, और macOS पर काम करता है। गाइड के अंत तक आपके पास एक पुन: उपयोग योग्य स्निपेट होगा जिसे आप किसी भी .NET सेवा या कंसोल एप्लिकेशन में जोड़ सकते हैं।

## त्वरित उत्तर

- **ट्यूटोरियल क्या कवर करता है?** Aspose.Page for .NET का उपयोग करके EPS फ़ाइलों के भीतर XMP मेटाडेटा (निर्माता, शीर्षक, संशोधित तिथि) बदलना।  
- **कौन सा लाइब्रेरी संस्करण आवश्यक है?** कोई भी Aspose.Page for .NET रिलीज़ जो XMP का समर्थन करता है (v24.10+).  
- **क्या मुझे लाइसेंस चाहिए?** प्रोडक्शन के लिए एक अस्थायी लाइसेंस आवश्यक है; विकास के लिए एक मुफ्त ट्रायल काम करता है।  
- **क्या मैं इसे .NET Core पर चला सकता हूँ?** हाँ – API .NET 5, .NET 6, और .NET Core 3.1+ के साथ संगत है।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बुनियादी मेटाडेटा अपडेट के लिए लगभग 5‑10 मिनट।

## XMP मेटाडेटा क्या है?

XMP मेटाडेटा एक मानकीकृत XML ब्लॉक है जो EPS और अन्य ग्राफिक फ़ॉर्मैट्स के भीतर वर्णनात्मक जानकारी (लेखक, शीर्षक, तिथियां) संग्रहीत करता है। यह फ़ाइल हेडर में सीधे एम्बेडेड होता है और कई डिज़ाइन और प्रकाशन टूल्स द्वारा पढ़ा जा सकता है, जिससे प्लेटफ़ॉर्म के बीच सुसंगत मेटाडेटा हैंडलिंग संभव होती है। XMP को अपडेट करने से डाउनस्ट्रीम एप्लिकेशन सही दस्तावेज़ गुण प्रदर्शित कर सकते हैं बिना दृश्य सामग्री बदले।

## EPS मेटाडेटा के लिए Aspose.Page क्यों उपयोग करें?

Aspose.Page **30+** ग्राफिक फ़ॉर्मैट्स को प्रोसेस कर सकता है और **1 GB** तक की EPS फ़ाइलों को पूरी फ़ाइल को मेमोरी में लोड किए बिना संभालता है, जिससे साधारण स्ट्रीम पार्सिंग की तुलना में RAM उपयोग में **70 %** की कमी आती है। लाइब्रेरी यह भी गारंटी देती है कि मेटाडेटा संपादन के बाद EPS की दृश्य रेंडरिंग अपरिवर्तित रहती है।

## पूर्वापेक्षाएँ

शुरू करने से पहले, सुनिश्चित करें कि निम्नलिखित तैयार हैं:

1. **Aspose.Page for .NET library** – इसे आधिकारिक Aspose.Page for .NET रिलीज़ पेज [here](https://releases.aspose.com/page/net/) से डाउनलोड करें। आप अन्य Aspose उत्पाद रिलीज़ [here](https://releases.aspose.com/) भी देख सकते हैं।  
2. **Document directory** – अपने मशीन पर एक फ़ोल्डर बनाएं जहाँ स्रोत EPS फ़ाइलें और आउटपुट फ़ाइलें स्थित हों।

अब जब पर्यावरण सेट हो गया है, चलिए आवश्यक नेमस्पेसेस इम्पोर्ट करते हैं।

## नेमस्पेसेस इम्पोर्ट करें

`Aspose.Page` नेमस्पेस कोर क्लासेस प्रदान करता है, जबकि `System.IO` आपको स्ट्रीम हैंडलिंग क्षमताएँ देता है।

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## EPS मेटाडेटा मान कैसे बदलें?

EPS फ़ाइल लोड करें, उसका XMP पैकेट प्राप्त करें, आवश्यक फ़ील्ड्स को संशोधित करें, और अपडेटेड EPS को डिस्क पर वापस लिखें। इस प्रक्रिया में पेज कंटेंट को रेंडर करने की आवश्यकता नहीं होती, इसलिए यह तेज़ और मेमोरी‑कुशल है। प्रत्येक ऑपरेशन के कोड उदाहरण देखने के लिए विस्तृत चरणों का पालन करें। यह एंड‑टू‑एंड फ्लो नीचे दिए गए चरणों में कवर किया गया है।

### चरण 1: EPS फ़ाइल इनपुट स्ट्रीम को इनिशियलाइज़ करें

एक रीड‑ओनली `FileStream` बनाएं जो स्रोत EPS फ़ाइल की ओर इशारा करता हो।

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### चरण 2: स्ट्रीम से PsDocument इंस्टेंस बनाएं

`PsDocument` मेमोरी में EPS दस्तावेज़ का टॉप‑लेवल ऑब्जेक्ट है। यह आपको पेज कंटेंट और एम्बेडेड XMP मेटाडेटा दोनों तक पहुंच प्रदान करता है।

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### चरण 3: XMP मेटाडेटा प्राप्त करें

`XmpMetadata` प्रॉपर्टी एक `XmpPacket` ऑब्जेक्ट लौटाती है जिसे आप क्वेरी और संपादित कर सकते हैं।

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### चरण 4: XMP मेटाडेटा मान संशोधित करें

अब आप तीन सामान्य फ़ील्ड्स बदलेंगे: **ModifyDate**, **Creator**, और **Title**।

#### चरण 4.1: ModifyDate मान बदलें

`ModifyDate` को वर्तमान UTC टाइमस्टैम्प पर सेट करें।

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### चरण 4.2: Creator मान बदलें

मौजूदा निर्माता को अपने एप्लिकेशन नाम से बदलें।

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### चरण 4.3: Title मान बदलें

शीर्षक को नए कंटेंट उद्देश्य को दर्शाने के लिए अपडेट करें।

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### चरण 5: बदले हुए XMP मेटाडेटा के साथ EPS फ़ाइल सहेजें

संपादन के बाद, दस्तावेज़ को वापस लिखें।

#### चरण 5.1: आउटपुट स्ट्रीम बनाएं

गंतव्य EPS फ़ाइल के लिए एक `FileStream` खोलें।

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### चरण 5.2: EPS फ़ाइल सहेजें

`PsDocument` इंस्टेंस पर `Save` कॉल करें, आउटपुट स्ट्रीम पास करते हुए।

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

अंत में, फ़ाइल हैंडल रिलीज़ करने के लिए इनपुट स्ट्रीम को बंद करें।

```csharp
// Save EPS file
document.Save(outPsStream);
```

बधाई हो! आपने EPS फ़ाइल के भीतर XMP मेटाडेटा को अपडेट करके **aspose.page change eps values** सफलतापूर्वक किया है।

## सामान्य समस्याएँ और ट्रबलशूटिंग

- **Empty XMP packet** – कुछ EPS फ़ाइलें XMP के बिना जेनरेट होती हैं। ऐसे में, मान असाइन करने से पहले `new XmpPacket()` के माध्यम से नया `XmpPacket` बनाएं।  
- **Large files** – 500 MB से बड़ी EPS फ़ाइलों के लिए, `PsDocumentOptions.UseMemoryMappedFiles = true` सेट करके स्ट्रीम बफ़रिंग सक्षम करें ताकि `OutOfMemoryException` से बचा जा सके।  
- **Incorrect date format** – XMP ISO 8601 की अपेक्षा करता है। अनुपालन स्ट्रिंग बनाने के लिए `DateTime.UtcNow.ToString("o")` उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Page for .NET को अन्य ग्राफिक फ़ॉर्मैट्स के साथ उपयोग कर सकता हूँ?**  
A: हाँ, लाइब्रेरी 30 से अधिक फ़ॉर्मैट्स का समर्थन करती है जिसमें PDF, SVG, और AI शामिल हैं, लेकिन XMP एडिटिंग API विशेष रूप से EPS और PDF के लिए हैं।

**Q: क्या ट्रायल संस्करण उपलब्ध है?**  
A: हाँ, आप Aspose.Page for .NET को Aspose रिलीज़ पेज [here](https://releases.aspose.com/) पर उपलब्ध मुफ्त ट्रायल के साथ आज़मा सकते हैं।

**Q: विस्तृत दस्तावेज़ीकरण कहाँ मिल सकता है?**  
A: व्यापक Aspose.Page .NET API रेफ़रेंस [here](https://reference.aspose.com/page/net/) पर पाया जा सकता है।

**Q: अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A: आप अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

**Q: क्या मैं Aspose.Page for .NET खरीद सकता हूँ?**  
A: बिल्कुल! लाइसेंसिंग विकल्पों के लिए Aspose.Page खरीद पेज [here](https://purchase.aspose.com/buy) पर जाएँ।

---

**अंतिम अपडेट:** 2026-08-13  
**परीक्षण किया गया:** Aspose.Page 24.10 for .NET  
**लेखक:** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## संबंधित ट्यूटोरियल

- [Aspose.Page for .NET के साथ EPS दस्तावेज़ में मेटाडेटा जोड़ें](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Aspose.Page for .NET के साथ EPS दस्तावेज़ से मेटाडेटा निकालें](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Aspose.Page for .NET के साथ नामित मान बदलें](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}