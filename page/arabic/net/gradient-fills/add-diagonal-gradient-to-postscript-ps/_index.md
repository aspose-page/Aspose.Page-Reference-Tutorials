---
title: أضف تدرجًا قطريًا إلى PostScript (PS) باستخدام Aspose.Page .NET
linktitle: إضافة تدرج قطري إلى PostScript (PS)
second_title: Aspose.Page .NET API
description: اكتشف بساطة إضافة التدرجات القطرية إلى مستندات PostScript في .NET باستخدام Aspose.Page. ارفع مستوى مشروعاتك باستخدام العناصر المرئية الديناميكية.
type: docs
weight: 10
url: /ar/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
---
## مقدمة

يمكن أن تؤدي إضافة تدرج قطري إلى مستند PostScript (PS) إلى إضفاء جاذبية بصرية وإبداعية على مشروعاتك. يوفر Aspose.Page for .NET حلاً سلسًا لدمج هذه الميزة في تطبيقاتك. في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة تدرج قطري إلى مستند PS باستخدام Aspose.Page، خطوة بخطوة.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Page لمكتبة .NET: تأكد من تثبيت Aspose.Page لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/page/net/).

- دليل المستندات: قم بإعداد دليل لمستنداتك حيث سيتم حفظ ملف PS الناتج.

والآن دعنا ننتقل إلى الدليل خطوة بخطوة.

## استيراد مساحات الأسماء

أولاً، تأكد من استيراد مساحات الأسماء الضرورية إلى مشروعك. تعد مساحات الأسماء هذه ضرورية للعمل مع وظائف Aspose.Page.

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
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## الخطوة 2: إنشاء خيارات الحفظ بحجم A4

```csharp
	//إنشاء خيارات الحفظ بحجم A4
	PsSaveOptions options = new PsSaveOptions();
```

## الخطوة 3: إنشاء مستند PS جديد مكون من صفحة واحدة

```csharp
	// قم بإنشاء مستند PS جديد مكون من صفحة واحدة
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 4: تحديد معلمات المستطيل

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## الخطوة 5: إنشاء مسار الرسومات

```csharp
	//قم بإنشاء مسار الرسومات من المستطيل الأول
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## الخطوة 6: إنشاء فرشاة التدرج الخطي

```csharp
	//قم بإنشاء فرشاة متدرجة خطية باستخدام المستطيل كحدود وألوان البداية والنهاية
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## الخطوة 7: إنشاء تحويل للفرشاة

```csharp
	//إنشاء تحويل للفرشاة. يجب أن يكون مكون المقياس X وY مساويًا لعرض المستطيل وارتفاعه على التوالي.
	// مكونات الترجمة هي إزاحات المستطيل
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## الخطوة 8: تطبيق التحولات على الفرشاة

```csharp
	//قم بتدوير التدرج، ثم قم بقياسه وترجمته للحصول على انتقال لوني مرئي في المستطيل المطلوب
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## الخطوة 9: اضبط التحويل إلى الفرشاة

```csharp
	//تعيين التحويل
	brush.Transform = brushTransform;
```

## الخطوة 10: اضبط الطلاء واملأ المستطيل

```csharp
	//تعيين الطلاء
	document.SetPaint(brush);

	//املأ المستطيل
	document.Fill(path);
```

## الخطوة 11: أغلق الصفحة الحالية

```csharp
	//إغلاق الصفحة الحالية
	document.ClosePage();
```

## الخطوة 12: احفظ المستند

```csharp
	//احفظ المستند
	document.Save();
}
// النهاية:1
```

باتباع هذه الخطوات، ستنجح في إضافة تدرج قطري إلى مستند PostScript باستخدام Aspose.Page لـ .NET.

## خاتمة

إن تحسين مستندات PS الخاصة بك باستخدام التدرجات القطرية يمكن أن يجعل مشاريعك جذابة وديناميكية بصريًا. يعمل Aspose.Page for .NET على تبسيط هذه العملية، مما يسمح للمطورين بدمج هذه الميزة بسهولة في تطبيقاتهم.

## الأسئلة الشائعة

### س1: هل Aspose.Page متوافق مع كافة أطر عمل .NET؟

ج1: يدعم Aspose.Page أطر عمل .NET المتنوعة، مما يضمن التوافق مع نطاق واسع من بيئات التطوير.

### س2: هل يمكنني تخصيص الألوان المتدرجة في Aspose.Page؟

ج2: نعم، توفر Aspose.Page المرونة في اختيار الألوان المتدرجة وتخصيصها وفقًا لمتطلبات مشروعك.

### س3: هل هناك نسخة تجريبية متاحة لـ Aspose.Page؟

 ج3: نعم، يمكنك استكشاف ميزات Aspose.Page عن طريق تنزيل الإصدار التجريبي[هنا](https://releases.aspose.com/).

### س4: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page؟

 ج4: احصل على ترخيص مؤقت لـ Aspose.Page[هنا](https://purchase.aspose.com/temporary-license/) لفتح ميزات إضافية.

### س5: أين يمكنني العثور على الدعم المجتمعي لـ Aspose.Page؟

 ج5: تفاعل مع مجتمع Aspose.Page على[المنتدى](https://forum.aspose.com/c/page/39) للمساعدة والمناقشات.