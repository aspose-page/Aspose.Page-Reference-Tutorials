---
date: 2026-01-18
description: تعلم كيفية إنشاء مستند بوستسكريبت .NET وإضافة مستطيلات باستخدام Aspose.Page
  لـ .NET. دليل خطوة بخطوة مع أمثلة على الشيفرة.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: إنشاء مستند بوستسكريبت .net – إضافة مستطيل باستخدام Aspose.Page
url: /ar/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مستطيل إلى PostScript (PS) باستخدام Aspose.Page لـ .NET

## المقدمة

إذا كنت تبحث عن **إنشاء مستند postscript .net**، فإن Aspose.Page توفر حلاً قويًا للتعامل مع ملفات PostScript. في هذا البرنامج التعليمي، سنرشدك إلى إضافة مستطيلات إلى مستند PostScript باستخدام Aspose.Page لـ .NET، مما يمنحك أساسًا قويًا لإنشاء رسومات أكثر غنى.

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.Page for .NET.
- **هل يمكنني إنشاء مستند PostScript من الصفر؟** نعم – تتيح لك الـ API إنشاء ملفات PS برمجيًا.
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للاختبار؛ الترخيص مطلوب للإنتاج.
- **كم من الوقت تستغرق التنفيذ؟** عادةً أقل من 10 دقائق للأشكال الأساسية.

## ما هو إنشاء مستند postscript .net؟
إنشاء مستند PostScript في .NET يعني توليد ملف .ps برمجيًا يصف محتوى الصفحة — نصًا، رسومات، أو أشكال — باستخدام Aspose.Page API. هذا النهج مثالي لإنشاء رسومات على الخادم، إنشاء تقارير تلقائيًا، أو أي سيناريو يتطلب تحكمًا دقيقًا في تنسيق الإخراج.

## لماذا تستخدم Aspose.Page لـ .NET؟
- **تحكم كامل في الرسومات** – ارسم أشكالًا، اضبط الألوان، وطبق الخطوط دون التعامل مع صsyntax PS منخفض المستوى.
- **متعدد المنصات** – يعمل على أنظمة Windows وLinux وmacOS.
- **بدون تبعيات خارجية** – المكتبة تدير جميع عمليات توليد PS داخليًا.
- **توثيق غني وأمثلة** – ابدأ العمل بسرعة.

## المتطلبات المسبقة

- **مكتبة Aspose.Page لـ .NET** – قم بتنزيلها وتثبيتها من [هنا](https://releases.aspose.com/page/net/).
- **بيئة التطوير** – Visual Studio أو VS Code أو أي IDE متوافق مع .NET.

## استيراد مساحات الأسماء

قبل بدء الترميز، استورد مساحات الأسماء التي تُظهر الفئات المطلوبة:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

الآن دعنا نقسم المثال إلى خطوات واضحة مرقمة.

## الخطوة 1: إعداد دليل المستند الخاص بك

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

استبدل `"Your Document Directory"` بالمجلد الذي تريد حفظ ملف PS الناتج فيه.

## الخطوة 2: إنشاء تدفق الإخراج لمستند PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

هذا التدفق يشير إلى **AddRectangle_outPS.ps**. يمكنك إعادة تسمية الملف أو تغيير الموقع حسب الحاجة.

## الخطوة 3: تعيين خيارات الحفظ وإنشاء مستند PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

هنا نخبر Aspose.Page باستخدام حجم صفحة A4 وإنشاء مستند من صفحة واحدة.

## الخطوة 4: إضافة مستطيل مملوء

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

نُعرّف مستطيلًا عند (250, 100) بعرض 150 وارتفاع 100، نحدد فرشاة برتقالية، ونملأ الشكل.

## الخطوة 5: إضافة مستطيل مُحدّد الحد

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

يتم إنشاء مستطيل ثانٍ أسفل الصفحة، هذه المرة بخط أحمر بسُمك 3 نقاط.

## الخطوة 6: إغلاق الصفحة وحفظ المستند

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

إغلاق الصفحة يُنهي الرسم، و`Save()` يكتب ملف PS إلى القرص.

## المشكلات الشائعة والنصائح

- **مسار ملف غير صحيح** – تأكد من أن `dataDir` ينتهي بفاصل مسار (`\\` أو `/`) أو استخدم `Path.Combine`.
- **ترخيص مفقود** – في بيئة الإنتاج، قم بتطبيق ترخيص Aspose قبل إنشاء المستند لتجنب علامات مائية للتقييم.
- **رؤية اللون** – إذا ظهر المستطيل فارغًا، تحقق من أن ألوان الفرشاة أو القلم تتباين مع خلفية الصفحة.

## الأسئلة المتكررة

**س:** هل يمكنني تخصيص ألوان المستطيلات؟  
**ج:** بالتأكيد. غيّر قيم `Color.Orange` أو `Color.Red` في مُنشئي `SolidBrush` و`Pen` إلى أي `System.Drawing.Color` تفضله.

**س:** هل Aspose.Page متوافق مع صيغ مستندات أخرى؟  
**ج:** نعم. بالإضافة إلى PostScript، يدعم Aspose.Page أيضًا إنشاء XPS وEPS.

**س:** كيف يمكنني إضافة نص إلى نفس المستند؟  
**ج:** استخدم الفئة `TextFragment` لوضع النص عند الإحداثيات المطلوبة، ثم استدعِ `document.Draw(textFragment)`.

**س:** أين يمكنني العثور على أمثلة إضافية والمرجع الكامل للـ API؟  
**ج:** استكشف الوثائق [هنا](https://reference.aspose.com/page/net/) وانضم إلى المجتمع في [منتدى Aspose.Page](https://forum.aspose.com/c/page/39).

**س:** هل يمكنني تجربة Aspose.Page قبل الشراء؟  
**ج:** نعم، قم بتنزيل نسخة تجريبية مجانية [هنا](https://releases.aspose.com/). للتقييم الموسع، فكر في الحصول على [ترخيص مؤقت](https://purchase.aspose.com/temporary-license/).

---

**آخر تحديث:** 2026-01-18  
**تم الاختبار مع:** Aspose.Page 24.12 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}