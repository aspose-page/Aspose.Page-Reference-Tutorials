---
title: أضف تدرجًا رأسيًا إلى PostScript (PS) باستخدام Aspose.Page
linktitle: إضافة تدرج عمودي إلى PostScript (PS)
second_title: Aspose.Page .NET API
description: تعرف على كيفية إضافة تدرجات رأسية جذابة بصريًا إلى مستندات PostScript (PS) في .NET باستخدام Aspose.Page. ارتقِ بمستوى إنشاء المستندات باستخدام هذا الدليل المفصّل خطوة بخطوة.
type: docs
weight: 14
url: /ar/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
---
## مقدمة

في مجال معالجة المستندات وإنشائها، تبرز Aspose.Page for .NET كأداة قوية للمطورين. سيرشدك هذا البرنامج التعليمي خلال عملية إضافة تدرج رأسي إلى مستند PostScript (PS) باستخدام Aspose.Page لـ .NET. بحلول نهاية هذا الدليل، سيكون لديك فهم واضح للخطوات اللازمة لتحقيق هذا التأثير الجذاب بصريًا.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:

-  Aspose.Page لـ .NET: تأكد من تثبيت مكتبة Aspose.Page. يمكنك العثور على الموارد والوثائق اللازمة[هنا](https://reference.aspose.com/page/net/).

- بيئة التطوير: قم بإعداد بيئة تطوير مناسبة، بما في ذلك بيئة التطوير المتكاملة (IDE) لتطوير .NET.

- الفهم الأساسي: تعرف على أساسيات تطوير .NET، بما في ذلك العمل مع التدفقات ومسارات الرسومات ومعالجة الألوان.

## استيراد مساحات الأسماء

في مشروع C# الخاص بك، قم بتضمين مساحات الأسماء المطلوبة في بداية ملف التعليمات البرمجية الخاص بك:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## الخطوة 1: إعداد دليل المستندات

ابدأ بتحديد المسار إلى دليل المستند الخاص بك. هذا هو الموقع الذي سيتم فيه حفظ مستند PS الخاص بك.

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء دفق الإخراج لمستند PostScript

قم بإنشاء دفق إخراج لمستند PostScript باستخدام فئة FileStream.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## الخطوة 3: إنشاء خيارات الحفظ ومستند PS

أنشئ خيارات حفظ بحجم A4 وقم بتهيئة مستند PS جديد مكون من صفحة واحدة.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 4: تحديد أبعاد المستطيل

حدد أبعاد المستطيل وموضعه حيث سيتم تطبيق التدرج الرأسي.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## الخطوة 5: إنشاء مسار الرسومات

قم ببناء مسار رسومات من المستطيل المحدد.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## الخطوة 6: تحديد ألوان الاستيفاء

إنشاء مجموعة من الألوان والمواضع الاستيفاء للتدرج.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## الخطوة 7: إنشاء فرشاة التدرج الخطي

قم بتكوين فرشاة متدرجة خطية باستخدام المستطيل كحدود وألوان البداية والنهاية.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## الخطوة 8: ضبط تحويل الفرشاة

قم بإنشاء تحويل للفرشاة، مع التأكد من أن مكونات مقياس X وY تتطابق مع عرض المستطيل وارتفاعه.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## الخطوة 9: اضبط الطلاء واملأ المستطيل

قم بتعيين الطلاء للمستند، واملأ المستطيل المحدد مسبقًا.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## الخطوة 10: أغلق الصفحة الحالية واحفظ المستند

أغلق الصفحة الحالية واحفظ مستند PostScript.

```csharp
document.ClosePage();
document.Save();
```

تهانينا! لقد نجحت في إضافة تدرج عمودي إلى مستند PostScript باستخدام Aspose.Page لـ .NET. قم بتجربة معلمات وألوان مختلفة لتحقيق تأثيرات بصرية متنوعة في مستنداتك.

## خاتمة

في هذا البرنامج التعليمي، استكشفنا عملية تحسين مستندات PostScript الخاصة بك عن طريق دمج التدرجات الرأسية. يوفر Aspose.Page for .NET بيئة سلسة لمثل هذه المعالجات، مما يمكّن المطورين من إنشاء مستندات مذهلة بصريًا دون عناء.

## الأسئلة الشائعة

### س1: هل يمكنني تطبيق تدرجات متعددة على مناطق مختلفة من نفس المستند؟

ج1: نعم يمكنك ذلك. ما عليك سوى تكرار الخطوات لكل منطقة بأبعادها المحددة ونظام الألوان الخاص بها.

### س2: كيف يمكنني دمج هذا الرمز في مشروع .NET الموجود الخاص بي؟

ج2: انسخ الكود والصقه في ملف مشروعك وتأكد من الإشارة إلى مكتبة Aspose.Page.

### س3: هل هناك أنواع تدرج أخرى متوفرة في Aspose.Page لـ .NET؟

A3: يدعم Aspose.Page أنواع التدرج المختلفة، بما في ذلك التدرجات الشعاعية والمسار. راجع الوثائق لمزيد من التفاصيل.

### س4: هل يمكنني استخدام Aspose.Page للمشاريع التجارية؟

 ج4: نعم يمكنك ذلك. يزور[هنا](https://purchase.aspose.com/buy) لاستكشاف خيارات الترخيص.

### س5: هل يوجد منتدى مجتمعي لـ Aspose.Page حيث يمكنني طلب المساعدة؟

 ج5: بالتأكيد! توجه إلى[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع المطورين الآخرين والحصول على المساعدة.