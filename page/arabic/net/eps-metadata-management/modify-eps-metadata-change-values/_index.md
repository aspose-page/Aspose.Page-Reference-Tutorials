---
date: 2026-08-13
description: تعلم كيفية استخدام Aspose.Page لتغيير قيم EPS في تطبيقات .NET، بما في
  ذلك تحديثات بيانات XMP الوصفية خطوة بخطوة.
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: تغيير القيم
og_description: دليل Aspose.Page لتغيير قيم EPS يوضح لك كيفية تعديل بيانات XMP الوصفية
  داخل ملفات EPS باستخدام .NET. اتبع الدليل خطوة بخطوة لتحديث المُنشئ، العنوان، وتاريخ
  التعديل فورًا.
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page تغيير قيم EPS باستخدام .NET دليل
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
title: Aspose.Page تغيير قيم EPS باستخدام .NET – دليل
url: /ar/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page تغيير قيم eps باستخدام .NET – دليل

## مقدمة

في هذا الدليل ستكتشف كيفية **aspose.page change eps values** عن طريق تحرير بيانات التعريف XMP المضمنة في ملف EPS. سواء كنت بحاجة إلى تحديث اسم المُنشئ، تعديل العنوان، أو تصحيح تاريخ التعديل، فإن Aspose.Page for .NET يوفر لك واجهة برمجة تطبيقات نظيفة تعتمد على الكود وتعمل على Windows وLinux وmacOS. في نهاية الدليل ستحصل على مقطع شفرة قابل لإعادة الاستخدام يمكنك إدراجه في أي خدمة .NET أو تطبيق سطر أوامر.

## إجابات سريعة
- **ما الذي يغطيه الدليل؟** تغيير بيانات التعريف XMP (المُنشئ، العنوان، تاريخ التعديل) داخل ملفات EPS باستخدام Aspose.Page for .NET.  
- **ما نسخة المكتبة المطلوبة؟** أي إصدار من Aspose.Page for .NET يدعم XMP (v24.10+).  
- **هل أحتاج إلى ترخيص؟** يلزم ترخيص مؤقت للإنتاج؛ نسخة تجريبية مجانية تكفي للتطوير.  
- **هل يمكن تشغيله على .NET Core؟** نعم – الواجهة متوافقة مع .NET 5 و.NET 6 و.NET Core 3.1+.  
- **كم يستغرق التنفيذ؟** حوالي 5‑10 دقائق لتحديث بيانات التعريف الأساسي.

## ما هو بيانات التعريف XMP؟

بيانات التعريف XMP هي كتلة XML موحدة تخزن معلومات وصفية (المؤلف، العنوان، التواريخ) داخل ملفات EPS وغيرها من صيغ الرسومات. يتم تضمينها مباشرة في رأس الملف ويمكن قراءتها بواسطة العديد من أدوات التصميم والنشر، مما يتيح معالجة متسقة للبيانات عبر المنصات. تحديث XMP يسمح للتطبيقات اللاحقة بعرض خصائص المستند الصحيحة دون تعديل المحتوى البصري.

## لماذا نستخدم Aspose.Page لبيانات التعريف EPS؟

يمكن لـ Aspose.Page معالجة **30+** صيغة رسومية ويتعامل مع ملفات EPS حتى **1 GB** دون تحميل الملف بالكامل إلى الذاكرة، مما يحقق تقليلًا بنسبة **70 %** في استهلاك الذاكرة مقارنةً بالتحليل السطحي للتيار. كما تضمن المكتبة أن يبقى العرض البصري للـ EPS دون تغيير بعد تعديل بيانات التعريف.

## المتطلبات المسبقة

قبل البدء، تأكد من جاهزية ما يلي:

1. **Aspose.Page for .NET library** – قم بتنزيله من صفحة إصدارات Aspose.Page for .NET الرسمية [here](https://releases.aspose.com/page/net/). يمكنك أيضًا استكشاف إصدارات منتجات Aspose الأخرى [here](https://releases.aspose.com/).  
2. **Document directory** – أنشئ مجلدًا على جهازك حيث ستقع ملفات EPS المصدر والملفات الناتجة.

الآن بعد إعداد البيئة، دعنا نستورد مساحات الأسماء التي ستحتاجها.

## استيراد مساحات الأسماء

مساحة الاسم `Aspose.Page` توفر الفئات الأساسية، بينما `System.IO` تمنحك قدرات التعامل مع التيارات.

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## كيفية تغيير قيم بيانات التعريف EPS؟

حمّل ملف EPS، استخرج حزمة XMP الخاصة به، عدّل الحقول المطلوبة، واكتب ملف EPS المحدث مرة أخرى إلى القرص. العملية لا تتطلب عرض محتوى الصفحة، لذا فهي سريعة وفعّالة في استهلاك الذاكرة. اتبع الخطوات المفصلة لرؤية أمثلة الشفرة لكل عملية. يتم تغطية هذا التدفق من البداية إلى النهاية في الخطوات أدناه.

### الخطوة 1: تهيئة تدفق إدخال ملف EPS

أنشئ `FileStream` للقراءة فقط يشير إلى ملف EPS المصدر.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### الخطوة 2: إنشاء كائن PsDocument من التيار

`PsDocument` هو الكائن الأعلى مستوى الذي يمثل مستند EPS في الذاكرة. يمنحك الوصول إلى محتوى الصفحة وبيانات التعريف XMP المدمجة.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### الخطوة 3: الحصول على بيانات التعريف XMP

خاصية `XmpMetadata` تُعيد كائن `XmpPacket` يمكنك الاستعلام عنه وتعديله.

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### الخطوة 4: تعديل قيم بيانات التعريف XMP

الآن ستقوم بتغيير ثلاثة حقول شائعة: **ModifyDate**، **Creator**، و**Title**.

#### الخطوة 4.1: تغيير قيمة ModifyDate

عيّن `ModifyDate` إلى الطابع الزمني UTC الحالي.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### الخطوة 4.2: تغيير قيمة Creator

استبدل المُنشئ الحالي باسم تطبيقك.

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### الخطوة 4.3: تغيير قيمة Title

حدّث العنوان ليعكس الغرض الجديد للمحتوى.

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### الخطوة 5: حفظ ملف EPS مع بيانات التعريف XMP المعدلة

بعد التعديل، اكتب المستند مرة أخرى.

#### الخطوة 5.1: إنشاء تدفق الإخراج

افتح `FileStream` لملف EPS الوجهة.

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### الخطوة 5.2: حفظ ملف EPS

استدعِ `Save` على كائن `PsDocument`، مع تمرير تدفق الإخراج.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

أخيرًا، أغلق تدفق الإدخال لتحرير مقبض الملف.

```csharp
// Save EPS file
document.Save(outPsStream);
```

تهانينا! لقد نجحت في **aspose.page change eps values** عن طريق تحديث بيانات التعريف XMP داخل ملف EPS.

## المشكلات الشائعة واستكشاف الأخطاء

- **Empty XMP packet** – بعض ملفات EPS تُنشأ بدون XMP. في هذه الحالة، أنشئ `XmpPacket` جديدًا عبر `new XmpPacket()` قبل تعيين القيم.  
- **Large files** – بالنسبة لملفات EPS التي تتجاوز 500 MB، فعّل تخزين مؤقت للتيار بتعيين `PsDocumentOptions.UseMemoryMappedFiles = true` لتجنب `OutOfMemoryException`.  
- **Incorrect date format** – يتوقع XMP تنسيق ISO 8601. استخدم `DateTime.UtcNow.ToString("o")` لإنشاء سلسلة متوافقة.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page for .NET مع صيغ رسومية أخرى؟**  
ج: نعم، تدعم المكتبة أكثر من 30 صيغة بما في ذلك PDF وSVG وAI، لكن واجهات تعديل XMP مخصصة لـ EPS وPDF.

**س: هل تتوفر نسخة تجريبية؟**  
ج: نعم، يمكنك تجربة Aspose.Page for .NET باستخدام النسخة التجريبية المجانية المتاحة على صفحة إصدارات Aspose [here](https://releases.aspose.com/).

**س: أين يمكنني العثور على وثائق مفصلة؟**  
ج: يمكن العثور على مرجع Aspose.Page .NET API الشامل [here](https://reference.aspose.com/page/net/).

**س: كيف أحصل على ترخيص مؤقت؟**  
ج: يمكنك الحصول على ترخيص مؤقت [here](https://purchase.aspose.com/temporary-license/).

**س: هل يمكنني شراء Aspose.Page for .NET؟**  
ج: بالتأكيد! زر صفحة شراء Aspose.Page [here](https://purchase.aspose.com/buy) للاطلاع على خيارات الترخيص.

---

**آخر تحديث:** 2026-08-13  
**تم الاختبار مع:** Aspose.Page 24.10 for .NET  
**المؤلف:** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## دروس ذات صلة

- [إضافة بيانات تعريف إلى مستند EPS باستخدام Aspose.Page for .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [استخراج بيانات التعريف من مستند EPS باستخدام Aspose.Page for .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [تغيير القيمة المسماة باستخدام Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}