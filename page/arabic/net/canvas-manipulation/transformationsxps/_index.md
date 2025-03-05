---
title: تحويلات XPS مع Aspose.Page لـ .NET
linktitle: التحولات XPS
second_title: Aspose.Page .NET API
description: قم بتحويل مستندات XPS بسهولة باستخدام Aspose.Page لـ .NET. اتبع دليلنا خطوة بخطوة لإجراء تحويلات سلسة.
type: docs
weight: 13
url: /ar/net/canvas-manipulation/transformationsxps/
---
## مقدمة

مرحبًا بك في عالم Aspose.Page for .NET، وهي مكتبة قوية تمكنك من إجراء تحويلات متنوعة على مستندات XPS دون عناء. في هذا البرنامج التعليمي، سنتعمق في عملية تحويل مستندات XPS باستخدام Aspose.Page لـ .NET. سواء كنت مطورًا متمرسًا أو بدأت للتو، سيرشدك هذا الدليل خلال كل خطوة، مما يضمن استيعاب المفاهيم بسهولة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر ما يلي:

-  Aspose.Page for .NET Library: قم بتنزيل المكتبة وتثبيتها من[Aspose.Page للتوثيق .NET](https://reference.aspose.com/page/net/).

- بيئة التطوير: قم بإعداد بيئة تطوير متوافقة، مثل Visual Studio أو أي أداة تطوير .NET أخرى.

- دليل المستندات الخاص بك: استبدل العنصر النائب في الكود بالمسار الفعلي إلى دليل المستندات الخاص بك.

الآن، دعونا ننتقل إلى البرنامج التعليمي!

## استيراد مساحات الأسماء

أولاً، تأكد من استيراد مساحات الأسماء الضرورية لجعل وظائف Aspose.Page لـ .NET متوفرة في التعليمات البرمجية الخاصة بك. أضف مساحات الأسماء التالية في بداية البرنامج النصي الخاص بك:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## الخطوة 1: إنشاء مستند XPS جديد

```csharp
// البداية:1
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";

// قم بإنشاء مستند XPS جديد
XpsDocument doc = new XpsDocument();
```

## الخطوة 2: إنشاء قماش رئيسي

```csharp
// قم بإنشاء لوحة رئيسية مشتركة لجميع عناصر الصفحة
XpsCanvas canvas1 = doc.AddCanvas();

// قم بإجراء الإزاحات اليسرى والعليا في اللوحة الرئيسية
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## الخطوة 3: إنشاء هندسة مسار مستطيل

```csharp
// إنشاء هندسة مسار المستطيل
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## الخطوة 4: إضافة تعبئة للمستطيلات

```csharp
// إنشاء تعبئة للمستطيلات
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## الخطوة 5: إضافة قماش جديد بدون تحويلات

```csharp
// أضف لوحة قماشية جديدة دون أي تحويلات إلى اللوحة الرئيسية
XpsCanvas canvas2 = canvas1.AddCanvas();

// قم بإنشاء مستطيل في هذه اللوحة القماشية واملأها
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## الخطوة 6: إضافة لوحة قماشية جديدة مع تحويل الترجمة

```csharp
// أضف لوحة قماشية جديدة مع ترجمة التحويل إلى اللوحة القماشية الرئيسية
XpsCanvas canvas3 = canvas1.AddCanvas();

// قم بترجمة هذه اللوحة القماشية لوضع مستطيل جديد أسفل المستطيل السابق
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// قم بترجمة هذه اللوحة القماشية إلى الجانب الأيمن من الصفحة
canvas3.RenderTransform.Translate(500, 0);

// قم بإنشاء مستطيل في هذه اللوحة القماشية واملأها
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## الخطوة 7: إضافة لوحة قماشية جديدة ذات تحويل مزدوج النطاق

```csharp
//أضف لوحة قماشية جديدة ذات تحويل مزدوج الحجم إلى اللوحة الرئيسية
XpsCanvas canvas4 = canvas1.AddCanvas();

// قم بترجمة هذه اللوحة القماشية لوضع مستطيل جديد أسفل المستطيل السابق
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// مقياس هذه اللوحة القماشية
canvas4.RenderTransform.Scale(2, 2);

// قم بإنشاء مستطيل في هذه اللوحة القماشية واملأها
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## الخطوة 8: إضافة لوحة قماشية جديدة مع التدوير حول تحويل النقطة

```csharp
// أضف لوحة قماشية جديدة مع التدوير حول تحويل النقطة إلى اللوحة القماشية الرئيسية
XpsCanvas canvas5 = canvas1.AddCanvas();

// قم بترجمة هذه اللوحة القماشية لوضع مستطيل جديد أسفل المستطيل السابق
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// قم بتدوير هذه اللوحة القماشية حول نقطة بزاوية 45 درجة
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// قم بإنشاء مستطيل في هذه اللوحة القماشية واملأها
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## الخطوة 9: احفظ مستند XPS الناتج

```csharp
// احفظ مستند XPS الناتج
doc.Save(dataDir + "output1.xps");
// النهاية:1
```

## خاتمة

تهانينا! لقد نجحت في تحويل مستند XPS باستخدام Aspose.Page لـ .NET. يغطي هذا الدليل الخطوات الأساسية، بدءًا من إعداد المتطلبات الأساسية وحتى إجراء التحويلات المختلفة. قم بتجربة هذه التقنيات واطلق العنان للإمكانات الكاملة لـ Aspose.Page for .NET في مشاريعك.

## الأسئلة الشائعة

### س1: هل Aspose.Page for .NET متوافق مع كافة بيئات تطوير .NET؟

A1: نعم، تم تصميم Aspose.Page for .NET للعمل بسلاسة مع بيئات تطوير .NET المتنوعة، بما في ذلك Visual Studio.

### س2: أين يمكنني العثور على أمثلة ووثائق إضافية لـ Aspose.Page لـ .NET؟

 ج2: قم بزيارة[Aspose.Page للتوثيق .NET](https://reference.aspose.com/page/net/) للحصول على وثائق وأمثلة شاملة.

### س3: هل يمكنني تجربة Aspose.Page لـ .NET قبل الشراء؟

 ج3: نعم، يمكنك استكشاف نسخة تجريبية مجانية من خلال زيارة[Aspose.Page تجربة مجانية](https://releases.aspose.com/).

### س٤: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟

 ج4: احصل على ترخيص مؤقت من خلال الزيارة[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/).

### س5: أين يمكنني شراء Aspose.Page لـ .NET؟

 A5: قم بشراء Aspose.Page لـ .NET على[Aspose.Page شراء](https://purchase.aspose.com/buy).