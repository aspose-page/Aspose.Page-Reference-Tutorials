---
date: 2026-08-08
description: تعلم كيفية إضافة عناصر المصفوفة إلى بيانات EPS الوصفية باستخدام Aspose.Page
  EPS metadata. يوضح هذا الدليل خطوة بخطوة لـ .NET كيفية إضافة عناصر المصفوفة وقراءة
  ملفات EPS بكفاءة.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: إضافة عناصر المصفوفة
og_description: اكتشف كيفية إضافة عناصر المصفوفة إلى بيانات EPS الوصفية باستخدام Aspose.Page
  EPS metadata. اتبع هذا البرنامج التعليمي المختصر لـ .NET لقراءة ملفات EPS وإدارة
  البيانات الوصفية بكفاءة.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: إضافة عناصر المصفوفة باستخدام Aspose.Page EPS metadata في .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: إضافة عناصر المصفوفة باستخدام Aspose.Page EPS metadata في .NET
url: /ar/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة عناصر المصفوفة مع بيانات تعريف Aspose.Page EPS في .NET

## مقدمة

في هذا الدرس ستتعلم كيفية إضافة عناصر المصفوفة إلى بيانات تعريف EPS باستخدام **Aspose.Page EPS metadata**. سواء كنت بحاجة إلى إثراء ملف EPS بعناوين إضافية أو منشئين أو وسوم مخصصة، فإن Aspose.Page يجعل المهمة بسيطة لأي مطور .NET. سنستعرض كل خطوة، من فتح تدفق EPS إلى حفظ حزمة XMP المحدثة، حتى تتمكن من دمج معالجة البيانات التعريفية في تطبيقاتك بثقة.

## إجابات سريعة
- **ما الذي يتيح لك القيام به Aspose.Page EPS metadata؟** يتيح قراءة وكتابة مصفوفات بيانات XMP التعريفية داخل ملفات EPS من .NET.  
- **أي فئة تمثل مستند EPS؟** `PsDocument` هي الفئة الأساسية لتحميل وحفظ محتوى EPS.  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تعمل للاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **هل يمكنني تعديل البيانات التعريفية دون تغيير رسومات EPS؟** نعم، يتم تغيير حزمة XMP فقط، مع ترك محتوى الصفحة دون تعديل.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.

## ما هو Aspose.Page EPS metadata؟
Aspose.Page EPS metadata هو كتلة معلومات مبنية على XMP مدمجة داخل ملف EPS. تخزن خصائص وصفية مثل العناوين، المنشئين، الكلمات المفتاحية، والوسوم المخصصة وفقًا للمعيار ISO 16684‑1. يمكن الوصول إلى البيانات التعريفية وتعديلها برمجيًا عبر Aspose.Page API، مما يتيح إدارة مستندات تلقائية وتحسين البحث.

## لماذا تعديل بيانات تعريف EPS؟
يمكن لـ Aspose.Page معالجة **أكثر من 30 حقلًا من البيانات التعريفية** والتعامل مع ملفات EPS تصل إلى **200 ميغابايت** دون تحميل المستند بالكامل في الذاكرة، مما يقلل استهلاك المعالج بنسبة تصل إلى 40 % مقارنةً بتحليل الملف بالكامل. تحديث البيانات التعريفية يحسن قابلية البحث، والامتثال، وأتمتة سير العمل اللاحق.

## المتطلبات المسبقة

- معرفة أساسية ببرمجة .NET.  
- تثبيت Aspose.Page for .NET – قم بتنزيله من [download Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (أو أي بيئة تطوير متوافقة مع .NET) لتشغيل عينة الشيفرة.  

## كيفية إضافة عناصر المصفوفة إلى بيانات تعريف EPS؟
لإضافة عناصر المصفوفة، قم أولاً بتحميل ملف EPS في كائن `PsDocument`، ثم استرجع حزمة XMP الخاصة به باستخدام `GetXmpMetadata()`. استخدم طريقة `AddArrayItem()` على مصفوفة XMP المطلوبة، مثل `dc:title` أو `dc:creator`، لإضافة قيم جديدة. أخيرًا، استدعِ `Save()` لكتابة البيانات التعريفية المحدثة إلى الملف مع الحفاظ على محتوى الرسومات دون تغيير.

### الخطوة 1: تهيئة تدفق إدخال ملف EPS
`PsDocument` يمثل مستند EPS ويوفر طرقًا للوصول إلى محتواه. الشيفرة التالية تفتح ملف EPS كتيار وتُنشئ كائن `PsDocument` instance.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### الخطوة 2: الحصول على بيانات XMP التعريفية
`GetXmpMetadata()` يسترجع حزمة XMP المدمجة في ملف EPS. إذا لم توجد حزمة، فإن API يولد واحدة جديدة استنادًا إلى تعليقات PostScript الموجودة.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### الخطوة 3: تغيير قيم بيانات XMP التعريفية
`AddArrayItem()` يضيف قيمة جديدة إلى مصفوفة XMP موجودة دون الكتابة فوق الإدخالات الأخرى. استخدمها لإضافة عناوين، منشئين، أو وسوم مخصصة إلى البيانات التعريفية.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### الخطوة 4: حفظ ملف EPS مع بيانات XMP التعريفية المعدلة
`Save()` يكتب حزمة XMP المعدلة مرة أخرى إلى ملف EPS مع الحفاظ على محتوى PostScript الأصلي. قدم مسار الإخراج لإنشاء ملف جديد أو استبدال المصدر.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## المشكلات الشائعة واستكشاف الأخطاء وإصلاحها

- **حزمة XMP فارغة** – إذا أعادت `GetXmpMetadata()` القيمة `null`، تأكد من أن ملف EPS يحتوي على كتلة تعليقات واحدة على الأقل؛ وإلا، أنشئ كائن `XmpMetadata` جديد يدويًا.  
- **مشكلات الترميز** – استخدم UTF‑8 عند إضافة قيم نصية لتجنب تلف الأحرف في اللغات غير ASCII.  
- **الملفات الكبيرة** – بالنسبة لملفات EPS التي تزيد عن 150 ميغابايت، فكر في تدفق الإدخال عبر `FileStream` مع مخزن مؤقت للحفاظ على استهلاك الذاكرة منخفضًا.

## الأسئلة المتكررة

**س: هل Aspose.Page متوافق مع جميع بيئات .NET؟**  
ج: نعم، يعمل Aspose.Page عبر .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6/7، موفرًا سلوك API ثابت على Windows و Linux و macOS.

**س: هل يمكنني استخدام Aspose.Page مجانًا؟**  
ج: يمكنك تقييم المكتبة بتنزيل نسخة تجريبية مجانية من [Aspose purchase page](https://purchase.aspose.com/buy). يلزم ترخيص تجاري للنشر في بيئات الإنتاج.

**س: هل تتوفر تراخيص مؤقتة لـ Aspose.Page؟**  
ج: يمكن الحصول على تراخيص مؤقتة من [temporary license page](https://purchase.aspose.com/temporary-license/) للمشاريع القصيرة الأجل أو فترات التقييم.

**س: أين يمكنني العثور على دعم المجتمع لـ Aspose.Page؟**  
ج: انضم إلى المناقشة في [Aspose.Page forum](https://forum.aspose.com/c/page/39) لطرح الأسئلة ومشاركة الحلول مع المطورين الآخرين.

**س: ما هو أحدث إصدار من Aspose.Page لـ .NET؟**  
ج: راجع [documentation](https://reference.aspose.com/page/net/) الرسمي للحصول على أحدث ملاحظات الإصدار وروابط التنزيل.

---

**آخر تحديث:** 2026-08-08  
**تم الاختبار مع:** Aspose.Page 24.11 for .NET  
**المؤلف:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## دروس ذات صلة

- [تغيير عناصر المصفوفة باستخدام Aspose.Page لـ .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [إضافة خصائص بسيطة باستخدام Aspose.Page لـ .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [إضافة مساحة اسم باستخدام Aspose.Page لـ .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}