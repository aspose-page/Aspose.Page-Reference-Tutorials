---
date: 2026-01-12
description: تعلم كيفية حفظ ملف PostScript وإنشاء مستند PostScript باستخدام Aspose.Page
  لـ .NET، وتطبيق تحولات متعددة للرسومات الديناميكية.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: حفظ ملف PostScript باستخدام تحويلات Aspose.Page (.NET)
url: /ar/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حفظ ملف PostScript باستخدام تحويلات Aspose.Page (.NET)

## المقدمة

في هذا الدرس ستكتشف كيفية **حفظ ملف PostScript** أثناء العمل مع Aspose.Page لـ .NET. سنستعرض إنشاء مستند PostScript، وتطبيق تحويلات متعددة مثل الإزاحة (translation)، والتحجيم (scaling)، والدوران (rotation)، والقص (shearing)، وأخيرًا حفظ النتيجة. في النهاية ستتمكن من إنشاء رسومات ديناميكية برمجياً وستعرف بالضبط أين تضع كل تحويل في حالة الرسومات.

## إجابات سريعة
- **ماذا يمكنني إنشاء؟** مستند PostScript كامل الميزات مع رسومات محوّلة.  
- **ما المكتبة المطلوبة؟** Aspose.Page لـ .NET (متاحة للتحميل من الموقع الرسمي).  
- **كيف أحفظ الملف؟** استخدم `PsDocument.Save()` بعد تكوين حالات الرسومات.  
- **هل يمكنني تطبيق تحويلات متعددة؟** نعم – ادمجها باستخدام `Transform` أو استدعاءات متسلسلة.  
- **هل تحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.

## ما هي عملية “حفظ ملف postscript”؟

حفظ ملف PostScript يعني تخزين أوامر الرسم التي أنشأتها في الذاكرة إلى ملف `.ps` على القرص. يمكن بعد ذلك أن يتم عرض الملف بواسطة أي مفسّر PostScript أو طابعة أو عارض.

## لماذا نستخدم Aspose.Page لـ .NET لإنشاء مستند postscript؟

توفر Aspose.Page واجهة برمجة تطبيقات عالية المستوى وغير معتمدة على الجهاز تُجرد الصياغة منخفضة المستوى للـ PostScript. ستحصل على:

- كائنات C# ذات نوعية قوية للمسارات، والفرش، والتحويلات.  
- معالجة تلقائية لمكدس حالة الرسومات (حفظ/استعادة).  
- دعم كامل لمصفوفات التحويل المعقدة دون الحاجة إلى حسابات يدوية.  

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود:

- مكتبة **Aspose.Page لـ .NET** مدمجة في مشروعك. احصل عليها من [رابط التحميل](https://releases.aspose.com/page/net/).  
- مجلد قابل للكتابة حيث سيتم تخزين ملف `.ps` المُولَّد. استبدل مسار العنصر النائب في الشيفرة بالمسار الفعلي لديك.

## استيراد المساحات الاسمية

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

الآن دعنا نستكشف كل خطوة من خطوات التحويل خطوة بخطوة.

## بدون تحويلات

### الخطوة 1: إنشاء تدفق الإخراج

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

هذا المقتطف ينشئ **مستند PostScript** يحتوي على مستطيل برتقالي واحد و**يحفظ ملف PostScript** دون تطبيق أي تحويلات.

## الإزاحة (Translation)

### الخطوة 1: حفظ حالة الرسومات

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

حفظ حالة الرسومات يتيح لك الرجوع بعد تحريك الكائنات.

### الخطوة 2: إزاحة حالة الرسومات

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

الإزاحة تنقل كل ما يُرسم بعد هذا الاستدعاء 250 وحدة إلى اليمين.

### الخطوة 3: ملء المستطيل بتحويل الإزاحة

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

الآن يظهر مستطيل أزرق على بعد 250 نقطة إلى يمين المستطيل البرتقالي.

### الخطوة 4: استعادة حالة الرسومات

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

الاستعادة تُعيد نظام الإحداثيات إلى وضعه الأصلي، بحيث لا يتأثر الرسم اللاحق بالإزاحة.

## التحجيم (Scaling)

> *يمكنك اتباع النمط نفسه — حفظ الحالة، تطبيق `Scale`، الرسم، ثم الاستعادة.*  
> **نصيحة احترافية:** استخدم التحجيم غير المتساوي (`Scale(sx, sy)`) لتمديد الكائنات في اتجاه واحد فقط.

## الدوران (Rotation)

> *قم بالدوران حول الأصل أو نقطة محورية مخصصة باستخدام `Rotate(angle)`.*
> **نصيحة احترافية:** ادمج `Translate` قبل الدوران لتدوير الكائن حول نقطة معينة.

## القص (Shearing)

> *تحويلات القص (`Shear(shx, shy)`) تميل الأشكال، مفيدة لتأثيرات المائل.*  

## التحويلات المعقدة

> *للحالات المتقدمة، أنشئ مصفوفة `Matrix` مخصصة ومرّرها إلى `Transform(matrix)`.*
> هنا يمكنك **تطبيق تحويلات متعددة** في خطوة واحدة.

## الخلاصة

لقد تعلمت كيفية **حفظ ملف PostScript**، **إنشاء مستند PostScript**، و**تطبيق تحويلات متعددة** باستخدام Aspose.Page لـ .NET. جرّب ترتيب التحويلات بطرق مختلفة، ادمجها، وشاهد كيف تتطور الرسومات.

## الأسئلة المتكررة

**س: كيف يمكنني تطبيق تحويلات متعددة على كائن واحد؟**  
ج: استخدم طريقة `Transform` مع مصفوفة `Matrix` مخصصة تجمع بين الإزاحة، والتحجيم، والدوران، أو القص بالترتيب الذي تحتاجه.

**س: هل يمكنني معاينة التحويلات قبل حفظ المستند؟**  
ج: نعم — قم بتحويل `PsDocument` إلى صورة أو استخدم عارض PostScript لتفقد النتيجة قبل استدعاء `Save()`.

**س: هل يمكن تطبيق التحويلات على عناصر محددة في المستند؟**  
ج: بالطبع. احفظ حالة الرسومات قبل رسم العنصر، طبّق التحويل المطلوب، ارسم، ثم استعد الحالة.

**س: هل هناك اعتبارات أداء عند التعامل مع تحويلات معقدة؟**  
ج: المصفوفات المعقدة تزيد من عبء المعالج. حافظ على بساطة التحويلات قدر الإمكان وأعد استخدام الحالات المحفوظة عند رسم العديد من الكائنات المتشابهة.

**س: كيف يمكنني الحصول على دعم أو مساعدة بخصوص استفسارات Aspose.Page؟**  
ج: زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على مساعدة المجتمع، أو تواصل مباشرة مع دعم Aspose.

---

**آخر تحديث:** 2026-01-12  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}