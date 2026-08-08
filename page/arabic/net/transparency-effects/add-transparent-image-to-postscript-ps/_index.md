---
date: 2026-03-26
description: تعلم كيفية إنشاء مستند PostScript باستخدام .NET وإضافة صورة شفافة باستخدام
  Aspose.Page. يغطي هذا الدليل خطوة بخطوة المتطلبات المسبقة، والكود، والنصائح.
linktitle: Add Transparent Image to PostScript (PS)
second_title: Aspose.Page .NET API
title: إنشاء مستند PostScript باستخدام .NET وصورة شفافة (Aspose.Page)
url: /ar/net/transparency-effects/add-transparent-image-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مستند PostScript .NET مع صورة شفافة (Aspose.Page)

## المقدمة

في هذا الدرس ستتعلم **كيفية إنشاء مستند PostScript .NET** وإدراج صورة PNG شفافة باستخدام Aspose.Page لـ .NET. إضافة الصور الشفافة تتيح لك بناء رسومات أكثر غنىً وطبقات—مثالية للعلامات المائية، التراكبات، أو نماذج واجهة المستخدم داخل ملف PS. سنستعرض كل خطوة، من إعداد البيئة إلى عرض كل من الصور غير الشفافة والشفافة.

## إجابات سريعة
- **ماذا يفعل Aspose.Page؟** يوفر API متكامل لإنشاء وتعديل وعرض مستندات PostScript (PS) و XPS في .NET.  
- **هل يمكنني إضافة PNG شفافة؟** نعم—استخدم `DrawTransparentImage` للتحكم في الشفافية.  
- **ما إصدارات .NET المدعومة؟** جميع إصدارات .NET Framework و .NET Core و .NET 5/6 الحديثة.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص مطلوب للإنتاج.  
- **كم من الوقت تستغرق العملية؟** تقريباً 10‑15 دقيقة للمثال الأساسي.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

- **Aspose.Page for .NET** – قم بتنزيله من [رابط التحميل](https://releases.aspose.com/page/net/).  
- مجلد ستحفظ فيه مستند PS والصورة التي تريد إدراجها.  
- صورة PNG شفافة (مثال: `mask1.png`) ستُستخدم للطبقة الشفافة.

## استيراد مساحات الأسماء

أولاً، استورد مساحات الأسماء التي تحتوي على الفئات التي سنحتاجها. هذا يمنحنا الوصول إلى نموذج مستند PS، أدوات الرسومات، وأنواع الرسم الأساسية في .NET.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## الخطوة 1: إعداد دليل المستند الخاص بك

حدد المسار حيث ستوجد صورة المصدر وملف PS الناتج. استبدل العنصر النائب بالمسار الفعلي على جهازك.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء تدفق إخراج لمستند PostScript

سنكتب محتوى PS المُولد إلى تدفق ملف. يُمرّر هذا التدفق لاحقاً إلى مُنشئ `PsDocument`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTransparentImage_outPS.ps", FileMode.Create))
{
    // Your code for the next steps will go here.
}
```

## الخطوة 3: تعيين خيارات الحفظ ولون الخلفية

قم بتكوين `PsSaveOptions` لتحديد طريقة حفظ الملف. ضبط لون الخلفية مفيد عندما تريد خلفية صلبة خلف العناصر الشفافة.

```csharp
PsSaveOptions options = new PsSaveOptions();
options.BackgroundColor = Color.FromArgb(211, 8, 48);
```

## الخطوة 4: إنشاء مستند PS بصفحة واحدة جديد

أنشئ المستند باستخدام التدفق والخيارات المحددة أعلاه. العلامة `false` تخبر Aspose.Page بعدم إغلاق التدفق تلقائيًا.

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 5: حفظ الرسومات وترجمتها

قبل الرسم، نقوم بحفظ حالة الرسومات الحالية وترجمة الأصل بحيث تظهر صورنا في الموقع المطلوب على الصفحة.

```csharp
document.WriteGraphicsSave();
document.Translate(20, 100);
```

## كيفية إضافة صورة شفافة إلى مستند PostScript

### الخطوة 6: إضافة صورة RGB غير شفافة

أولاً نضيف نفس ملف PNG كصورة غير شفافة عادية. هذا يوضح الفرق البصري عندما نطبق الشفافية لاحقًا.

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 100, 0), Color.Empty);
}
```

### الخطوة 7: إضافة صورة شفافة

الآن نستخدم `DrawTransparentImage` لعرض PNG بقيمة شفافية. المعامل الثالث (`255`) يمثل الشفافية الكاملة؛ القيم الأقل تزيد الشفافية. هنا نُـ **حدد شفافية الصورة في .NET**.

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawTransparentImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 350, 0), 255);
}
```

> **نصيحة احترافية:** لجعل الصورة شفافة بنسبة 50 %، مرّر `128` بدلاً من `255`.

## الخطوة 8: استعادة الرسومات وإغلاق الصفحة

بعد الرسم، استعد حالة الرسومات السابقة وأغلق الصفحة لإنهاء المحتوى.

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## الخطوة 9: حفظ المستند

أخيرًا، احفظ ملف PS على القرص.

```csharp
document.Save();
```

باتباع هذه الخطوات، تكون قد **أنشأت مستند PostScript .NET** يحتوي على كل من صورة غير شفافة وصورة شفافة، مما يوضح كيفية **رسم صورة شفافة C#** باستخدام Aspose.Page.

## لماذا نستخدم Aspose.Page لتأثيرات الشفافية؟

- **تحكم كامل** في حالة الرسومات، المصفوفات، ومستويات الشفافية.  
- **بدون تبعيات خارجية**—كل شيء يعمل داخل كود .NET النقي.  
- **دعم متعدد المنصات** يتيح لك إنشاء ملفات PS على Windows أو Linux أو macOS.

## المشكلات الشائعة & استكشاف الأخطاء

| المشكلة | الحل |
|-------|----------|
| الصورة تظهر غير شفافة بالكامل حتى بعد `DrawTransparentImage` | تأكد من أن قيمة ألفا (المعامل الثالث) أقل من `255`. |
| ملف PS يظهر صفحة فارغة | تحقق من ضبط لون الخلفية وأن مسار التدفق صحيح. |
| استثناء “File not found” | تحقق مرة أخرى من `dataDir` وأن `mask1.png` موجود في ذلك المجلد. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام صيغ صور أخرى غير PNG للشفافية؟**  
ج: نعم—يدعم Aspose.Page صيغ PNG و GIF و TIFF للعرض الشفاف.

**س: هل Aspose.Page متوافق مع أحدث إطار .NET؟**  
ج: بالتأكيد. يتم تحديث المكتبة بانتظام لتدعم .NET 6 و .NET 7 والإصدارات الأحدث.

**س: هل يمكنني تطبيق الشفافية على مستند PS موجود؟**  
ج: نعم. افتح المستند باستخدام `PsDocument`، أضف صفحة جديدة أو عدّل صفحة موجودة، ثم استخدم نفس طريقة `DrawTransparentImage`.

**س: ما المزايا التي يقدمها Aspose.Page مقارنةً بمكتبات الرسومات العامة؟**  
ج: تم تصميمه خصيصًا لـ PS/XPS، ويوفر تحكمًا دقيقًا في الرسومات المتجهة، الخطوط، ومعالجة الصور دون الحاجة إلى محرك عرض كامل.

**س: هل هناك حدود لمستوى الشفافية الذي يمكنني تحديده؟**  
ج: لا. يمكنك تحديد أي قيمة ألفا من `0` (شفافة تمامًا) إلى `255` (غير شفافة تمامًا).

## الخلاصة

لقد أوضحنا كيفية **إنشاء مستند PostScript .NET** وإدراج كل من الصور غير الشفافة والشفافة باستخدام Aspose.Page. تفتح هذه التقنية الباب أمام تخطيطات مستندات متقدمة، العلامات المائية، والرسومات الطبقية—كلها مُولدة برمجيًا من C#.

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}