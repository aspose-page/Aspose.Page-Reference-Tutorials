---
title: تحويلات PS مع Aspose.Page لـ .NET
linktitle: التحولات PS
second_title: Aspose.Page .NET API
description: أطلق العنان لإمكانات Aspose.Page لـ .NET باستخدام هذا الدليل الشامل حول تحويلات PostScript. قم بإنشاء رسومات ديناميكية دون عناء.
weight: 12
url: /ar/net/canvas-manipulation/transformationsps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويلات PS مع Aspose.Page لـ .NET

## مقدمة

مرحبًا بك في عالم Aspose.Page for .NET، حيث يمكنك إطلاق العنان لقوة التحولات في مستندات PostScript. سيرشدك هذا البرنامج التعليمي خلال التحويلات المختلفة مثل الترجمة والقياس والتدوير والقص والتحويلات المعقدة، مما يسمح لك بإنشاء رسومات مذهلة وديناميكية.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Page for .NET Library: تأكد من دمج مكتبة Aspose.Page for .NET في مشروعك. يمكنك تنزيله من[رابط التحميل](https://releases.aspose.com/page/net/).

- دليل المستندات: قم بإعداد دليل لمستنداتك واستبدل العنصر النائب في الكود بالمسار الفعلي.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، قم باستيراد مساحات الأسماء الضرورية للعمل مع Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

الآن، دعونا نقسم كل مثال إلى خطوات متعددة بتنسيق دليل خطوة بخطوة.


## لا التحولات

### الخطوة 1: إنشاء دفق الإخراج

```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";

// إنشاء دفق الإخراج لمستند بوستسكريبت
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // إنشاء خيارات الحفظ بالقيم الافتراضية
    PsSaveOptions options = new PsSaveOptions();

    // قم بإنشاء مستند PS جديد مكون من صفحة واحدة
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // إنشاء مسار الرسومات من المستطيل
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // اضبط الطلاء في حالة الرسومات في المستوى العلوي
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // املأ المستطيل الأول الموجود في حالة الرسومات ذات المستوى العلوي وبدون أي تحويلات
    document.Fill(path);

    // إغلاق الصفحة الحالية
    document.ClosePage();

    // احفظ المستند
    document.Save();
}
```

ينشئ هذا الرمز مستند PostScript بدون أي تحويلات، ويملأ المستطيل باللون البرتقالي.

## ترجمة

### الخطوة 1: حفظ حالة الرسومات

```csharp
// احفظ حالة الرسومات للعودة إلى هذه الحالة بعد التحويل
document.WriteGraphicsSave();
```

تعمل هذه الخطوة على حفظ حالة الرسومات الحالية، مما يسمح لنا بالعودة إليها بعد التحويل.

### الخطوة 2: ترجمة حالة الرسومات

```csharp
// قم بإزاحة حالة الرسومات الحالية 250 إلى اليمين
document.Translate(250, 0);
```

قم بترجمة حالة الرسومات الحالية عن طريق إضافة مكون ترجمة، ثم قم بتعيين الطلاء في حالة الرسومات الحالية إلى اللون الأزرق.

### الخطوة 3: املأ المستطيل بتحويل الترجمة

```csharp
// اضبط الطلاء على حالة الرسومات الحالية
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// املأ المستطيل الثاني في حالة الرسومات الحالية (يحتوي على تحويل ترجمة)
document.Fill(path);
```

تقوم هذه الخطوة بملء المستطيل الثاني في حالة الرسومات الحالية، والذي يتضمن الآن تحويل الترجمة.

### الخطوة 4: استعادة حالة الرسومات

```csharp
// استعادة حالة الرسومات إلى المستوى السابق (العلوي).
document.WriteGraphicsRestore();
```

بعد ملء المستطيل، قم باستعادة حالة الرسومات إلى المستوى السابق.

تابع هذا الدليل التفصيلي خطوة بخطوة لكل نوع تحويل، بما في ذلك القياس والتدوير والقص والتحويلات المعقدة.

## خاتمة

تهانينا! لقد نجحت في التنقل عبر الإمكانات التحويلية لـ Aspose.Page لـ .NET. الآن، قم بتجربة مجموعات مختلفة وأطلق العنان لإبداعك في تحويلات مستندات PostScript.

## الأسئلة الشائعة

### س1: كيف يمكنني تطبيق تحويلات متعددة على كائن واحد؟

A1: لتطبيق تحويلات متعددة، استخدم`Transform` الطريقة مع مصفوفة تحويل مخصصة.

### س2: هل يمكنني معاينة التحويلات قبل حفظ المستند؟

ج2: نعم، يمكنك تصور التحويلات عن طريق عرض المستند ومعاينته في عارض مناسب.

### س3: هل من الممكن تطبيق التحويلات على عناصر محددة في المستند؟

A3: نعم، يمكنك عزل التحويلات إلى عناصر رسومية معينة داخل المستند.

### س 4: هل هناك أي اعتبارات للأداء عند التعامل مع التحويلات المعقدة؟

ج4: قد تؤثر التحويلات المعقدة على الأداء، لذا قم بتحسين التعليمات البرمجية لتحقيق الكفاءة.

### س5: كيف يمكنني الحصول على الدعم أو طلب المساعدة فيما يتعلق بالاستعلامات المتعلقة بـ Aspose.Page؟

 ج5: قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) لدعم المجتمع والمناقشات.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
