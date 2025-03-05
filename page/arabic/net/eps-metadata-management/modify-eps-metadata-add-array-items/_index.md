---
title: إضافة عناصر المصفوفة باستخدام Aspose.Page
linktitle: إضافة عناصر المصفوفة
second_title: Aspose.Page .NET API
description: اكتشف كيفية إضافة عناصر المصفوفة في ملفات EPS باستخدام Aspose.Page لـ .NET. اتبع دليلنا خطوة بخطوة للتعامل السلس مع المستندات.
type: docs
weight: 11
url: /ar/net/eps-metadata-management/modify-eps-metadata-add-array-items/
---
## مقدمة

في مجال معالجة المستندات ومعالجتها في .NET، تبرز Aspose.Page كأداة قوية. من بين إمكانياته العديدة، يعد التعامل مع عناصر المصفوفة داخل ملف EPS مطلبًا شائعًا. في هذا البرنامج التعليمي، سوف نستكشف عملية إضافة عناصر المصفوفة خطوة بخطوة باستخدام Aspose.Page في بيئة .NET. سواء كنت مطورًا متمرسًا أو وافدًا جديدًا، سيرشدك هذا الدليل خلال العملية بوضوح ودقة.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

- فهم أساسي لبرمجة .NET.
-  تم تثبيت Aspose.Page لـ .NET. إذا لم يكن الأمر كذلك، يمكنك تنزيله من[هنا](https://releases.aspose.com/page/net/).
- محرر التعليمات البرمجية، مثل Visual Studio، للمتابعة مع الأمثلة.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، تأكد من استيراد مساحات الأسماء الضرورية للاستفادة من وظائف Aspose.Page. أضف الأسطر التالية في بداية الكود الخاص بك:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

توفر مساحات الأسماء هذه إمكانية الوصول إلى الفئات والأساليب الأساسية المطلوبة لمعالجة ملف EPS.

## الخطوة 1: تهيئة دفق إدخال ملف EPS

```csharp
// البداية:3
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// تهيئة دفق إدخال ملف EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//قم بإنشاء مثيل PsDocument من الدفق
PsDocument document = new PsDocument(psStream);            
// النهاية:3
```

 هنا، نقوم بإعداد دفق الإدخال الأولي لملف EPS وإنشاء ملف`PsDocument` مثال.

## الخطوة 2: احصل على بيانات تعريف XMP

```csharp
// البداية:4
// احصل على بيانات تعريف XMP. إذا كان ملف EPS لا يحتوي على بيانات تعريف XMP، فسنحصل على ملف جديد مملوء بالقيم من تعليقات بيانات تعريف PS (%%Creator، %%CreateDate، %%Title، إلخ)
XmpMetadata xmp = document.GetXmpMetadata();
// النهاية:4
```

قم باسترجاع بيانات تعريف XMP من ملف EPS. إذا كان ملف EPS يفتقر إلى بيانات تعريف XMP، فسيتم إنشاء ملف جديد بقيم من تعليقات بيانات تعريف PS.

## الخطوة 3: تغيير قيم بيانات تعريف XMP

```csharp
// البداية:5
// تغيير قيم بيانات تعريف XMP

// أضف عنوانًا آخر. سيتم إضافته في نهاية المصفوفة بشكل افتراضي.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// أضف منشئًا آخر. سيتم إضافته في المصفوفة بواسطة فهرس (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// النهاية:5
```

قم بتعديل بيانات تعريف XMP عن طريق إضافة عناوين ومنشئين جدد إلى المصفوفة.

## الخطوة 4: احفظ ملف EPS مع بيانات تعريف XMP التي تم تغييرها

```csharp
// البداية:6
// احفظ ملف EPS مع بيانات تعريف XMP التي تم تغييرها

// إنشاء دفق الإخراج
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // حفظ ملف EPS
    document.Save(outPsStream);
}
// النهاية:6
```

وأخيرًا، احفظ ملف EPS ببيانات تعريف XMP المحدثة. سوف تنعكس التغييرات التي تم إجراؤها على عناصر الصفيف في ملف الإخراج.

## خاتمة

تعد إضافة عناصر المصفوفة باستخدام Aspose.Page في .NET عملية مباشرة، كما هو موضح في هذا البرنامج التعليمي. من خلال المتطلبات الأساسية الصحيحة والدليل خطوة بخطوة، يمكن للمطورين التعامل مع ملفات EPS بسلاسة، مما يضمن أن مستنداتهم تلبي متطلبات بيانات التعريف المحددة.

## الأسئلة الشائعة

### س1: هل Aspose.Page متوافق مع كافة بيئات .NET؟

ج1: نعم، تم تصميم Aspose.Page للعمل بسلاسة مع كافة بيئات .NET، مما يوفر وظائف متسقة عبر الأنظمة الأساسية.

### س2: هل يمكنني استخدام Aspose.Page مجانًا؟

 ج2: يقدم Aspose.Page إصدارًا تجريبيًا مجانيًا، مما يسمح للمستخدمين باستكشاف ميزاته. لمواصلة الاستخدام، يجب شراء ترخيص من[هنا](https://purchase.aspose.com/buy).

### س3: هل التراخيص المؤقتة متاحة لـ Aspose.Page؟

 ج3: نعم، يمكن الحصول على التراخيص المؤقتة من[هنا](https://purchase.aspose.com/temporary-license/) لاحتياجات المشروع على المدى القصير.

### س4: أين يمكنني العثور على الدعم المجتمعي لـ Aspose.Page؟

ج4: لإجراء مناقشات ودعم المجتمع، قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39).

### س5: ما هو الإصدار الأحدث من Aspose.Page لـ .NET؟

 ج5: للوصول إلى أحدث إصدار من Aspose.Page لـ .NET، راجع[توثيق](https://reference.aspose.com/page/net/).