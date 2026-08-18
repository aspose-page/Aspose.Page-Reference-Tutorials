---
date: 2026-02-23
description: تعرّف على كيفية إنشاء مستندات XPS بتدرّج قطري باستخدام Aspose.Page لـ
  .NET وارتقِ بعروضك البصرية بسهولة.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: إنشاء تدرج قطري XPS باستخدام Aspose.Page لـ .NET
url: /ar/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء XPS بتدرج قطري باستخدام Aspose.Page لـ .NET

## مقدمة

## إجابات سريعة
- **ماذا يفعل أسلوب API؟** ينشئ فرشاة تدرج خطية تمتد قطريًا عبر مسار.  
- **أي فئة تمثل مستند XPS؟** `XpsDocument`.  
- **هل أحتاج إلى ترخيص لتشغيل العينة؟** النسخة التجريبية المجانية تكفي للتطوير؛ الترخيص مطلوب للإنتاج.  
- **هل يمكنني تغيير اتجاه التدرج؟** نعم — قم بضبط قيم `PointF` للبداية والنهاية.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.

## ما هو **create diagonal gradient xps**؟
التدرج القطري هو انتقال سلس للألوان يمتد من أحد زوايا الشكل إلى الزاوية المقابلة. في XPS، يتم تحقيق هذا التأثير عن طريق تطبيق `LinearGradientBrush` على خاصية التعبئة (fill) للمسار. مكتبة Aspose.Page تُجرد العلامات منخفضة المستوى لـ XPS، مما يتيح لك التركيز على الألوان والهندسة.

## لماذا تستخدم Aspose.Page للتدرجات القطرية؟
- **عروض عالية الدقة** – الناتج يطابق مواصفات XPS بدقة.  
- **تكامل كامل مع .NET** – يعمل مع C#، VB.NET، وأي لغة .NET.  
- **بدون تبعيات خارجية** – كل شيء يُدار داخل العملية، لا حاجة إلى COM أو Office.  
- **قابل للتوسع للوثائق المعقدة** – يمكنك دمج عدة تدرجات، صور، ونصوص في نفس الصفحة.

## المتطلبات المسبقة

1. **مكتبة Aspose.Page لـ .NET** – قم بتنزيلها [من هنا](https://releases.aspose.com/page/net/).  
2. **بيئة التطوير** – Visual Studio، Rider، أو أي محرر يدعم مشاريع .NET.  

الآن، دعنا نغوص في الشيفرة.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، قم بتضمين مساحات الأسماء اللازمة من مكتبة Aspose.Page للوصول إلى الفئات والأساليب المطلوبة. أضف مساحات الأسماء التالية في بداية الشيفرة الخاصة بك:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## الخطوة 1: تحديد دليل المستند

ابدأ بتحديد المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي سيتم حفظ مستند XPS الناتج مع التدرج القطري فيه.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء مستند XPS جديد

قم بتهيئة `XpsDocument` جديد باستخدام مكتبة Aspose.Page.

```csharp
XpsDocument doc = new XpsDocument();
```

## الخطوة 3: تعريف ألوان التدرج

أنشئ قائمة من كائنات `XpsGradientStop`، كل منها يمثل لونًا في التدرج القطري.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## الخطوة 4: إضافة تدرج قطري إلى مسار

أنشئ مسارًا جديدًا مع هندسة محددة، وطبق التدرج القطري عليه. اضبط تحويل العرض (rendering transform) وخصائص التعبئة حسب الحاجة.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## الخطوة 5: حفظ مستند XPS الناتج

أخيرًا، احفظ مستند XPS المعدل إلى الدليل المحدد.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

لقد نجحت الآن في **إنشاء ملف XPS بتدرج قطري**. لا تتردد في تجربة نقاط ألوان مختلفة، سلاسل هندسية، أو مصفوفات تحويل لإنتاج مجموعة متنوعة من التأثيرات البصرية.

## المشكلات الشائعة والحلول
- **التدرج غير مرئي** – تحقق من أن هندسة المسار مغلقة وأن نقاط البداية/النهاية للفرشاة تقع داخل حدود المسار.  
- **ألوان غير صحيحة** – تأكد من استخدام `CreateColor` بالقيم ARGB الصحيحة؛ الطريقة تتوقع قيمًا في النطاق 0‑255.  
- **الملف غير محفوظ** – تحقق من أن `dataDir` يشير إلى مجلد موجود وأن التطبيق يمتلك صلاحيات الكتابة.

## الأسئلة المتكررة

**س: هل يمكنني تطبيق عدة تدرجات على أجزاء مختلفة من المستند؟**  
ج: نعم، يمكنك إنشاء مسارات متعددة وتطبيق تدرجات مميزة على كل منها.

**س: هل توجد أنماط تدرج مسبقة التعريف؟**  
ج: Aspose.Page يسمح بتدرجات مخصصة، مما يمنحك سيطرة كاملة على انتقالات الألوان.

**س: هل يمكنني استخدام Aspose.Page لـ .NET مع صيغ مستندات أخرى؟**  
ج: Aspose.Page يركز أساسًا على معالجة مستندات XPS.

**س: كيف يمكنني التعامل مع الأخطاء المتعلقة بمعالجة المستند؟**  
ج: راجع [التوثيق](https://reference.aspose.com/page/net/) لأفضل ممارسات معالجة الأخطاء.

**س: هل هناك نسخة تجريبية متاحة قبل الشراء؟**  
ج: نعم، يمكنك استكشاف [النسخة التجريبية المجانية](https://releases.aspose.com/) لتجربة Aspose.Page لـ .NET.

**س: كيف أغير اتجاه التدرج إلى عمودي أو أفقي؟**  
ج: عدل معاملات `PointF` في `CreateLinearGradientBrush` لتحديد نقاط بداية ونهاية جديدة.

**س: هل تدعم المكتبة الشفافية في التدرجات؟**  
ج: نعم — أضف قيمة ألفا عند إنشاء الألوان باستخدام `CreateColor`.

## الخلاصة

Aspose.Page لـ .NET يبسط عملية تحسين مستندات XPS باستخدام التدرجات القطرية. قدم لك هذا الدليل كل شيء من إعداد المتطلبات المسبقة إلى حفظ الملف النهائي. استمر في تجربة أشكال وألوان مختلفة لجعل تقارير XPS، الكتيبات، أو الفواتير الخاصة بك تبرز حقًا.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-02-23  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET  
**المؤلف:** Aspose