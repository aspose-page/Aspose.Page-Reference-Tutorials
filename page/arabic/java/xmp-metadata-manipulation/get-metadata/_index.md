---
date: 2026-05-25
description: تعلم كيفية قراءة XMP باستخدام Aspose.Page مع Java. يوضح هذا الدليل خطوة
  بخطوة استخراج بيانات XMP الوصفية، معلومات المنشئ، الطوابع الزمنية، الصور المصغرة،
  والمزيد.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: كيفية قراءة بيانات XMP الوصفية باستخدام Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: قراءة XMP باستخدام Aspose.Page – دليل Java
url: /ar/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# احصل على البيانات الوصفية من XMP باستخدام Java

## كيف تقرأ XMP باستخدام Aspose.Page (Java)؟

قم بتحميل ملف EPS باستخدام `new Document("file.eps")` — تمثل فئة `Document` ملفًا تم تحميله. استدعِ `getXmpMetadata()`، التي تستخرج حزمة XMP، ثم استعلم عن كائن `XmpMetadata` المسترجع — واجهة شبيهة بالخريطة لخصائص XMP — لاسترجاع المفاتيح التي تحتاجها. كل هذا مطلوب لقراءة XMP باستخدام Aspose.Page. تقوم الواجهة البرمجية (API) بتجريد التحليل منخفض المستوى، لذا ستحصل على خريطة جاهزة للاستخدام للخصائص في سطرين فقط من الشيفرة.

مرحبًا بكم في دليلنا خطوة بخطوة الذي يوضح **كيفية قراءة بيانات XMP الوصفية** باستخدام Java ومكتبة Aspose.Page. XMP (منصة البيانات الوصفية القابلة للتوسيع) هي معيار واسع الانتشار لتضمين بيانات وصفية غنية داخل المستندات. بنهاية هذا الدليل، ستكون قادرًا على قراءة XMP لتنسيق المستند، واستخراج معلومات المُنشئ، والطوابع الزمنية، والصور المصغرة، وأكثر—مما يمكنك من بناء حلول تحليل مستندات أكثر ذكاءً.

## إجابات سريعة
- **ماذا يعني “قراءة XMP”؟** يعني استخراج حزمة XMP برمجيًا التي تخزن البيانات الوصفية داخل الملف.  
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (حمّلها من الصفحة الرسمية [هنا](https://releases.aspose.com/page/java/)).  
- **هل أحتاج إلى ترخيص؟** يلزم ترخيص مؤقت أو كامل للإنتاج؛ النسخة التجريبية المجانية تعمل للتقييم.  
- **ما نسخة Java المدعومة؟** Java 8 أو أعلى.  
- **هل يمكنني قراءة XMP من صيغ أخرى؟** نعم – تقوم Aspose.Page باستخراج XMP من EPS وPDF وJPEG وPNG وأكثر من 20 صيغة أخرى.

## المتطلبات المسبقة
قبل الغوص في الشيفرة، تأكد من وجود ما يلي:

- **مجموعة تطوير جافا (JDK)** – Java 8+ مثبتة ومُكوَّنة على جهازك.  
- **Aspose.Page for Java** – حمّل المكتبة من الموقع الرسمي [هنا](https://releases.aspose.com/page/java/).  
- ملف EPS يحتوي على بيانات XMP الوصفية (مثال: `xmp1.eps`).  

## استيراد الحزم
فئة `XmpMetadata` موجودة في مساحة الاسم `com.aspose.page.xmp`، بينما فئة `Document` في `com.aspose.page`. استوردهما لتتمكن من العمل مع ملف EPS وبياناته الوصفية.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## الخطوة 1: تهيئة تدفق ملف EPS الإدخالي
ابدأ بتحديد مسار دليل المستندات الخاص بك وتهيئة تدفق ملف EPS الإدخالي.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## الخطوة 2: الحصول على بيانات XMP الوصفية
كائن `XmpMetadata` هو كائن Aspose.Page الذي يحتفظ بحزمة XMP المستخرجة من المستند. احصل عليه باستخدام `document.getXmpMetadata()`. إذا كان الملف يفتقر إلى XMP، فإن الواجهة البرمجية (API) تُنشئ حزمة حد أدنى من تعليقات PostScript الموجودة.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## الخطوة 3: استخراج معلومات CreatorTool
المفتاح `CreatorTool` يقع تحت مساحة الاسم `xmp` ويسجل التطبيق الذي أنشأ الملف. تحقق من وجوده واطبع قيمته.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## الخطوة 4: استخراج معلومات CreateDate
يخزن `CreateDate` الطابع الزمني عندما تم إنشاء المستند أصلاً. استخدم نمط `containsKey`/`get` نفسه لقراءته.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## الخطوة 5: استرجاع عرض الصورة المصغرة
إذا كانت هناك صور مصغرة، فإن مصفوفة `xmp:Thumbnails` تحتوي على إدخال أو أكثر. كل إدخال يحتوي على `width` و`height` والبيانات الثنائية. المثال يستخرج عرض الصورة المصغرة الأولى.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## الخطوة 6: استخراج معلومات الصيغة
المفتاح `format` يخبرك بصيغة الملف الأصلية (مثال: “application/postscript”). هذا مفيد عندما تحتاج إلى تسجيل أو التحقق من أنواع المصدر.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## الخطوة 7: الحصول على DocumentID
`DocumentID` هو معرف فريد يُعيّن من قبل تطبيق المُنشئ. يمكن استخدامه لإزالة التكرارات في مكتبات الأصول الكبيرة.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## لماذا هذا مهم
يمكن لـ Aspose.Page قراءة XMP من **أكثر من 20** صيغة ملف وتُعالج المستندات حتى **500 ميغابايت** دون تحميل الملف بالكامل إلى الذاكرة، مما يمنحك وصولًا سريعًا ومنخفض التكلفة إلى البيانات الوصفية الأساسية. هذه القدرة حاسمة لأنابيب المعالجة الدفعية، وأنظمة إدارة الأصول الرقمية، وأي حل يعتمد على سمات المستند القابلة للبحث والقراءة آليًا.

## المشكلات الشائعة والنصائح
- **غياب XMP:** قد لا تحتوي بعض ملفات EPS على XMP. ستُنشئ استدعاء `getXmpMetadata()` مجموعة حد أدنى استنادًا إلى تعليقات PS الموجودة، لكنك لن تحصل على بيانات وصفية كاملة إلا إذا كانت مدمجة.  
- **مصفوفات الصور المصغرة:** يمكن للمفتاح `xmp:Thumbnails` أن يحتوي على عدة إدخالات. المثال يستخرج الأولى فقط؛ كرّر عبر المصفوفة إذا كنت بحاجة إلى جميع الصور المصغرة.  
- **الوعي بمساحات الأسماء:** مفاتيح XMP تستخدم مساحات أسماء (مثال: `xmp:`، `dc:`). تأكد من الإشارة إلى اسم المفتاح الدقيق؛ وإلا سيعيد `containsKey` قيمة false.  

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Page for Java مع لغات برمجة أخرى؟
نعم، تدعم Aspose.Page Java و .NET والعديد من اللغات الأخرى. راجع القائمة الكاملة في [التوثيق](https://reference.aspose.com/page/java/).

### هل تتوفر نسخة تجريبية مجانية لـ Aspose.Page for Java؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على الدعم لـ Aspose.Page for Java؟
قم بزيارة [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على مساعدة المجتمع والدعم الرسمي.

### كيف أحصل على ترخيص مؤقت لـ Aspose.Page for Java؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### هل هناك موارد إضافية لـ Aspose.Page for Java؟
استكشف [التوثيق](https://reference.aspose.com/page/java/) الكامل وحمّل المكتبة [هنا](https://releases.aspose.com/page/java/).

## أسئلة إضافية
**س: هل يعمل هذا النهج مع ملفات PDF التي تحتوي على XMP؟**  
ج: نعم، يمكن لـ Aspose.Page قراءة XMP من PDF وEPS والعديد من صيغ الصور.

**س: هل يمكنني تعديل بيانات XMP الوصفية بعد قراءتها؟**  
ج: بالطبع. كائن `XmpMetadata` قابل للتعديل؛ يمكنك إضافة أو تحديث أو إزالة المفاتيح ثم حفظ المستند.

**س: هل هناك طريقة لاستخراج جميع صور المصغرة، وليس الأبعاد فقط؟**  
ج: يمكنك استرجاع البيانات الثنائية من الخاصية `xmpGImg:data` لكل إدخال صورة مصغرة وكتابتها إلى ملف.

## الخلاصة
لقد أصبحت الآن متمكنًا من **كيفية قراءة بيانات XMP الوصفية** باستخدام Java و Aspose.Page. باتباع هذه الخطوات يمكنك استخراج أدوات الإنشاء، والطوابع الزمنية، والصور المصغرة، ومعلومات الصيغة، ومعرفات المستند — مما يمنحك نظرة شاملة على البيانات الوصفية المدمجة في ملفات EPS الخاصة بك. لا تتردد في تجربة مساحات أسماء XMP إضافية لاستخراج بيانات أكثر غنىً لتطبيقاتك.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

## دروس ذات صلة

- [دليل Aspose Page Java – إضافة بيانات XMP الوصفية إلى ملفات EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [دليل aspose.page xmp – إضافة مساحة اسم في XMP باستخدام Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [دليل aspose page xmp – تغيير القيمة المسماة في XMP باستخدام Java](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}