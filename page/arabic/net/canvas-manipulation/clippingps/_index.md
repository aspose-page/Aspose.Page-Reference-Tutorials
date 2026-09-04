---
date: 2026-06-25
description: تعلم كيفية إضافة مسار قص في PostScript باستخدام Aspose.Page لـ .NET –
  دليل خطوة بخطوة مع تقنيات فرشاة الرسم والمستطيل المتقطع.
keywords:
- how to add clipping path
- Aspose.Page clipping
- PostScript graphics .NET
linktitle: قص PS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add clipping path in PostScript using Aspose.Page for
    .NET – step‑by‑step guide with paint brush and dashed rectangle techniques.
  headline: How to Add Clipping Path to PostScript with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to add clipping path in PostScript using Aspose.Page for
    .NET – step‑by‑step guide with paint brush and dashed rectangle techniques.
  name: How to Add Clipping Path to PostScript with Aspose.Page for .NET
  steps:
  - name: Set Document Directory
    text: Define the folder where your source and output files will live. This makes
      it easy to locate the generated PS file later.
  - name: Create Output Stream for PostScript Document
    text: Create a writable stream that will hold the generated PS file. Using a `FileStream`
      ensures the file is written directly to disk.
  - name: Create Save Options
    text: '`PsSaveOptions` is Aspose.Page’s configuration object for PS output. It
      lets you control compression, version, and other rendering details.'
  - name: Create a New 1‑Paged PS Document
    text: '`PsDocument` represents a PostScript document object. You instantiate it
      with the output stream and the save options you just configured.'
  - name: Create Graphics Path from the Rectangle
    text: '`GraphicsPath` is a vector container for geometric shapes. Here we start
      with a simple rectangle that will later be clipped.'
  - name: Clipping by Shape
    text: We add a clipping path using a circle, set the paint brush to blue, and
      fill the rectangle within the clipped region. This demonstrates how clipping
      limits drawing to the circle’s interior.
  - name: Displace Upper Level Graphics State & Draw Dashed Rectangle
    text: After restoring the previous graphics state, we translate the cursor, create
      a `Pen` with `DashStyle.Dash`, and draw a dashed rectangle around the clipped
      content. The blue stroke highlights the clipping boundary. `Pen` defines stroke
      attributes such as color and dash style. `DashStyle.Dash` specifi
  - name: Close and Save Document
    text: Finish the page, flush the stream, and dispose of resources. The PS file
      is now written to disk and ready for viewing in any PostScript viewer. You have
      now successfully **added clipping path**, set a custom paint brush, and drawn
      a dashed rectangle around your graphics using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: It restricts drawing operations to a defined shape, hiding everything
      outside that shape.
    question: What does “add clipping path” do?
  - answer: Aspose.Page for .NET provides a rich API for PS/EPS manipulation.
    question: Which library handles clipping in .NET?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes, use `SetPaint` with any `SolidBrush` or gradient you prefer.
    question: Can I change the brush color?
  - answer: Absolutely – create a `Pen` with `DashStyle.Dash` and use `Draw`.
    question: Is drawing a dashed rectangle possible?
  type: FAQPage
second_title: Aspose.Page .NET API
title: كيفية إضافة مسار قص إلى PostScript باستخدام Aspose.Page لـ .NET
url: /ar/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة مسار قص إلى PostScript باستخدام Aspose.Page لـ .NET

## مقدمة

في هذا الدرس الشامل ستتعلم **كيفية إضافة مسار قص** إلى مستند PostScript (PS) باستخدام Aspose.Page لـ .NET. سنستعرض كل خطوة، نوضح لك كيفية **تعيين فرشاة رسم**، ونظهر لك كيفية **رسم مستطيل متقطع** حول المحتوى المقص. في النهاية ستحصل على ملف PS يعمل بالكامل يوضح القص بالشكل، مما يمنح رسوماتك مظهرًا أكثر ديناميكية واحترافية.

## إجابات سريعة
- **ماذا يفعل “إضافة مسار قص”؟** يقتصر عمليات الرسم على شكل محدد، ويخفي كل ما هو خارج ذلك الشكل.  
- **أي مكتبة تتعامل مع القص في .NET؟** Aspose.Page لـ .NET توفر واجهة برمجة تطبيقات غنية لمعالجة PS/EPS.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ يتطلب الترخيص التجاري للإنتاج.  
- **هل يمكنني تغيير لون الفرشاة؟** نعم، استخدم `SetPaint` مع أي `SolidBrush` أو تدرج تفضله.  
- **هل يمكن رسم مستطيل متقطع؟** بالتأكيد – أنشئ `Pen` مع `DashStyle.Dash` واستخدم `Draw`.  

## ما هو مسار القص في PostScript؟

مسار القص يحدد المنطقة المرئية لأوامر الرسم اللاحقة، ويتجاهل أي شيء يتم رسمه خارج حدوده. عمليًا، يسمح لك بقناع الرسومات بحيث يُظهر فقط الجزء داخل المسار، وهو أمر أساسي لإنشاء تركيبات معقدة دون تعديل دائم للكائنات الأصلية.

## كيفية إضافة مسار قص إلى مستند PostScript باستخدام Aspose.Page؟

قم بتحميل `PsDocument`، عرّف مسار رسومي (على سبيل المثال، دائرة)، طبق `Clip()` لتقييد منطقة الرسم، ثم استخدم `SetPaint` و `Fill` لرسم المحتوى داخل المنطقة المقصوصة. بعد استعادة حالة الرسوم يمكنك رسم أشكال إضافية—مثل مستطيل متقطع—دون التأثير على المنطقة المقصوصة. هذه السلسلة من الخطوات تنفذ القص ببضع نداءات API مختصرة.

`PsDocument` يمثل كائن مستند PostScript.  
`GraphicsPath` هو حاوية متجهة للأشكال الهندسية.  
`Clip()` يحدد منطقة القص للرسم اللاحق.  
`SetPaint` يعيّن فرشاة تُستخدم لملء الأشكال.  
`Fill` يرسم المسار الحالي باستخدام اللون الحالي.

## لماذا تستخدم Aspose.Page للقص؟

تدعم Aspose.Page **أكثر من 50 تنسيق إدخال وإخراج**، بما في ذلك PS و EPS و PDF و SVG وأنواع الصور، ويمكنها معالجة مستندات مئات الصفحات دون تحميل الملف بالكامل في الذاكرة. المكتبة لا تحتاج إلى **أي تبعيات خارجية**، وتعمل على **.NET Framework 4.5+** و **.NET Core 3.1+** و **.NET 6+**، وتوفر تحكمًا كاملاً في حالة الرسوم (حفظ/استعادة، ترجمة، تدوير). هذه الفوائد الم quantified تجعلها خيارًا موثوقًا لتوليد الرسومات على الخادم.

## المتطلبات المسبقة

- معرفة أساسية ببرمجة C#.  
- مكتبة Aspose.Page لـ .NET مثبتة – يمكنك تنزيلها [هنا](https://releases.aspose.com/page/net/).  
- Visual Studio أو أي بيئة تطوير .NET مفضلة.  

## استيراد المساحات الاسمية

المساحات الاسمية التالية تمنحك الوصول إلى كائنات الرسوم الأساسية وخيارات الحفظ الخاصة بـ PS.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

الآن دعنا نفصل المثال إلى خطوات واضحة مرقمة.

### الخطوة 1: تعيين دليل المستند

حدد المجلد الذي ستعيش فيه ملفات المصدر والإخراج. هذا يجعل من السهل العثور على ملف PS المُولد لاحقًا.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### الخطوة 2: إنشاء تدفق إخراج لمستند PostScript

أنشئ تدفقًا قابلًا للكتابة سيحتوي على ملف PS المُولد. استخدام `FileStream` يضمن كتابة الملف مباشرة إلى القرص.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### الخطوة 3: إنشاء خيارات الحفظ

`PsSaveOptions` هو كائن تكوين Aspose.Page لإخراج PS. يتيح لك التحكم في الضغط والإصدار وتفاصيل العرض الأخرى.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### الخطوة 4: إنشاء مستند PS بصفحة واحدة جديد

`PsDocument` يمثل كائن مستند PostScript. تقوم بإنشائه باستخدام تدفق الإخراج وخيارات الحفظ التي قمت بتكوينها للتو.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### الخطوة 5: إنشاء مسار رسومي من المستطيل

`GraphicsPath` هو حاوية متجهة للأشكال الهندسية. هنا نبدأ بمستطيل بسيط سيُقص لاحقًا.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### الخطوة 6: القص بالشكل

نضيف مسار قص باستخدام دائرة، نعيّن فرشاة اللون إلى الأزرق، ونملأ المستطيل داخل المنطقة المقصوصة. هذا يوضح كيف يحدّ القص من الرسم داخل داخل الدائرة.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### الخطوة 7: إزاحة حالة الرسوم العليا ورسم مستطيل متقطع

بعد استعادة حالة الرسوم السابقة، نقوم بترجمة المؤشر، إنشاء `Pen` مع `DashStyle.Dash`، ورسم مستطيل متقطع حول المحتوى المقصوص. يبرز الحد الأزرق حدود القص.

`Pen` يحدد خصائص الخط مثل اللون ونمط القطع.  
`DashStyle.Dash` يحدد نمط الخط المتقطع.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### الخطوة 8: إغلاق وحفظ المستند

أكمل الصفحة، أفرغ التدفق، وتخلص من الموارد. الآن تم كتابة ملف PS إلى القرص وجاهز للعرض في أي عارض PostScript.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

الآن لقد نجحت في **إضافة مسار قص**، تعيين فرشاة رسم مخصصة، ورسم مستطيل متقطع حول رسوماتك باستخدام Aspose.Page لـ .NET.

## المشكلات الشائعة والحلول

- **القص غير مرئي:** تأكد من استدعاء `WriteGraphicsSave()` قبل الترجمة و`WriteGraphicsRestore()` بعد الملء.  
- **الألوان غير صحيحة:** تحقق من أن `SetPaint` يتم استدعاؤه بعد `Clip` وقبل `Fill`.  
- **الخطوط المتقطعة تظهر صلبة:** تأكد من ضبط `DashStyle` للـ `Pen` إلى `DashStyle.Dash` قبل `SetStroke`.  

## الأسئلة المتكررة

### س1: هل يمكنني استخدام Aspose.Page لـ .NET مع لغات برمجة أخرى؟

ج: Aspose.Page مصممة أساسًا لتطبيقات .NET، لكن Aspose تقدم مكتبات مكافئة لـ Java و C++ وغيرها من المنصات.

### س2: أين يمكنني العثور على أمثلة إضافية ووثائق Aspose.Page لـ .NET؟

ج: يمكنك استكشاف المزيد من الأمثلة والوثائق التفصيلية على [توثيق Aspose.Page](https://reference.aspose.com/page/net/).

### س3: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page لـ .NET؟

ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Page لـ .NET [هنا](https://releases.aspose.com/).

### س4: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟

ج: يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### س5: أين يمكنني الحصول على الدعم أو مناقشة استفسارات متعلقة بـ Aspose.Page؟

ج: زر [منتديات Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع والمناقشات.

---

**آخر تحديث:** 2026-06-25  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء مستند PostScript باستخدام Aspose.Page لـ .NET](/page/net/document-creation/create-postscript-document/)
- [حفظ ملف PostScript باستخدام تحويلات Aspose.Page (.NET)](/page/net/canvas-manipulation/transformationsps/)
- [إنشاء مستند postscript .net – إضافة مستطيل باستخدام Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}