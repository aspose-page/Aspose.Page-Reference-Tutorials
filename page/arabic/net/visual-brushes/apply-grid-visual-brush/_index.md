---
date: 2026-04-03
description: تعلم كيفية إضافة مستطيل شفاف وتطبيق فرشاة شبكة بصرية في .NET باستخدام
  Aspose.Page لإنشاء مستندات XPS مذهلة.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: تطبيق فرشاة الشبكة البصرية
second_title: Aspose.Page .NET API
title: إضافة مستطيل شفاف باستخدام فرشاة بصرية للشبكة (.NET)
url: /ar/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مستطيل شفاف باستخدام فرشاة بصرية شبكية (.NET)

## مقدمة

If you’re looking to **add a transparent rectangle** to an XPS document while also applying a stylish Grid Visual Brush, you’ve come to the right place. In this tutorial we’ll walk through the exact steps needed with Aspose.Page for .NET, so you can create visually rich documents that stand out. By the end you’ll have a complete, runnable example that demonstrates both techniques in a single, easy‑to‑follow workflow.

## إجابات سريعة
- **ما الذي يفعله المستطيل الشفاف؟** يضيف طبقة شبه شفافة تسمح للمحتوى الخلفي بالظهور.  
- **أي واجهة برمجة تطبيقات (API) تنشئ الفرشاة؟** `XpsDocument.CreateVisualBrush` يبني فرشاة بصرية شبكية.  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للاختبار؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.  
- **كم من الوقت تستغرق التنفيذ؟** حوالي 10‑15 دقيقة لمثال أساسي.

## ما هو المستطيل الشفاف في XPS؟
المستطيل الشفاف هو ببساطة شكل يكون لون التعبئة فيه يحتوي على مكوّن ألفا أقل من 1.0، مما يسمح للرسومات الأساسية بأن تكون مرئية جزئياً. هذا مثالي لتسليط الضوء على الأقسام دون إخفاء الخلفية بالكامل.

## لماذا نستخدم فرشاة بصرية شبكية؟
تتيح لك فرشاة بصرية شبكية (Grid Visual Brush) تكرار رسم متجه صغير عبر مساحة أكبر، مما يخلق أنماطًا مثل الشبكات أو الخطوط المتقاطعة أو القوام المخصص. الجمع بينها وبين مستطيل شفاف يمنحك تأثيرات بصرية متعددة الطبقات تكون خفيفة الوزن ومستقلة عن الدقة.

## المتطلبات المسبقة

Before diving into the code, make sure you have:

- **Aspose.Page for .NET** – يمكنك تنزيله [هنا](https://releases.aspose.com/page/net/).
- بيئة تطوير .NET (Visual Studio، VS Code، أو أي IDE تفضله).
- مجلد سيتم حفظ ملفات XPS المُولدة فيه.

## استيراد مساحات الأسماء

In your C# file, import the required namespaces:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Now let’s break the solution into clear, numbered steps.

## الخطوة 1: تهيئة XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

نبدأ بإنشاء كائن `XpsDocument`، والذي سيحمل جميع عمليات الرسم اللاحقة.

## الخطوة 2: إنشاء هندسة شبكة أرجوانية

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

هذه الهندسة تحدد مخطط الشبكة التي ستملأها الفرشاة البصرية.

## الخطوة 3: تصميم فرشاة بصرية شبكة أرجوانية

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

هنا نرسم بلاطة صغيرة باللون الأرجواني سيتم تكرارها عبر الشبكة.

## الخطوة 4: تطبيق VisualBrush على الشبكة

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

استدعاء `CreateVisualBrush` يربط البلاطة الأرجوانية بهندسة الشبكة ويفعل التكرار.

## الخطوة 5: إضافة الشبكة إلى Canvas

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

نضع الشبكة المتكررة على لوحة (Canvas) ونطبق تحويل إزاحة لتظهر في الموقع المطلوب.

## الخطوة 6: إضافة مستطيل شفاف

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

في هذه الخطوة **نضيف مستطيلًا شفافًا** (الشكل الأحمر مع `Opacity = 0.7f`). اضبط قيمة الشفافية للتحكم في مدى شفافية المستطيل.

## الخطوة 7: حفظ المستند

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

يتم كتابة ملف XPS إلى المجلد الذي حددته مسبقًا.

## حالات الاستخدام الشائعة

- **تمييز التقارير:** وضع مستطيل شبه شفاف لتسليط الضوء على مخطط أو جدول.  
- **تأثيرات العلامة المائية:** دمج شبكة متكررة مع طبقة شفافة للحصول على علامة تجارية خفيفة.  
- **ملفات PDF/XPS تفاعلية:** استخدم النمط كخلفية لحقول النماذج مع الحفاظ على قابلية قراءة واجهة المستخدم.

## نصائح استكشاف الأخطاء وإصلاحها

- **الشفافية غير مرئية؟** تأكد من أن عارضك يدعم شفافية XPS؛ قد يتجاهل بعض العارضات القديمة خاصية `Opacity`.  
- **حجم البلاطة غير صحيح؟** تحقق من أن المستطيل المصدر (`new RectangleF(0f, 0f, 10f, 10f)`) يطابق أبعاد البلاطة المتجهية.  
- **الملف لم يُحفظ؟** تحقق مرة أخرى من أن `dataDir` يشير إلى دليل موجود وقابل للكتابة.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page for .NET في تطبيقات الويب وسطح المكتب؟**  
ج: نعم، المكتبة تعمل عبر جميع أنواع تطبيقات .NET.

**س: هل هناك نسخة تجريبية متاحة قبل الشراء؟**  
ج: بالتأكيد، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

**س: أين يمكنني العثور على دعم إضافي أو مناقشات المجتمع؟**  
ج: زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على مساعدة من المجتمع ومهندسي Aspose.

**س: كيف يمكنني الحصول على ترخيص مؤقت للتقييم؟**  
ج: يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: ما الوثائق الأخرى المتاحة لـ Aspose.Page for .NET؟**  
ج: استكشف الوثائق الشاملة [هنا](https://reference.aspose.com/page/net/).

---

**آخر تحديث:** 2026-04-03  
**تم الاختبار مع:** Aspose.Page 24.12 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}