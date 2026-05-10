---
date: 2026-03-16
description: تعلم كيفية قص صور EPS وتغيير حجم ملفات صور EPS في .NET باستخدام Aspose.Page.
  اتبع هذا الدليل خطوة بخطوة لقص EPS وتغيير حجم صورة EPS بسهولة.
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: كيفية قص صور EPS باستخدام Aspose.Page لـ .NET
url: /ar/net/image-manipulation/crop-eps-images/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قص صور EPS باستخدام Aspose.Page لـ .NET

## المقدمة

إذا كنت بحاجة إلى معرفة **كيفية قص EPS** في تطبيق .NET، فقد وصلت إلى المكان الصحيح. في هذا الدرس سنرشدك خطوة بخطوة إلى قص وإعادة تحجيم ملفات EPS باستخدام مكتبة Aspose.Page القوية لـ .NET. سواءً كنت تُحسّن أداة تقارير أو تُعدّ رسومات لخدمة ويب، فإن إتقان هذه التقنية سيوفر لك الوقت ويعطيك نتائج دقيقة إلى البكسل.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع قص EPS؟** Aspose.Page لـ .NET  
- **الطريقة الأساسية؟** `doc.CropEps(outputStream, newBoundingBox)`  
- **هل يمكنني أيضًا إعادة تحجيم EPS؟** نعم – استخدم `ResizeEps` بالبوصة أو المليمتر أو النسب المئوية.  
- **المتطلبات المسبقة؟** .NET (Framework 4.5+ / .NET Core 3.1+)، تثبيت Aspose.Page، ملف EPS.  
- **الوقت التقريبي للتنفيذ؟** حوالي 10 دقائق لتدفق عمل قص‑و‑تحجيم أساسي.

## المتطلبات المسبقة

قبل الغوص في الشيفرة، تأكد من وجود ما يلي:

- معرفة عملية بتطوير .NET.  
- مكتبة Aspose.Page لـ .NET مثبتة. إذا لم تكن مثبتة، يمكنك تحميلها [هنا](https://releases.aspose.com/page/net/).  
- صورة EPS نموذجية (استبدل `"input.eps"` في الشيفرة بالملف الفعلي لديك).

## استيراد مساحات الأسماء

لنبدأ باستيراد مساحات الأسماء التي تمنحنا الوصول إلى فئات معالجة EPS.

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## كيفية قص صور EPS – دليل خطوة بخطوة

### الخطوة 1: تهيئة `PsDocument`

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

ننشئ كائن `PsDocument` من تدفق EPS الإدخالي. هذا الكائن يمثل ملف EPS في الذاكرة ويمنحنا الوصول إلى طرق القص وإعادة التحجيم.

### الخطوة 2: استخراج صندوق الحدود الأصلي

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

صندوق الحدود يُظهر الأبعاد الحالية للوحة EPS. معرفة هذه القيم تساعدك على تعريف مستطيل قص آمن.

### الخطوة 3: إنشاء تدفق إخراج

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

نفتح تدفقًا قابلًا للكتابة حيث سيتم حفظ EPS المقصوص. استخدام كتلة `using` يضمن إغلاق التدفق بشكل صحيح.

### الخطوة 4: تعريف صندوق حدود جديد

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

استبدل الأرقام بالإحداثيات التي تريد الاحتفاظ بها. تأكد من أن القيم الجديدة تبقى داخل صندوق الحدود الأصلي؛ وإلا سيفشل العملية.

### الخطوة 5: قص وحفظ EPS

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

هذا السطر الواحد يُجري عملية القص ويكتب النتيجة إلى `output_crop.eps`. الطريقة تُعدِّل المستند في الذاكرة، لذا يمكنك ربط عمليات إضافية إذا لزم الأمر.

## تغيير حجم صورة EPS

بعد القص، غالبًا ما ترغب في تعديل حجم EPS للعرض أو الطباعة. تدعم Aspose.Page ثلاث وحدات قياس.

### تغيير الحجم بالبوصة

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### تغيير الحجم بالمليمتر

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### تغيير الحجم بالنسبة المئوية

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

كل استدعاء يكتب فوق الناتج السابق، لذا احرص على إنشاء تدفق جديد إذا كنت تحتاج ملفات منفصلة لكل حجم.

## المشكلات الشائعة & استكشاف الأخطاء وإصلاحها

| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| **قيم صندوق الحدود خارج النطاق** | الصندوق الجديد يتجاوز أبعاد الأصل | تحقق من قيم `initialBoundingBox` واختر إحداثيات داخل هذا النطاق. |
| **ملف الإخراج فارغ** | تدفق الإخراج لم يتم تفريغه أو إغلاقه | تأكد من إكمال كتلة `using` قبل الوصول إلى الملف، أو استدعِ `outputEpsStream.Flush()`. |
| **تحجيم غير متوقع** | خلط الوحدات (مثل البوصة مقابل المليمتر) | دائمًا حدد تعداد `Units` الصحيح الذي يتطابق مع قيم الحجم الخاصة بك. |

## الأسئلة المتكررة

### س1: هل يمكنني استخدام Aspose.Page لـ .NET مع صيغ صور أخرى؟

ج1: يركز Aspose.Page أساسًا على صور EPS، لكن Aspose توفر مكتبات متعددة لصيغ مختلفة. راجع وثائقهم للعثور على الصيغ المحددة.

### س2: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟

ج2: زر [هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت للاختبار.

### س3: هل هناك أي قيود على حجم الصورة التي يمكنني معالجتها باستخدام Aspose.Page لـ .NET؟

ج3: صُممت Aspose.Page للتعامل مع صور بأحجام مختلفة. ومع ذلك، قد تختلف الأداء بناءً على تعقيد الصورة.

### س4: هل هناك منتدى مجتمع لمناقشات Aspose.Page؟

ج4: نعم، يمكنك التفاعل مع مجتمع Aspose.Page [هنا](https://forum.aspose.com/c/page/39).

### س5: أين يمكنني العثور على وثائق مفصلة لـ Aspose.Page لـ .NET؟

ج5: راجع الوثائق [هنا](https://reference.aspose.com/page/net/).

---

**آخر تحديث:** 2026-03-16  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}