---
date: 2026-03-29
description: تعلم كيفية استخدام فرشاة تدرج لوني خطية في C# لإنشاء شفافية شبه حقيقية
  في PostScript باستخدام Aspose.Page لـ .NET.
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: فرشاة التدرج الخطي C# للشفافية الزائفة في PS
url: /ar/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# فرشاة التدرج الخطي C# للشفافية الزائفة في PostScript (PS)

## المقدمة

إذا كنت بحاجة إلى إضافة تأثير شفافية خفيف إلى ملفات PostScript (PS) الخاصة بك، فإن **فرشاة التدرج الخطي C#** هي الأداة المثالية. تجعل لك Aspose.Page for .NET من السهل رسم مستطيلات بملء تدرج معتم وشفاف جزئياً، مما يمنح مستنداتك مظهرًا عصريًا متعدد الطبقات. في هذا الدرس سنستعرض الخطوات الدقيقة لإنشاء شفافية زائفة باستخدام فرشاة التدرج الخطي في C#.

## إجابات سريعة
- **ما المكتبة التي توفر فرشاة التدرج الخطي؟** Aspose.Page for .NET
- **أي فئة رسومية تنشئ التدرج؟** `LinearGradientBrush`
- **هل يمكنني التحكم في الشفافية لكل لون؟** نعم، باستخدام `Color.FromArgb(alpha, …)`
- **هل أحتاج إلى ترخيص للإنتاج؟** يلزم وجود ترخيص صالح لـ Aspose.Page
- **الإصدارات المدعومة من .NET؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## ما هي فرشاة التدرج الخطي C#؟

`LinearGradientBrush` هي كائن GDI+ يرسم انتقالًا سلسًا بين لونين على طول خط مستقيم. عندما تحدد قناة ألفا (0‑255) لكل لون، يمكنك إنشاء تدرجات شفافة جزئياً — وهو بالضبط ما نحتاجه للشفافية الزائفة في PostScript.

## لماذا نستخدم فرشاة التدرج الخطي C# للشفافية الزائفة؟

- **تحكم دقيق في الشفافية:** ضبط قيمة ألفا لكل لون لتحقيق مستوى الشفافية المطلوب.  
- **عرض مستقل عن الجهاز:** تعمل الفرشاة بنفس الطريقة على الشاشة، PDF، EPS، ومخرجات PS.  
- **واجهة برمجة تطبيقات بسيطة:** بضع أسطر من كود C# تنتج تأثيرات بصرية احترافية.

## المتطلبات المسبقة

قبل الغوص في الكود، تأكد من أنك تمتلك:

- Aspose.Page for .NET مثبتة. يمكنك تنزيلها من [توثيق Aspose.Page](https://reference.aspose.com/page/net/).
- مجلد قابل للكتابة حيث سيتم حفظ مستند PostScript المُولد.

الآن بعد أن لديك الأدوات اللازمة، دعنا نبدأ بإنشاء المستطيلات الشفافة جزئياً.

## استيراد المساحات الاسمية

قبل أن نبدأ، استورد المساحات الاسمية التي تحتوي على الفئات التي سنستخدمها:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## الخطوة 1: إنشاء تدفق الإخراج لمستند PostScript

نبدأ بإنشاء تدفق ملف سيحمل ملف PS الناتج، ثم نهيئ `PsDocument`.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 2: إنشاء مستطيل بملء تدرج **معتم**

هنا نقوم بإنشاء `LinearGradientBrush` حيث ألوانه معتمة بالكامل (alpha = 255). سيعمل هذا المستطيل كطبقة خلفية.

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## الخطوة 3: إنشاء مستطيل بملء تدرج **شفاف جزئياً**

الآن نستخدم **فرشاة التدرج الخطي C#** حيث قيم ألفا أقل من 255 (مثلاً 150 و 50). هذا يجعل المستطيل شفافاً جزئياً، محققاً تأثير الشفافية الزائفة.

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## الخطوة 4: إغلاق الصفحة وحفظ المستند

أخيرًا نكمل الصفحة ونكتب ملف PS إلى القرص.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

باتباع هذه الخطوات الأربع يمكنك دمج المستطيلات المعتمة والشفافة جزئياً بسلاسة، مما يخلق تأثير شفافية زائفة مقنع في أي مخرج PostScript.

## المشكلات الشائعة والحلول

| المشكلة | سبب حدوثه | الحل |
|-------|----------------|-----|
| الألوان تظهر معتمة بالكامل | تم تعيين قيمة ألفا إلى 255 عن طريق الخطأ | استخدم `Color.FromArgb(alpha, …)` مع `alpha` < 255 |
| التدرج ممتد بشكل غير صحيح | مصفوفة التحويل غير صحيحة | تحقق من أن معلمات المصفوفة تتطابق مع أبعاد المستطيل |
| ملف الإخراج فارغ | لم يتم إغلاق الـ Stream أو عدم استدعاء `Save()` | تأكد من تنفيذ `document.ClosePage()` و `document.Save()` داخل كتلة `using` |

## الأسئلة المتكررة

**س: هل Aspose.Page متوافق مع جميع إصدارات .NET؟**  
ج: Aspose.Page for .NET متوافق مع إصدارات مختلفة من إطار .NET، مما يضمن المرونة وسهولة التكامل.

**س: هل يمكنني تطبيق الشفافية الزائفة على أشكال أخرى غير المستطيلات؟**  
ج: نعم، يمكن تطبيق نفس المبادئ على أي شكل عن طريق تعديل `GraphicsPath` وفقًا لذلك.

**س: أين يمكنني العثور على أمثلة إضافية ووثائق؟**  
ج: استكشف [Aspose.Page documentation](https://reference.aspose.com/page/net/) للحصول على أمثلة شاملة ومراجع API مفصلة.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page؟**  
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Page عبر [this link](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page؟**  
ج: قم بزيارة [this link](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت لـ Aspose.Page.

---

**آخر تحديث:** 2026-03-29  
**تم الاختبار مع:** Aspose.Page 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}