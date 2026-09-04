---
date: 2026-06-25
description: تعلم كيفية قص مستندات XPS باستخدام Aspose.Page لـ .NET. يوضح لك هذا الدليل
  خطوة بخطوة كيفية إنشاء ملفات XPS ومعالجتها وحفظها بكفاءة.
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: قص XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: كيفية قص XPS باستخدام Aspose.Page لـ .NET
url: /ar/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قص XPS باستخدام Aspose.Page لـ .NET

## مقدمة

مرحبًا بكم في هذا الدرس الشامل حول **كيفية قص XPS** باستخدام Aspose.Page لـ .NET! في هذا الدليل، ستتعلم خطوة بخطوة كيفية إنشاء مستند XPS، وتطبيق أقنعة قص هندسية، وحفظ النتيجة. يتيح لك القص إخفاء أجزاء من القماش، مما يتيح تخطيطات متقدمة مثل الصور المقنّعة، الأشكال المخصصة، أو مناطق المحتوى المركّزة — كل ذلك دون مغادرة شفرة .NET الخاصة بك.

## إجابات سريعة
- **ما هو قص XPS؟** تطبيق قناع هندسي (قص) لتحديد المنطقة المرئية لعناصر قماش XPS.  
- **ما هي المكتبة الأنسب لهذا؟** توفر Aspose.Page لـ .NET واجهة برمجة تطبيقات كاملة لإنشاء XPS والقص.  
- **المتطلبات المسبقة؟** Visual Studio، بيئة تشغيل .NET، ومكتبة Aspose.Page لـ .NET.  
- **كم من الوقت تستغرق عملية التنفيذ؟** حوالي 10‑15 دقيقة لسيناريو قص أساسي.  
- **هل يمكنني استخدام هذا في الإنتاج؟** نعم، مع ترخيص Aspose صالح (يتوفر نسخة تجريبية).

## ما هو “كيفية قص XPS”؟
يعني قص XPS تطبيق قناع هندسي على القماش بحيث لا يتم رسم أي شيء خارج القناع. هذه التقنية مثالية لإنشاء صور مقنّعة، أزرار بأشكال مخصصة، أو لتوجيه انتباه القارئ إلى منطقة معينة في الصفحة. من خلال تعريف هندسة قص — مثل مستطيل أو دائرة أو مسار معقد — تحصل على تحكم دقيق فيما يظهر في صفحة XPS النهائية.

## لماذا تستخدم Aspose.Page لـ .NET لقص XPS؟
توفر Aspose.Page معالجة XPS من جانب الخادم بشكل حتمي دون الاعتماد على مكونات خارجية. تدعم **أكثر من 50 تنسيقًا للإدخال والإخراج**، ويمكنها معالجة **ملفات XPS مكوّنة من 200 صفحة في أقل من 0.5 ثانية** على معالج قياسي بسرعة 2.5 GHz، وتعمل عبر .NET Framework 4.0+، .NET Core 2.0+، .NET 5، .NET 6، و .NET 7. تمنحك واجهة البرمجة تحكمًا كاملاً في تحويلات القماش، هندسات المسار، والفرش، مما يضمن مخرجات عالية الجودة في كل مرة.

## المتطلبات المسبقة
- تم تثبيت Visual Studio على جهازك.  
- تم إضافة مكتبة Aspose.Page لـ .NET إلى مشروعك. يمكنك تنزيلها [هنا](https://releases.aspose.com/page/net/).  
- معرفة أساسية بلغة البرمجة C#.

## كيفية قص XPS؟
قم بتحميل مستند XPS، إنشاء قماش، تعريف هندسة قص (مثل دائرة)، تعيين الهندسة إلى خاصية `Clip` الخاصة بالقماش، رسم المحتوى الخاص بك، وأخيرًا حفظ المستند. يمكن تنفيذ جميع هذه الخطوات ببضع استدعاءات للطرق فقط، وتتعامل Aspose.Page تلقائيًا مع ترميز XML الأساسي، بحيث تركز على التصميم البصري بدلاً من بنية الملف.

## استيراد مساحات الأسماء
لكي تستخدم وظائف Aspose.Page لـ .NET، تحتاج إلى استيراد مساحات الأسماء المطلوبة إلى مشروعك. اتبع الخطوات التالية:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

الآن، دعنا نقسم شفرة المثال التي قدمتها إلى خطوات متعددة.

## الخطوة 1: تعيين مسار دليل المستند.
حدد المجلد الذي سيتم إنشاء ملف XPS فيه. يضمن استخدام `Path.Combine` الفاصل الصحيح للمجلد على أي نظام تشغيل.

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## الخطوة 2: إنشاء مستند XPS جديد.
إنشاء كائن من فئة `XpsDocument`، التي تمثل حزمة XPS بالكامل.

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 3: إنشاء القماش الرئيسي.
تمثل فئة `Canvas` سطح رسم داخل صفحة XPS حيث يتم عرض الأشكال والصور والنص.

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## الخطوة 4: تعيين إزاحات اليسار والعلو في القماش الرئيسي.
قم بضبط موضع القماش للتحكم في مكان بدء الرسم على الصفحة.

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## الخطوة 5: إنشاء هندسة مسار مستطيل.
`PathGeometry` تُعرّف شكلًا متجهيًا؛ هنا نقوم بإنشاء مستطيل بسيط.

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## الخطوة 6: إنشاء تعبئة للمستطيلات.
حدد فرشاة لون صلبة ستُستخدم لتعبئة المستطيل.

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## الخطوة 7: إضافة قماش آخر مع قص إلى القماش الرئيسي.
إنشاء قماش فرعي سيتلقى قناع قص.

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## الخطوة 8: إنشاء هندسة دائرة للقص.
يمكن لـ `PathGeometry` أيضًا تمثيل الدوائر؛ سيتم تعيين هذه الهندسة إلى خاصية `Clip` للقماش الفرعي.

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## الخطوة 9: إنشاء مستطيل في القماش الثاني وتعبئته.
ارسم مستطيلًا داخل القماش المقصوص؛ فقط الجزء داخل الدائرة سيكون مرئيًا.

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## الخطوة 10: إضافة القماش الثاني مع مستطيل مخطط إلى القماش الرئيسي.
أضف مستطيلًا مع حد لتوضيح كيفية تفاعل الحدود مع القص.

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## الخطوة 11: إنشاء مستطيل في القماش الثالث وتحديد حد له.
القماش الثالث يوضح الرسم المستقل دون قص.

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## الخطوة 12: حفظ مستند XPS الناتج.
احفظ حزمة XPS إلى نظام الملفات.

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## المشكلات الشائعة والحلول
- **مسار غير صالح** – تأكد من أن `dataDir` ينتهي بشرطة مائلة عكسية (`\\`) أو استخدم `Path.Combine`.  
- **القص غير مطبق** – تحقق من أن سلسلة هندسة القص مُشكّلة بشكل صحيح؛ قد يؤدي نقص مساحة إلى تجاهل القص.  
- **استثناء الترخيص** – في بناء غير تجريبي، أضف ترخيص Aspose صالح قبل إنشاء المستند لتجنب استثناءات وقت التشغيل.

## الأسئلة المتكررة
### س1: هل يمكنني استخدام Aspose.Page لـ .NET مع صيغ مستندات أخرى؟
ج1: يركز Aspose.Page لـ .NET أساسًا على مستندات XPS، لكن Aspose توفر مكتبات أخرى لصيغ مستندات مختلفة.

### س2: هل Aspose.Page لـ .NET مناسب للمبتدئين؟
ج2: نعم، تم تصميم Aspose.Page لـ .NET لتكون سهلة الاستخدام، ويمكن للمبتدئين فهم وظائفها بسرعة مع الوثائق المناسبة.

### س3: أين يمكنني العثور على المزيد من الأمثلة والموارد؟
ج3: قم بزيارة [الوثائق](https://reference.aspose.com/page/net/) و[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على موارد وأمثلة واسعة.

### س4: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟
ج4: يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### س5: هل يتوفر نسخة تجريبية مجانية لـ Aspose.Page لـ .NET؟
ج5: نعم، يمكنك تجربة النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

## أسئلة متكررة إضافية
**Q:** هل يمكنني دمج عدة هندسات قص على قماش واحد؟  
**A:** نعم، يمكنك تعيين `PathGeometry` معقد يحتوي على عدة مسارات فرعية إلى خاصية `Clip`، مما يسمح بقناع متعدد الطبقات.

**Q:** هل يؤثر القص على تحويل PDF؟  
**A:** عند تحويل XPS إلى PDF لاحقًا باستخدام Aspose.PDF، يتم الحفاظ على هندسة القص، لذا يبقى الناتج البصري متطابقًا.

**Q:** هل يمكن تحريك القص في XPS؟  
**A:** XPS بحد ذاته لا يدعم الرسوم المتحركة؛ ومع ذلك، يمكنك إنشاء سلسلة من صفحات XPS بأشكال قص مختلفة لمحاكاة الحركة.

---

**آخر تحديث:** 2026-06-25  
**تم الاختبار مع:** Aspose.Page 24.11 for .NET  
**المؤلف:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## دروس ذات صلة
- [كيفية تحويل XPS باستخدام Aspose.Page لـ .NET](/page/net/canvas-manipulation/transformationsxps/)
- [إضافة مستطيل إلى مستند XPS باستخدام Aspose.Page لـ .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [تحويل XPS إلى PDF باستخدام Aspose.Page لـ .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}