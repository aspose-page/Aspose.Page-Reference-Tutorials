---
date: 2026-03-03
description: تعلم كيفية تعيين حجم صفحة مخصص وإضافة صفحة PS ثانية إلى مستند PostScript
  باستخدام Aspose.Page لـ .NET.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: تعيين حجم صفحة مخصص في مستند PS باستخدام Aspose.Page
url: /ar/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة صفحة إلى مستند PostScript (PS) باستخدام Aspose.Page

## مقدمة

## إجابات سريعة
- **هل يمكنني تعيين حجم صفحة مخصص؟** نعم – فقط مرّر العرض والارتفاع عند فتح الصفحة.  
- **كيف يمكنني إضافة صفحة PS ثانية؟** استدعِ `document.OpenPage(width, height)` مرة ثانية.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.  
- **هل أحتاج إلى ترخيص؟** الترخيص المؤقت يكفي للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **أين يمكنني تحميل Aspose.Page؟** من صفحة التحميل الرسمية المذكورة أدناه.

## المتطلبات المسبقة

قبل الخوض في الشرح، تأكد من توفر المتطلبات التالية:

- معرفة عملية بتطوير .NET.  
- تثبيت Visual Studio على جهازك.  
- مكتبة Aspose.Page لـ .NET، والتي يمكنك تحميلها [هنا](https://releases.aspose.com/page/net/).  
- دليل المستندات المفضل لديك للاختبار.

## استيراد المساحات الاسمية

تأكد من تضمين المساحات الاسمية الضرورية في مشروعك للوصول إلى الوظائف التي توفرها Aspose.Page. في المثال المرفق، تم تضمين المساحات الاسمية بشكل ضمني، لكن من الضروري التحقق مرة أخرى وإجراء التعديلات حسب بنية مشروعك.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## الخطوة 1: إعداد مشروعك

أنشئ مشروع .NET جديد في Visual Studio وقم بإعداد التكوينات اللازمة. تأكد من إضافة مرجع لمكتبة Aspose.Page في مشروعك.

## تعيين حجم صفحة مخصص وإضافة صفحة PS ثانية

يوضح هذا القسم بالضبط كيفية **تعيين حجم صفحة مخصص** لكل صفحة وكيفية **إضافة صفحة ps ثانية** إلى نفس المستند.

### الخطوة 2: تهيئة المستند

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### الخطوة 3: إضافة الصفحة الأولى (الحجم الافتراضي)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### الخطوة 4: إضافة الصفحة الثانية بحجم مختلف (مخصص)

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### الخطوة 5: حفظ المستند

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

اتبع هذه الخطوات بدقة، وستتمكن بنجاح من **تعيين حجم صفحة مخصص** وإضافة **صفحة PS ثانية** إلى مستند PostScript باستخدام Aspose.Page لـ .NET.

## لماذا هذا مهم

- **تخطيط دقيق** – أبعاد الصفحة المخصصة تتيح لك مطابقة مواصفات الطابعة أو إنشاء تنسيقات كتيب فريدة.  
- **صفحات متعددة** – إضافة صفحة ثانية (أو أكثر) يتيح تقارير متعددة الصفحات دون الحاجة إلى أدوات دمج خارجية.  
- **متعدد المنصات** – يمكن عرض ملف PS المُولد على أي جهاز يدعم PostScript أو تحويله إلى PDF لاحقًا.

## المشكلات الشائعة وإصلاح الأخطاء

- **مسار غير صحيح** – تأكد من أن `dataDir` ينتهي بفاصل مسار أو استخدم `Path.Combine`.  
- **مشكلات الترخيص** – بدون ترخيص صالح، قد تضيف المكتبة علامة مائية أو تقيد عدد الصفحات.  
- **الخلط بين الوحدات** – العرض والارتفاع يُقاسان بالنقاط (1 نقطة = 1/72 بوصة). اضبط القيم وفقًا لذلك.

## الأسئلة المتكررة

**س1: هل Aspose.Page متوافق مع صيغ مستندات مختلفة؟**  
ج1: يركز Aspose.Page أساسًا على معالجة مستندات PostScript. بالنسبة للصيغ الأخرى، يمكنك استكشاف مكتبات Aspose المصممة لاحتياجات محددة.

**س2: هل يمكنني تخصيص حجم الصفحة في Aspose.Page؟**  
ج2: بالتأكيد! كما هو موضح في الشرح، يمكنك تحديد أحجام مختلفة لكل صفحة وفقًا لمتطلباتك.

**س3: أين يمكنني العثور على المزيد من الأمثلة والوثائق؟**  
ج3: زر [الوثائق](https://reference.aspose.com/page/net/) للحصول على معلومات شاملة ومجموعة متنوعة من الأمثلة.

**س4: كيف أحصل على ترخيص مؤقت لـ Aspose.Page؟**  
ج4: انتقل إلى [هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت لأغراض الاختبار.

**س5: أين يمكنني الحصول على دعم المجتمع أو طرح الأسئلة؟**  
ج5: انضم إلى [منتدى مجتمع Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع المطورين الآخرين، مشاركة الخبرات، وطلب المساعدة.

---

**آخر تحديث:** 2026-03-03  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}