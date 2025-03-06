---
title: قص XPS باستخدام Aspose.Page لـ .NET
linktitle: قطع XPS
second_title: Aspose.Page .NET API
description: اكتشف قوة Aspose.Page لـ .NET في هذا الدليل التفصيلي خطوة بخطوة حول قص مستندات XPS. يمكنك إنشاء ملفات XPS ومعالجتها وحفظها بسهولة.
weight: 11
url: /ar/net/canvas-manipulation/clippingxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قص XPS باستخدام Aspose.Page لـ .NET

## مقدمة

مرحبًا بك في هذا البرنامج التعليمي الشامل حول قص XPS باستخدام Aspose.Page لـ .NET! في هذا الدليل، سنرشدك خلال عملية إنشاء مستندات XPS ومعالجتها وحفظها باستخدام Aspose.Page لـ .NET. XPS، أو مواصفات ورق XML، هو تنسيق مستند قياسي ومفتوح، ويوفر Aspose.Page for .NET أدوات قوية للعمل مع مستندات XPS في تطبيقات .NET الخاصة بك.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Visual Studio على جهازك.
-  تمت إضافة Aspose.Page لمكتبة .NET إلى مشروعك. يمكنك تنزيله[هنا](https://releases.aspose.com/page/net/).
- المعرفة الأساسية بلغة البرمجة C#.

## استيراد مساحات الأسماء

من أجل استخدام Aspose.Page لوظائف .NET، تحتاج إلى استيراد مساحات الأسماء المطلوبة إلى مشروعك. اتبع الخطوات التالية:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

الآن، دعنا نقسم رمز المثال الذي قدمته إلى خطوات متعددة.

## الخطوة 1: قم بتعيين مسار دليل المستند.

```csharp
string dataDir = "Your Document Directory";
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي لدليل المستندات الخاص بك.

## الخطوة 2: إنشاء مستند XPS جديد.

```csharp
XpsDocument doc = new XpsDocument();
```

يؤدي هذا إلى إنشاء مستند XPS جديد ستعمل معه.

## الخطوة 3: إنشاء اللوحة الرئيسية.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

تقوم هذه الخطوة بإنشاء اللوحة الرئيسية، وهي شائعة لجميع عناصر الصفحة.

## الخطوة 4: قم بتعيين الإزاحات اليسرى والعليا في اللوحة الرئيسية.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

اضبط الإزاحات اليسرى والعليا وفقًا لمتطلباتك.

## الخطوة 5: إنشاء هندسة مسار مستطيل.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

يؤدي هذا إلى إنشاء هندسة المسار للمستطيل.

## الخطوة 6: إنشاء تعبئة للمستطيلات.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

تحديد لون التعبئة للمستطيلات.

## الخطوة 7: أضف لوحة قماشية أخرى تحتوي على مقطع إلى اللوحة القماشية الرئيسية.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

تضيف هذه الخطوة لوحة قماشية أخرى إلى اللوحة الرئيسية.

## الخطوة 8: إنشاء هندسة دائرة للمقطع.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

يؤدي هذا إلى إنشاء مقطع هندسي دائري وتطبيقه على اللوحة القماشية الثانية.

## الخطوة 9: قم بإنشاء مستطيل في اللوحة القماشية الثانية واملأه.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

تقوم هذه الخطوة بإنشاء مستطيل في اللوحة القماشية الثانية وتعبئته.

## الخطوة 10: أضف اللوحة القماشية الثانية بمستطيل محدد إلى اللوحة القماشية الرئيسية.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

يؤدي هذا إلى إضافة لوحة قماشية أخرى إلى اللوحة القماشية الرئيسية.

## الخطوة 11: قم بإنشاء مستطيل في اللوحة القماشية الثالثة وقم برسمه.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

يؤدي هذا إلى إنشاء مستطيل في اللوحة القماشية الثالثة وتطبيق حد عليه.

## الخطوة 12: احفظ مستند XPS الناتج.

```csharp
doc.Save(dataDir + "output2.xps");
```

يؤدي هذا إلى حفظ مستند XPS في الدليل المحدد.

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية قص XPS باستخدام Aspose.Page لـ .NET. يقدم هذا الدليل شرحًا تفصيليًا للخطوات المتضمنة في هذه العملية.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.Page لـ .NET مع تنسيقات المستندات الأخرى؟

A1: يركز Aspose.Page for .NET بشكل أساسي على مستندات XPS، لكن Aspose يوفر مكتبات أخرى لتنسيقات المستندات المختلفة.

### س2: هل Aspose.Page for .NET مناسب للمبتدئين؟

ج2: نعم، تم تصميم Aspose.Page for .NET ليكون سهل الاستخدام، ويمكن للمبتدئين استيعاب وظائفه بسرعة من خلال التوثيق المناسب.

### س3: أين يمكنني العثور على المزيد من الأمثلة والموارد؟

 ج3: قم بزيارة[توثيق](https://reference.aspose.com/page/net/) و[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على موارد وأمثلة واسعة النطاق.

### س٤: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟

 ج4: يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).

### س5: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page لـ .NET؟

 ج5: نعم، يمكنك استكشاف النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
