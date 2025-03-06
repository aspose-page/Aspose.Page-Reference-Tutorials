---
title: أضف التدرج الأفقي إلى PostScript (PS) باستخدام Aspose.Page
linktitle: إضافة التدرج الأفقي إلى بوستسكريبت (PS)
second_title: Aspose.Page .NET API
description: قم بتحسين مستندات PostScript بتدرجات أفقية مذهلة باستخدام Aspose.Page لـ .NET. اتبع برنامجنا التعليمي خطوة بخطوة للتنفيذ السلس.
weight: 12
url: /ar/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# أضف التدرج الأفقي إلى PostScript (PS) باستخدام Aspose.Page

## مقدمة

مرحبًا بك في هذا البرنامج التعليمي الشامل حول إضافة التدرجات الأفقية إلى مستندات PostScript (PS) باستخدام Aspose.Page for .NET. Aspose.Page هي مكتبة قوية تسهل معالجة المستندات بتنسيقات مختلفة، مما يوفر للمطورين الأدوات التي يحتاجونها لإنشاء المستندات وتعديلها وعرضها بسلاسة.

في هذا البرنامج التعليمي، سوف نركز على تحسين مستندات PostScript الخاصة بك عن طريق دمج التدرجات الأفقية الجذابة. سنرشدك خلال كل خطوة من العملية، مما يضمن حصولك على فهم قوي للتنفيذ.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Page for .NET Library: تأكد من دمج مكتبة Aspose.Page for .NET في بيئة التطوير الخاصة بك. يمكنك تنزيله من[Aspose.Page لوثائق .NET](https://reference.aspose.com/page/net/).

- دليل المستندات: قم بإعداد دليل لتخزين مستنداتك، واستبدل "دليل المستندات الخاص بك" في الكود المقدم بالمسار الفعلي.

الآن، دعونا نستكشف كيفية إضافة تدرج أفقي إلى مستند PostScript خطوة بخطوة.

## استيراد مساحات الأسماء

قبل أن تبدأ، من الضروري استيراد مساحات الأسماء الضرورية للوصول إلى الوظائف التي يوفرها Aspose.Page. أضف مساحات الأسماء التالية في بداية التعليمات البرمجية الخاصة بك:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## الخطوة 1: إعداد المستند

```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";

// إنشاء دفق الإخراج لمستند بوستسكريبت
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // إنشاء خيارات الحفظ بحجم A4
    PsSaveOptions options = new PsSaveOptions();

    // قم بإنشاء مستند PS جديد مكون من صفحة واحدة
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 2: تحديد مستطيل التدرج والألوان

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // قم بإنشاء مسار الرسومات من المستطيل الأول
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    //قم بإنشاء فرشاة متدرجة خطية باستخدام المستطيل كحدود وألوان البداية والنهاية
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## الخطوة 3: ضبط التحويل للفرشاة

```csharp
    // إنشاء تحويل للفرشاة. يجب أن يكون مكون المقياس X وY مساويًا لعرض المستطيل وارتفاعه على التوالي.
    // مكونات الترجمة هي إزاحات المستطيل
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // تعيين التحويل
    brush.Transform = brushTransform;
```

## الخطوة 4: اضبط الطلاء واملأ المستطيل

```csharp
    // تعيين الطلاء
    document.SetPaint(brush);

    // املأ المستطيل
    document.Fill(path);
```

## الخطوة 5: املأ النص بالتدرج

```csharp
    // تعبئة النص بالتدرج
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## الخطوة 6: تعيين السكتة الدماغية والنص المخطط التفصيلي

```csharp
    // ضبط السكتة الدماغية الحالية
    document.SetStroke(new Pen(brush, 5));
    // مخطط تفصيلي للنص مع التدرج
    document.OutlineText("ABC", font, 200, 400);
```

## الخطوة 7: أغلق الصفحة الحالية واحفظ المستند

```csharp
    // إغلاق الصفحة الحالية
    document.ClosePage();

    // احفظ المستند
    document.Save();
}
```

تهانينا! لقد نجحت في إضافة تدرج أفقي إلى مستند PostScript باستخدام Aspose.Page لـ .NET.

## خاتمة

في هذا البرنامج التعليمي، قمنا بتغطية عملية تحسين مستندات PostScript الخاصة بك باستخدام التدرجات الأفقية باستخدام مكتبة Aspose.Page for .NET. باتباع الدليل الموضح خطوة بخطوة، اكتسبت رؤى قيمة حول الاستفادة من هذه الأداة القوية لمعالجة المستندات.

## الأسئلة الشائعة

### س1: هل يمكنني تطبيق التدرجات على أشكال أخرى إلى جانب المستطيلات؟

 A1: نعم، يمكنك تطبيق التدرجات على الأشكال المختلفة باستخدام Aspose.Page. تعديل`GraphicsPath` الخلق لتناسب الشكل المحدد الخاص بك.

### س2: كيف يمكنني تغيير الألوان المتدرجة؟

 ج2: اضبط`Color.FromArgb` القيم في`LinearGradientBrush` إنشاء مثيل لتحقيق الألوان التدرج المطلوب.

### س3: هل Aspose.Page متوافق مع تنسيقات المستندات المختلفة؟

ج3: يدعم Aspose.Page تنسيقات المستندات المختلفة، بما في ذلك XPS وPS وPDF والمزيد. الرجوع إلى الوثائق للحصول على قائمة شاملة.

### س4: هل يمكنني استخدام Aspose.Page للمشاريع التجارية؟

 ج4: نعم، يأتي Aspose.Page مزودًا بخيارات الترخيص التجاري. يزور[هنا](https://purchase.aspose.com/buy) للتفاصيل.

### س5: هل يوجد منتدى مجتمعي لمستخدمي Aspose.Page؟

 ج5: نعم، انضم إلى مجتمع Aspose.Page على[Aspose.صفحة المنتدى](https://forum.aspose.com/c/page/39) للتواصل مع المستخدمين الآخرين وطلب المساعدة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
