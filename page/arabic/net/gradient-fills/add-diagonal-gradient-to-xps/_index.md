---
title: أضف تدرجًا قطريًا إلى XPS باستخدام Aspose.Page لـ .NET
linktitle: إضافة التدرج القطري إلى XPS
second_title: Aspose.Page .NET API
description: تعرف على كيفية إضافة تدرجات قطرية جذابة إلى مستندات XPS باستخدام Aspose.Page لـ .NET. ارفع مستوى عروضك التقديمية المرئية دون عناء.
weight: 11
url: /ar/net/gradient-fills/add-diagonal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# أضف تدرجًا قطريًا إلى XPS باستخدام Aspose.Page لـ .NET

## مقدمة

في مجال معالجة المستندات، يبرز Aspose.Page for .NET كمجموعة أدوات قوية تمكن المطورين من التعامل مع مستندات XPS بسهولة. إحدى الميزات المثيرة التي تقدمها هي القدرة على إضافة تدرجات قطرية، مما يسمح لك بتعزيز المظهر المرئي لمستنداتك. سيرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة، ويوضح كيفية دمج التدرجات القطرية في ملفات XPS باستخدام Aspose.Page لـ .NET.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Page لمكتبة .NET: تأكد من تثبيت Aspose.Page لمكتبة .NET. إذا لم يكن الأمر كذلك، يمكنك تنزيله[هنا](https://releases.aspose.com/page/net/).

2. بيئة التطوير: قم بإعداد بيئة التطوير المفضلة لديك للعمل مع .NET.

الآن، لنبدأ بإضافة التدرجات القطرية إلى XPS باستخدام Aspose.Page لـ .NET.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، قم بتضمين مساحات الأسماء الضرورية من مكتبة Aspose.Page للوصول إلى الفئات والأساليب المطلوبة. أضف مساحات الأسماء التالية في بداية التعليمات البرمجية الخاصة بك:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## الخطوة 1: قم بتعيين دليل المستندات

ابدأ بتحديد المسار إلى دليل المستند الخاص بك. هذا هو المكان الذي سيتم فيه حفظ مستند XPS الناتج مع التدرج القطري.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء مستند XPS جديد

قم بتهيئة XpsDocument جديد باستخدام مكتبة Aspose.Page.

```csharp
XpsDocument doc = new XpsDocument();
```

## الخطوة 3: تحديد الألوان المتدرجة

قم بإنشاء قائمة بكائنات XpsGradientStop، يمثل كل منها لونًا في التدرج القطري.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... كرر للألوان الأخرى
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## الخطوة 4: إضافة تدرج قطري إلى المسار

قم بإنشاء مسار جديد بهندسة محددة، وقم بتطبيق التدرج القطري عليه. اضبط خصائص تحويل العرض والتعبئة حسب الحاجة.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## الخطوة 5: احفظ مستند XPS الناتج

وأخيرًا، احفظ مستند XPS المعدل في الدليل المحدد.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

لقد نجحت الآن في إضافة تدرج قطري إلى مستند XPS باستخدام Aspose.Page لـ .NET. قم بتجربة الألوان والأشكال الهندسية المختلفة لإنشاء تأثيرات بصرية مذهلة.

## خاتمة

يعمل Aspose.Page for .NET على تبسيط عملية تحسين مستندات XPS باستخدام التدرجات القطرية. يرشدك هذا البرنامج التعليمي عبر الخطوات، بدءًا من إعداد المتطلبات الأساسية وحتى حفظ المستند النهائي. استكشف المزيد من الإمكانيات وارفع مستوى عرض المستندات لديك.

## الأسئلة الشائعة

### س1: هل يمكنني تطبيق تدرجات متعددة على أجزاء مختلفة من المستند؟

A1: نعم، يمكنك إنشاء مسارات متعددة وتطبيق تدرجات مميزة على كل منها.

### س2: هل تتوفر أنماط متدرجة محددة مسبقًا؟

ج2: يسمح Aspose.Page بالتدرجات اللونية المخصصة، مما يمنحك التحكم الكامل في انتقالات الألوان.

### س3: هل يمكنني استخدام Aspose.Page لـ .NET مع تنسيقات المستندات الأخرى؟

A3: يركز Aspose.Page بشكل أساسي على معالجة مستندات XPS.

### س4: كيف يمكنني معالجة الأخطاء المتعلقة بمعالجة المستندات؟

 ج4: راجع[توثيق](https://reference.aspose.com/page/net/)لمعالجة الأخطاء أفضل الممارسات.

### س5: هل تتوفر نسخة تجريبية قبل الشراء؟

 ج5: نعم، يمكنك استكشاف[تجربة مجانية](https://releases.aspose.com/) لتجربة Aspose.Page لـ .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
