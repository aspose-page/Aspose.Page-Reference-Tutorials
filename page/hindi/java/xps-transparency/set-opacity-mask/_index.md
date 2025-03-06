---
title: जावा एक्सपीएस में अपारदर्शिता मास्क सेट करें
linktitle: जावा एक्सपीएस में अपारदर्शिता मास्क सेट करें
second_title: Aspose.Page जावा एपीआई
description: Aspose.Page के साथ Java XPS में अपारदर्शिता मास्क सेट करने की शक्ति की खोज करें। दृश्यात्मक रूप से उन्नत दस्तावेज़ अनुभव के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 11
url: /hi/java/xps-transparency/set-opacity-mask/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा एक्सपीएस में अपारदर्शिता मास्क सेट करें

## परिचय
Aspose.Page का उपयोग करके जावा XPS में अपारदर्शिता मास्क सेट करने पर हमारी व्यापक मार्गदर्शिका में आपका स्वागत है। इस ट्यूटोरियल में, हम आपको जावा के लिए Aspose.Page की शक्तिशाली सुविधाओं का उपयोग करके एक XPS दस्तावेज़ बनाने, एक कैनवास जोड़ने और एक आयत पर एक अपारदर्शिता मास्क लगाने की प्रक्रिया के बारे में बताएंगे।
## आवश्यक शर्तें
इस ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- जावा प्रोग्रामिंग की बुनियादी समझ।
-  जावा लाइब्रेरी के लिए Aspose.Page स्थापित किया गया। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/page/java/).
-  Aspose.Page के लिए एक वैध लाइसेंस। यदि आपके पास लाइसेंस नहीं है, तो आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
- जावा अनुप्रयोगों को चलाने के लिए एक विकास वातावरण स्थापित किया गया है।
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करके प्रारंभ करें। सुनिश्चित करें कि आपके पास Aspose.Page लाइब्रेरी ठीक से एकीकृत है। आपका मार्गदर्शन करने के लिए नीचे एक स्निपेट दिया गया है:
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
अब, आइए उदाहरण कोड को कई चरणों में विभाजित करें:
## चरण 1: एक नया XPS दस्तावेज़ बनाएँ
```java
// एक नया XPS दस्तावेज़ बनाएँ
XpsDocument doc = new XpsDocument();
```
## चरण 2: एक कैनवास जोड़ें
```java
// नया कैनवास
XpsCanvas canvas = doc.addCanvas();
```
## चरण 3: अपारदर्शिता मास्क के साथ एक आयत जोड़ें
```java
// बीच में बायीं ओर आयत, जिसमें अपारदर्शिता ImageBrush से ढकी हुई है
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## चरण 4: इमेजब्रश के साथ अपारदर्शिता मास्क सेट करें
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## चरण 5: परिणामी XPS दस्तावेज़ सहेजें
```java
// परिणामी XPS दस्तावेज़ सहेजें
doc.save(dataDir + "OpacityMask_out.xps"); 
```
Aspose.Page का उपयोग करके अपने Java XPS दस्तावेज़ में अपारदर्शिता मास्क शामिल करने के लिए इन चरणों का सावधानीपूर्वक पालन करें।
## निष्कर्ष
बधाई हो! आपने Aspose.Page के साथ Java XPS में अपारदर्शिता मास्क सेट करना सफलतापूर्वक सीख लिया है। यह सुविधा आपके दस्तावेज़ों में दृश्य समृद्धि की एक परत जोड़ती है, जिससे वे अधिक आकर्षक और गतिशील बन जाते हैं।
## पूछे जाने वाले प्रश्न
### क्या Aspose.Page सभी जावा विकास परिवेशों के साथ संगत है?
हां, Aspose.Page को विभिन्न जावा विकास परिवेशों के साथ निर्बाध रूप से काम करने के लिए डिज़ाइन किया गया है।
### क्या मैं Aspose.Page का उपयोग बिना लाइसेंस के कर सकता हूँ?
हालाँकि आप Aspose.Page का उपयोग बिना लाइसेंस के कर सकते हैं, लेकिन सुविधाओं और समर्थन की पूरी श्रृंखला के लिए इसे प्राप्त करने की अनुशंसा की जाती है।
### क्या परीक्षण संस्करण पर कोई सीमाएँ हैं?
परीक्षण संस्करण में कुछ सुविधा सीमाएँ हो सकती हैं। विवरण के लिए दस्तावेज़ की जाँच करना उचित है।
### मैं Aspose.Page के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 आप विजिट कर सकते हैं[Aspose.पेज फोरम](https://forum.aspose.com/c/page/39) सामुदायिक सहायता के लिए या प्रीमियम सहायता के लिए लाइसेंस खरीदने के लिए।
### क्या Aspose.Page के लिए कोई मनी-बैक गारंटी है?
 को देखें[खरीद पृष्ठ](https://purchase.aspose.com/buy) धनवापसी नीतियों की जानकारी के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
