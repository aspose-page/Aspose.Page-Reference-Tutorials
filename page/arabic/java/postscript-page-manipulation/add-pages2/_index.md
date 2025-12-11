---
date: 2025-12-11
description: تعلم كيفية تعيين حجم صفحة مخصص وإضافة صفحات إلى مستندات Java PostScript
  باستخدام Aspose.Page. اتبع دليلنا خطوة بخطوة للتلاعب السلس بالمستندات.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: دروس Aspose.Page للغة Java – تعيين حجم صفحة مخصص أثناء إضافة صفحات في PostScript
url: /ar/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Tutorial – تعيين حجم صفحة مخصص أثناء إضافة صفحات في PostScript

## Introduction
في تطبيقات Java الحديثة، غالبًا ما يكون من الضروري **تعيين حجم صفحة مخصص** لإخراج PostScript — سواء كنت تولد فواتير، تذاكر، أو رسومات مخصصة. تجعل Aspose.Page for Java هذه المهمة سهلة. في هذا الدرس ستتعلم كيفية إضافة صفحات وتعيين أحجام صفحات مخصصة في مستند PostScript، خطوة بخطوة، حتى تتمكن من إنتاج التخطيط المناسب في كل مرة.

## Quick Answers
- **هل يمكنني تعيين أحجام صفحات مختلفة لكل صفحة؟** نعم، يمكنك فتح الصفحات بأبعاد مخصصة باستخدام `document.openPage(width, height)`.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يتطلب النشر غير التجريبي ترخيصًا صالحًا لـ Aspose.Page.  
- **ما إصدارات Java المدعومة؟** تعمل المكتبة مع Java 8 وما فوق.  
- **هل الـ API آمن للاستخدام المتعدد الخيوط؟** كائنات Document ليست آمنة للاستخدام المتعدد الخيوط؛ أنشئ `PsDocument` منفصل لكل خيط.  
- **ما الحد الأقصى لحجم ملف PostScript؟** تتعامل Aspose.Page بفعالية مع الملفات متعددة الميغابايت؛ استهلاك الذاكرة يتناسب مع المحتوى وليس عدد الصفحات.

## Prerequisites
قبل أن نبدأ، تأكد من وجود ما يلي:

- فهم أساسي لبرمجة Java.  
- إضافة Aspose.Page for Java إلى مشروعك (Maven/Gradle أو JAR يدوي).  
- بيئة تطوير Java (IDE، JDK 8+).  

## Import Packages
للبدء، استورد الفئات الضرورية من مكتبة Aspose.Page.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Create a Multipaged PostScript Document
الخطوة 1: إنشاء مستند PostScript متعدد الصفحات  
أولاً، أنشئ `PsDocument` جديدًا مconfigured للصفحات المتعددة. هذا يُعد تدفق الإخراج ويخبر المكتبة أننا سنعمل على ملف متعدد الصفحات.

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

## Step 2: Add Content to the First Page
الخطوة 2: إضافة محتوى إلى الصفحة الأولى  
مع جاهزية المستند، يمكنك إضافة أي محتوى تحتاجه إلى الصفحة الأولى. عند الانتهاء، أغلق الصفحة لتثبيت محتواها.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## How to set custom page size
كيفية تعيين حجم صفحة مخصص  
إذا لم يكن حجم الصفحة الافتراضي هو ما تحتاجه، يمكنك **تعيين حجم صفحة مخصص** عند فتح صفحة جديدة. هذا مفيد للإيصالات، الملصقات، أو أي تخطيط غير قياسي.

## Step 3: Add a Second Page with Different Size
الخطوة 3: إضافة صفحة ثانية بحجم مختلف  
فيما يلي نفتح صفحة ثانية ونحدد صراحةً عرضًا وارتفاعًا مخصصين (بالنقاط). هذا يوضح كيفية تعيين حجم صفحة مخصص للصفحات الفردية.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Step 4: Save the Document
الخطوة 4: حفظ المستند  
أخيرًا، احفظ التغييرات عن طريق حفظ المستند. جميع الصفحات — بما في ذلك تلك ذات الأحجام المخصصة — تُكتب إلى ملف الإخراج.

```java
// Save the document
document.save();
```

باتباع هذه الخطوات، يمكنك إضافة صفحات بسهولة و**تعيين أحجام صفحات مخصصة** في مستند PostScript Java باستخدام Aspose.Page، مما يمنحك التحكم الكامل في تخطيط كل صفحة.

## Conclusion
الخاتمة  
Aspose.Page for Java توفر API قوي وسهل الاستخدام للمطورين لمعالجة مستندات PostScript. الآن تعرف كيف تضيف صفحات متعددة، تطبق أبعاد مخصصة، وتحفظ النتيجة — مما يمكنك من إنشاء مخرجات مُنسقة بدقة لأي حل مبني على Java.

## Frequently Asked Questions
### هل يمكنني إضافة صفحات بأحجام مختلفة في مستند PostScript واحد؟
نعم، كما هو موضح في هذا الدرس، يمكنك إضافة صفحات بأحجام متفاوتة في مستند PostScript متعدد الصفحات.  
### هل هناك أي قيود على عدد الصفحات التي يمكنني إضافتها؟
تدعم Aspose.Page إضافة عدد غير محدود عمليًا من الصفحات إلى المستند.  
### هل يمكنني إضافة محتوى مخصص، مثل الصور أو الرسومات، إلى الصفحات؟
بالطبع! تسمح Aspose.Page بإضافة مجموعة واسعة من المحتوى، بما في ذلك النصوص، الصور، والعناصر الرسومية الأخرى.  
### هل Aspose.Page مناسبة للتعامل مع المستندات الكبيرة؟
نعم، تم تصميم Aspose.Page للتعامل بكفاءة مع المستندات الصغيرة والكبيرة على حد سواء.  
### أين يمكنني العثور على موارد إضافية ودعم لـ Aspose.Page؟
استكشف [توثيق Aspose.Page](https://reference.aspose.com/page/java/)، أو زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع.  

**Additional Q&A**

**س:** *ما صيغ الصور المدعومة عند الرسم على صفحة PostScript؟*  
**ج:** يمكنك تضمين صور PNG، JPEG، BMP، و GIF مباشرةً باستخدام API الرسم.  

**س:** *كيف يمكنني تغيير DPI الافتراضي للمستند؟*  
**ج:** قم بتعيين `PsSaveOptions.setResolution(int dpi)` قبل إنشاء `PsDocument`.  

**س:** *هل يمكنني تشفير ملف PostScript باستخدام كلمة مرور؟*  
**ج:** PostScript نفسه لا يدعم التشفير، ولكن يمكنك تغليف الإخراج في ملف PDF وتطبيق إعدادات الأمان إذا لزم الأمر.  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose