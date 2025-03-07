---
title: أضف تدرجًا رأسيًا إلى XPS باستخدام Aspose.Page لـ .NET
linktitle: أضف التدرج الرأسي إلى XPS
second_title: Aspose.Page .NET API
description: تعرف على كيفية تحسين مستندات XPS بالتدرجات الرأسية باستخدام Aspose.Page لـ .NET. اتبع دليلنا خطوة بخطوة للتكامل السلس.
weight: 15
url: /ar/net/gradient-fills/add-vertical-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# أضف تدرجًا رأسيًا إلى XPS باستخدام Aspose.Page لـ .NET

## مقدمة

مرحبًا بك في هذا البرنامج التعليمي خطوة بخطوة حول كيفية إضافة تدرج عمودي إلى مستند XPS باستخدام Aspose.Page لـ .NET. Aspose.Page عبارة عن واجهة برمجة تطبيقات قوية تسمح لك بالعمل مع ملفات XPS (مواصفات ورق XML) في تطبيقات .NET الخاصة بك. في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مستند XPS جديد وإضافة تدرج رأسي إلى المسار وحفظ النتيجة.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

-  Aspose.Page for .NET Library: تأكد من تثبيت Aspose.Page لمكتبة .NET في بيئة التطوير الخاصة بك. يمكنك تنزيله[هنا](https://releases.aspose.com/page/net/).

- بيئة التطوير: قم بإعداد بيئة تطوير .NET باستخدام IDE المفضل لديك، مثل Visual Studio.

الآن، لنبدأ بإضافة تدرج رأسي إلى مستند XPS باستخدام Aspose.Page لـ .NET.

## استيراد مساحات الأسماء

في تطبيق .NET الخاص بك، قم بتضمين مساحات الأسماء الضرورية للوصول إلى فئات Aspose.Page وأساليبه.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## الخطوة 1: قم بإعداد دليل المستندات الخاص بك

قبل أن تبدأ، قم بتعيين المسار إلى دليل المستند الخاص بك حيث تريد حفظ مستند XPS الناتج.

```csharp
// البداية:3
string dataDir = "Your Document Directory";
// النهاية:3
```

## الخطوة 2: إنشاء مستند XPS جديد

قم بتهيئة مستند XPS جديد باستخدام الكود التالي:

```csharp
// البداية:4
XpsDocument doc = new XpsDocument();
// النهاية:4
```

## الخطوة 3: تحديد توقفات التدرج

قم بإنشاء قائمة بتوقفات التدرج، مع تحديد اللون والموضع لكل توقف. في هذا المثال، نحدد تدرجًا رأسيًا بخمس نقاط توقف.

```csharp
// البداية:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// النهاية:5
```

## الخطوة 4: إنشاء مسار مع التدرج

حدد المسار من خلال تحديد هندسته وتطبيق فرشاة متدرجة خطية عليه.

```csharp
// البداية:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// النهاية:6
```

## الخطوة 5: احفظ مستند XPS الناتج

احفظ مستند XPS المعدل في الدليل المحدد.

```csharp
// البداية:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// النهاية:7
```

تهانينا! لقد نجحت في إضافة تدرج عمودي إلى مستند XPS باستخدام Aspose.Page لـ .NET.

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية الاستفادة من Aspose.Page لـ .NET لتحسين مستندات XPS بالتدرجات الرأسية. يعمل Aspose.Page على تبسيط المهام المعقدة، مما يوفر للمطورين طريقة سلسة لمعالجة ملفات XPS في تطبيقات .NET الخاصة بهم.

## الأسئلة الشائعة

### س1: هل Aspose.Page متوافق مع Visual Studio 2019؟

ج1: نعم، Aspose.Page متوافق مع Visual Studio 2019. تأكد من تثبيت الإصدار الصحيح من المكتبة.

### س2: هل يمكنني استخدام Aspose.Page للمشاريع التجارية؟

 ج٢: نعم، يمكن استخدام Aspose.Page للمشاريع التجارية. يزور[هنا](https://purchase.aspose.com/buy) لاستكشاف خيارات الترخيص.

### س3: هل هناك نسخة تجريبية مجانية متاحة؟

 ج3: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Page[هنا](https://releases.aspose.com/).

### س٤: أين يمكنني العثور على وثائق Aspose.Page؟

 ج4: الوثائق متاحة[هنا](https://reference.aspose.com/page/net/).

### س5: كيف يمكنني الحصول على الدعم أو طرح الأسئلة؟

 ج5: قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) لدعم المجتمع.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
