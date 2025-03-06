---
title: قم بتطبيق نمط تبليط الملمس على PostScript (PS) باستخدام Aspose.Page
linktitle: تطبيق نمط تبليط الملمس على PostScript (PS)
second_title: Aspose.Page .NET API
description: قم بتحسين مستندات PostScript (PS) الخاصة بك باستخدام أنماط تجانب النسيج باستخدام Aspose.Page لـ .NET. اتبع دليلنا خطوة بخطوة للحصول على لمسة إبداعية.
weight: 10
url: /ar/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بتطبيق نمط تبليط الملمس على PostScript (PS) باستخدام Aspose.Page

## مقدمة

مرحبًا بك في هذا البرنامج التعليمي خطوة بخطوة حول كيفية تطبيق نمط تجانب النسيج على مستند PostScript (PS) باستخدام Aspose.Page لـ .NET. Aspose.Page هي مكتبة قوية تسمح لك بالعمل مع تنسيقات المستندات المختلفة، وفي هذا البرنامج التعليمي، سنستكشف كيفية تحسين مستندات PS الخاصة بك عن طريق إضافة أنماط تجانب النسيج.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:

- [استوديو مرئي](https://visualstudio.microsoft.com/) المثبتة على جهازك.
- المعرفة الأساسية ببرمجة C#.
-  تحميل وتثبيت[Aspose.Page لمكتبة .NET](https://releases.aspose.com/page/net/).
- ملف صورة لنمط النسيج (على سبيل المثال، "TestTexture.bmp").

## استيراد مساحات الأسماء

في كود C# الخاص بك، تأكد من استيراد مساحات الأسماء الضرورية:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

دعنا نقسم المثال المقدم إلى خطوات متعددة لإرشادك خلال العملية.

## الخطوة 1: إعداد دليل المستندات

```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الذي تريد حفظ مستند PS الخاص بك فيه.

## الخطوة 2: إنشاء دفق الإخراج لمستند PS

```csharp
// إنشاء دفق الإخراج لمستند بوستسكريبت
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // إنشاء خيارات الحفظ بحجم A4
    PsSaveOptions options = new PsSaveOptions();

    // قم بإنشاء مستند PS جديد مكون من صفحة واحدة
    PsDocument document = new PsDocument(outPsStream, options, false);
```

تقوم هذه الخطوة بإعداد دفق الإخراج لمستند PS، بما في ذلك تحديد حجم المستند.

## الخطوة 3: تطبيق نمط تبليط الملمس

```csharp
// قم بإنشاء كائن نقطي من ملف الصورة
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // إنشاء فرشاة الملمس من الصورة
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //أضف مقياسًا في اتجاه X إلى النمط
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // قم بتعيين فرشاة الملمس هذه كالطلاء الحالي
    document.SetPaint(brush);
}
```

تتضمن هذه الخطوة إنشاء فرشاة نسيج من صورة وتعيينها كالطلاء الحالي للمستند.

## الخطوة 4: إنشاء مسار مستطيل وملء

```csharp
// إنشاء مسار مستطيل
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// ملء المستطيل
document.Fill(path);
```

هنا، نحدد مسارًا مستطيلًا ونملأه بفرشاة الملمس المحددة مسبقًا.

## الخطوة 5: ضبط السكتة الدماغية والرسم

```csharp
// احصل على الطلاء الحالي
Brush paint = document.GetPaint();

// تعيين السكتة الدماغية الحمراء
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// السكتة الدماغية المستطيل
document.Draw(path);
```

تتضمن هذه الخطوة ضبط خصائص الحد ورسم المستطيل المحدد.

## الخطوة 6: ملء النص وتحديده بنمط الملمس

```csharp
// تعبئة النص بنمط الملمس
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// مخطط تفصيلي للنص مع نمط الملمس
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

أخيرًا، نقوم بملء النص وتحديد الخطوط العريضة له باستخدام نمط النسيج، مما يعزز المظهر المرئي للمستند الخاص بك.

## الخطوة 7: حفظ وإغلاق المستند

```csharp
// إغلاق الصفحة الحالية
document.ClosePage();

// احفظ المستند
document.Save();
```

تأكد من إغلاق الصفحة الحالية وحفظ المستند لتطبيق التغييرات.

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تطبيق نمط تجانب النسيج على مستند PostScript باستخدام Aspose.Page لـ .NET. قم بتجربة صور وأنماط مختلفة لتخصيص مستندات PS الخاصة بك بشكل أكبر.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام تنسيقات صور أخرى لنمط النسيج؟

A1: نعم، يدعم Aspose.Page تنسيقات الصور المختلفة. التأكد من التوافق مع وثائق المكتبة.

### س2: هل Aspose.Page متوافق مع .NET Core؟

ج2: نعم، Aspose.Page متوافق مع كل من .NET Framework و.NET Core.

### س3: كيف يمكنني ضبط حجم المستطيل المزخرف؟

 A3: قم بتعديل الأبعاد في`RectangleF` المعلمات أثناء إنشاء المسار.

### س4: هل يمكنني إضافة أنماط نسيج متعددة إلى مستند واحد؟

ج4: نعم، يمكنك تكرار العملية بصور ومسارات مختلفة.

### س5: أين يمكنني العثور على موارد ودعم إضافيين؟

 ج5: قم بزيارة[Aspose.صفحة المنتدى](https://forum.aspose.com/c/page/39) لدعم المجتمع واستكشاف[توثيق](https://reference.aspose.com/page/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
