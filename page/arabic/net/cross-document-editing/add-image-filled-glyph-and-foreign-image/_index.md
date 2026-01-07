---
date: 2026-01-07
description: تعلم كيفية إنشاء مستند XPS باستخدام .NET و Aspose.Page. يوضح هذا الدليل
  إضافة رموز مملوءة بالصور وصور خارجية للحصول على مرئيات مستند أغنى.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: إنشاء مستند XPS باستخدام .NET مع Aspose.Page – حرف مملوء بصورة وصورة أجنبية
url: /ar/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مستند XPS .NET باستخدام Aspose.Page – حرف مملوء بالصورة وصورة أجنبية

## المقدمة

إذا كنت بحاجة إلى **إنشاء مستند XPS .NET** تطبيقات تبدو مصقولة ومهنية، فإن Aspose.Page يزودك بالأدوات لدمج الصور مباشرةً داخل الحروف وإعادة استخدام موارد الرسومات عبر المستندات. في هذا البرنامج التعليمي سنستعرض بناء ملفين XPS، ملء الحروف بفرشاة صورة، ثم إعادة استخدام تلك الفرشاة في مستند ثانٍ. في النهاية ستفهم لماذا يوفر هذا النهج الذاكرة، يبسط التنسيق، ويفتح إمكانيات إبداعية للتقارير، الفواتير، أو أي محتوى قابل للطباعة.

## إجابات سريعة
- **ما الذي يغطيه هذا البرنامج التعليمي؟** إضافة حروف مملوءة بالصورة وإعادة استخدامها عبر مستندات XPS باستخدام Aspose.Page لـ .NET.  
- **ما هي الكلمة المفتاحية الأساسية المستهدفة؟** `create xps document .net`.  
- **المتطلبات المسبقة؟** بيئة تطوير .NET، Aspose.Page لـ .NET، ومجلد لملفات XPS الخاصة بك.  
- **كم من الوقت تستغرق التنفيذ؟** حوالي 10‑15 دقيقة للحصول على نموذج عمل.  
- **هل يمكنني استخدام صيغ صور أخرى؟** نعم – أي صيغة يدعمها `System.Drawing.Image` في .NET.

## المتطلبات المسبقة

قبل الغوص في الشيفرة، تأكد من أن لديك ما يلي جاهزًا:

- **Aspose.Page for .NET** – قم بتنزيل أحدث مكتبة من [here](https://releases.aspose.com/page/net/).  
- **بيئة التطوير** – Visual Studio 2022 (أو أي بيئة تطوير تدعم .NET 6+).  
- **دليل المستندات** – أنشئ مجلدًا على جهازك سيحتوي على صور الإدخال وملفات XPS المولدة؛ سنشير إليه بـ **Your Document Directory** في المقاطع.

## استيراد مساحات الأسماء

ابدأ باستدعاء مساحات الأسماء المطلوبة للعمل مع كائنات XPS وأدوات الرسم.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## دليل خطوة بخطوة

### الخطوة 1: إنشاء مستند XPS الأول

نبدأ بإنشاء مستند XPS فارغ سيستضيف الحرف المملوء بالصورة.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### الخطوة 2: إضافة حروف إلى المستند الأول

بعد ذلك، أضف حرفًا (حرف نصي) سنملأه لاحقًا بفرشاة صورة.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### الخطوة 3: ملء الحروف بفرشاة صورة

هنا نقوم بإنشاء `ImageBrush` من ملف TIFF موجود في دليل البيانات الخاص بنا ونطبقه على الحرف. تم ضبط الفرشاة على وضع التكرار (tile mode) بحيث تتكرر الصورة إذا تجاوزت مساحة الحرف حجم الصورة.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### الخطوة 4: إنشاء مستند XPS الثاني

الآن نقوم بإنشاء مستند XPS ثانٍ سيعيد استخدام نمط الحرف وفرشاة الصورة من الأول.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### الخطوة 5: إضافة ح باستخدام الخط من المستند الأول

نضيف حرفًا إلى المستند الثاني، مع إعادة استخدام كائن الخط نفسه من المستند الأول. يضمن ذلك اتساقًا بصريًا عبر الملفين.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### الخطوة 6: إنشاء فرشاة صورة من تعبئة المستند الأول

بدلاً من تحميل الصورة مرة أخرى، نقوم باستنساخ الفرشاة من `glyphs1` وتعيينها إلى `glyphs2`. يوضح هذا كيف يمكنك **إنشاء مستند XPS .NET** سير عمل يشارك الموارد بكفاءة.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### الخطوة 7: حفظ المستندات

أخيرًا، احفظ كلا ملفي XPS على القرص. يمكنك الآن فتحهما بأي عارض XPS لرؤية تأثير الحرف المملوء بالصورة.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## لماذا تستخدم الحروف المملوءة بالصورة عند إنشاء مستند XPS .NET؟

- **التأثير البصري** – تحويل النص العادي إلى عناصر غنية بالرسومات دون تحويل الصفحة بأكملها إلى نقطية.  
- **إعادة استخدام الموارد** – مشاركة الفرشات والخطوط عبر مستندات متعددة، مما يقلل من استهلاك الذاكرة.  
- **المرونة** – تكرار، تمديد، أو تدوير فرشاة الصورة لتحقيق أنماط مخصصة أو علامة تجارية.

## المشكلات الشائعة والنصائح

- **أخطاء مسار الملف** – تأكد من أن `dataDir` ينتهي بفاصل مسار (`\` أو `/`) المناسب لنظام التشغيل الخاص بك.  
- **صيغ الصور غير المدعومة** – يعمل Aspose.Page بشكل أفضل مع TIFF و PNG و JPEG. قم بتحويل الصيغ الأخرى قبل الاستخدام.  
- **TileMode غير مطبق** – تأكد من تحويل النوع إلى `XpsImageBrush` قبل تعيين `TileMode`؛ وإلا سيتم تجاهل الخاصية.

## الأسئلة المتكررة

### س1: هل يمكنني استخدام صيغ صور مختلفة لملء الحروف؟

**ج:** نعم، يدعم Aspose.Page صيغ TIFF و PNG و JPEG و BMP و GIF. فقط قدم الامتداد الصحيح للملف في استدعاء `CreateImageBrush`.

### س2: كيف يمكنني تخصيص مظهر الحروف أكثر؟

**ج:** استكشف خصائص إضافية على `XpsGlyphs` مثل `Opacity` و `RenderTransform` و `Stroke` لضبط العرض بدقة.

### س3: هل Aspose.Page مناسب لمعالجة مجموعات مستندات كبيرة؟

**ج:** بالتأكيد. المكتبة مُحسّنة لسيناريوهات الأداء العالي ويمكنها معالجة آلاف ملفات XPS في وظائف الدُفعات.

### س4: هل يمكنني تطبيق أنماط مختلفة على حروف فردية؟

**ج:** نعم. كل مثال من `XpsGlyphs` يمكن أن يمتلك تعبئة، حد، وتحويل خاص به، مما يمنحك تحكمًا دقيقًا.

### س5: ما هي فوائد استخدام Aspose.Page مقارنة بأدوات معالجة المستندات الأخرى؟

**ج:** يقدم Aspose.Page واجهة برمجة تطبيقات كاملة ومجانية من الترخيص لإنشاء XPS ومعالجته وتحويله، مع وثائق شاملة ودعم على مدار 24 ساعة.

---

**آخر تحديث:** 2026-01-07  
**تم الاختبار مع:** Aspose.Page 24.12 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}