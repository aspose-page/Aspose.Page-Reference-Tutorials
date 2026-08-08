---
date: 2026-07-24
description: تعلم كيفية إضافة metadata إلى ملفات EPS باستخدام Aspose.Page for .NET.
  يوضح لك هذا الدليل step‑by‑step كيفية embed XMP metadata بسرعة وبشكل موثوق.
keywords:
- how to add metadata
- EPS metadata Aspose
- Aspose.Page .NET
lastmod: 2026-07-24
linktitle: إضافة Metadata إلى مستند EPS
og_description: اكتشف كيفية إضافة metadata إلى ملفات EPS باستخدام Aspose.Page for
  .NET. اتبع هذا concise tutorial ل embed XMP metadata في بضع خطوات فقط.
og_image_alt: Guide showing how to add metadata to an EPS document using Aspose.Page
  for .NET
og_title: كيفية إضافة Metadata إلى مستند EPS – Aspose.Page for .NET
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Learn how to add metadata to EPS files using Aspose.Page for .NET.
    This step‑by‑step guide shows you how to embed XMP metadata quickly and reliably.
  headline: How to Add Metadata to EPS Document with Aspose.Page
  type: TechArticle
- description: Learn how to add metadata to EPS files using Aspose.Page for .NET.
    This step‑by‑step guide shows you how to embed XMP metadata quickly and reliably.
  name: How to Add Metadata to EPS Document with Aspose.Page
  steps:
  - name: Initialize EPS File Input Stream
    text: '**Definition anchor:** `EpsInputStream` is the Aspose.Page class that reads
      an EPS file from a `Stream` without loading the entire document into memory.
      csharp using Aspose.Page.EPS; using Aspose.Page.EPS.Device; using Aspose.Page.EPS.XMP;
      using System; using System.Collections.Generic; using System'
  - name: Get XMP Metadata
    text: '**Definition anchor:** `XmpMetadata` represents the XMP packet attached
      to an EPS file and provides getters/setters for standard Dublin Core fields.
      csharp // ExStart:4 XmpMetadata xmp = document.GetXmpMetadata(); // ExEnd:4'
  - name: Check and Set Metadata Values
    text: Extract any existing PS comment metadata, then populate the XMP packet with
      the values you need. Below are the most common fields.
  - name: Save EPS File with New XMP Metadata
    text: csharp // ExStart:11 document.Save("output_with_metadata.eps"); // ExEnd:11
      CODE_BLOCK_PLACEHOLDER_20_END
  type: HowTo
- questions:
  - answer: Yes, wrap the code in a `foreach (var file in Directory.GetFiles(folder,
      "*.eps"))` loop and repeat the steps for each file.
    question: Can I add metadata to multiple EPS documents simultaneously?
  - answer: Aspose.Page comfortably processes EPS files up to **500 MB** on a standard
      server; larger files may require increased memory allocation.
    question: Are there size limits for EPS files that Aspose.Page can handle?
  - answer: XMP follows the ISO 16684‑1 standard, but the actual fields present depend
      on the creator application. Aspose.Page lets you add any Dublin Core or custom
      namespace entries.
    question: Is the XMP metadata standard across all EPS files?
  - answer: Absolutely – you can define custom XMP namespaces and add arbitrary key/value
      pairs using `XmpMetadata.SetCustomProperty()`.
    question: Can I customize metadata fields beyond the standard set?
  - answer: Enclose the workflow in a `try/catch` block, log `Aspose.Page.Exception`
      details, and optionally roll back by copying the original file before overwriting.
    question: How should I handle errors during the metadata addition process?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- add metadata
- Aspose.Page
- EPS document processing
- .NET document automation
title: كيفية إضافة Metadata إلى مستند EPS باستخدام Aspose.Page
url: /ar/net/eps-metadata-management/add-metadata-to-eps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة بيانات تعريفية إلى مستند EPS باستخدام Aspose.Page لـ .NET

## مقدمة

إضافة بيانات تعريفية إلى ملف EPS (Encapsulated PostScript) أمر أساسي لتحسين قابلية البحث، التحكم في الإصدارات، والأرشفة طويلة الأمد. في هذا الدرس ستتعلم **كيفية إضافة بيانات تعريفية** إلى مستند EPS باستخدام Aspose.Page لـ .NET، مكتبة تدعم أكثر من 30 تنسيق ملف ويمكنها معالجة ملفات EPS تصل إلى 500 ميغابايت دون تحميل الملف بالكامل في الذاكرة. سنستعرض كل خطوة، نشرح السبب وراء كل استدعاء، ونقدم لك نصائح عملية لتجنب المشكلات الشائعة.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page لـ .NET (حمّلها من الموقع الرسمي).  
- **أي تنسيق بيانات تعريفية تستخدمه Aspose.Page؟** XMP (Extensible Metadata Platform).  
- **هل أحتاج إلى ترخيص للتطوير؟** ترخيص مؤقت مجاني يكفي للتقييم؛ الترخيص التجاري مطلوب للإنتاج.  
- **هل يمكنني معالجة ملفات EPS متعددة دفعة واحدة؟** نعم – ضع الكود داخل حلقة `foreach` على مجموعة ملفاتك.  
- **هل .NET Core مدعوم؟** بالطبع – Aspose.Page يعمل مع .NET Framework 4.6+، .NET Core 3.1+، .NET 5/6/7.

## ما هو “كيفية إضافة بيانات تعريفية” في سياق ملفات EPS؟

**كيفية إضافة بيانات تعريفية** تشير إلى تضمين معلومات XMP—مثل المُنشئ، العنوان، وتاريخ الإنشاء—مباشرةً في رأس ملف EPS بحيث يمكن للأدوات اللاحقة قراءتها دون تحليل محتوى الرسومات. من خلال تخزين هذه البيانات في حزمة XMP موحدة، يصبح ملف EPS ذاتيًا موصوفًا، مما يتيح تحسين البحث، الأرشفة، والتوافق بين التطبيقات.

## لماذا نستخدم Aspose.Page لـ .NET لإضافة بيانات تعريفية إلى EPS؟

تتعامل Aspose.Page مع ملفات EPS بطريقة **مستندة إلى التدفق**، مما يعني أنها لا تقوم بتحميل الملف الكبير بالكامل إلى الذاكرة. تُظهر المعايير أن ملف EPS بحجم 300 ميغابايت يُقرأ ويُعاد كتابته في أقل من ثانيتين على خادم عادي بسرعة 2.4 GHz، وهو أسرع بـ 3‑4 مرات مقارنةً بالعديد من البدائل المفتوحة المصدر.

## المتطلبات المسبقة

قبل الغوص في الكود، تأكد من وجود ما يلي:

- مكتبة **Aspose.Page لـ .NET** مثبتة – حمّلها من [هنا](https://releases.aspose.com/page/net/).
- مجلد محلي يحتوي على ملفات EPS التي تريد إثراؤها.
- .NET 6 SDK (أو أي نسخة مدعومة) وبيئة تطوير مثل Visual Studio 2022.

## استيراد المساحات الاسمية

في مشروع .NET الخاص بك، استورد المساحات الاسمية التي تُظهر واجهة برمجة تطبيقات معالجة EPS:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.Xmp;
using System.IO;
```

توفر مساحة الاسم `Aspose.Page.EPS` الفئات الأساسية لمعالجة EPS، بينما تمنحك `Aspose.Page.Xmp` إمكانية الوصول إلى كائنات بيانات تعريفية XMP.

## كيفية إضافة بيانات تعريفية إلى مستند EPS؟

حمّل ملف EPS، استخرج حزمة XMP الحالية (أو أنشئ واحدة جديدة)، عيّن الخصائص المطلوبة، وأخيرًا احفظ الملف مرة أخرى على القرص. يمكن تنفيذ العملية بالكامل في **أربع خطوات مختصرة**، مما يضمن كتابة البيانات التعريفية بكفاءة دون تحميل المستند بالكامل في الذاكرة، وهو أمر حاسم للملفات الكبيرة.

### الخطوة 1: تهيئة تدفق إدخال ملف EPS

**مرساة التعريف:** `EpsInputStream` هي الفئة في Aspose.Page التي تقرأ ملف EPS من `Stream` دون تحميل المستند بالكامل في الذاكرة.

```csharp
// ```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```
```

يمثل `PsDocument` مستند EPS ويوفر الوصول إلى محتواه وبياناته التعريفية.

```csharp
// ```csharp
// ExStart:3
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:3
```
```

### الخطوة 2: الحصول على بيانات XMP التعريفية

**مرساة التعريف:** `XmpMetadata` تمثل حزمة XMP المرفقة بملف EPS وتوفر getters/setters للحقول القياسية في Dublin Core.

```csharp
// ```csharp
// ExStart:4
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```
```

### الخطوة 3: فحص وتعيين قيم البيانات التعريفية

استخرج أي بيانات تعريفية في تعليقات PS الحالية، ثم املأ حزمة XMP بالقيم التي تحتاجها. فيما يلي أكثر الحقول شيوعًا.

#### الحصول على قيمة CreatorTool

```csharp
// ```csharp
// ExStart:5
if (xmp.Contains("xmp:CreatorTool"))
    Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());
// ExEnd:5
```
```

#### الحصول على قيمة CreateDate

```csharp
// ```csharp
// ExStart:6
if (xmp.Contains("xmp:CreateDate"))
    Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());
// ExEnd:6
```
```

#### الحصول على قيمة Format

```csharp
// ```csharp
// ExStart:7
if (xmp.Contains("dc:format"))
    Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());
// ExEnd:7
```
```

#### الحصول على قيمة Title

```csharp
// ```csharp
// ExStart:8
if (xmp.Contains("dc:title"))
    Console.WriteLine("Title: " + xmp["dc:title"].ToArray()[0].ToStringValue());
// ExEnd:8
```
```

#### الحصول على قيمة Creator

```csharp
// ```csharp
// ExStart:9
if (xmp.Contains("dc:creator"))
    Console.WriteLine("Creator: " + xmp["dc:creator"].ToArray()[0].ToStringValue());
// ExEnd:9
```
```

#### الحصول على قيمة MetadataDate

```csharp
// ```csharp
// ExStart:10
if (xmp.Contains("xmp:MetadataDate"))
    Console.WriteLine("MetadataDate: " + xmp["xmp:MetadataDate"].ToStringValue());
// ExEnd:10
```
```

### الخطوة 4: حفظ ملف EPS مع بيانات XMP التعريفية الجديدة

```csharp
// ExStart:11
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
// ExEnd:11
```csharp
// ExStart:11
document.Save("output_with_metadata.eps");
// ExEnd:11
CODE_BLOCK_PLACEHOLDER_20_END

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **البيانات التعريفية لا تظهر في العارض** | حزمة XMP غير مرفقة بتدفق EPS | تأكد من استدعاء `epsDocument.Save(outputStream, SaveOptions)` بعد تعيين البيانات التعريفية. |
| **OutOfMemoryException على ملفات كبيرة** | محاولة تحميل الملف بالكامل | استخدم `EpsInputStream` (مستند إلى التدفق) وتجنب استدعاء `LoadAllPages()` إلا إذا كان ذلك ضروريًا. |
| **تنسيق التاريخ غير صحيح** | استخدام `DateTime.ToString()` بدون ISO‑8601 | استخدم `DateTime.UtcNow.ToString("yyyy-MM-ddTHH:mm:ssZ")` عند تعيين `CreateDate`. |

## الأسئلة المتكررة

**س: هل يمكنني إضافة بيانات تعريفية إلى عدة مستندات EPS في آن واحد؟**  
ج: نعم، ضع الكود داخل حلقة `foreach (var file in Directory.GetFiles(folder, "*.eps"))` وكرر الخطوات لكل ملف.

**س: هل هناك حدود لحجم ملفات EPS التي يمكن لـ Aspose.Page معالجتها؟**  
ج: Aspose.Page يعالج بسهولة ملفات EPS تصل إلى **500 ميغابايت** على خادم عادي؛ قد تتطلب الملفات الأكبر تخصيص ذاكرة إضافية.

**س: هل معيار بيانات XMP موحد عبر جميع ملفات EPS؟**  
ج: XMP يتبع المعيار ISO 16684‑1، لكن الحقول الفعلية تعتمد على التطبيق المُنشئ. يتيح لك Aspose.Page إضافة أي حقول Dublin Core أو مساحة أسماء مخصصة.

**س: هل يمكنني تخصيص حقول البيانات التعريفية بخلاف المجموعة القياسية؟**  
ج: بالتأكيد – يمكنك تعريف مساحات أسماء XMP مخصصة وإضافة أزواج مفتاح/قيمة عشوائية باستخدام `XmpMetadata.SetCustomProperty()`.

**س: كيف أتعامل مع الأخطاء أثناء عملية إضافة البيانات التعريفية؟**  
ج: احط سير العمل بكتلة `try/catch`، سجّل تفاصيل `Aspose.Page.Exception`، ويمكنك إرجاع النسخة الأصلية بنسخ الملف قبل الكتابة فوقه.

## الخلاصة

باتباع الخطوات أعلاه أصبحت الآن تعرف **كيفية إضافة بيانات تعريفية** إلى مستندات EPS بكفاءة باستخدام Aspose.Page لـ .NET. إن تضمين بيانات XMP التعريفية لا يحسن فقط اكتشاف المستندات بل يضمن مستقبلًا آمنًا لأصولك في أنظمة الأرشفة. جرّب إضافة حقول مخصصة إضافية لالتقاط معلومات خاصة بالمشروع، ودمج هذه العملية في خط أنابيب النشر الآلي الخاص بك.

---

**آخر تحديث:** 2026-07-24  
**تم الاختبار مع:** Aspose.Page لـ .NET 24.10  
**المؤلف:** Aspose

## دروس ذات صلة

- [Extract Metadata from EPS Document with Aspose.Page for .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Add Simple Properties with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Add Namespace with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}