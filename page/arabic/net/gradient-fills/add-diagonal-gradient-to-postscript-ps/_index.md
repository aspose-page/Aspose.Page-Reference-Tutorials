---
date: 2026-02-23
description: تعلم كيفية إضافة تدرج إلى ملفات PostScript، حفظ ملف PostScript بحجم صفحة
  A4، وتعبئة مستطيل بتدرج باستخدام Aspose.Page لـ .NET.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: كيفية إضافة تدرج – تدرج قطري في PostScript (PS) باستخدام Aspose.Page .NET
url: /ar/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة تدرج لوني مائل إلى PostScript (PS) باستخدام Aspose.Page .NET

## المقدمة

إضافة تدرج لوني مائل إلى مستند PostScript (PS) يمكن أن يحسن المظهر البصري بشكل كبير، خاصة عندما تحتاج إلى **كيفية إضافة تدرج** في التقارير التقنية، الكتيبات، أو التطبيقات التي تعتمد على الرسومات. في هذا الدرس ستتعرف بالضبط على كيفية إضافة تدرج لوني إلى ملف PostScript، ضبط حجم الصفحة A4، وتعبئة مستطيل بانتقال لوني سلس باستخدام Aspose.Page لـ .NET.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page لـ .NET  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6  
- **هل يمكنني تغيير اتجاه التدرج؟** نعم – قم بتدوير تحويل الفرشاة كما هو موضح في الشيفرة  
- **كيف أحفظ النتيجة؟** استخدم `PsDocument.Save()` الذي يكتب ملف PostScript إلى القرص  
- **هل تحتاج إلى ترخيص للإنتاج؟** نعم، الترخيص التجاري يفتح جميع الوظائف  

## ما هو التدرج المائل في PostScript؟

التدرج المائل هو انتقال لوني خطي يجرى بزاوية (عادةً 45°) عبر الشكل. في PostScript، يتحقق ذلك بتطبيق `LinearGradientBrush` مع مصفوفة تحويل مخصصة تقوم بتدوير، تحجيم، وترجمة التدرج لتتناسب مع المستطيل المطلوب.

## لماذا نستخدم Aspose.Page لتعبئات التدرج؟

Aspose.Page يُبسط أوامر PostScript منخفضة المستوى، مما يتيح لك العمل مع كائنات رسومية مألوفة في .NET. يمكنك إنشاء تعبئات معقدة، ضبط أبعاد الصفحة، وتصدير مباشرة إلى **حفظ ملف PostScript** دون الحاجة للتعامل مع صsyntax PS الخام.

## المتطلبات المسبقة

- **مكتبة Aspose.Page لـ .NET** – قم بتحميلها [هنا](https://releases.aspose.com/page/net/).  
- **دليل المستند** – مجلد سيتم كتابة ملف `*.ps` المُولد فيه.

الآن بعد أن غطينا الأساسيات، دعنا نستعرض التنفيذ خطوة بخطوة.

## استيراد المساحات الاسمية

أولاً، استورد المساحات الاسمية التي تمنحك الوصول إلى جهاز EPS، أدوات الرسم، وفئات الإدخال/الإخراج.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## الخطوة 1: إنشاء تدفق إخراج لمستند PostScript (Create PostScript Document)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## الخطوة 2: ضبط حجم صفحة A4 (Save Options)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## الخطوة 3: إنشاء مستند PS بصفحة واحدة جديدة

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 4: تعريف معلمات المستطيل

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## الخطوة 5: إنشاء مسار رسومي

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## الخطوة 6: إنشاء فرشاة تدرج خطي (Fill Rectangle Gradient)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## الخطوة 7: إنشاء تحويل للفرشاة

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## الخطوة 8: تطبيق التحويلات على الفرشاة (Rotate, Scale, Translate)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## الخطوة 9: ضبط التحويل للفرشاة

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## الخطوة 10: ضبط اللون وتعبئة المستطيل

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## الخطوة 11: إغلاق الصفحة الحالية

```csharp
	//Close current page
	document.ClosePage();
```

## الخطوة 12: حفظ المستند (Save PostScript File)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## كيفية حفظ ملف PostScript

استدعاء `PsDocument.Save()` يكتب محتوى PostScript المكتمل إلى التدفق الذي فتحته في **الخطوة 1**. بعد انتهاء كتلة `using`، سيكون الملف `DiagonaGradient_outPS.ps` متاحًا في الدليل الذي حددته.

## حالات الاستخدام الشائعة

- **الوثائق التقنية** التي تحتاج إلى تظليل خلفية خفيف.  
- **الكتيبات التسويقية** حيث يضيف التدرج المائل مظهرًا عصريًا.  
- **مولدات التقارير الآلية** التي تنتج ملفات PS قابلة للطباعة مباشرة.

## استكشاف الأخطاء وإصلاحها ونصائح

- **ألوان غير صحيحة** – تحقق مرة أخرى من قيم ARGB الممررة إلى `LinearGradientBrush`.  
- **التدرج غير مرئي** – تأكد من أن مصفوفة التحويل تدور وتُحجم بشكل صحيح؛ استدعاء `Rotate(-45)` يحدد زاوية القطر.  
- **الملف غير مُنشأ** – تحقق من أن `dataDir` يشير إلى مجلد موجود وأن التطبيق يمتلك صلاحيات الكتابة.

## الأسئلة المتكررة

**س: هل Aspose.Page متوافق مع جميع إطارات .NET؟**  
ج: يدعم Aspose.Page مجموعة واسعة من إصدارات .NET، من .NET Framework 4.5+ إلى .NET 6+، مما يضمن توافقًا واسعًا.

**س: هل يمكنني تخصيص ألوان التدرج في Aspose.Page؟**  
ج: نعم، يمكنك تحديد أي ألوان ARGB عند إنشاء `LinearGradientBrush`، مما يمنحك التحكم الكامل في ألوان البداية والنهاية.

**س: هل هناك نسخة تجريبية متاحة لـ Aspose.Page؟**  
ج: نعم، يمكنك استكشاف ميزات Aspose.Page بتحميل النسخة التجريبية [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page؟**  
ج: احصل على ترخيص مؤقت لـ Aspose.Page [هنا](https://purchase.aspose.com/temporary-license/) لفتح قدرات إضافية أثناء التقييم.

**س: أين يمكنني العثور على دعم المجتمع لـ Aspose.Page؟**  
ج: تفاعل مع مجتمع Aspose.Page على [المنتدى](https://forum.aspose.com/c/page/39) للحصول على المساعدة والنقاشات.

---

**آخر تحديث:** 2026-02-23  
**تم الاختبار مع:** Aspose.Page لـ .NET (أحدث إصدار ثابت)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}