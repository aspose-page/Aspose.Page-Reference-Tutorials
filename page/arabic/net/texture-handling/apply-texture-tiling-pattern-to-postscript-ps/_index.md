---
date: 2026-03-26
description: تعلم كيفية إنشاء مستند PostScript باستخدام .NET مع أنماط تجانب القوام
  باستخدام Aspose.Page. اتبع دليلنا خطوة بخطوة لإضافة قوام غني إلى ملفات PS الخاصة
  بك.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: إنشاء مستند PostScript .NET مع تجانب القوام
url: /ar/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مستند PostScript .NET مع نمط تجانب القوام

## كيفية إنشاء مستند PostScript .NET مع نمط تجانب القوام

## إجابات سريعة
- **ما المكتبة المستخدمة؟** Aspose.Page for .NET  
- **هل يمكنني استخدام .NET Core؟** نعم، المكتبة تدعم .NET Core و .NET 5/6  
- **ما صيغ الصور التي تعمل مع القوام؟** أي صيغة يدعمها System.Drawing (BMP، PNG، JPEG، إلخ).  
- **كم من الوقت تستغرق التنفيذ؟** حوالي 10‑15 دقيقة للمثال الأساسي  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للاختبار؛ الترخيص مطلوب للإنتاج  

## المتطلبات المسبقة

- [Visual Studio](https://visualstudio.microsoft.com/) مثبت على جهازك.  
- معرفة أساسية ببرمجة C#.  
- تحميل وتثبيت [Aspose.Page for .NET library](https://releases.aspose.com/page/net/).  
- ملف صورة لنمط القوام (مثال: **TestTexture.bmp**).

## استيراد مساحات الأسماء

في ملف C# الخاص بك، استورد مساحات الأسماء المطلوبة حتى يعرف المترجم أين يجد الأنواع التي سنستخدمها:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## الخطوة 1: إعداد دليل المستند

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

استبدل **Your Document Directory** بالمجلد الذي تريد حفظ ملف PS المُولد فيه.

## الخطوة 2: إنشاء تدفق الإخراج لمستند PS

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

هذا الجزء يفتح تدفق ملف، يضبط حجم الصفحة (A4 افتراضيًا)، وينشئ كائن **PsDocument** جديد سنرسم عليه.

## الخطوة 3: تطبيق نمط تجانب القوام

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

هنا نقوم بتحميل الـ bitmap، نغلفه بـ **TextureBrush**، نمدده أفقيًا اختياريًا، ونخبر **PsDocument** باستخدام هذه الفرشاة للعمليات الرسومية اللاحقة.

## الخطوة 4: إنشاء مسار مستطيل وتعبئته

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

يتم تعريف مستطيل بسيط وتعبئته بفرشاة القوام التي حددناها مسبقًا.

## الخطوة 5: ضبط الحد والرسم

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

نسترجع اللون الحالي (فرشاة القوام)، ننشئ قلمًا أحمر للحد، ونرسم حدود المستطيل.

## الخطوة 6: تعبئة ونقش النص بنمط القوام

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

هذه الخطوة توضح قدرة **تعبئة ونقش النص**: يتم تعبئة الأحرف “ABC” بفرشاة القوام ثم يتم نقشها، مما ينتج تأثيرًا بصريًا بارزًا.

## الخطوة 7: حفظ وإغلاق المستند

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

إغلاق الصفحة يُنهي أوامر الرسم، و`Save()` يكتب ملف PostScript إلى القرص.

## المشكلات الشائعة والحلول

- **القوام يبدو مشدودًا بشكل غير صحيح** – عدل قيم `Matrix` للتحكم في التحجيم في اتجاهي X/Y.  
- **الصورة غير موجودة** – تأكد أن `dataDir` يشير إلى المجلد الصحيح وأن اسم الملف مطابق تمامًا، بما في ذلك حالة الأحرف.  
- **الألوان غير صحيحة** – تذكر أن PostScript يستخدم مساحة ألوان مستقلة عن الجهاز؛ تأكد من استخدام كائنات `Color` التي تُطابق بشكل صحيح.

## الأسئلة المتكررة

**س:** هل يمكنني استخدام صيغ صور أخرى لنمط القوام؟  
**ج:** نعم، أي صيغة يدعمها `System.Drawing.Bitmap` (BMP، PNG، JPEG، GIF، إلخ) تعمل.

**س:** هل Aspose.Page متوافق مع .NET Core؟  
**ج:** بالتأكيد. المكتبة تعمل على .NET Framework و .NET Core و .NET 5/6.

**س:** كيف أغير حجم المستطيل المملوء بالقوام؟  
**ج:** عدل قيم `RectangleF` في خطوة إنشاء المستطيل (مثال: `new RectangleF(0, 0, 300, 150)`).

**س:** هل يمكنني تطبيق أنماط قوام متعددة في مستند واحد؟  
**ج:** نعم. فقط أنشئ `TextureBrush` جديد بصورة مختلفة واستدعِ `SetPaint` مرة أخرى قبل رسم الشكل أو النص التالي.

**س:** أين يمكنني العثور على المزيد من الأمثلة ومرجع الـ API؟  
**ج:** زر [Aspose.Page Forum](https://forum.aspose.com/c/page/39) للحصول على مساعدة المجتمع و[documentation](https://reference.aspose.com/page/net/) الرسمي للحصول على تفاصيل استخدام الـ API.

## الخلاصة

أنت الآن تعرف كيف **تنشئ مستند PostScript .NET** وتطبق نمط تجانب القوام، بما في ذلك كيفية **تعبئة ونقش النص** بهذا القوام. جرّب صورًا مختلفة، ومصفوفات تحجيم، وبدائيات الرسم لإنتاج ملفات PS ذات نمط مخصص للتقارير، والنشرات، أو أي مخرجات غنية بالرسومات.

---

**آخر تحديث:** 2026-03-26  
**تم الاختبار مع:** Aspose.Page 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}