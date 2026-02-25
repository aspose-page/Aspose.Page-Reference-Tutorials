---
date: 2026-02-25
description: تعلم كيفية إنشاء مستند XPS وتطبيق تدرج خطي باستخدام Aspose.Page لـ .NET.
  اتبع دليلنا خطوة بخطوة لحفظ ملف XPS.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: إنشاء مستند XPS بتدرج عمودي باستخدام Aspose.Page
url: /ar/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

 produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة تدرج عمودي إلى XPS باستخدام Aspose.Page لـ .NET

## مقدمة

في هذا الدرس ستقوم **بإنشاء مستند XPS** يحتوي على تدرج عمودي سلس. إضافة التدرجات هي طريقة شائعة لجعل ملفات XPS تبدو أكثر احترافية — مثالية للتقارير والكتيبات أو أي رسومات قابلة للطباعة. سنستعرض كل خطوة، من إعداد المشروع إلى حفظ ملف XPS النهائي، حتى تتمكن من تطبيق تدرج خطي على أي مسار بسرعة.

## إجابات سريعة
- **ماذا يغطي هذا الدرس؟** إضافة تدرج خطي عمودي إلى مسار في مستند XPS.  
- **ما المكتبة المطلوبة؟** Aspose.Page لـ .NET.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **كم يستغرق التنفيذ؟** حوالي 10‑15 دقيقة لمثال أساسي.  
- **هل يمكنني حفظ النتيجة كملف XPS؟** نعم، طريقة `Save` تكتب الملف إلى القرص.

## ما هو التدرج العمودي في XPS؟

التدرج العمودي هو انتقال لوني يمتد من أعلى الشكل إلى أسفله. في XPS، يتم تحقيق ذلك باستخدام **فرشاة تدرج خطي** تحدد نقاط البداية والنهاية، بالإضافة إلى مجموعة من نقاط التدرج التي تتحكم في اللون عند مواضع محددة.

## لماذا نستخدم Aspose.Page لإنشاء مستند XPS مع التدرجات؟

- **تكامل كامل مع .NET** – يعمل مع .NET Framework و .NET Core و .NET 5/6+.  
- **بدون تبعيات خارجية** – جميع عمليات العرض تتم عبر المكتبة.  
- **دقة عالية** – يتم عرض التدرجات بالضبط كما تم تعريفها، متطابقة مع مواصفات XPS.  
- **سهولة الصيانة** – نموذج كائنات واضح للمسارات والفرشاة والألوان.

## المتطلبات المسبقة

- Aspose.Page لـ .NET: تأكد من تثبيت مكتبة Aspose.Page لـ .NET في بيئة التطوير الخاصة بك. يمكنك تنزيلها [هنا](https://releases.aspose.com/page/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET باستخدام IDE المفضل لديك، مثل Visual Studio.

الآن بعد أن أصبح كل شيء جاهزًا، دعنا نتعمق في الشيفرة.

## استيراد مساحات الأسماء

في تطبيق .NET الخاص بك، قم بتضمين مساحات الأسماء اللازمة للوصول إلى فئات وأساليب Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## الخطوة 1: إعداد دليل المستند الخاص بك

حدد المجلد الذي سيتم حفظ ملف XPS المُولد فيه.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## الخطوة 2: إنشاء مستند XPS جديد

أنشئ مستند XPS جديدًا سنملأه لاحقًا بمسار مملوء بالتدرج.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## الخطوة 3: تعريف نقاط التدرج

نقاط التدرج تحدد الألوان ومواقعها على طول خط التدرج. هنا نقوم بإنشاء خمس نقاط لإنتاج انتقال عمودي سلس.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## الخطوة 4: إنشاء مسار مع تدرج

نرسم مسارًا على شكل مستطيل ونطبق **فرشاة تدرج خطي** تمتد عموديًا من النقطة (10, 110) إلى النقطة (10, 200). تستقبل الفرشاة نقاط التدرج التي تم تعريفها مسبقًا.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## الخطوة 5: حفظ مستند XPS الناتج

أخيرًا، اكتب مستند XPS إلى القرص. هذه الخطوة **حفظ ملف XPS** تنتج `AddVerticalGradient_outXPS.xps` في المجلد الذي حددته.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**نصيحة احترافية:** تحقق من النتيجة بفتح ملف XPS في عارض Windows XPS أو أي عارض طرف ثالث للتأكد من ظهور التدرج كما هو متوقع.

## المشكلات الشائعة & استكشاف الأخطاء وإصلاحها

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| التدرج يظهر كلون صلب | لم تتم إضافة نقاط التدرج إلى الفرشاة | تأكد من تنفيذ `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);`. |
| الملف غير موجود عند الحفظ | `dataDir` يشير إلى مجلد غير موجود | أنشئ الدليل أولاً أو استخدم مسارًا مطلقًا. |
| الألوان تبدو مختلفة | قيم اللون تستخدم ترتيب ARGB؛ تحقق من ترتيب القنوات | استخدم `CreateColor(alpha, red, green, blue)` بشكل صحيح. |

## الأسئلة المتكررة

**س: هل Aspose.Page متوافق مع Visual Studio 2019؟**  
ج: نعم، Aspose.Page متوافق مع Visual Studio 2019. تأكد من تثبيت الإصدار الصحيح من المكتبة.

**س: هل يمكنني استخدام Aspose.Page للمشاريع التجارية؟**  
ج: نعم، يمكن استخدام Aspose.Page للمشاريع التجارية. زر [هنا](https://purchase.aspose.com/buy) لاستكشاف خيارات الترخيص.

**س: هل تتوفر نسخة تجريبية مجانية؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Page [هنا](https://releases.aspose.com/).

**س: أين يمكنني العثور على توثيق Aspose.Page؟**  
ج: التوثيق متاح [هنا](https://reference.aspose.com/page/net/).

**س: كيف يمكنني الحصول على الدعم أو طرح الأسئلة؟**  
ج: زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع.

## الخاتمة

أنت الآن تعرف كيفية **إنشاء مستند XPS**، **تطبيق تدرج خطي**، و **حفظ ملف XPS** باستخدام Aspose.Page لـ .NET. يمنحك هذا النهج تحكمًا كاملاً في التنسيق البصري لمخرجات XPS، مما يجعل مستنداتك القابلة للطباعة مميزة.

---  

**آخر تحديث:** 2026-02-25  
**تم الاختبار مع:** Aspose.Page for .NET 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}