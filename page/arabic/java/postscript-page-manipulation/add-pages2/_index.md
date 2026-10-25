---
date: 2026-10-25
description: تعلم كيفية تعيين حجم صفحة مخصص وإضافة صفحات إلى مستندات Java PostScript
  باستخدام Aspose.Page. اتبع دليلنا خطوة بخطوة لتعديل المستندات بسلاسة.
keywords:
- set custom page size
- Aspose.Page Java
- PostScript page manipulation
- add pages PostScript
lastmod: 2026-10-25
linktitle: إضافة صفحات في PostScript
og_description: تعلم كيفية تعيين حجم صفحة مخصص في PostScript باستخدام Aspose.Page
  للـ Java. اتبع تعليمات خطوة بخطوة لإضافة الصفحات، وتحديد الأبعاد، وحفظ المستند بكفاءة.
og_image_alt: Aspose.Page Java tutorial showing how to set custom page size in a PostScript
  document
og_title: تعيين حجم صفحة مخصص في PostScript باستخدام Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to set custom page size and add pages to Java PostScript
    documents using Aspose.Page. Follow our step‑by‑step guide for seamless document
    manipulation.
  headline: Aspose.Page Java Tutorial – set custom page size while Adding Pages in
    PostScript
  type: TechArticle
- questions:
  - answer: Yes—you can open pages with custom dimensions using `document.openPage(width,
      height)`.
    question: Can I set different page sizes for each page?
  - answer: A valid Aspose.Page license is required for non‑evaluation deployments.
    question: Do I need a license for production use?
  - answer: The library works with Java 8 and newer.
    question: Which Java versions are supported?
  - answer: Document instances are not thread‑safe; create a separate `PsDocument`
      per thread.
    question: Is the API thread‑safe?
  - answer: Aspose.Page handles multi‑megabyte files efficiently; memory usage scales
      with content, not page count.
    question: How large can a PostScript file be?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java PostScript
- custom page size
- add pages
- document generation
title: دروس Aspose.Page Java – تعيين حجم صفحة مخصص أثناء إضافة صفحات في PostScript
url: /ar/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# دليل Aspose.Page Java – ضبط حجم الصفحة المخصص أثناء إضافة الصفحات في PostScript

## مقدمة
في تطبيقات Java الحديثة، غالبًا ما يكون **set custom page size** لإخراج PostScript مطلوبًا — سواءً كنت تولد فواتير أو تذاكر أو رسومات مخصصة. يوضح هذا الدليل كيفية ضبط حجم الصفحة المخصص لكل صفحة، وإضافة صفحات متعددة، وإنشاء ملف PostScript يتطابق مع احتياجات التخطيط الدقيقة الخاصة بك. ستحصل على مثال كامل وقابل للتنفيذ يمكنك إدراجه في أي مشروع Java 8+.

## إجابات سريعة
- **Can I set different page sizes for each page?** نعم—يمكنك فتح الصفحات بأبعاد مخصصة باستخدام `document.openPage(width, height)`.  
- **Do I need a license for production use?** يلزم وجود ترخيص Aspose.Page صالح للاستخدام في بيئات الإنتاج غير التجريبية.  
- **Which Java versions are supported?** المكتبة تعمل مع Java 8 والإصدارات الأحدث.  
- **Is the API thread‑safe?** كائنات Document غير آمنة للاستخدام المتعدد الخيوط؛ أنشئ `PsDocument` منفصل لكل خيط.  
- **How large can a PostScript file be?** Aspose.Page يتعامل مع ملفات متعددة الميجابايت بكفاءة؛ استهلاك الذاكرة يتناسب مع المحتوى وليس عدد الصفحات.  
- **Can I use the open page width/height overload?** بالتأكيد—`openPage(double width, double height)` يتيح لك تحديد أي أبعاد بالنقاط.  

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن لديك:

- فهم أساسي لبرمجة Java.  
- إضافة Aspose.Page for Java إلى مشروعك (Maven/Gradle أو JAR يدوي).  
- بيئة تطوير Java (IDE، JDK 8+).  

## استيراد الحزم
الفئات التالية مطلوبة: `FileOutputStream` لكتابة الملفات، `PsDocument` لإنشاء مستندات PostScript، و`PsSaveOptions` لتكوين خيارات الإخراج.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## الخطوة 1: إنشاء مستند PostScript متعدد الصفحات
`PsDocument` هي الفئة الأساسية التي تمثل مستند PostScript يمكنه احتواء صفحات متعددة.

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

## الخطوة 2: إضافة محتوى إلى الصفحة الأولى
مع جاهزية المستند، يمكنك إضافة أي محتوى تحتاجه إلى الصفحة الأولى. عند الانتهاء، أغلق الصفحة لتثبيت محتواها.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## كيفية ضبط حجم الصفحة المخصص
يمكنك ضبط حجم صفحة مخصص عن طريق استدعاء `document.openPage(width, height)` بالأبعاد المطلوبة بالنقاط قبل رسم أي محتوى. تقوم `openPage(width, height)` بفتح صفحة جديدة بالعرض والارتفاع المحددين، مما يمنحك التحكم الكامل في مساحة الصفحة. إذا لم يكن حجم الصفحة الافتراضي هو ما تحتاجه، يمكنك **set a custom page size** عند فتح صفحة جديدة. هذا مفيد للإيصالات، الملصقات، أو أي تخطيط غير قياسي.

## الخطوة 3: إضافة صفحة ثانية بحجم مختلف
في الأسفل نفتح صفحة ثانية ونحدد صراحةً عرضًا وارتفاعًا مخصصين (بالنقاط). يوضح هذا كيفية ضبط حجم صفحة مخصص للصفحات الفردية، مما يمنحك القدرة على العمل مع **different page sizes** داخل نفس المستند.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## الخطوة 4: حفظ المستند
أخيرًا، احفظ التغييرات عن طريق حفظ المستند. تُكتب جميع الصفحات — بما في ذلك تلك ذات الأحجام المخصصة — إلى ملف الإخراج.

```java
// Save the document
document.save();
```

باتباع هذه الخطوات، يمكنك إضافة الصفحات بسهولة و**set custom page size** في مستند PostScript بلغة Java باستخدام Aspose.Page، مما يمنحك التحكم الكامل في تخطيط كل صفحة.

## لماذا تستخدم Aspose.Page لضبط حجم الصفحة المخصص؟
توفر Aspose.Page تحكمًا دقيقًا في أبعاد الصفحة، مما يتيح لك تعريف أي عرض وارتفاع بالنقاط، دمج أحجام صفحات متعددة داخل مستند واحد، وبث المحتوى بكفاءة لتوليد PostScript عالي الأداء. هذا يجعلها مثالية للفواتير، التذاكر، ومعالجة الدفعات الكبيرة حيث يجب أن يبقى استهلاك الذاكرة منخفضًا.

تتيح لك Aspose.Page تعريف أبعاد الصفحة بدقة بالنقاط، دمج أحجام متعددة في ملف واحد، وبث المحتوى بكفاءة، مما يمنحك تحكمًا دقيقًا وأداءً عاليًا لتوليد PostScript.  
- **Precision:** تُعرّف الأبعاد بالنقاط، لذا تحصل على تحكم دقيق في عرض وارتفاع الصفحة.  
- **Flexibility:** دمج وتطابق **different page sizes** في ملف PostScript واحد.  
- **Performance:** تقوم المكتبة ببث المحتوى مباشرة إلى ملف الإخراج، وتتعامل مع ملفات تصل إلى 500 MB مع الحفاظ على استهلاك الذاكرة تحت 100 MB، مما يجعلها مناسبة لسيناريوهات **generate PostScript file** على نطاق واسع.  
- **Rich API:** تدعم أكثر من 30 بدائية رسومية، 10 صيغ صور، وعدد غير محدود من كائنات النص لكل صفحة — كل ذلك مع احترام الأبعاد المخصصة التي تحددها.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **Page dimensions appear swapped** | تذكر أن `openPage(width, height)` يتوقع العرض أولاً، ثم الارتفاع (كلاهما بالنقاط). |
| **Content overflows the page** | استخدم نظام إحداثيات `PsGraphics` لتحديد موضع العناصر داخل الحدود المخصصة، أو قم بتكبير الرسم. |
| **Out‑of‑memory errors on huge documents** | فعّل البث بكتابة مباشرة إلى `FileOutputStream` كما هو موضح، وتجنب تحميل صور كبيرة إلى الذاكرة دفعة واحدة. |

## الأسئلة المتكررة
### هل يمكنني إضافة صفحات بأحجام مختلفة في مستند PostScript واحد؟
نعم، كما هو موضح في هذا الدليل، يمكنك إضافة صفحات بأحجام مختلفة في مستند PostScript متعدد الصفحات.  

### هل هناك أي قيود على عدد الصفحات التي يمكنني إضافتها؟
يدعم Aspose.Page إضافة عدد غير محدود تقريبًا من الصفحات إلى المستند.  

### هل يمكنني إضافة محتوى مخصص، مثل الصور أو الرسومات، إلى الصفحات؟
بالتأكيد! يتيح لك Aspose.Page إضافة مجموعة واسعة من المحتويات، بما في ذلك النصوص، الصور، والعناصر الرسومية الأخرى.  

### هل Aspose.Page مناسبة للتعامل مع المستندات الكبيرة؟
نعم، تم تصميم Aspose.Page للتعامل بكفاءة مع المستندات الصغيرة والكبيرة على حد سواء.  

### أين يمكنني العثور على موارد إضافية ودعم لـ Aspose.Page؟
استكشف [وثائق Aspose.Page](https://reference.aspose.com/page/java/)، أو زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع.  

**أسئلة وإجابات إضافية**

**س:** *ما صيغ الصور المدعومة عند الرسم على صفحة PostScript؟*  
**ج:** يمكنك تضمين صور PNG، JPEG، BMP، وGIF مباشرةً باستخدام واجهة برمجة الرسم.  

**س:** *كيف يمكنني تغيير DPI الافتراضي للمستند؟*  
**ج:** اضبط `PsSaveOptions.setResolution(int dpi)` قبل إنشاء `PsDocument`.  

**س:** *هل يمكنني تشفير ملف PostScript بكلمة مرور؟*  
**ج:** لا يدعم PostScript التشفير نفسه، ولكن يمكنك تغليف المخرجات في ملف PDF وتطبيق إعدادات الأمان إذا لزم الأمر.

---  
**آخر تحديث:** 2026-10-25  
**تم الاختبار مع:** Aspose.Page for Java 24.10  
**المؤلف:** Aspose  

## دروس ذات صلة

- [كيفية ضبط حجم صفحة A4 وإنشاء PostScript في Java باستخدام Aspose.Page](/page/java/document-creation/postscript/)
- [كيفية تحويل PostScript إلى PDF باستخدام Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [كيفية رسم مستطيل في PostScript Java باستخدام Aspose.Page](/page/java/postscript-shapes/add-rectangle/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}