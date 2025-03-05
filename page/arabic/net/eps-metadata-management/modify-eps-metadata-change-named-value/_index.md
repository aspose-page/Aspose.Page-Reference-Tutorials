---
title: قم بتغيير القيمة المسماة باستخدام Aspose.Page لـ .NET
linktitle: تغيير القيمة المسماة
second_title: Aspose.Page .NET API
description: تعرف على كيفية تغيير القيم المسماة في ملفات EPS باستخدام Aspose.Page لـ .NET. قم بتخصيص بيانات تعريف XMP بسهولة لمعالجة المستندات المخصصة.
type: docs
weight: 16
url: /ar/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---
## مقدمة

في عالم معالجة المستندات، يبرز Aspose.Page for .NET كأداة قوية لمعالجة ملفات EPS. إحدى الوظائف الرئيسية التي تقدمها هي القدرة على تغيير القيم المسماة ضمن بيانات تعريف XMP. سيرشدك هذا البرنامج التعليمي خلال عملية تغيير قيمة مسماة باستخدام Aspose.Page لـ .NET، مما يمكّنك من تخصيص ملفات EPS الخاصة بك وفقًا لاحتياجاتك المحددة.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Page for .NET: تأكد من تثبيت مكتبة Aspose.Page for .NET. إذا لم يكن الأمر كذلك، يمكنك تنزيله[هنا](https://releases.aspose.com/page/net/).

- دليل المستندات: احصل على دليل مخصص لملفات EPS الخاصة بك حيث يمكنك إجراء تغييرات القيمة المسماة.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، تحتاج إلى استيراد مساحات الأسماء الضرورية للوصول إلى الوظائف التي يوفرها Aspose.Page. أضف مساحات الأسماء التالية إلى التعليمات البرمجية الخاصة بك:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

الآن، دعونا نقسم الكود إلى خطوات متعددة لفهم شامل:

## الخطوة 1: تهيئة دفق إدخال ملف EPS

```csharp
// البداية:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// النهاية:1
```

في هذه الخطوة، قمنا بإعداد دفق الإدخال لملف EPS الذي تريد تعديله. تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي لدليل المستندات الخاص بك.

## الخطوة 2: احصل على بيانات تعريف XMP

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

قم باسترجاع بيانات تعريف XMP الموجودة من ملف EPS. إذا كان ملف EPS لا يحتوي على بيانات تعريف XMP، فسيتم إنشاء ملف جديد بقيم من تعليقات بيانات تعريف PS.

## الخطوة 3: تغيير قيم بيانات تعريف XMP

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

نوضح هنا تغيير قيمتين مسماتين داخل بنية "xmpTPg:MaxPageSize". يمكنك تخصيص هذا وفقًا لمتطلباتك المحددة.

## الخطوة 4: احفظ ملف EPS مع بيانات تعريف XMP التي تم تغييرها

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

احفظ ملف EPS المعدل في دفق الإخراج. سيعكس الملف الآن التغييرات التي تم إجراؤها على بيانات تعريف XMP.

## خاتمة

من خلال هذا البرنامج التعليمي، تعلمت كيفية الاستفادة من Aspose.Page لـ .NET لتغيير القيم المسماة ضمن بيانات تعريف XMP في ملفات EPS. تفتح هذه الوظيفة عالمًا من الإمكانيات لتخصيص مستنداتك وتخصيصها لتلبية متطلبات محددة.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.Page لـ .NET مع تنسيقات المستندات الأخرى؟

A1: نعم، يدعم Aspose.Page تنسيقات المستندات المختلفة، بما في ذلك EPS وXPS وPDF.

### س2: هل هناك إصدار تجريبي متاح لـ Aspose.Page لـ .NET؟

 ج2: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).

### س3: أين يمكنني العثور على مزيد من الوثائق حول Aspose.Page لـ .NET؟

 ج3: راجع الوثائق[هنا](https://reference.aspose.com/page/net/).

### س٤: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟

 ج4: يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).

### س5: ما هي خيارات الدعم المتاحة لـ Aspose.Page لمستخدمي .NET؟

 ج5: قم بزيارة منتدى المجتمع[هنا](https://forum.aspose.com/c/page/39) للدعم والمناقشات.