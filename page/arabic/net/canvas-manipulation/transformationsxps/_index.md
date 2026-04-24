---
date: 2026-01-05
description: تعلم كيفية تحويل مستندات XPS بسهولة مع Aspose.Page لـ .NET. اتبع دليلنا
  خطوة بخطوة للتحويلات السلسة.
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: كيفية تحويل XPS باستخدام Aspose.Page لـ .NET
url: /ar/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحويل XPS باستخدام Aspose.Page لـ .NET

## مقدمة

مرحبًا بك في عالم Aspose.Page لـ .NET، مكتبة قوية تتيح لك إجراء تحولات مختلفة على مستندات XPS بسهولة. **في هذا البرنامج التعليمي، ستكتشف كيفية تحويل مستندات XPS باستخدام Aspose.Page لـ .NET**، سواء كنت مطورًا متمرسًا أو مبتدئًا. سنستعرض كل خطوة، نشرح السبب وراء كل تحويل، ونقدم لك نصائح عملية يمكنك تطبيقها في مشاريع حقيقية.

## إجابات سريعة
- **ما الذي يمكنك تحقيقه؟** إنشاء، نقل، تحجيم، وتدوير عناصر لوحة XPS برمجيًا.  
- **ما المكتبة المطلوبة؟** Aspose.Page لـ .NET (أحدث إصدار).  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **المنصات المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.  
- **كم يستغرق التنفيذ؟** حوالي 10‑15 دقيقة للتحولات الأساسية المعروضة هنا.

## ما هو “كيفية تحويل XPS”؟
تشير عبارة *كيفية تحويل XPS* إلى تعديل تخطيط وحجم واتجاه العناصر داخل مستند XPS (XML Paper Specification) برمجيًا. باستخدام Aspose.Page، يمكنك تطبيق تحولات قائمة على المصفوفات على اللوحات، مما يمنحك تحكمًا دقيقًا في الموضع، التحجيم، والتدوير دون الحاجة لتعديل XML الخاص بـ XPS يدويًا.

## لماذا نستخدم Aspose.Page لتحويلات XPS؟
- **تكامل كامل مع .NET** – يعمل بسلاسة مع Visual Studio، Rider، وغيرها من بيئات التطوير.  
- **بدون تبعيات خارجية** – تتولى الواجهة البرمجية كل تفاصيل XPS منخفضة المستوى.  
- **دعم غني للتحولات** – نقل، تحجيم، تدوير، ودمج تحولات متعددة في استدعاء واحد.  
- **محسن للأداء** – مناسب لإنشاء تقارير، فواتير، أو أي رسومات قابلة للطباعة في الوقت الفعلي.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

- **Aspose.Page لـ .NET Library** – قم بتنزيله وتثبيته من الوثائق الرسمية: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **بيئة التطوير** – Visual Studio، Visual Studio Code، أو أي بيئة IDE متوافقة مع .NET.  
- **دليل المستندات** – مجلد على جهازك لقراءة/كتابة ملفات XPS. استبدل العنصر النائب في الشيفرة بالمسار الفعلي.

الآن بعد أن تم إعداد كل شيء، لنغوص في الشيفرة.

## استيراد المساحات الاسمية

أولاً، استورد المساحات الاسمية التي تكشف عن فئات Aspose.Page التي ستحتاجها:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## كيفية تحويل XPS – دليل خطوة بخطوة

### الخطوة 1: إنشاء مستند XPS جديد

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Explanation*: نبدأ بتحديد المجلد الذي يحتوي على ملفات المصدر والإخراج، ثم ننشئ كائن `XpsDocument` فارغ. هذا الكائن سيكون اللوحة لجميع التحولات اللاحقة.

### الخطوة 2: إنشاء لوحة رئيسية

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Why this matters*: تعمل اللوحة الرئيسية كحاوية لجميع اللوحات الأخرى. من خلال تطبيق إزاحة صغيرة نضمن عدم قطع المحتوى عند حافة الصفحة.

### الخطوة 3: إنشاء هندسة مسار مستطيل

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Tip*: سلسلة المسار تتبع صيغة مسار XPS القياسية (`M` للتحرك، `L` للخط، `Z` للإغلاق). عدّل الإحداثيات لتغيير حجم المستطيل.

### الخطوة 4: إضافة تعبئة للمستطيلات

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro tip*: استخدم `CreateColor` مع قيم RGB لتطابق لوحة ألوان علامتك التجارية.

### الخطوة 5: إضافة لوحة جديدة بدون تحولات

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

هنا نضع مستطيلًا على الصفحة دون أي تحويل إضافي—مفيد كعنصر أساسي للمقارنة.

### الخطوة 6: إضافة لوحة جديدة مع تحويل نقل

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*What’s happening?* المصفوفة الأولى تنقل المستطيل إلى الأسفل بمقدار 200 وحدة. استدعاء `Translate` التالي يزحه 500 وحدة إلى اليمين، مظهرًا كيف يمكن ربط عمليات النقل المتعددة.

### الخطوة 7: إضافة لوحة جديدة مع تحويل تحجيم مزدوج

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Why scale?* التحجيم بمقدار 2 يضاعف عرض وارتفاع المستطيل، مما يتيح لك إنشاء رسومات أكبر دون إعادة تعريف الهندسة.

### الخطوة 8: إضافة لوحة جديدة مع تحويل تدوير حول نقطة

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Key insight*: `RotateAround` يدور اللوحة حول نقطة مخصصة (هنا (100, 50))، مما يمنحك تحكمًا دقيقًا في محور التدوير.

### الخطوة 9: حفظ مستند XPS الناتج

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

بعد تطبيق جميع التحولات، يتم حفظ المستند إلى `output1.xps`. افتح الملف في أي عارض XPS لرؤية المستطيلات المتراصة مع عمليات النقل، التحجيم، والتدوير الخاصة بها.

## المشكلات الشائعة & استكشاف الأخطاء

| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| ملف إخراج فارغ | `dataDir` يشير إلى مجلد غير موجود | تأكد من وجود المجلد أو استخدم مسارًا مطلقًا |
| المستطيلات غير موضوعة كما هو متوقع | قيم المصفوفة غير صحيحة | راجع ترتيب استدعاءات `Translate`، `Scale`، و `RotateAround` |
| الألوان غير صحيحة | قيم RGB خارج النطاق 0‑255 | استخدم قيم بايت صالحة لكل قناة |

## الأسئلة المتكررة

**س: هل Aspose.Page لـ .NET متوافق مع جميع بيئات تطوير .NET؟**  
ج: نعم، يعمل بسلاسة مع Visual Studio، Visual Studio Code، Rider، وأي IDE يدعم .NET.

**س: أين يمكنني العثور على أمثلة إضافية ووثائق API مفصلة؟**  
ج: زر الوثائق الرسمية على [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**س: هل يمكنني تجربة Aspose.Page قبل شراء الترخيص؟**  
ج: بالتأكيد. نسخة تجريبية مجانية متاحة هنا: [Aspose.Page Free Trial](https://releases.aspose.com/).

**س: كيف أحصل على ترخيص مؤقت للاختبار؟**  
ج: يمكنك طلبه عبر صفحة الترخيص المؤقت: [Temporary License](https://purchase.aspose.com/temporary-license/).

**س: أين أشتري ترخيصًا كاملاً؟**  
ج: اشترِ مباشرة من متجر Aspose: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**آخر تحديث:** 2026-01-05  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}