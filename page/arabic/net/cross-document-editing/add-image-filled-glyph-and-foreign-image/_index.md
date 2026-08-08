---
date: 2026-06-30
description: تعلم كيفية إنشاء XPS Document .NET وإضافة Image Filled Glyphs أو Foreign
  Images باستخدام Aspose.Page for .NET في بضع خطوات سهلة.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: إضافة Image Filled Glyph & Foreign Image
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: إنشاء XPS Document .NET – إضافة Image Filled Glyph & Foreign Image باستخدام
  Aspose.Page
url: /ar/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مستند XPS .NET – إضافة حرف مملوء بصورة وصورة خارجية باستخدام Aspose.Page

## مقدمة

في تطوير .NET، تُعد مهام **create XPS document .NET** شائعة عندما تحتاج إلى رسومات عالية الجودة ومستقلة عن الدقة. تجعل Aspose.Page for .NET ذلك بسيطًا وتتيح لك إثراء ملفات XPS بحروف مملوءة بالصور أو سحب صور من مستند XPS آخر. في نهاية هذا الدرس ستعرف كيفية إنشاء مستندين XPS، ملء الحروف بالصور، وإعادة استخدام تلك الصور عبر المستندات—مما يجعلها مثالية لإنشاء الفواتير، الشهادات، أو أي مخرجات غنية بصريًا.

## إجابات سريعة
- **ما الذي يدعمه Aspose.Page؟** أكثر من 25 صيغة صورة وإمكانية معالجة ملفات XPS حتى 500 MB دون تحميل كامل الذاكرة.  
- **كم عدد أسطر الكود لإضافة حرف مملوء بصورة؟** سطران فقط: إنشاء `ImageBrush` وتعيينه إلى `Glyph`.  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، الترخيص التجاري يزيل علامات التقييم.  
- **ما إصدارات .NET المتوافقة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **هل يمكنني إعادة استخدام الخطوط من XPS آخر؟** بالتأكيد – يمكنك استيراد مجموعة الخطوط من المستند الأول إلى الثاني.

## كيف تنشئ مستند XPS باستخدام Aspose.Page .NET؟

حمّل مكتبة Aspose.Page، أنشئ كائنًا من `XpsDocument`، أضف صفحة، واستدعِ `Save` – هذه هي سير العمل الكامل في ثلاث جمل مختصرة. يتعامل API تلقائيًا مع حجم الصفحة، DPI، وإدارة الموارد، لذا لا تحتاج إلى إدارة هياكل XPS منخفضة المستوى بنفسك. يتوسع هذا النهج من منشور صفحة واحدة إلى كتالوجات مئات الصفحات.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

- **Aspose.Page for .NET** – قم بتنزيله من [هنا](https://releases.aspose.com/page/net/).  
- **IDE .NET** – Visual Studio, Rider, أو VS Code مع امتداد C#.  
- **مجلد لمستنداتك** – سنشير إليه بـ **Your Document Directory** في مقتطفات الشيفرة.

## استيراد مساحات الأسماء

توفر مساحة الأسماء `Aspose.Page.XPS` الفئات الأساسية لمستندات XPS، بينما تحتوي `Aspose.Page.XPS.XpsModel` على عناصر النموذج مثل الحروف والفرش. استوردها في أعلى ملفك:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## ما هو الحرف المملوء بصورة؟

الحرف هو شكل متجهي يمكن عرضه بلون صلب، تدرج لوني، أو فرشاة صورة. عندما تطبق `ImageBrush`، يتم طلاء داخل الحرف بالصورة الموفرة، مما يتيح تأثيرات بصرية معقدة دون تحويل الصفحة بأكملها إلى نقطية.

## الخطوة 1: إنشاء مستند XPS الأول

`XpsDocument` يمثل حزمة XPS وهو نقطة الدخول لإنشاء وحفظ ملفات XPS. ابدأ بإنشاء مستند XPS الأول الذي سيستضيف الحروف المملوءة بالصور.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## الخطوة 2: إضافة حروف إلى المستند الأول

`XpsGlyphs` يحدد مجموعة من الحروف (أحرف النص) التي يمكن وضعها على صفحة. أضف حروفًا إلى المستند الأول، مع تحديد الخط، الحجم، النمط، والموقع.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## الخطوة 3: ملء الحروف بفرشاة صورة

`ImageBrush` يرسم منطقة بصورة، مما يسمح للأنماط أو الصور بملء الأشكال. املأ الحروف بفرشاة صورة، باستخدام صورة من دليل البيانات الخاص بك.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## الخطوة 4: إنشاء مستند XPS الثاني

`XpsDocument` يُستخدم لإنشاء ملف XPS جديد يمكنه احتواء صفحات، موارد، ومحتوى. الآن، أنشئ مستند XPS الثاني الذي سيضم الحروف من المستند الأول.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## الخطوة 5: إضافة حروف باستخدام الخط من المستند الأول

`Font` يمثل نوع الخط المستخدم لعرض النص في مستند XPS. أضف حروفًا إلى المستند الثاني، باستخدام الخط المستخرج من المستند الأول. من خلال مشاركة مجموعة الخطوط، تحافظ على حجم الملف منخفضًا وتضمن التناسق البصري.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## الخطوة 6: إنشاء فرشاة صورة من تعبئة المستند الأول

يمكن إنشاء `ImageBrush` من تعبئة موجودة لإعادة استخدام نفس الصورة عبر المستندات. أنشئ فرشاة صورة من تعبئة المستند الأول واستخدمها لملء الحروف في المستند الثاني. تسمح لك تقنية “الصورة الخارجية” بإعادة استخدام الرسومات دون تكرار ملف المصدر.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## الخطوة 7: حفظ المستندات

`Save` يكتب حزمة XPS إلى ملف، مدمجًا جميع الموارد. احفظ كل من مستندي XPS الأول والثاني إلى مجلد الإخراج. طريقة `Save` تكتب حزمة XPS، مدمجة جميع الموارد وتحافظ على الحروف المملوءة بالصور.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## المشكلات الشائعة والحلول

| المشكلة | سبب حدوثها | الحل |
|-------|----------------|-----|
| **الصورة لا تظهر داخل الحرف** | تم إنشاء `ImageBrush` بعنوان URI غير صحيح أو حجم الصورة يتجاوز حدود الحرف. | تحقق من مسار الصورة، واختياريًا اضبط `ImageBrush.Stretch = Stretch.Uniform`. |
| **الخطوط مفقودة في المستند الثاني** | لم يتم تصدير موارد الخط من XPS الأول. | استخدم `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` قبل إضافة الحروف. |
| **تباطؤ الأداء على الملفات الكبيرة** | تحميل صور كبيرة إلى الذاكرة لكل حرف. | أعد استخدام نسخة واحدة من `ImageBrush` لجميع الحروف، أو قلل دقة الصورة قبل الاستخدام. |

## الأسئلة المتكررة

### س1: هل يمكنني استخدام صيغ صور مختلفة لملء الحروف؟

ج1: نعم، يدعم Aspose.Page صيغ PNG، JPEG، BMP، GIF، TIFF، وأكثر—أكثر من 25 صيغة إجمالاً.

### س2: كيف يمكنني تخصيص مظهر الحروف أكثر؟

ج2: استكشف خصائص مثل `Glyph.Stroke`، `Glyph.FillOpacity`، و `Glyph.Transform` لضبط الخطوط الخارجية، الشفافية، والدوران.

### س3: هل Aspose.Page مناسب للتعامل مع مجموعات مستندات كبيرة؟

ج3: بالتأكيد. المعالجة تتم للملفات XPS التي تحتوي على مئات الصفحات باستخدام البث، مع الحفاظ على استهلاك الذاكرة أقل من 100 MB حتى للوثائق التي تحتوي على 500 صفحة.

### س4: هل يمكنني تطبيق أنماط مختلفة على حروف فردية؟

ج4: نعم، كل كائن `Glyph` يمتلك خصائص `Fill`، `Stroke`، و `Transform` الخاصة به، مما يسمح بتنسيق كل حرف على حدة.

### س5: ما هي فوائد استخدام Aspose.Page مقارنة بأدوات XPS الأخرى؟

ج5: يدعم Aspose.Page أكثر من 25 صيغة صورة، يعالج ملفات حتى 500 MB دون تحميل كامل للذاكرة، ويوفر API أصلي 100 % لـ .NET—مما يلغي الحاجة إلى COM interop أو أدوات خارجية.

---

**آخر تحديث:** 2026-06-30  
**تم الاختبار مع:** Aspose.Page 24.11 for .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إنشاء مستند XPS – Aspose.Page for .NET](/page/net/document-creation/)
- [إضافة صورة إلى مستند XPS باستخدام Aspose.Page for .NET](/page/net/image-management/add-image-to-xps-document/)
- [إضافة نسخة من الحرف وتغيير اللون باستخدام Aspose.Page for .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}