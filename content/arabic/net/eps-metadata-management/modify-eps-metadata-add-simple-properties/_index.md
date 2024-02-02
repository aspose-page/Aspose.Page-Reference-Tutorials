---
title: أضف خصائص بسيطة باستخدام Aspose.Page لـ .NET
linktitle: إضافة خصائص بسيطة
second_title: Aspose.Page .NET API
description: قم بتحسين ملفات EPS باستخدام Aspose.Page لـ .NET. أضف خصائص بسيطة بسهولة لبيانات تعريف المستند المخصصة.
type: docs
weight: 14
url: /ar/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---
## مقدمة

في مجال معالجة المستندات وتحسينها، يظهر Aspose.Page for .NET كأداة قوية توفر للمطورين القدرة على إضافة بيانات تعريف XMP وتعديلها داخل ملفات EPS بسلاسة. سيرشدك هذا البرنامج التعليمي خلال عملية إضافة خصائص بسيطة إلى ملف EPS باستخدام Aspose.Page لـ .NET.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Page for .NET: تأكد من تثبيت Aspose.Page for .NET في بيئة التطوير الخاصة بك. إذا لم يكن الأمر كذلك، يمكنك تنزيله[هنا](https://releases.aspose.com/page/net/).

2.  دليل المستندات: قم بإعداد دليل لتخزين ملفات EPS الخاصة بك. تحديث`dataDir` متغير في مقتطف التعليمات البرمجية المقدم مع المسار إلى دليل المستند الخاص بك.

## استيراد مساحات الأسماء

للبدء، قم باستيراد مساحات الأسماء الضرورية لتمكين الاتصال بـ Aspose.Page لـ .NET. أضف الأسطر التالية في بداية ملف التعليمات البرمجية الخاص بك:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## الخطوة 1: تهيئة دفق إدخال ملف EPS

```csharp
// البداية:1
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// تهيئة دفق إدخال ملف EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//قم بإنشاء مثيل PsDocument من الدفق
PsDocument document = new PsDocument(psStream);
```

## الخطوة 2: احصل على بيانات تعريف XMP

```csharp
// احصل على بيانات تعريف XMP. إذا كان ملف EPS لا يحتوي على بيانات تعريف XMP، فسنحصل على ملف جديد مملوء بالقيم من تعليقات بيانات تعريف PS (%%Creator، %%CreateDate، %%Title، وما إلى ذلك)
XmpMetadata xmp = document.GetXmpMetadata();
```

## الخطوة 3: تغيير قيم بيانات تعريف XMP

```csharp
// تغيير قيم بيانات تعريف XMP
DateTime now = DateTime.UtcNow;

// إضافة خاصية عدد صحيح
xmp.Add("xmp:Intg1", new XmpValue(111));

// إضافة خاصية التاريخ والوقت
xmp.Add("xmp:Date1", new XmpValue(now));

// أضف خاصية مزدوجة
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//إضافة خاصية السلسلة
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## الخطوة 4: احفظ ملف EPS مع بيانات تعريف XMP التي تم تغييرها

```csharp
// احفظ ملف EPS مع بيانات تعريف XMP التي تم تغييرها

// إنشاء دفق الإخراج
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // حفظ ملف EPS
    document.Save(outPsStream);
}
```

## الخطوة 5: أغلق FileStream

```csharp
finally
{
    psStream.Close();
}
```

باتباع هذه الخطوات، يمكنك بسهولة دمج خصائص بسيطة في ملفات EPS الخاصة بك باستخدام Aspose.Page لـ .NET.

## خاتمة

في الختام، أثبت Aspose.Page for .NET أنه أصل لا يقدر بثمن للمطورين الذين يسعون إلى تحسين ملفات EPS باستخدام بيانات تعريف XMP المخصصة. ومن خلال إضافة خصائص بسيطة، يمكنك تخصيص مستنداتك وإثرائها لتلبية متطلبات محددة، مما يفتح عالمًا من الإمكانيات لمعالجة المستندات.

## الأسئلة الشائعة

### Q1: هل Aspose.Page for .NET متوافق مع كافة ملفات EPS؟

A1: يدعم Aspose.Page for .NET نطاقًا واسعًا من ملفات EPS. ومع ذلك، قد يختلف التوافق بناءً على مدى تعقيد الملفات الفردية وبنيتها.

### س٢: هل يمكنني تعديل بيانات تعريف XMP الموجودة باستخدام Aspose.Page لـ .NET؟

ج2: بالتأكيد! كما هو موضح في هذا البرنامج التعليمي، يمكنك بسهولة تغيير قيم بيانات تعريف XMP الحالية أو إضافة قيم جديدة لتناسب احتياجاتك.

### س3: هل هناك أي قيود على أنواع الخصائص التي يمكنني إضافتها؟

A3: يدعم Aspose.Page for .NET أنواع البيانات المختلفة للخصائص، بما في ذلك الأعداد الصحيحة والتواريخ والمضاعفات والسلاسل. لديك المرونة في اختيار النوع المناسب للبيانات التعريفية الخاصة بك.

### س 4: كيف يمكنني الحصول على الدعم الفني لـ Aspose.Page لـ .NET؟

 ج4: للحصول على المساعدة الفنية، قم بزيارة[Aspose.صفحة المنتدى](https://forum.aspose.com/c/page/39) أو استكشاف[توثيق](https://reference.aspose.com/page/net/) للحصول على إرشادات شاملة.

### س5: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page لـ .NET؟

 ج5: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).