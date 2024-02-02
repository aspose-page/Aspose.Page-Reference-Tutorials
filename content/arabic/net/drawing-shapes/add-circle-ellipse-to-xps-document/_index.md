---
title: أضف Circle Ellipse إلى مستند XPS باستخدام Aspose.Page لـ .NET
linktitle: أضف دائرة القطع الناقص إلى مستند XPS
second_title: Aspose.Page .NET API
description: قم بتحسين مستندات XPS بتدرجات شعاعية نابضة بالحياة باستخدام Aspose.Page لـ .NET. اتبع دليلنا خطوة بخطوة للحصول على تأثيرات بصرية مذهلة.
type: docs
weight: 11
url: /ar/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---
## مقدمة

يعد إنشاء مستندات XPS جذابة بصريًا مطلبًا شائعًا في التطبيقات المختلفة. يوفر Aspose.Page for .NET مجموعة قوية من الميزات لمعالجة مستندات XPS بكفاءة. في هذا البرنامج التعليمي، سنركز على إضافة شكل بيضاوي دائري إلى مستند XPS باستخدام Aspose.Page لـ .NET. اتبع الخطوات الموضحة أدناه لتحسين مستندات XPS الخاصة بك بتدرجات شعاعية نابضة بالحياة.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  تم تثبيت Aspose.Page لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/page/net/).
- بيئة تطوير، ويفضل أن تكون Visual Studio أو أي أداة تطوير .NET أخرى.
- المعرفة الأساسية ببرمجة C#.

## استيراد مساحات الأسماء

للبدء، قم بتضمين مساحات الأسماء الضرورية في كود C# الخاص بك:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

الآن، دعونا نقسم المثال إلى عدة خطوات:

## الخطوة 1: إعداد المستند

```csharp
// البداية:1
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// قم بإنشاء مستند XPS جديد
XpsDocument doc = new XpsDocument();
```

هنا، نقوم بتهيئة مستند XPS جديد باستخدام Aspose.Page لـ .NET.

## الخطوة 2: تحديد القطع الناقص التدرج الشعاعي

```csharp
// شكل بيضاوي متدرج شعاعي في أسفل اليسار
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

تتضمن هذه الخطوة تحديد شكل بيضاوي متدرج شعاعي مع توقفات لونية مختلفة.

## الخطوة 3: تعيين فرشاة التدرج الشعاعي

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

هنا، قمنا بتعيين حد القطع الناقص على فرشاة متدرجة شعاعية، وتزويدها بالمعلمات الضرورية.

## الخطوة 4: ضبط سمك السكتة الدماغية

```csharp
path.StrokeThickness = 12f;
```

تتضمن هذه الخطوة ضبط سمك الحد للحصول على رؤية أفضل.

## الخطوة 5: احفظ مستند XPS الناتج

```csharp
// احفظ مستند XPS الناتج
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// النهاية:1
```

وأخيرًا، احفظ مستند XPS المعدل في الموقع المطلوب.

## خاتمة

تهانينا! لقد نجحت في إضافة شكل بيضاوي دائري بتدرجات شعاعية إلى مستند XPS الخاص بك باستخدام Aspose.Page لـ .NET. قم بتجربة معلمات وألوان مختلفة لتحقيق التأثيرات المرئية المطلوبة في مستنداتك.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.Page لـ .NET مع تنسيقات المستندات الأخرى؟

A1: يتعامل Aspose.Page لـ .NET بشكل خاص مع معالجة مستندات XPS. بالنسبة للتنسيقات الأخرى، فكر في استخدام مكتبات Aspose ذات الصلة.

### س2: هل الترخيص المؤقت متاح لأغراض الاختبار؟

 ج2: نعم، يمكنك الحصول على ترخيص مؤقت للاختبار من خلال الزيارة[هذا الرابط](https://purchase.aspose.com/temporary-license/).

### س3: أين يمكنني العثور على مساعدة ومناقشات إضافية؟

 ج3: قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) لدعم المجتمع والمناقشات.

### س 4: هل هناك أي وثائق عينة متاحة للرجوع إليها؟

 ج4: اكتشف[توثيق](https://reference.aspose.com/page/net/) للحصول على أمثلة وإرشادات شاملة.

### س5: هل يمكنني شراء Aspose.Page لـ .NET؟

 ج5: نعم، يمكنك شراء المكتبة[هنا](https://purchase.aspose.com/buy).