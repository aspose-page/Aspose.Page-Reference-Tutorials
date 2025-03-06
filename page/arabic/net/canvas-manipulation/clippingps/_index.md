---
title: قص PS باستخدام Aspose.Page لـ .NET
linktitle: لقطة PS
second_title: Aspose.Page .NET API
description: اكتشف قوة Aspose.Page لـ .NET في هذا البرنامج التعليمي خطوة بخطوة حول قص مستندات PostScript. تعلم كيفية تحسين قدرات معالجة المستندات الخاصة بك دون عناء.
weight: 10
url: /ar/net/canvas-manipulation/clippingps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قص PS باستخدام Aspose.Page لـ .NET

## مقدمة

مرحبًا بك في البرنامج التعليمي الشامل حول استخدام Aspose.Page لـ .NET لتنفيذ القطع في مستندات PostScript (PS). سيرشدك هذا البرنامج التعليمي خلال عملية قص مستندات PS باستخدام Aspose.Page، وهي مكتبة قوية للعمل مع تنسيقات المستندات المختلفة في تطبيقات .NET.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

- معرفة عملية بلغة البرمجة C#.
-  تم تثبيت Aspose.Page لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/page/net/).
- بيئة تطوير متكاملة (IDE) مثل Visual Studio.

## استيراد مساحات الأسماء

ابدأ باستيراد مساحات الأسماء الضرورية في كود C# الخاص بك:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

الآن، دعونا نقسم المثال إلى عدة خطوات:

## الخطوة 1: قم بتعيين دليل المستندات

```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء دفق الإخراج لمستند PostScript

```csharp
// إنشاء دفق الإخراج لمستند بوستسكريبت
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

## الخطوة 3: إنشاء خيارات الحفظ

```csharp
// إنشاء خيارات الحفظ بالقيم الافتراضية
PsSaveOptions options = new PsSaveOptions();
```

## الخطوة 4: إنشاء مستند PS جديد مكون من صفحة واحدة

```csharp
// قم بإنشاء مستند PS جديد مكون من صفحة واحدة
PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 5: إنشاء مسار الرسومات من المستطيل

```csharp
// إنشاء مسار الرسومات من المستطيل
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

## الخطوة 6: القطع حسب الشكل

```csharp
// احفظ حالة الرسومات للعودة إلى هذه الحالة بعد التحويل
document.WriteGraphicsSave();

//قم بإزاحة حالة الرسومات الحالية بمقدار 100 نقطة إلى اليمين و100 نقطة إلى الأسفل.
document.Translate(100, 100);

// إنشاء مسار الرسومات من الدائرة
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// إضافة لقطة بدائرة إلى حالة الرسومات الحالية
document.Clip(circlePath);

// اضبط الطلاء على حالة الرسومات الحالية
document.SetPaint(new SolidBrush(Color.Blue));

// املأ المستطيل في حالة الرسومات الحالية (مع القطع)
document.Fill(rectanglePath);

// استعادة حالة الرسومات إلى المستوى السابق (العلوي).
document.WriteGraphicsRestore();
```

## الخطوة 7: إزاحة حالة الرسومات ذات المستوى العلوي

```csharp
// قم بإزاحة حالة الرسومات ذات المستوى العلوي بمقدار 100 نقطة إلى اليمين و100 نقطة إلى الأسفل.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// ارسم المستطيل في حالة الرسومات الحالية (لا يحتوي على قطع) فوق المستطيل المقطوع
document.Draw(rectanglePath);
```

## الخطوة 8: إغلاق وحفظ المستند

```csharp
// إغلاق الصفحة الحالية
document.ClosePage();

// احفظ المستند
document.Save();
```

لقد نجحت الآن في تنفيذ القص في مستند PostScript باستخدام Aspose.Page لـ .NET.

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية استخدام Aspose.Page لـ .NET لتنفيذ القطع في مستندات PostScript. توفر هذه المكتبة القوية طريقة سلسة وفعالة للتعامل مع تنسيقات المستندات المختلفة في تطبيقات .NET الخاصة بك.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.Page لـ .NET مع لغات برمجة أخرى؟

A1: تم تصميم Aspose.Page بشكل أساسي لتطبيقات .NET. ومع ذلك، يوفر Aspose مكتبات مماثلة للغات البرمجة الأخرى.

### س2: أين يمكنني العثور على أمثلة ووثائق إضافية لـ Aspose.Page لـ .NET؟

 ج2: يمكنك استكشاف المزيد من الأمثلة والوثائق التفصيلية حول[Aspose.Page الوثائق](https://reference.aspose.com/page/net/).

### س3: هل تتوفر نسخة تجريبية مجانية من Aspose.Page لـ .NET؟

 ج3: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.Page لـ .NET[هنا](https://releases.aspose.com/).

### س٤: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟

 ج4: يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).

### س5: أين يمكنني الحصول على الدعم أو مناقشة الاستعلامات المتعلقة بـ Aspose.Page؟

 ج5: قم بزيارة[منتديات Aspose.Page](https://forum.aspose.com/c/page/39) لدعم المجتمع والمناقشات.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
