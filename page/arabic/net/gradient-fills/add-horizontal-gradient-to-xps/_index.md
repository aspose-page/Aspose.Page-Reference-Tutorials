---
date: 2026-02-25
description: تعلم كيفية إنشاء تدرج XPS بملء أفقي باستخدام Aspose.Page لـ .NET. ارتقِ
  بالجاذبية البصرية بسهولة في مستنداتك.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'إنشاء تدرج XPS: تعبئة أفقية باستخدام Aspose.Page لـ .NET'
url: /ar/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

 assemble.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء تدرج XPS – إضافة تدرج أفقي إلى XPS باستخدام Aspose.Page for .NET

## المقدمة

في هذا البرنامج التعليمي ستقوم **بإنشاء تدرجات XPS** التي تمتد أفقياً عبر صفحاتك. إضافة تدرج أفقي يمكن أن يجعل مستند XPS يبدو أكثر صقلاً وجاذبية على الفور، خاصةً للتقارير والكتيبات أو أي مخرجات غنية بالمرئيات. سنستعرض العملية بالكامل باستخدام Aspose.Page for .NET، بدءًا من إعداد البيئة حتى حفظ ملف XPS النهائي.

## إجابات سريعة
- **ماذا يغطي هذا البرنامج التعليمي؟** إضافة تدرج أفقي إلى مستند XPS باستخدام Aspose.Page for .NET.  
- **ما المكتبة المطلوبة؟** Aspose.Page for .NET (أي نسخة حديثة).  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للتطوير؛ الترخيص التجاري مطلوب للإنتاج.  
- **كم من الوقت تستغرق التنفيذ؟** حوالي 5–10 دقائق لتدرج أساسي.  
- **هل يمكنني تغيير اتجاه التدرج؟** نعم – عدل نقاط البداية/النهاية لـ `LinearGradientBrush`.

## كيفية إنشاء تدرج XPS باستخدام Aspose.Page for .NET

فيما يلي دليل خطوة بخطوة يشرح **لماذا** توجد كل سطر من الشيفرة، وليس فقط **ماذا** يفعل. لا تتردد في المتابعة في Visual Studio أو محرر .NET المفضل لديك.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من توفر المتطلبات التالية:

1. Aspose.Page for .NET Library: تأكد من تثبيت مكتبة Aspose.Page for .NET في بيئة التطوير الخاصة بك. يمكنك تنزيلها من [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).
2. بيئة التطوير: قم بإعداد بيئة تطوير مناسبة، بما في ذلك محرر شفرة مثل Visual Studio.

## استيراد المساحات الاسمية

ابدأ باستيراد المساحات الاسمية (namespaces) الضرورية إلى مشروعك. هذه المساحات الاسمية أساسية للعمل مع Aspose.Page for .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

الآن، دعنا نقسم المثال المقدم إلى عدة خطوات.

## الخطوة 1: تعيين مسار دليل المستند

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## الخطوة 2: إنشاء مستند XPS جديد

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## الخطوة 3: تهيئة نقاط التدرج

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## الخطوة 4: إنشاء مسار جديد

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## الخطوة 5: حفظ مستند XPS الناتج

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

الآن، لقد أضفت بنجاح تدرجًا أفقيًا إلى مستند XPS الخاص بك باستخدام Aspose.Page for .NET.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|---------|--------|------|
| التدرج يظهر كلون صلب | نقاط التدرج لم تُضاف بشكل صحيح | تأكد من تنفيذ `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` بعد ضبط الفرشاة. |
| الملف المحفوظ فارغ | `dataDir` يشير إلى مجلد غير موجود | تحقق من وجود المجلد أو استخدم مسارًا مطلقًا. |
| خطأ تجميع على `PointF` | المرجع `System.Drawing` مفقود | أضف مرجعًا إلى `System.Drawing.Common` (لـ .NET Core/5+). |

## الأسئلة المتكررة

### س1: أين يمكنني العثور على وثائق Aspose.Page for .NET؟

ج1: يمكنك العثور على الوثائق [هنا](https://reference.aspose.com/page/net/).

### س2: كيف يمكنني تنزيل Aspose.Page for .NET؟

ج2: يمكنك تنزيل المكتبة من [صفحة تنزيل Aspose.Page for .NET](https://releases.aspose.com/page/net/).

### س3: أين يمكنني شراء Aspose.Page for .NET؟

ج3: يمكنك شراء Aspose.Page for .NET من [صفحة الشراء](https://purchase.aspose.com/buy).

### س4: هل هناك نسخة تجريبية مجانية متاحة؟

ج4: نعم، يمكنك الحصول على نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

### س5: كيف أحصل على ترخيص مؤقت لـ Aspose.Page for .NET؟

ج5: يمكنك الحصول على ترخيص مؤقت من [هذا الرابط](https://purchase.aspose.com/temporary-license/).

## أسئلة شائعة

**س: هل يمكنني استخدام تقنية التدرج هذه مع مستندات XPS التي تحتوي بالفعل على صور؟**  
ج: بالتأكيد. يتم تطبيق التدرج على طبقة المسار، لذا تظل الصور الموجودة دون تغيير.

**س: هل يمكن إنشاء تدرج عمودي بدلاً من ذلك؟**  
ج: نعم. غيّر نقاط البداية والنهاية لـ `LinearGradientBrush` لتكون لها إحداثيات Y مختلفة مع الحفاظ على X ثابتًا.

**س: هل يدعم Aspose.Page .NET Core؟**  
ج: المكتبة متوافقة بالكامل مع .NET Core، .NET 5، والإصدارات الأحدث.

**س: كيف يمكنني إعادة استخدام نفس التدرج عبر صفحات متعددة؟**  
ج: أنشئ `XpsLinearGradientBrush` مرة واحدة، احفظه في متغير، وعيّنها إلى المسارات في كل صفحة.

## الخاتمة

تحسين مستندات XPS الخاصة بك باستخدام التدرجات لا يحسن المظهر البصري فحسب، بل يقدم تجربة مستخدم أكثر جاذبية. باستخدام Aspose.Page for .NET، يمكنك **إنشاء تدرجات XPS** بسرعة وبشكل موثوق، مما يمنح تقاريرك، كتيباتك، أو الكتب الإلكترونية لمسة احترافية.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-02-25  
**تم الاختبار باستخدام:** Aspose.Page for .NET 24.11  
**المؤلف:** Aspose