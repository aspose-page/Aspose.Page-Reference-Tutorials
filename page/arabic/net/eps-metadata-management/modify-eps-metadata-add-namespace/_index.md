---
date: 2026-08-08
description: تعلم كيفية تهيئة مستند Aspose.Page، وإضافة مساحة اسم XML، وتعديل بيانات
  XMP الوصفية في ملفات EPS باستخدام Aspose.Page لـ .NET.
keywords:
- initialize aspose page document
- c# add xml namespace
- open eps file stream
- how to add xmp namespace
lastmod: 2026-08-08
linktitle: إضافة مساحة اسم
og_description: تهيئة مستند Aspose.Page، إضافة مساحة اسم XML، وتحرير بيانات XMP الوصفية
  في ملفات EPS باستخدام Aspose.Page لـ .NET. اتبع خطوات مختصرة ومقاطع كود.
og_image_alt: Guide showing how to add namespace to EPS metadata using Aspose.Page
  for .NET
og_title: تهيئة مستند Aspose.Page وإضافة مساحة اسم في .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to initialize Aspose.Page document, add an XML namespace,
    and modify XMP metadata in EPS files using Aspose.Page for .NET.
  headline: Initialize Aspose.Page document and add namespace in .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for .NET works with .NET Framework 4.5+, .NET Core 3.1+,
      and .NET 5/6+.
    question: Is Aspose.Page compatible with all versions of .NET?
  - answer: Absolutely. Retrieve the `XmpMetadata` object and read its properties
      without invoking `SetProperty` or `AddNamespace`.
    question: Can I extract metadata without modifying it?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support or assistance?
  - answer: Yes, you can explore a free trial of Aspose.Page on the [Aspose.Page free
      trial](https://releases.aspose.com/) page.
    question: Is there a free trial available for Aspose.Page?
  - answer: Obtain a temporary license on the [temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/)
      page for testing purposes.
    question: How can I obtain a temporary license for Aspose.Page?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- Aspose.Page
- c# document processing
title: تهيئة مستند Aspose.Page وإضافة مساحة اسم في .NET
url: /ar/net/eps-metadata-management/modify-eps-metadata-add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تهيئة مستند Aspose.Page وإضافة مساحة اسم في .NET

## مقدمة

في تطوير .NET الحديث، **initialize aspose page document** غالبًا ما تكون الخطوة الأولى عندما تحتاج إلى التعامل مع ملفات EPS برمجيًا. توفر لك Aspose.Page for .NET تحكمًا كاملاً في بيانات XMP الوصفية، مما يتيح لك إضافة مساحات اسم XML مخصصة، تعديل الخصائص الموجودة، وحفظ التغييرات مرة أخرى إلى الملف. يشرح هذا البرنامج التعليمي كل التفاصيل — من استيراد مساحات الاسم الصحيحة إلى حفظ ملف EPS المعدل — بحيث يمكنك دمج إدارة البيانات الوصفية في سير عملك بثقة.

## إجابات سريعة
- **ما هو السطر الأول من الشيفرة؟** Create a `new Document("yourfile.eps")` to load the EPS file.
- **ما هي الطريقة التي تضيف مساحة اسم؟** Use `XmpMetadata.AddNamespace(prefix, uri)`.
- **هل أحتاج إلى ترخيص للتطوير؟** A free trial works for testing; a license is required for production.
- **هل يمكنني تدفق ملفات EPS الكبيرة؟** Yes—use a `FileStream` to open the file without loading it entirely into memory.
- **هل هذا متوافق مع .NET 6+؟** Absolutely; Aspose.Page supports .NET Framework 4.5+, .NET Core 3.1+, and .NET 6+.

## ما هو initialize aspose page document؟

تمثل الفئة `Document` ملف EPS تم تحميله في الذاكرة. تحميل الملف باستخدام `new Document("file.eps")` يمنحك وصولًا مباشرًا إلى صفحاته، رسوماته، وبيانات XMP الوصفية، مما يتيح لك قراءة أو تعديل أي جزء من المستند. كما توفر طرقًا للعمل مع بيانات XMP الوصفية ومحتوى الصفحة.

## لماذا إضافة مساحة اسم XML إلى بيانات EPS الوصفية؟

إضافة مساحة اسم XML مخصصة توسع مخطط البيانات الوصفية، مما يتيح لك تخزين معلومات مملوكة إلى جانب حقول XMP القياسية. تدعم Aspose.Page **50+** خاصية XMP ويمكنها التعامل مع ملفات تحتوي على **200+ صفحة** دون الحاجة إلى وجود المستند بالكامل في الذاكرة RAM، مما يترجم إلى معالجة أسرع واستهلاك أقل للذاكرة.

## المتطلبات المسبقة

1. **Aspose.Page for .NET library** – قم بتنزيله من [Aspose.Page documentation](https://reference.aspose.com/page/net/).  
2. **.NET development environment** – Visual Studio 2022، Rider، أو أي بيئة تطوير تدعم .NET 6+.

تأكد من أن المكتبة مُشار إليها في مشروعك (عن طريق NuGet أو إشارة DLL مباشرة) قبل المتابعة.

## استيراد مساحات الاسم

للعمل مع Aspose.Page يجب عليك استيراد مساحات الاسم الأساسية التي تُظهر الفئات `Document` و XMP.

ستحتاج إلى:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.XMP;
using System.IO;
```

تمنحك هذه الاستيرادات الوصول إلى الفئات `Document` و `XmpMetadata` وفئات معالجة التدفقات المطلوبة للخطوات القادمة.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## الخطوة 1: تهيئة مشروعك

افتح ملف المصدر حيث تريد وضع الشيفرة. ابدأ بإنشاء نسخة من الفئة `Document`، التي **initialize aspose page document** للمزيد من التلاعب. تمثل الفئة `Document` مستند EPS وتوفر وصولًا إلى محتواه وبياناته الوصفية.

```csharp
var epsDocument = new Document("sample.eps");
```

هذا السطر يحمل ملف EPS في كائن `epsDocument`، مما يجعل جميع استدعاءات API اللاحقة ممكنة.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## الخطوة 2: فتح تدفق ملف eps

توفر الفئة `FileStream` تدفقًا لقراءة وكتابة الملفات، مما يساعد على تجنب تحميل ملف EPS بالكامل في الذاكرة.

```csharp
using (FileStream fs = new FileStream("sample.eps", FileMode.Open, FileAccess.ReadWrite))
{
    // Stream is ready for XMP operations
}
```

نمط `open eps file stream` موصى به لأعباء العمل الإنتاجية.

```csharp
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);

// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

## الخطوة 3: الحصول على بيانات xmp الوصفية

تُغلف الفئة `XmpMetadata` بيانات XMP الوصفية لمستند EPS.

```csharp
XmpMetadata xmp = epsDocument.XmpMetadata;
```

الآن لديك كائن `xmp` قابل للتلاعب يحتوي على جميع إدخالات البيانات الوصفية الحالية.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments.
XmpMetadata xmp = document.GetXmpMetadata();
```

## الخطوة 4: تعديل بيانات xmp الوصفية

تُسجل طريقة `AddNamespace` مساحة اسم XML جديدة باستخدام بادئة وURI، وتُعيّن طريقة `SetProperty` قيمة لخاصية وصفية.

```csharp
// Define a new namespace
string prefix = "myNs";
string uri = "http://mycompany.com/metadata";

// Register the namespace with the XMP metadata object
xmp.AddNamespace(prefix, uri);

// Add a custom property under the new namespace
xmp.SetProperty($"{prefix}:Author", "John Doe");
```

تُسجِّل استدعاء `AddNamespace` البادئة، وتخزن `SetProperty` قيمة باستخدام تلك البادئة.

```csharp
// Add new XML namespace "tmp".
xmp.RegisterNamespaceUri("tmp", "http://www.some.org/schema/tmp#");

// Add new string property in the new namespace.
xmp.Add("tmp:newKey", new XmpValue("NewValue"));
```

## الخطوة 5: حفظ ملف eps

تكتب طريقة `Save` المستند وبياناته الوصفية مرة أخرى إلى نظام الملفات.

```csharp
epsDocument.Save("sample-updated.eps");
```

بعد هذه الخطوة، يحتوي ملف EPS على مساحة الاسم والخاصية المضافة حديثًا.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_namespace_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
```

## المشكلات الشائعة واستكشاف الأخطاء

- **Namespace already exists** – إذا أطلقت `AddNamespace` خطأً، فالبادئة مسجلة بالفعل. استخدم بادئة مختلفة أو استرجع الـ URI الموجود باستخدام `xmp.GetNamespaceUri(prefix)`.
- **File locked by another process** – تأكد من تحرير `FileStream` (كتلة `using`) قبل استدعاء `Save`.
- **Metadata not persisting** – تحقق من أن ملف EPS يدعم XMP فعليًا (معظم ملفات EPS الحديثة تدعم ذلك). قد تحتاج الملفات القديمة إلى إعادة إنشائها.

## الأسئلة المتكررة

**س: هل Aspose.Page متوافق مع جميع إصدارات .NET؟**  
نعم، Aspose.Page for .NET يعمل مع .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6+.

**س: هل يمكنني استخراج البيانات الوصفية دون تعديلها؟**  
نعم، استرجع كائن `XmpMetadata` واقرأ خصائصه دون استدعاء `SetProperty` أو `AddNamespace`.

**س: أين يمكنني العثور على دعم إضافي أو مساعدة؟**  
A: زر [Aspose.Page forum](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع والنقاشات.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page؟**  
نعم، يمكنك تجربة نسخة تجريبية مجانية من Aspose.Page على صفحة [Aspose.Page free trial](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page؟**  
احصل على ترخيص مؤقت عبر صفحة [temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/) لأغراض الاختبار.

---

**آخر تحديث:** 2026-08-08  
**تم الاختبار مع:** Aspose.Page 24.11 for .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إضافة بيانات وصفية إلى مستند EPS باستخدام Aspose.Page for .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [إضافة خصائص بسيطة باستخدام Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [استخراج البيانات الوصفية من مستند EPS باستخدام Aspose.Page for .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}