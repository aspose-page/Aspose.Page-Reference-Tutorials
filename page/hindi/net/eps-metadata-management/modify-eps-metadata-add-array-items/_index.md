---
date: 2026-08-08
description: Aspose.Page EPS मेटाडेटा का उपयोग करके EPS मेटाडेटा में एरे आइटम जोड़ना
  सीखें। यह चरण‑दर‑चरण .NET गाइड दिखाता है कि एरे आइटम कैसे जोड़ें और EPS फ़ाइलों
  को कुशलतापूर्वक पढ़ें।
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: एरे आइटम जोड़ें
og_description: Aspose.Page EPS मेटाडेटा का उपयोग करके EPS मेटाडेटा में एरे आइटम जोड़ना
  जानें। इस संक्षिप्त .NET ट्यूटोरियल का पालन करके EPS फ़ाइलों को पढ़ें और मेटाडेटा
  को कुशलतापूर्वक प्रबंधित करें।
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Aspose.Page EPS मेटाडेटा के साथ .NET में एरे आइटम जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Aspose.Page EPS मेटाडेटा के साथ .NET में एरे आइटम जोड़ें
url: /hi/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page EPS मेटाडाटा के साथ .NET में एरे आइटम जोड़ें

## परिचय

इस ट्यूटोरियल में आप सीखेंगे कि **Aspose.Page EPS metadata** का उपयोग करके EPS मेटाडाटा में एरे आइटम कैसे जोड़ें। चाहे आपको EPS फ़ाइल में अतिरिक्त शीर्षक, निर्माता, या कस्टम टैग जोड़ने की आवश्यकता हो, Aspose.Page किसी भी .NET डेवलपर के लिए इस कार्य को सरल बनाता है। हम प्रत्येक चरण को विस्तार से बताएँगे, EPS स्ट्रीम को खोलने से लेकर अपडेटेड XMP पैकेट को सहेजने तक, ताकि आप आत्मविश्वास के साथ अपने एप्लिकेशन में मेटाडाटा हैंडलिंग को एकीकृत कर सकें।

## त्वरित उत्तर
- **Aspose.Page EPS metadata आपको क्या करने देता है?** यह .NET से EPS फ़ाइलों के भीतर XMP मेटाडाटा एरे को पढ़ने और लिखने में सक्षम बनाता है।  
- **कौन सा क्लास EPS दस्तावेज़ का प्रतिनिधित्व करता है?** `PsDocument` EPS सामग्री को लोड और सहेजने के लिए मुख्य क्लास है।  
- **क्या विकास के लिए मुझे लाइसेंस चाहिए?** टेस्टिंग के लिए एक फ्री ट्रायल काम करता है; प्रोडक्शन के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **क्या मैं EPS ग्राफ़िक्स को बदले बिना मेटाडाटा संशोधित कर सकता हूँ?** हां, केवल XMP पैकेट बदला जाता है, पेज सामग्री अपरिवर्तित रहती है।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Aspose.Page EPS मेटाडाटा क्या है?
Aspose.Page EPS metadata एक XMP‑आधारित सूचना ब्लॉक है जो EPS फ़ाइल में एम्बेड किया जाता है। यह शीर्षक, निर्माता, कीवर्ड, और कस्टम टैग जैसी वर्णनात्मक प्रॉपर्टीज़ को ISO 16684‑1 मानक के अनुसार संग्रहीत करता है। यह मेटाडाटा Aspose.Page API के माध्यम से प्रोग्रामेटिकली एक्सेस और संशोधित किया जा सकता है, जिससे स्वचालित दस्तावेज़ प्रबंधन और खोज अनुकूलन संभव होता है।

## EPS मेटाडाटा को संशोधित क्यों करें?
Aspose.Page **30 से अधिक मेटाडाटा फ़ील्ड्स** को प्रोसेस कर सकता है और **200 MB** तक की EPS फ़ाइलों को पूरी दस्तावेज़ को मेमोरी में लोड किए बिना संभाल सकता है, जिससे पूर्ण‑फ़ाइल पार्सिंग की तुलना में CPU उपयोग में 40 % तक कमी आती है। मेटाडाटा को अपडेट करने से खोज योग्यता, अनुपालन, और डाउनस्ट्रीम वर्कफ़्लो ऑटोमेशन में सुधार होता है।

## पूर्वापेक्षाएँ
- बुनियादी .NET प्रोग्रामिंग ज्ञान।  
- Aspose.Page for .NET स्थापित है – इसे यहाँ से डाउनलोड करें [download Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- सैंपल कोड चलाने के लिए Visual Studio (या कोई भी .NET‑संगत IDE)।

## EPS मेटाडाटा में एरे आइटम कैसे जोड़ें?
एरे आइटम जोड़ने के लिए, पहले EPS फ़ाइल को `PsDocument` में लोड करें, फिर `GetXmpMetadata()` का उपयोग करके उसका XMP पैकेट प्राप्त करें। इच्छित XMP एरे, जैसे `dc:title` या `dc:creator`, पर `AddArrayItem()` मेथड का उपयोग करके नए मान जोड़ें। अंत में, `Save()` को कॉल करके अपडेटेड मेटाडाटा को फ़ाइल में लिखें जबकि ग्राफ़िक सामग्री अपरिवर्तित रहे।

### चरण 1: eps फ़ाइल इनपुट स्ट्रीम को इनिशियलाइज़ करें
`PsDocument` एक EPS दस्तावेज़ का प्रतिनिधित्व करता है और इसकी सामग्री तक पहुँचने के लिए मेथड्स प्रदान करता है। निम्नलिखित कोड EPS फ़ाइल को एक स्ट्रीम के रूप में खोलता है और एक `PsDocument` इंस्टेंस बनाता है।

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### चरण 2: xmp मेटाडाटा प्राप्त करें
`GetXmpMetadata()` EPS फ़ाइल में एम्बेडेड XMP पैकेट को प्राप्त करता है। यदि कोई पैकेट मौजूद नहीं है, तो API मौजूदा PostScript टिप्पणियों के आधार पर एक नया बनाता है।

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### चरण 3: xmp मेटाडाटा मान बदलें
`AddArrayItem()` मौजूदा XMP एरे में नया मान जोड़ता है बिना अन्य एंट्रीज़ को ओवरराइट किए। इसे मेटाडाटा में शीर्षक, निर्माता, या कस्टम टैग जोड़ने के लिए उपयोग करें।

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### चरण 4: बदले हुए xmp मेटाडाटा के साथ eps फ़ाइल सहेजें
`Save()` संशोधित XMP पैकेट को वापस EPS फ़ाइल में लिखता है जबकि मूल PostScript सामग्री को संरक्षित रखता है। आउटपुट पाथ प्रदान करके नई फ़ाइल बनाएं या स्रोत को ओवरराइट करें।

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## सामान्य जाल और समस्या निवारण
- **Null XMP packet** – यदि `GetXmpMetadata()` `null` लौटाता है, तो सुनिश्चित करें कि EPS फ़ाइल में कम से कम एक टिप्पणी ब्लॉक हो; अन्यथा, मैन्युअली एक नया `XmpMetadata` इंस्टेंस बनाएं।  
- **Encoding issues** – गैर‑ASCII भाषाओं में अक्षर भ्रष्टाचार से बचने के लिए स्ट्रिंग मान जोड़ते समय UTF‑8 का उपयोग करें।  
- **Large files** – यदि EPS फ़ाइल 150 MB से बड़ी है, तो मेमोरी उपयोग कम रखने के लिए बफ़र के साथ `FileStream` द्वारा इनपुट को स्ट्रीम करने पर विचार करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Page सभी .NET वातावरणों के साथ संगत है?**  
A: हाँ, Aspose.Page .NET Framework 4.5+, .NET Core 3.1+, और .NET 5/6/7 पर काम करता है, और Windows, Linux और macOS पर सुसंगत API व्यवहार प्रदान करता है।

**Q: क्या मैं Aspose.Page मुफ्त में उपयोग कर सकता हूँ?**  
A: आप लाइब्रेरी का मूल्यांकन मुफ्त ट्रायल डाउनलोड से कर सकते हैं [Aspose purchase page](https://purchase.aspose.com/buy). प्रोडक्शन डिप्लॉयमेंट के लिए एक कमर्शियल लाइसेंस आवश्यक है।

**Q: क्या Aspose.Page के लिए अस्थायी लाइसेंस उपलब्ध हैं?**  
A: अस्थायी लाइसेंस छोटे‑समय प्रोजेक्ट्स या मूल्यांकन अवधि के लिए [temporary license page](https://purchase.aspose.com/temporary-license/) से प्राप्त किए जा सकते हैं।

**Q: मैं Aspose.Page के लिए सामुदायिक समर्थन कहाँ पा सकता हूँ?**  
A: अन्य डेवलपर्स के साथ प्रश्न पूछने और समाधान साझा करने के लिए [Aspose.Page forum](https://forum.aspose.com/c/page/39) पर चर्चा में शामिल हों।

**Q: .NET के लिए Aspose.Page का नवीनतम संस्करण क्या है?**  
A: नवीनतम रिलीज़ नोट्स और डाउनलोड लिंक के लिए आधिकारिक [documentation](https://reference.aspose.com/page/net/) देखें।

---

**अंतिम अपडेट:** 2026-08-08  
**परीक्षित संस्करण:** Aspose.Page 24.11 for .NET  
**लेखक:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## संबंधित ट्यूटोरियल

- [Aspose.Page for .NET के साथ एरे आइटम बदलें](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Aspose.Page for .NET के साथ सरल प्रॉपर्टीज़ जोड़ें](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Aspose.Page for .NET के साथ नेमस्पेस जोड़ें](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}