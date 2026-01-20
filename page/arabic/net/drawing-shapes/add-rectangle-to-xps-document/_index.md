---
date: 2026-01-20
description: تعلم كيفية إنشاء مستند XPS، وإضافة مستطيل، وحفظ ملف XPS باستخدام Aspose.Page
  لـ .NET في هذا الدليل خطوة بخطوة.
linktitle: Add Rectangle to XPS Document
second_title: Aspose.Page .NET API
title: 'إنشاء مستند XPS: إضافة مستطيل باستخدام Aspose.Page لـ .NET'
url: /ar/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مستند XPS: إضافة مستطيل باستخدام Aspose.Page لـ .NET

## المقدمة

في هذا الدرس ستقوم **بإنشاء ملفات مستند XPS** ورسم مستطيل داخلها باستخدام مكتبة Aspose.Page لـ .NET. إضافة أشكال مثل المستطيلات هي متطلب شائع عندما تحتاج إلى إنشاء فواتير أو تقارير أو رسومات مخصصة برمجياً. اتبع الخطوات أدناه وستحصل على ملف XPS جاهز للاستخدام في دقائق.

## إجابات سريعة
- **ما الذي يمكنني إنشاؤه؟** مستندات XPS مع رسومات متجهية ونص.  
- **ما المكتبة؟** Aspose.Page لـ .NET (تتوفر نسخة تجريبية مجانية).  
- **كم من الوقت يستغرق؟** حوالي 5‑10 دقائق للتنفيذ والتشغيل.  
- **هل أحتاج إلى ترخيص؟** يلزم ترخيص مؤقت للاستخدام في الإنتاج.  
- **هل يمكنني حفظ النتيجة كملف XPS؟** نعم – طريقة `Save` تكتب **ملف XPS محفوظ** إلى القرص.

## ما هو “إنشاء مستند XPS”؟

إنشاء مستند XPS يعني بناء وصف صفحة برمجياً بتنسيق XML Paper Specification. الملف الناتج يكون مستقلاً عن الدقة، وهو مثالي للطباعة والعرض عالي الجودة عبر المنصات.

## لماذا تستخدم Aspose.Page لإنشاء مستند XPS؟

- **دعم كامل لـ .NET** – يعمل مع .NET Framework و .NET Core و .NET 5/6+.  
- **واجهة برمجة تطبيقات رسم غنية** – تشمل هندسة المسار، الفُرش، الأقلام، ومعالجة النص.  
- **بدون تبعيات خارجية** – كل شيء يعمل داخل العملية دون الحاجة إلى Office أو Acrobat.  

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. **Aspose.Page لـ .NET** – قم بتنزيله [هنا](https://releases.aspose.com/page/net/).  
2. **مجلد قابل للكتابة** حيث سيتم تخزين ملفات XPS التي تم إنشاؤها.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، استورد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## الخطوة 1: تعيين دليل المستند

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **نصيحة احترافية:** استخدم مسارًا مطلقًا أو `Path.Combine` لتجنب مشاكل فاصل المسار على أنظمة تشغيل مختلفة.

## الخطوة 2: إنشاء مستند XPS جديد

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

في هذه المرحلة لديك كائن **تم إنشاء مستند XPS** سيحتوي على جميع عناصر الرسم.

## الخطوة 3: إضافة مستطيل (باستخدام create path geometry)

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

استدعاء `CreatePathGeometry` **ينشئ هندسة مسار** التي تحدد حدود المستطيل. يمكنك تعديل سلسلة الأوامر الشبيهة بـ SVG لرسم أشكال أخرى.

## الخطوة 4: حفظ المستند (حفظ ملف XPS)

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

استدعاء `Save` يكتب **ملف XPS المحفوظ** إلى الموقع الذي حددته.

تهانينا! لقد نجحت في **إنشاء مستند XPS**، وإضافة مستطيل، وحفظ الملف.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| `FileNotFoundException` على `doc.Save` | `dataDir` يشير إلى مجلد غير موجود | تأكد من وجود المجلد أو أنشئه باستخدام `Directory.CreateDirectory(dataDir)`. |
| المستطيل غير مرئي | ملف تعريف لون الخط مفقود أو هندسة المسار مشوهة | تحقق من مسار ملف ICC وسلسلة الهندسة (`M … Z`). |
| تباطؤ الأداء في المستندات الكبيرة | عدد كبير جدًا من استدعاءات `AddPath` الفردية | اجمع عمليات الرسم في دفعات أو أعد استخدام كائنات الفُرش/الأقلام. |

## الأسئلة المتكررة

**س: هل Aspose.Page متوافق مع جميع تطبيقات .NET؟**  
ج: نعم، تم تصميم Aspose.Page للعمل بسلاسة مع جميع تطبيقات .NET.

**س: أين يمكنني العثور على وثائق Aspose.Page لـ .NET؟**  
ج: الوثائق متاحة [هنا](https://reference.aspose.com/page/net/).

**س: هل يمكنني تجربة Aspose.Page لـ .NET مجانًا قبل الشراء؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟**  
ج: زر [هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت.

**س: أين يمكنني الحصول على دعم المجتمع أو طرح أسئلة متعلقة بـ Aspose.Page لـ .NET؟**  
ج: زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع.

**آخر تحديث:** 2026-01-20  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}