---
title: إظهار الشفافية الزائفة في PostScript (PS) باستخدام Aspose.Page
linktitle: إظهار الشفافية الزائفة في بوستسكريبت (PS)
second_title: Aspose.Page .NET API
description: اكتشف قوة الشفافية الزائفة في PostScript باستخدام Aspose.Page لـ .NET. اتبع دليلنا خطوة بخطوة للحصول على مستندات مذهلة بصريًا.
type: docs
weight: 13
url: /ar/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---
## مقدمة

هل تتطلع إلى تحسين المظهر المرئي لمستندات PostScript (PS) الخاصة بك من خلال دمج الشفافية الزائفة؟ يوفر Aspose.Page for .NET حلاً قويًا لتحقيق هذا التأثير دون عناء. في هذا البرنامج التعليمي خطوة بخطوة، سنرشدك خلال عملية إظهار الشفافية الزائفة في PostScript باستخدام Aspose.Page.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

- Aspose.Page لـ .NET: تأكد من تثبيت مكتبة Aspose.Page لـ .NET. يمكنك تنزيله من[Aspose.Page الوثائق](https://reference.aspose.com/page/net/).

- دليل المستندات: قم بإعداد دليل لتخزين مستندات PostScript الخاصة بك.

الآن بعد أن أصبحت لديك الأدوات اللازمة في ترسانتك، دعنا نستكشف كيفية عرض الشفافية الزائفة في PostScript باستخدام Aspose.Page.

## استيراد مساحات الأسماء

قبل الخوض في المثال، تأكد من استيراد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## الخطوة 1: إنشاء دفق الإخراج لمستند PostScript

```csharp
// البداية:1
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
//إنشاء دفق الإخراج لمستند بوستسكريبت
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//إنشاء خيارات الحفظ بحجم A4
	PsSaveOptions options = new PsSaveOptions();

	// قم بإنشاء مستند PS جديد مكون من صفحة واحدة
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 2: إنشاء مستطيل مع تعبئة متدرجة غير شفافة

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

## الخطوة 3: إنشاء مستطيل مع تعبئة متدرجة شفافة

```csharp
	offsetX = 350;

	//قم بإنشاء مسار الرسومات من المستطيل الأول
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//قم بإنشاء ألوان فرشاة متدرجة خطية بحيث تكون الشفافية ليست 255، بل 150 و50. لذا فهي شفافة.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## الخطوة 4: أغلق الصفحة الحالية واحفظ المستند

```csharp
	document.ClosePage();
	document.Save();
}
// النهاية:1
```

باتباع هذه الخطوات، يمكنك دمج الشفافية الزائفة بسلاسة في مستندات PostScript الخاصة بك باستخدام Aspose.Page for .NET.

## خاتمة

في الختام، يقدم Aspose.Page for .NET طريقة مباشرة وفعالة لتحسين العناصر المرئية لمستندات PostScript الخاصة بك. توفر الخطوات الموضحة أعلاه مسارًا واضحًا لدمج الشفافية الزائفة، مما يسمح لك بإنشاء مخرجات مذهلة بصريًا.

## الأسئلة الشائعة

### س1: هل Aspose.Page متوافق مع كافة إصدارات .NET؟

ج1: يتوافق Aspose.Page for .NET مع إصدارات مختلفة من .NET Framework، مما يضمن المرونة وسهولة التكامل.

### س2: هل يمكنني تطبيق الشفافية الزائفة على أشكال أخرى إلى جانب المستطيلات؟

ج2: نعم، يمكن تطبيق نفس المبادئ على الأشكال الأخرى عن طريق ضبط GraphicsPath وفقًا لذلك.

### س3: أين يمكنني العثور على أمثلة ووثائق إضافية؟

 ج3: اكتشف[Aspose.Page الوثائق](https://reference.aspose.com/page/net/) للحصول على أمثلة شاملة ووثائق مفصلة.

### س4: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page؟

 ج4: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.Page من[هذا الرابط](https://releases.aspose.com/).

### س5: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page؟

 ج5: زيارة[هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت لصفحة Aspose.Page.