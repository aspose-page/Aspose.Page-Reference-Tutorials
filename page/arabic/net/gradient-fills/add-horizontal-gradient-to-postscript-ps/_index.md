---
date: 2026-02-25
description: عزّز مستندات PostScript بمستطيل تدرج خطي باستخدام Aspose.Page لـ .NET.
  اتبع دليلنا خطوة بخطوة لتعلم تعبئة النص بالتدرج وتدرج حدود النص.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: إضافة مستطيل بتدرج لوني خطي إلى PostScript (PS) باستخدام Aspose.Page
url: /ar/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مستطيل تدرج خطي إلى PostScript (PS) باستخدام Aspose.Page

## المقدمة

مرحبًا بكم في هذا الدرس الشامل حول إضافة **مستطيل تدرج خطي** إلى مستندات PostScript (PS) باستخدام Aspose.Page لـ .NET. Aspose.Page هي مكتبة قوية تتيح لك إنشاء وتعديل وعرض المستندات بمجموعة متنوعة من الصيغ، وسنركز اليوم على كيفية إدخال تدرجات جذابة بصريًا إلى ملفات PS الخاصة بك.

### إجابات سريعة
- **ماذا يفعل مستطيل التدرج الخطي؟** يملأ مساحة مستطيلة بانتقال سلس للألوان من جانب إلى آخر.  
- **أي API يتعامل مع تعبئة النص بالتدرج؟** `LinearGradientBrush` مع `SetPaint` و `FillAndStrokeText`.  
- **هل يمكنني تحديد حدود النص بتدرج؟** نعم—استخدم `SetStroke` مع فرشاة تدرج واستدعِ `OutlineText`.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يتطلب الاستخدام غير التجريبي ترخيص تجاري لـ Aspose.Page.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

- مكتبة Aspose.Page لـ .NET: تأكد من إضافة المكتبة إلى مشروعك. يمكنك تنزيلها من [توثيق Aspose.Page لـ .NET](https://reference.aspose.com/page/net/).
- دليل المستندات: أنشئ مجلدًا على القرص حيث سيتم حفظ ملف PS المُولد واستبدل **“Your Document Directory”** في الشيفرة بهذا المسار.

## استيراد المساحات الاسمية

لبدء العمل، استورد المساحات الاسمية التي تمنحك الوصول إلى فئات الرسم والفئات الخاصة بـ PS:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## ما هو مستطيل التدرج الخطي؟

**مستطيل التدرج الخطي** هو ببساطة شكل مستطيل يُطلّق داخله تدرج خطي—تنتقل الألوان بسلاسة على طول خط مستقيم، عادةً من اليسار إلى اليمين (أفقي) أو من الأعلى إلى الأسفل (عمودي). في Aspose.Page يمكنك تحقيق ذلك بدمج `GraphicsPath` الذي يحدد المستطيل مع `LinearGradientBrush` الذي يصف انتقال اللون.

## لماذا نستخدم تعبئة النص بالتدرج وتدرج حدود النص؟

- **جاذبية بصرية:** يضيف النص المملوء بالتدرج عمقًا وأسلوبًا حديثًا إلى التقارير، الفواتير، أو المواد الترويجية.  
- **اتساق العلامة التجارية:** طابق ألوان الشركة باستخدام قيم ARGB الدقيقة.  
- **مرونة:** يمكن إعادة استخدام نفس الفرشاة لتعبئة الأشكال، تعبئة النص، وتدرج حدود النص، مما يقلل من تكرار الشيفرة.

## الخطوة 1: إعداد المستند

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 2: تعريف مستطيل التدرج والألوان

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## الخطوة 3: ضبط التحويل للفرشاة

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## الخطوة 4: ضبط الطلاء وتعبئة المستطيل

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## كيفية تطبيق تعبئة النص بالتدرج

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## استخدام تدرج حدود النص

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## الخطوة 7: إغلاق الصفحة الحالية وحفظ المستند

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

تهانينا! لقد أضفت بنجاح **مستطيل تدرج خطي** إلى مستند PostScript واستخدمت نفس الفرشاة لـ **تعبئة النص بالتدرج** و**تدرج حدود النص**.

## حالات الاستخدام الشائعة والنصائح

- **عناوين التقارير:** املأ كتل النص الكبيرة بالتدرجات لتسليط الضوء على عناوين الأقسام.  
- **شعارات العلامة التجارية:** أعد إنشاء أشكال الشعار باستخدام تعبئة التدرج للحصول على هوية بصرية متسقة.  
- **نصيحة احترافية:** أعد استخدام نفس كائن `LinearGradientBrush` لعدة استدعاءات رسم للحفاظ على توافق الألوان بين الأشكال والنصوص.

## الأسئلة المتكررة

### س1: هل يمكنني تطبيق التدرجات على أشكال أخرى غير المستطيلات؟
**ج:** نعم، يمكنك تطبيق التدرجات على أي شكل يُحدده `GraphicsPath`. ما عليك سوى إضافة دوائر أو مضلعات أو مسارات مخصصة قبل استدعاء `document.Fill(path)`.

### س2: كيف يمكنني تغيير ألوان التدرج؟
**ج:** عدّل قيم `Color.FromArgb` عند إنشاء `LinearGradientBrush`. اللون الأول هو بداية التدرج، والثاني هو نهايته.

### س3: هل Aspose.Page متوافق مع صيغ مستندات مختلفة؟
**ج:** بالتأكيد. يدعم Aspose.Page صيغ XPS، PS، PDF، والعديد من صيغ المتجهات الأخرى. راجع الوثائق الرسمية للقائمة الكاملة.

### س4: هل يمكنني استخدام Aspose.Page في مشاريع تجارية؟
**ج:** نعم، يتوفر ترخيص تجاري. راجع صفحة الشراء للتفاصيل: [here](https://purchase.aspose.com/buy).

### س5: أين يمكنني العثور على دعم المجتمع؟
**ج:** انضم إلى منتدى مجتمع Aspose.Page: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**آخر تحديث:** 2026-02-25  
**تم الاختبار مع:** Aspose.Page 24.10 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}