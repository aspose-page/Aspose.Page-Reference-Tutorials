---
date: 2026-02-28
description: تعلم كيفية إنشاء مستند XPS باستخدام .NET وإضافة صورة باستخدام Aspose.Page
  لـ .NET. اتبع هذا الدليل خطوة بخطوة للحصول على تجربة تطوير سلسة.
linktitle: Add Image to XPS Document
second_title: Aspose.Page .NET API
title: إنشاء مستند XPS باستخدام .NET – إضافة صورة باستخدام Aspose.Page
url: /ar/net/image-management/add-image-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة صورة إلى مستند XPS باستخدام Aspose.Page لـ .NET

في هذا الدرس ستتعلم كيفية **create XPS document .NET** وإدراج صورة باستخدام مكتبة Aspose.Page القوية. سواءً كنت تولد تقارير أو فواتير أو رسومات مخصصة، فإن إضافة عناصر بصرية إلى ملفات XPS هو طلب شائع لمطوري .NET.

## المقدمة

في عالم تطوير .NET، دمج الصور في مستندات XPS هو طلب شائع. Aspose.Page لـ .NET يبسط هذه العملية، مقدماً مجموعة أدوات قوية للتلاعب وتحسين مستندات XPS بسهولة. سيوجهك هذا الدرس عبر خطوات إضافة صورة إلى مستند XPS باستخدام Aspose.Page لـ .NET.

## إجابات سريعة
- **ما الذي يغطيه هذا الدرس؟** إضافة صورة إلى مستند XPS باستخدام Aspose.Page لـ .NET.  
- **ما هي الكلمة المفتاحية الأساسية المستهدفة؟** *create xps document .net*  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية متاحة؛ الترخيص مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** يعمل مع .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.  
- **كم من الوقت تستغرق عملية التنفيذ؟** حوالي 5‑10 دقائق لإدراج صورة أساسي.

## ما هو “create XPS document .NET”؟
إنشاء مستند XPS في .NET يعني توليد ملف XML Paper Specification (XPS) برمجياً—وهو تنسيق مستند ثابت التخطيط—باستخدام C# أو VB.NET. توفر Aspose.Page API سلسة تُجرد التفاصيل منخفضة المستوى، مما يتيح لك التركيز على المحتوى مثل النصوص والأشكال والصور.

## لماذا تستخدم Aspose.Page لإضافة صورة؟
- **تحكم كامل** في تموضع الصور وتكبيرها واقتصاصها.  
- **بدون تبعيات خارجية** – المكتبة تتعامل مع فك تشفير الصورة داخلياً.  
- **دعم متعدد المنصات** لبيئات Windows و Linux.  
- **دقة عالية** في العرض تحافظ على جودة الصورة في ملف XPS النهائي.

## المتطلبات المسبقة

قبل الغوص في الدرس، تأكد من توفر المتطلبات التالية:

1. مكتبة Aspose.Page لـ .NET: قم بتحميل وتثبيت المكتبة من [Aspose.Page .NET Documentation](https://reference.aspose.com/page/net/).
2. بيئة التطوير: إعداد بيئة تطوير .NET، مثل Visual Studio.
3. صورة نموذجية: احصل على ملف صورة نموذجية (مثال: "QL_logo_color.tif") ترغب في إضافتها إلى مستند XPS.

## استيراد مساحات الأسماء

ابدأ باستيراد مساحات الأسماء الضرورية إلى مشروع .NET الخاص بك. هذه المساحات أساسية لاستخدام الميزات التي توفرها Aspose.Page لـ .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## إضافة صورة إلى مستند XPS باستخدام Aspose.Page

فيما يلي نستعرض كل خطوة مطلوبة لـ **create XPS document .NET** وإدراج صورة.

### الخطوة 1: تحديد دليل المستند

ابدأ بتحديد المسار إلى دليل المستندات الخاص بك. تضمن هذه الخطوة أن يعرف مشروعك مكان العثور على الملفات وحفظها.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

### الخطوة 2: إنشاء مستند XPS

أنشئ مستند XPS جديد باستخدام Aspose.Page لـ .NET.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

### الخطوة 3: إضافة صورة إلى مستند XPS

الآن، دعنا نضيف الصورة إلى مستند XPS. في هذا المثال، سنستخدم صورة نموذجية باسم "QL_logo_color.tif".

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

### الخطوة 4: حفظ مستند XPS الناتج

احفظ مستند XPS مع الصورة المضافة.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

الآن لقد أضفت صورة بنجاح إلى مستند XPS باستخدام Aspose.Page لـ .NET!

## المشكلات الشائعة والحلول

- **خطأ ملف غير موجود** – تحقق من أن `dataDir` يشير إلى المجلد الصحيح وأن اسم ملف الصورة يطابق تماماً، بما في ذلك حساسية الأحرف في Linux.
- **الصورة تظهر مشوهة** – اضبط عوامل التكبير في `CreateMatrix` أو معلمات `RectangleF` للتحكم في الحجم ونسبة الأبعاد.
- **تنسيق صورة غير مدعوم** – تدعم Aspose.Page تنسيقات الصور النقطية الشائعة (PNG, JPEG, TIFF). حوّل التنسيقات غير المدعومة قبل استخدام `CreateImageBrush`.

## الأسئلة المتكررة

### س1: هل Aspose.Page لـ .NET متوافق مع أحدث إصدارات إطار عمل .NET؟

A1: تم تصميم Aspose.Page لـ .NET لتكون متوافقة مع مجموعة واسعة من إصدارات إطار عمل .NET، بما في ذلك الإصدارات الأخيرة. راجع [documentation](https://reference.aspose.com/page/net/) للحصول على تفاصيل محددة.

### س2: هل يمكنني استخدام Aspose.Page لـ .NET في بيئات Windows و Linux معاً؟

A2: نعم، Aspose.Page لـ .NET مستقل عن المنصة، مما يجعله مناسباً للاستخدام في بيئات Windows و Linux.

### س3: هل هناك خيارات ترخيص لـ Aspose.Page لـ .NET؟

A3: نعم، يمكنك استكشاف خيارات الترخيص وإجراء الشراء [here](https://purchase.aspose.com/buy).

### س4: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page لـ .NET؟

A4: نعم، يمكنك تجربة Aspose.Page لـ .NET مجاناً عبر الوصول إلى [free trial](https://releases.aspose.com/).

### س5: أين يمكنني طلب المساعدة أو التفاعل مع المجتمع الخاص بـ Aspose.Page لـ .NET؟

A5: زر [Aspose.Page for .NET forum](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع والحصول على الدعم.

## الخاتمة

في هذا الدرس، استكشفنا كيفية الاستفادة من Aspose.Page لـ .NET لإدراج الصور بسلاسة في مستندات XPS. يضمن هذا الدليل خطوة بخطوة عملية دمج سلسة، مما يعزز قدرات تطوير .NET الخاصة بك ويساعدك على **create XPS document .NET** حلولاً بصرية غنية.

---

**آخر تحديث:** 2026-02-28  
**تم الاختبار مع:** Aspose.Page for .NET 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}