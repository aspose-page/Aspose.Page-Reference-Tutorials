---
title: أضف مستطيلًا إلى مستند XPS باستخدام Aspose.Page لـ .NET
linktitle: أضف مستطيلًا إلى مستند XPS
second_title: Aspose.Page .NET API
description: قم بتحسين إنشاء المستندات باستخدام Aspose.Page لـ .NET. تعرف على كيفية إضافة مستطيلات إلى مستندات XPS في هذا البرنامج التعليمي خطوة بخطوة.
type: docs
weight: 13
url: /ar/net/drawing-shapes/add-rectangle-to-xps-document/
---
## مقدمة

Aspose.Page for .NET هي مكتبة قوية توفر مجموعة متنوعة من الميزات للعمل مع مستندات XPS (مواصفات ورق XML) في تطبيقات .NET. في هذا البرنامج التعليمي، سنركز على إضافة مستطيل إلى مستند XPS باستخدام Aspose.Page لـ .NET. اتبع هذا الدليل التفصيلي خطوة بخطوة لتحسين عملية إنشاء المستندات الخاصة بك.

## المتطلبات الأساسية

قبل أن تبدأ بهذا البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Page for .NET Library: تأكد من تثبيت Aspose.Page لمكتبة .NET في بيئة التطوير الخاصة بك. يمكنك تنزيله[هنا](https://releases.aspose.com/page/net/).

2. دليل المستندات: قم بإعداد دليل حيث تريد تخزين مستندات XPS الخاصة بك.

## استيراد مساحات الأسماء

في تطبيق .NET الخاص بك، قم بتضمين مساحات الأسماء الضرورية لاستخدام وظائف Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## الخطوة 1: قم بتعيين دليل المستندات

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

## الخطوة 3: إضافة مستطيل

```csharp
// البداية:5
// مستطيل محدد بلون CMYK (أزرق) في أسفل اليسار
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// النهاية:5
```

## الخطوة 4: احفظ المستند

```csharp
// البداية:6
// احفظ مستند XPS الناتج
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// النهاية:6
```

تهانينا! لقد نجحت في إضافة مستطيل إلى مستند XPS باستخدام Aspose.Page لـ .NET.

## خاتمة

يعمل Aspose.Page for .NET على تبسيط مهام معالجة المستندات، مما يسمح للمطورين بإنشاء مستندات XPS وتعديلها بسهولة. يوضح هذا الدليل التفصيلي كيفية إضافة مستطيل إلى مستند XPS الخاص بك، مما يوفر أساسًا متينًا لمزيد من الاستكشاف.

## الأسئلة الشائعة

### س1: هل Aspose.Page متوافق مع كافة تطبيقات .NET؟

ج1: نعم، تم تصميم Aspose.Page للعمل بسلاسة مع كافة تطبيقات .NET.

### س٢: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page لـ .NET؟

 ج2: الوثائق متاحة[هنا](https://reference.aspose.com/page/net/).

### س3: هل يمكنني تجربة Aspose.Page لـ .NET مجانًا قبل الشراء؟

 ج3: نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).

### س٤: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟

 ج4: زيارة[هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت.

### س5: أين يمكنني طلب دعم المجتمع أو طرح الأسئلة المتعلقة بـ Aspose.Page for .NET؟

 ج5: قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) لدعم المجتمع.