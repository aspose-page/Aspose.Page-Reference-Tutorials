---
date: 2026-01-05
description: تعلم كيفية إضافة مسار قص في PostScript باستخدام Aspose.Page لـ .NET –
  دليل خطوة بخطوة مع تقنيات تعيين فرشاة الرسم ورسم مستطيل متقطع.
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: إضافة مسار قص إلى PS باستخدام Aspose.Page لـ .NET
url: /ar/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مسار قص إلى PS باستخدام Aspose.Page لـ .NET

## المقدمة

في هذا الدرس الشامل ستكتشف كيفية **إضافة مسار قص** إلى مستند PostScript (PS) باستخدام Aspose.Page لـ .NET. سنستعرض كل خطوة، ونوضح لك كيفية **تعيين فرشاة الرسم**، ونظهر لك كيفية **رسم مستطيل متقطع** حول المحتوى المقصوص. في النهاية، ستحصل على ملف PS يعمل بالكامل يوضح القص بالشكل، مما يجعل رسوماتك أكثر ديناميكية واحترافية.

## إجابات سريعة
- **ماذا يفعل “إضافة مسار قص”؟** يقتصر عمليات الرسم على شكل محدد، ويخفي كل ما هو خارج ذلك الشكل.  
- **أي مكتبة تتعامل مع القص في .NET؟** توفر Aspose.Page لـ .NET واجهة برمجة تطبيقات غنية لمعالجة PS/EPS.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتطوير؛ يتطلب الترخيص التجاري للإنتاج.  
- **هل يمكنني تغيير لون الفرشاة؟** نعم، استخدم `SetPaint` مع أي `SolidBrush` أو تدرج تفضله.  
- **هل يمكن رسم مستطيل متقطع؟** بالتأكيد – أنشئ `Pen` مع `DashStyle.Dash` واستخدم `Draw`.  

## ما هو مسار القص في PostScript؟
مسار القص هو ما يحدد المنطقة المرئية لأوامر الرسم اللاحقة. أي شيء يُرسم خارج المسار يتم تجاهله، مما يتيح لك إنشاء رسومات مقنَّفة معقدة دون تعديل المحتوى الأصلي.

## لماذا نستخدم Aspose.Page للقص؟
- **بدون تبعيات خارجية** – مكتبة .NET خالصة.  
- **تحكم كامل** في حالة الرسومات (حفظ/استعادة، ترجمة، تدوير).  
- **بدائل رسم غنية** مثل `SetPaint` و `Clip` و `Draw` مع أقلام وفرش قابلة للتخصيص.  

## المتطلبات المسبقة

- معرفة أساسية ببرمجة C#.  
- مكتبة Aspose.Page لـ .NET مثبتة – يمكنك تنزيلها [هنا](https://releases.aspose.com/page/net/).  
- Visual Studio أو أي بيئة تطوير .NET مفضلة.  

## استيراد المساحات الاسمية

أولاً، استورد المساحات الاسمية المطلوبة لمعالجة الرسومات:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

الآن لنقسم المثال إلى خطوات واضحة مرقمة.

### الخطوة 1: تعيين دليل المستند

حدد المجلد الذي ستعيش فيه ملفات المصدر والإخراج الخاصة بك.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### الخطوة 2: إنشاء تدفق إخراج لمستند PostScript

أنشئ تدفقًا قابلًا للكتابة سيحمل ملف PS المُولد.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### الخطوة 3: إنشاء خيارات الحفظ

أنشئ كائن `PsSaveOptions` بالإعدادات الافتراضية. يمكنك تخصيصه لاحقًا إذا لزم الأمر.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### الخطوة 4: إنشاء مستند PS بصفحة واحدة

ابدأ كائن `PsDocument` الذي يمثل ملف PS الخاص بك.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### الخطوة 5: إنشاء مسار رسومي من المستطيل

سنستخدم مستطيلًا كالشكل الأساسي الذي سيُقص لاحقًا.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### الخطوة 6: القص بالشكل

هنا **نضيف مسار قص** باستخدام دائرة، **نعيّن فرشاة الرسم** إلى اللون الأزرق، ونملأ المستطيل داخل المنطقة المقصوصة.

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

### الخطوة 7: إزاحة حالة الرسومات العليا ورسم مستطيل متقطع

بعد استعادة الحالة السابقة، نحرك مؤشر الرسومات مرة أخرى، **نرسم مستطيلًا متقطعًا**، ونطبق حدًا أزرق.

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

أكمل الصفحة واكتب ملف PS إلى القرص.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

لقد نجحت الآن في **إضافة مسار قص**، وتعيين فرشاة رسم مخصصة، ورسم مستطيل متقطع حول رسوماتك باستخدام Aspose.Page لـ .NET.

## المشكلات الشائعة والحلول

- **القص غير مرئي:** تأكد من استدعاء `WriteGraphicsSave()` قبل الترجمة و `WriteGraphicsRestore()` بعد التعبئة.  
- **ألوان غير صحيحة:** تحقق من أن `SetPaint` يتم استدعاؤه بعد `Clip` وقبل `Fill`.  
- **الخطوط المتقطعة تظهر صلبة:** تأكد من ضبط `DashStyle` للـ `Pen` إلى `DashStyle.Dash` قبل `SetStroke`.  

## الأسئلة المتكررة

### س1: هل يمكنني استخدام Aspose.Page لـ .NET مع لغات برمجة أخرى؟
ج: تم تصميم Aspose.Page أساسًا لتطبيقات .NET. ومع ذلك، توفر Aspose مكتبات مماثلة للغات برمجة أخرى.

### س2: أين يمكنني العثور على أمثلة إضافية وتوثيق Aspose.Page لـ .NET؟
يمكنك استكشاف المزيد من الأمثلة والتوثيق التفصيلي على [توثيق Aspose.Page](https://reference.aspose.com/page/net/).

### س3: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page لـ .NET؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Page لـ .NET [هنا](https://releases.aspose.com/).

### س4: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### س5: أين يمكنني الحصول على الدعم أو مناقشة استفسارات متعلقة بـ Aspose.Page؟
قم بزيارة [منتديات Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع والمناقشات.

---

**آخر تحديث:** 2026-01-05  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}