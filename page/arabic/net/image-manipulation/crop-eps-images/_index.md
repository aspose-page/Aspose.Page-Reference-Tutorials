---
title: قص صور EPS باستخدام Aspose.Page لـ .NET
linktitle: قص صور EPS
second_title: Aspose.Page .NET API
description: استكشف العالم السلس لمعالجة صور EPS في .NET باستخدام Aspose.Page. قم بقص الصور وتغيير حجمها بسهولة للحصول على نتائج مذهلة.
weight: 10
url: /ar/net/image-manipulation/crop-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قص صور EPS باستخدام Aspose.Page لـ .NET

## مقدمة

هل تواجه صعوبة في التعامل مع صور EPS في تطبيقات .NET الخاصة بك؟ لا مزيد من البحث! في هذا البرنامج التعليمي، سنرشدك خلال عملية اقتصاص صور EPS باستخدام مكتبة Aspose.Page القوية لـ .NET. سواء كنت مطورًا متمرسًا أو بدأت للتو، سيساعدك هذا الدليل المفصّل خطوة بخطوة على تحقيق اقتصاص دقيق للصور دون عناء.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

- معرفة عملية بتطوير .NET.
-  تم تثبيت Aspose.Page لمكتبة .NET. إذا لم يكن الأمر كذلك، يمكنك تنزيله[هنا](https://releases.aspose.com/page/net/).
- نموذج لصورة EPS (استبدل "input.eps" في الكود بملفك الفعلي).

## استيراد مساحات الأسماء

فلنبدأ باستيراد مساحات الأسماء الضرورية لكي يعمل الكود الخاص بنا بسلاسة. 

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

الآن، دعونا نقسم البرنامج التعليمي إلى خطوات متعددة.

## الخطوة 1: تهيئة PsDocument

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

 تهيئة أ`PsDocument` كائن مع دفق EPS المدخلات.

## الخطوة 2: استخراج المربع المحيط

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

قم باسترجاع المربع المحيط الأولي لصورة EPS.

## الخطوة 3: إنشاء دفق الإخراج

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

قم بإنشاء دفق إخراج لصورة EPS التي تم اقتصاصها.

## الخطوة 4: تحديد المربع المحيط الجديد

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

تحديد مربع محيط جديد للاقتصاص. تأكد من أن القيم الجديدة موجودة داخل المربع المحيط الأولي.

## الخطوة 5: الاقتصاص والحفظ

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

قم بقص صورة EPS باستخدام المربع المحيط الجديد واحفظها في دفق الإخراج.

كرر هذه الخطوات لسيناريوهات تغيير الحجم المختلفة.

## تغيير حجم صور EPS

### تغيير الحجم بالبوصة

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

قم بتغيير حجم صورة EPS وحفظها بالأبعاد المحددة بالبوصة.

### تغيير الحجم بالملليمتر

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

قم بتغيير حجم صورة EPS وحفظها بالأبعاد المحددة بالملليمتر.

### تغيير الحجم في النسب المئوية

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

قم بتغيير حجم صورة EPS وحفظها بالأبعاد المحددة بالنسب المئوية.

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية اقتصاص صور EPS وتغيير حجمها باستخدام Aspose.Page لـ .NET. الآن، قم بتحسين قدرات معالجة الصور الخاصة بك والارتقاء بتطبيقات .NET الخاصة بك إلى المستوى التالي.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.Page لـ .NET مع تنسيقات الصور الأخرى؟

A1: يركز Aspose.Page بشكل أساسي على صور EPS، لكن Aspose يوفر مكتبات متنوعة لتنسيقات مختلفة. تحقق من وثائقهم لتنسيقات محددة.

### س2: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟

 ج2: زيارة[هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت للاختبار.

### س3: هل هناك أي قيود على حجم الصورة التي يمكنني معالجتها باستخدام Aspose.Page لـ .NET؟

A3: تم تصميم Aspose.Page للتعامل مع الصور ذات الأحجام المختلفة. ومع ذلك، قد يختلف الأداء بناءً على مدى تعقيد الصورة.

### س4: هل يوجد منتدى مجتمعي لمناقشات Aspose.Page؟

 ج4: نعم، يمكنك التفاعل مع مجتمع Aspose.Page[هنا](https://forum.aspose.com/c/page/39).

### س5: أين يمكنني العثور على الوثائق التفصيلية لـ Aspose.Page لـ .NET؟

 ج5: راجع الوثائق[هنا](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
