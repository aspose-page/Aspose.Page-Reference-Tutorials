---
date: 2026-03-03
description: تعلم كيفية استخدام Aspose.Page لـ .NET لتجميع الصور في مستندات XPS. يوضح
  هذا الدليل خطوة بخطوة كيفية تجميع الصورة بكفاءة وتعزيز الجاذبية البصرية.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: كيفية استخدام Aspose.Page لإضافة صورة متكررة إلى مستند XPS
url: /ar/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استخدام Aspose.Page لإضافة صورة متكررة إلى مستند XPS

## مقدمة

إذا كنت تتساءل **عن كيفية استخدام Aspose** لإضفاء نمط بصري أغنى على ملفات XPS الخاصة بك، فقد وصلت إلى المكان الصحيح. في هذا الدرس سنستعرض الخطوات الدقيقة المطلوبة **لتكرار صورة** داخل مستند XPS باستخدام Aspose.Page لـ .NET. في النهاية ستحصل على مقتطف قابل لإعادة الاستخدام يمكنك إدراجه في أي مشروع .NET لإنشاء رسومات صور متكررة بسرعة.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for .NET  
- **أي طريقة تنشئ الفرشاة المتكررة؟** `CreateImageBrush` مع `TileMode = XpsTileMode.Tile`  
- **هل يمكن التحكم في الشفافية؟** نعم – اضبط `path.Fill.Opacity` (مثال: 0.5f)  
- **هل أحتاج إلى ترخيص للاختبار؟** الترخيص المؤقت يكفي للتقييم؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+

## ما هو Aspose.Page ولماذا نستخدم الصور المتكررة؟

Aspose.Page هو API قوي يتيح للمطورين إنشاء وتحرير وعرض XPS وPDF وغيرها من الصيغ القائمة على الصفحات دون الاعتماد على Microsoft Office. تكرار الصورة—أي تكرار البت ماب عبر شكل—يساعدك على ملء مساحات كبيرة بأنماط أو علامات مائية أو خلفيات نسيجية مع الحفاظ على حجم الملف منخفضًا.

## كيفية استخدام Aspose.Page لتكرار الصور في مستندات XPS

فيما يلي مثال كامل جاهز للتنفيذ. كل خطوة مشروحة بلغة بسيطة قبل كتلة الشيفرة المقابلة، لتتمكن من فهم **سبب** كل سطر.

### المتطلبات المسبقة

- **Aspose.Page for .NET** – قم بتحميل المكتبة وإضافتها إلى مشروعك من الموقع الرسمي [هنا](https://reference.aspose.com/page/net/).  
- **بيئة التطوير** – Visual Studio (أي إصدار) أو أي بيئة تطوير .NET أخرى تفضلها.

### استيراد المساحات الاسمية

أولاً، استورد المساحات الاسمية المطلوبة حتى يعرف المترجم أين يجد فئات XPS.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### الخطوة 1: تحديد دليل المستند

حدد المكان الذي سيُحفظ فيه ملف XPS المُولد والصورة المصدر. استبدل العنصر النائب بمسار فعلي على جهازك.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### الخطوة 2: إنشاء مستند XPS جديد

أنشئ مستند XPS فارغ سيحمل الرسمة المتكررة.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### الخطوة 3: إضافة صورة متكررة

هنا نقوم بإنشاء مسار مستطيل، نملأه بـ `ImageBrush`، ونضبط الفرشاة على وضع التكرار. خاصية `TileMode` تخبر المحرك بتكرار الصورة أفقياً وعمودياً. عدّل إحداثيات المستطيل أو الصورة المصدر حسب حاجتك.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### الخطوة 4: حفظ مستند XPS الناتج

أخيرًا، اكتب المستند إلى القرص. يمكن فتح ملف الإخراج بأي عارض XPS أو معالجته لاحقًا باستخدام Aspose.Page.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## المشكلات الشائعة والنصائح

- **أخطاء المسار** – تأكد من أن `dataDir` ينتهي بشرطة مائلة (`/`) أو استخدم `Path.Combine` لتجنب مشاكل الفواصل المفقودة.  
- **اختلاف أحجام الصورة** – يجب أن تكون الصورة المصدر كبيرة بما يكفي لمنطقة التكرار؛ وإلا قد يظهر النمط مشوهًا.  
- **الشفافية غير مرئية** – بعض العارضات تتجاهل الشفافية في XPS؛ اختبر باستخدام عارض يدعم عرض XPS بالكامل (مثل XPS Viewer على Windows).

## الأسئلة المتكررة

### س1: هل Aspose.Page متوافق مع جميع بيئات تطوير .NET؟
ج: نعم، Aspose.Page يعمل مع Visual Studio وRider وVS Code وأي بيئة تدعم .NET.

### س2: هل يمكنني تعديل شفافية الصورة المتكررة؟
ج: بالتأكيد. المثال يضبط `path.Fill.Opacity = 0.5f;`—يمكنك تغيير القيمة العشرية بين 0 (شفاف) و 1 (معتم).

### س3: هل توجد أوضاع تكرار أخرى متاحة في Aspose.Page لـ .NET؟
ج: نعم. بجانب `XpsTileMode.Tile`، يمكنك استخدام `FlipX`، `FlipY`، و`FlipXY` لإنشاء أنماط معكوسة.

### س4: كيف أتعامل مع الترخيص المؤقت لـ Aspose.Page؟
ج: راجع صفحة [الترخيص المؤقت](https://purchase.aspose.com/temporary-license/) على موقع Aspose للحصول على تفاصيل حول الحصول على ترخيص تجريبي وتطبيقه.

### س5: أين يمكنني طلب المساعدة أو التواصل مع مجتمع Aspose.Page؟
ج: زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) لطرح الأسئلة، مشاركة المقتطفات، والتعلم من المطورين الآخرين.

### س6: هل يمكنني استخدام هذه الطريقة لإنشاء تأثير علامة مائية؟
ج: نعم. بتقليل الشفافية واختيار صورة شبه شفافة، تعمل الفرشاة المتكررة كعلامة مائية متكررة بشكل مثالي.

## الخلاصة

أنت الآن تعرف **كيفية استخدام Aspose** لإضافة صورة متكررة إلى مستند XPS، التحكم في شفافيتها، وحفظ النتيجة للاستخدام لاحقًا. هذه التقنية مثالية للأنماط الخلفية، العلامات المائية، أو أي حالة تحتاج فيها إلى رسمة متكررة تضيف جاذبية بصرية دون زيادة حجم الملف. لا تتردد في تجربة أشكال، صور، وأوضاع تكرار مختلفة لتناسب احتياجات مشروعك.

---

**آخر تحديث:** 2026-03-03  
**تم الاختبار مع:** Aspose.Page for .NET (أحدث إصدار)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}