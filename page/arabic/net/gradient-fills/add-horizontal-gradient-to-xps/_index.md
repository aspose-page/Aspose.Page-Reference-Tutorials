---
title: أضف التدرج الأفقي إلى XPS باستخدام Aspose.Page لـ .NET
linktitle: أضف التدرج الأفقي إلى XPS
second_title: Aspose.Page .NET API
description: تعرف على كيفية إضافة تدرجات أفقية مذهلة إلى مستندات XPS الخاصة بك باستخدام Aspose.Page لـ .NET. رفع الجاذبية البصرية دون عناء.
weight: 13
url: /ar/net/gradient-fills/add-horizontal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# أضف التدرج الأفقي إلى XPS باستخدام Aspose.Page لـ .NET

## مقدمة

في هذا البرنامج التعليمي، سنستكشف كيفية تحسين مستندات XPS عن طريق إضافة تدرج أفقي باستخدام Aspose.Page لـ .NET. Aspose.Page for .NET هي مكتبة قوية توفر معالجة سلسة لمستندات XPS (مواصفات ورق XML) في تطبيقات .NET. يمكن أن تؤدي إضافة التدرجات إلى إضفاء جاذبية بصرية على مستنداتك، وسيرشدك هذا الدليل خلال العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Page for .NET Library: تأكد من تثبيت Aspose.Page لمكتبة .NET في بيئة التطوير الخاصة بك. يمكنك تنزيله من[Aspose.Page للتوثيق .NET](https://reference.aspose.com/page/net/).

2. بيئة التطوير: قم بإعداد بيئة تطوير مناسبة، بما في ذلك محرر التعليمات البرمجية مثل Visual Studio.

## استيراد مساحات الأسماء

ابدأ باستيراد مساحات الأسماء الضرورية إلى مشروعك. تعد مساحات الأسماء هذه ضرورية للعمل مع Aspose.Page لـ .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

الآن، دعونا نقسم المثال المقدم إلى خطوات متعددة.

## الخطوة 1: قم بتعيين مسار دليل المستندات

```csharp
// البداية:3
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// النهاية:3
```

## الخطوة 2: إنشاء مستند XPS جديد

```csharp
// البداية:4
// قم بإنشاء مستند XPS جديد
XpsDocument doc = new XpsDocument();
// النهاية:4
```

## الخطوة 3: تهيئة توقفات التدرج

```csharp
// البداية:5
// تهيئة قائمة XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// النهاية:5
```

## الخطوة 4: إنشاء مسار جديد

```csharp
// البداية:6
//قم بإنشاء مسار جديد عن طريق تعريف الهندسة في شكل مختصر
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// النهاية:6
```

## الخطوة 5: احفظ مستند XPS الناتج

```csharp
// البداية:7
// احفظ مستند XPS الناتج
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// النهاية:7
```

لقد نجحت الآن في إضافة تدرج أفقي إلى مستند XPS الخاص بك باستخدام Aspose.Page لـ .NET.

## خاتمة

لا يؤدي تحسين مستندات XPS الخاصة بك بالتدرجات إلى تحسين جاذبيتها المرئية فحسب، بل يوفر أيضًا تجربة مستخدم أكثر جاذبية. يعمل Aspose.Page for .NET على تبسيط هذه العملية، مما يسمح لك بتحقيق نتائج احترافية دون عناء.

## الأسئلة الشائعة

### س1: أين يمكنني العثور على Aspose.Page لوثائق .NET؟

 ج1: يمكنك العثور على الوثائق[هنا](https://reference.aspose.com/page/net/).

### س٢: كيف يمكنني تنزيل Aspose.Page لـ .NET؟

 ج2: يمكنك تنزيل المكتبة من[Aspose.Page لصفحة تنزيل .NET](https://releases.aspose.com/page/net/).

### س3: أين يمكنني شراء Aspose.Page لـ .NET؟

 ج3: يمكنك شراء Aspose.Page لـ .NET من[صفحة الشراء](https://purchase.aspose.com/buy).

### س4: هل هناك نسخة تجريبية مجانية متاحة؟

 ج4: نعم، يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).

### س5: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟

 ج5: يمكنك الحصول على ترخيص مؤقت من[هذا الرابط](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
