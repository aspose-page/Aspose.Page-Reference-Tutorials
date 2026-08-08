---
date: 2026-06-30
description: تعلم كيفية إنشاء مستند postscript .NET وإضافة مستطيلات باستخدام Aspose.Page
  لـ .NET. دليل خطوة بخطوة مع أمثلة الشيفرة.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: إضافة مستطيل إلى PostScript (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: إنشاء مستند PostScript .NET – إضافة مستطيل Aspose.Page
url: /ar/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مستطيل إلى PostScript (PS) باستخدام Aspose.Page لـ .NET

## مقدمة

Aspose.Page for .NET هي مكتبة تمكّن من إنشاء ومعالجة ملفات PostScript و EPS و XPS برمجيًا. إذا كنت تبحث عن **إنشاء مستند postscript .net**، فإن هذا الدليل يشرح لك كيفية إضافة مستطيلات إلى مستند PostScript باستخدام Aspose.Page، مما يمنحك أساسًا قويًا لتوليد رسومات أكثر غنى.

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.Page for .NET.  
- **هل يمكنني إنشاء مستند PostScript من الصفر؟** نعم – تتيح لك API إنشاء ملفات PS برمجيًا.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تعمل للاختبار؛ الترخيص مطلوب للإنتاج.  
- **كم من الوقت تستغرق العملية؟** عادةً أقل من 10 دقائق للأشكال الأساسية.

## ما هو إنشاء مستند postscript .net؟
إنشاء مستند PostScript في .NET يعني توليد ملف `.ps` برمجيًا يصف محتوى الصفحة — نصًا أو رسومات أو أشكال — باستخدام Aspose.Page API. هذا النهج مثالي لتوليد الرسومات على الخادم، إنشاء تقارير تلقائية، أو أي سيناريو يتطلب تحكمًا دقيقًا في تنسيق الإخراج.

## لماذا تستخدم Aspose.Page لـ .NET؟
Aspose.Page يدعم **30+ graphics primitives** ويمكنه إنشاء ملفات حتى **500 MB** دون تحميل المستند بالكامل في الذاكرة، مما يوفر عرضًا عالي الأداء على Windows و Linux و macOS. يمنحك تحكمًا كاملاً في الأشكال والألوان والحدود مع إلغاء الحاجة لكتابة شفرة PostScript منخفضة المستوى.

- **Full control over graphics** – ارسم الأشكال، حدد الألوان، وطبق الحدود دون التعامل مع صsyntax PS منخفض المستوى.  
- **Cross‑platform** – يعمل على أنظمة Windows و Linux و macOS.  
- **No external dependencies** – المكتبة تتعامل مع جميع عمليات توليد PS داخليًا.  
- **Rich documentation & examples** – ابدأ العمل بسرعة.

## المتطلبات المسبقة

- **Aspose.Page for .NET Library** – قم بتنزيل وتثبيت من [here](https://releases.aspose.com/page/net/).  
- **Development Environment** – Visual Studio, VS Code، أو أي بيئة تطوير متوافقة مع .NET.

## استيراد المساحات الاسمية

مساحة الأسماء `Aspose.Page` تكشف عن الفئات الأساسية التي ستحتاجها، مثل `Document` و `Page` و `SolidBrush` و `Pen`. استوردها قبل بدء كتابة الشيفرة.

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

## الخطوة 2: إنشاء تدفق إخراج لمستند PostScript

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

نحدد مستطيلًا عند (250, 100) بعرض 150 وارتفاع 100، نعيّن فرشاة برتقالية، ونملأ الشكل.

## الخطوة 5: إضافة مستطيل محاط بحد

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

يتم إنشاء مستطيل ثاني أسفل الصفحة، هذه المرة بخط حدود أحمر بسمك 3 نقاط.

## الخطوة 6: إغلاق الصفحة وحفظ المستند

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

إغلاق الصفحة ينهى الرسم، و`Save()` يكتب ملف PS إلى القرص.

## كيف تنشئ مستند postscript .net؟
`Document` هي الفئة الرئيسية التي تمثل ملف PostScript في Aspose.Page. `SaveOptions` تحدد الإعدادات مثل حجم الصفحة وتنسيق الإخراج للمستند. حمّل كائن `Document`، اضبط `SaveOptions` لصفحة A4، ارسم الأشكال باستخدام `SolidBrush` أو `Pen`، ثم استدعِ `document.Save()` — العملية بأكملها تتطلب بضع أسطر من الشيفرة وتعمل على أي بيئة .NET مدعومة. يتيح لك هذا النمط إنشاء ملفات PostScript متوافقة بالكامل دون الحاجة للتعامل مع شفرة PS الخام.

## كيف تولد ملف postscript
استخدم فئة `SaveOptions` في Aspose.Page لتحديد تنسيق الإخراج كـ PostScript (`SaveFormat.PS`). تقوم المكتبة ببث المحتوى مباشرة إلى ملف أو تدفق ذاكرة، مما يتيح لك إنشاء مستندات كبيرة بكفاءة دون استهلاك مفرط للذاكرة.

## المشكلات الشائعة والنصائح

- **Incorrect file path** – تأكد من أن `dataDir` ينتهي بفاصل مسار (`\\` أو `/`) أو استخدم `Path.Combine`.  
- **Missing license** – في بيئة الإنتاج، قم بتطبيق ترخيص Aspose قبل إنشاء المستند لتجنب علامات مائية للتقييم.  
- **Color visibility** – إذا ظهر المستطيل فارغًا، تحقق من أن ألوان الفرشاة أو القلم تتباين مع خلفية الصفحة.

## الأسئلة المتكررة

**Q:** هل يمكنني تخصيص ألوان المستطيلات؟  
**A:** بالتأكيد. غيّر قيم `Color.Orange` أو `Color.Red` في مُنشئي `SolidBrush` و `Pen` إلى أي `System.Drawing.Color` تفضله.

**Q:** هل Aspose.Page متوافق مع صيغ مستندات أخرى؟  
**A:** نعم. بالإضافة إلى PostScript، يدعم Aspose.Page أيضًا توليد XPS و EPS.

**Q:** كيف يمكنني إضافة نص إلى نفس المستند؟  
**A:** استخدم الفئة `TextFragment` لوضع النص عند الإحداثيات المطلوبة، ثم استدعِ `document.Draw(textFragment)`.

**Q:** أين يمكنني العثور على أمثلة إضافية والمرجع الكامل للـ API؟  
**A:** استكشف الوثائق [here](https://reference.aspose.com/page/net/) وانضم إلى المجتمع في [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** هل يمكنني تجربة Aspose.Page قبل الشراء؟  
**A:** نعم، قم بتنزيل نسخة تجريبية مجانية [here](https://releases.aspose.com/). للتقييم الموسع، فكر في الحصول على [temporary license](https://purchase.aspose.com/temporary-license/).

**آخر تحديث:** 2026-06-30  
**تم الاختبار مع:** Aspose.Page 24.12 for .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية إنشاء مستند PostScript باستخدام Aspose.Page لـ .NET](/page/net/document-creation/create-postscript-document/)
- [إضافة صورة إلى مستند PostScript (PS) باستخدام Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [إضافة نص إلى مستند PostScript (PS) باستخدام Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}