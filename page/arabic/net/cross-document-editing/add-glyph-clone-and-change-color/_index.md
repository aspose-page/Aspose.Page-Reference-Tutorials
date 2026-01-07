---
date: 2026-01-07
description: تعلم كيفية إنشاء مستند XPS، إضافة نسخ من الحروف، استخدام فرشاة لون صلبة،
  وحفظ ملف XPS باستخدام Aspose.Page لـ .NET.
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: إنشاء مستند XPS – إضافة نسخة من الحرف وتغيير اللون باستخدام Aspose.Page لـ
  .NET
url: /ar/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مستند XPS – إضافة نسخة من Glyph وتغيير اللون باستخدام Aspose.Page لـ .NET

## مقدمة

## إجابات سريعة
- **ما هو الهدف الأساسي؟** إنشاء مستند XPS، إضافة نسخ من glyph وتغيير ألوانها.  
- **ما المكتبة المستخدمة؟** Aspose.Page لـ .NET.  
- **هل أحتاج إلى ترخيص؟** يتوفر ترخيص مؤقت للتقييم؛ يلزم ترخيص كامل للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.  
- **كيف أحفظ النتيجة؟** استخدم طريقة `Save` لكتابة ملف XPS إلى القرص.

## المتطلبات المسبقة

- فهم أساسي للغة البرمجة C#.  
- تثبيت Visual Studio أو أي بيئة تطوير C# مفضلة أخرى.  
- مكتبة Aspose.Page لـ .NET. يمكنك تنزيلها [هنا](https://releases.aspose.com/page/net/).  
- الإلمام بتنسيق مستند XPS.

## استيراد مساحات الأسماء

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## كيفية إنشاء مستند XPS وإضافة نسخ Glyph

### الخطوة 1: إعداد دليل المستندات الخاص بك

```csharp
string dataDir = "Your Document Directory";
```

### الخطوة 2: إنشاء مستند XPS الأول

```csharp
XpsDocument doc1 = new XpsDocument();
```

### الخطوة 3: إضافة Glyphs إلى المستند الأول

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### الخطوة 4: ملء Glyphs بفرشاة لون صلبة

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### الخطوة 5: إنشاء مستند XPS الثاني

```csharp
XpsDocument doc2 = new XpsDocument();
```

### الخطوة 6: كيفية إضافة نسخة Glyph إلى مستند آخر

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### الخطوة 7: كيفية تغيير لون Glyph المستنسخ

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### الخطوة 8: حفظ ملف XPS – المستند الأول

```csharp
doc1.Save(dataDir + "out1.xps");
```

### الخطوة 9: حفظ ملف XPS – المستند الثاني

```csharp
doc2.Save(dataDir + "out2.xps");
```

تهانينا! لقد نجحت في **إنشاء مستندات XPS**، إضافة نسخ glyph، وتغيير ألوانها باستخدام Aspose.Page لـ .NET.

## لماذا نستخدم استنساخ Glyph وتغيير الألوان؟

- **قابلية إعادة الاستخدام:** استنساخ glyphs الموجودة لإعادة استخدام الأشكال المتجهية المعقدة دون إعادة تعريفها.  
- **الأداء:** يقلل من وقت المعالجة مقارنة بإعادة إنشاء glyphs من الصفر.  
- **مرونة التصميم:** تطبيق مثيلات `SolidColorBrush` مختلفة على نفس glyph لتحقيق سمات بصرية متنوعة.  
- **تحرير عبر المستندات:** استنساخ glyphs عبر ملفات XPS متعددة، مما يتيح توحيد العلامة التجارية عبر التقارير.

## المشكلات الشائعة & استكشاف الأخطاء وإصلاحها

| المشكلة | الحل |
|-------|----------|
| **Clone returns null** | تأكد من إضافة glyph المصدر (`glyphs`) إلى المستند الأول قبل الاستنساخ. |
| **Color does not change** | حوّل `glyphs.Fill` إلى `XpsSolidColorBrush` قبل تعيين خاصية `Color` (كما هو موضح في الخطوة 7). |
| **File not saved** | تحقق من أن `dataDir` يشير إلى مجلد صالح وقابل للكتابة وأن لديك الأذونات المناسبة لنظام الملفات. |
| **Unexpected glyph size** | اضبط معامل حجم الخط (الوسيط الثاني في `AddGlyphs`) لتكبير glyph بشكل مناسب. |

## الأسئلة المتكررة

**س1: هل يمكنني استخدام Aspose.Page لـ .NET مع صيغ مستندات أخرى؟**  
ج1: Aspose.Page لـ .NET مصممة خصيصًا للعمل مع مستندات XPS. إذا كنت بحاجة إلى معالجة صيغ أخرى، يمكنك استكشاف مكتبات Aspose الأخرى المخصصة لتلك الصيغ.

**س2: هل يتوفر ترخيص مؤقت لـ Aspose.Page لـ .NET؟**  
ج2: نعم، يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار. زر [هنا](https://purchase.aspose.com/temporary-license/) للمزيد من المعلومات.

**س3: كيف يمكنني الحصول على الدعم أو طلب المساعدة في أي مشكلة؟**  
ج3: لا تتردد بزيارة [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع وطلب المساعدة.

**س4: هل هناك أي قيود على نسخة التجربة المجانية؟**  
ج4: نسخة التجربة المجانية تحتوي على بعض القيود، ومن المستحسن مراجعة الوثائق للحصول على التفاصيل قبل الاستخدام.

**س5: أين يمكنني العثور على وثائق شاملة لـ Aspose.Page لـ .NET؟**  
ج5: يمكنك الرجوع إلى الوثائق [هنا](https://reference.aspose.com/page/net/) للحصول على معلومات مفصلة وأمثلة.

**س6: كيف أغير لون الحد (stroke) لـ glyph بدلاً من التعبئة؟**  
ج6: استخدم `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);` لتعيين فرشاة الحد.

**س7: هل يمكنني إضافة عدة نسخ glyph إلى نفس المستند؟**  
ج7: نعم، استدعِ `doc2.Add(glyphs.Clone());` بشكل متكرر، مع تعديل المواقع حسب الحاجة.

---

**آخر تحديث:** 2026-01-07  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}