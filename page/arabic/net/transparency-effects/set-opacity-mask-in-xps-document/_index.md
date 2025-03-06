---
title: قم بتعيين قناع العتامة في مستند XPS باستخدام Aspose.Page لـ .NET
linktitle: قم بتعيين قناع العتامة في مستند XPS
second_title: Aspose.Page .NET API
description: تعرف على كيفية تعيين أقنعة العتامة في مستندات XPS باستخدام Aspose.Page لـ .NET. تعزيز جماليات الوثيقة دون عناء.
weight: 12
url: /ar/net/transparency-effects/set-opacity-mask-in-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بتعيين قناع العتامة في مستند XPS باستخدام Aspose.Page لـ .NET

## مقدمة

تعد أقنعة العتامة ضرورية عندما تريد إنشاء مستندات جذابة بصريًا بمستويات مختلفة من الشفافية. يعمل Aspose.Page for .NET على تبسيط هذه العملية، حيث يوفر للمطورين مجموعة شاملة من الأدوات لتحسين مستندات XPS. في هذا البرنامج التعليمي، سنستكشف كيفية تعيين قناع العتامة في دليل خطوة بخطوة.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

-  Aspose.Page for .NET: تأكد من تثبيت المكتبة. إذا لم يكن الأمر كذلك، يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/page/net/).

- دليل المستندات: قم بإعداد دليل لتخزين مستندات XPS الخاصة بك.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية:

```csharp
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using Aspose.Page.Xps.XpsModel.Shapes;
using Aspose.Page.Xps.XpsModel.Text;
using System.Drawing;
```

## الخطوة 1: إنشاء مستند XPS جديد

```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// قم بإنشاء مستند XPS جديد
XpsDocument doc = new XpsDocument();
```

ابدأ بإنشاء مستند XPS جديد باستخدام Aspose.Page لـ .NET.

## الخطوة 2: إضافة Canvas إلى مثيل XpsDocument

```csharp
// أضف Canvas إلى مثيل XpsDocument
XpsCanvas canvas = doc.AddCanvas();
```

الآن، أضف لوحة قماشية إلى مستند XPS. ستكون اللوحة القماشية بمثابة حاوية للعناصر الرسومية المختلفة.

## الخطوة 3: إضافة مستطيل مع قناع العتامة

```csharp
// مستطيل مع عتامة مقنعة بواسطة ImageBrush
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.OpacityMask = doc.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)path.OpacityMask).TileMode = XpsTileMode.Tile;
```

 أضف مستطيلاً إلى اللوحة القماشية واضبط درجة التعتيم باستخدام`OpacityMask`ملكية. في هذا المثال، نستخدم صورة كقناع العتامة.

## الخطوة 4: احفظ مستند XPS الناتج

```csharp
// احفظ مستند XPS الناتج
doc.Save(dataDir + "OpacityMask_out.xps");
```

أخيرًا، احفظ مستند XPS المعدل مع تطبيق قناع العتامة.

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تعيين أقنعة العتامة في مستندات XPS باستخدام Aspose.Page لـ .NET. تفتح هذه الميزة عالمًا من الإمكانيات الإبداعية لتصميم مستندات متطورة وجذابة بصريًا.

## الأسئلة الشائعة

### س1: هل يمكنني تطبيق أقنعة العتامة على أشكال أخرى إلى جانب المستطيلات؟

A1: نعم، يسمح لك Aspose.Page for .NET بتطبيق أقنعة العتامة على أشكال مختلفة، بما في ذلك الدوائر والمضلعات والمسارات المخصصة.

### س2: هل يقتصر قناع العتامة على الصور؟

ج2: لا، بينما يستخدم هذا البرنامج التعليمي صورة كقناع عتامة، يمكنك استخدام الألوان الصلبة أو التدرجات اللونية أو حتى الأنماط.

### س 3: هل توجد خيارات متقدمة لضبط مستويات العتامة؟

ج3: بالتأكيد، يوفر Aspose.Page for .NET تحكمًا تفصيليًا في إعدادات العتامة، مما يسمح لك بتحقيق تأثيرات شفافية دقيقة.

### س4: هل يمكنني تطبيق أقنعة عتامة متعددة على عنصر واحد؟

ج4: نعم، يمكنك وضع أقنعة عتامة متعددة في طبقات لإنشاء تأثيرات شفافية معقدة.

### س5: هل Aspose.Page متوافق مع تنسيقات المستندات الأخرى؟

ج5: يركز Aspose.Page بشكل أساسي على مستندات XPS، لكن Aspose يوفر نطاقًا من المنتجات للتعامل مع التنسيقات المختلفة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
