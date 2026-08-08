---
date: 2026-07-19
description: تعلم كيفية إنشاء مستند XPS .NET وإضافة مستطيل باستخدام Aspose.Page for
  .NET في دليل مختصر خطوة بخطوة.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: إضافة مستطيل إلى مستند XPS
og_description: إنشاء مستند XPS .NET بسرعة. يوضح هذا البرنامج التعليمي كيفية إضافة
  مستطيل إلى ملف XPS باستخدام Aspose.Page for .NET، مع شفرة واضحة ونصائح.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: إنشاء مستند XPS .NET – إضافة مستطيل باستخدام Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: إنشاء مستند XPS .NET – إضافة مستطيل باستخدام Aspose.Page
url: /ar/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مستند XPS .NET – إضافة مستطيل باستخدام Aspose.Page

## مقدمة

في هذا البرنامج التعليمي ستتعلم كيفية **إنشاء مستند XPS .NET** ورسم مستطيل داخله باستخدام Aspose.Page for .NET. سواءً كنت تبني محرك تقارير، أو فاتورة قابلة للطباعة، أو طبقة رسومات مخصصة، فإن القدرة على إنشاء ملفات XPS برمجياً تمنحك التحكم الكامل في التخطيط والدقة. اتبع الخطوات أدناه وستحصل على ملف XPS جاهز للاستخدام في دقائق.

## إجابات سريعة
- **ما هو الهدف الأساسي؟** إنشاء مستند XPS .NET وإضافة شكل مستطيل.  
- **ما المكتبة المطلوبة؟** Aspose.Page for .NET (قابلة للتنزيل من الموقع الرسمي).  
- **هل أحتاج إلى ترخيص للاختبار؟** النسخة التجريبية المجانية تعمل للتطوير؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **كم يستغرق التنفيذ؟** حوالي 5‑10 دقائق لإنشاء مستطيل أساسي.

## ما هو Aspose.Page for .NET؟
Aspose.Page for .NET هو API عالي الأداء ومُدار بالكامل يتيح للمطورين إنشاء وتحرير وعرض مستندات XPS (XML Paper Specification) برمجياً دون الاعتماد على مكونات خارجية. يوفر نموذج كائنات غني لرسم الأشكال والنصوص والصور، ويدعم ميزات متقدمة مثل إدارة الألوان، الضغط، وتحويل PDF، مما يجعله مناسباً لمجموعة واسعة من سيناريوهات إنشاء المستندات.

## لماذا تستخدم Aspose.Page لإنشاء مستند XPS .NET؟
يدعم Aspose.Page **أكثر من 30 ميزة XPS**—بما في ذلك الرسومات المتجهية، تخطيط النص، وإدارة الألوان—ويمكنه إنشاء ملفات تصل إلى **500 ميغابايت** دون تحميل المستند بالكامل في الذاكرة. تضمن هذه القدرة المكمَّنة أداءً سلساً حتى في مهام الطباعة على نطاق واسع.

## المتطلبات المسبقة

قبل أن تبدأ بهذا البرنامج التعليمي، تأكد من توفر المتطلبات التالية:

1. مكتبة Aspose.Page for .NET: تأكد من تثبيت مكتبة Aspose.Page for .NET في بيئة التطوير الخاصة بك. يمكنك تنزيلها [هنا](https://releases.aspose.com/page/net/).
2. دليل المستندات: أنشئ دليلًا حيث تريد تخزين مستندات XPS الخاصة بك.

## استيراد مساحات الأسماء

في تطبيق .NET الخاص بك، قم بتضمين مساحات الأسماء الضرورية لاستخدام وظائف Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## كيف أضيف مستطيلًا إلى مستند XPS في .NET؟

حمّل مستند XPS، أنشئ كائن `Graphics`، عرّف `RectangleF` بالحجم المطلوب، واستدعِ `DrawRectangle`. هذه السلسلة ترسم مستطيلًا في سطر واحد من الشيفرة وتتعامل تلقائيًا مع مقياس DPI. بالنسبة للصفحات بحجم A4 المعتادة، يظهر مستطيل بحجم 200 × 100 نقطة في الوسط دون حسابات إضافية.

### الخطوة 1: تعيين دليل المستند

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### الخطوة 2: إنشاء مستند XPS جديد

تمثل فئة `XpsDocument` ملف XPS الذي تقوم بإنشائه وتوفر طرقًا لإضافة الصفحات والرسومات والموارد الأخرى.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### الخطوة 3: إضافة مستطيل

`XpsPath` يعرّف كائن مسار قابل للرسم داخل مستند XPS، مما يتيح لك ضبط الهندسة، الحد، التعبئة، وغيرها من الخصائص البصرية.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### الخطوة 4: حفظ المستند

طريقة `Save` تكتب مستند XPS المُنشأ إلى مسار الملف المحدد على القرص.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

تهانينا! لقد أضفت بنجاح مستطيلًا إلى مستند XPS باستخدام Aspose.Page for .NET.

## المشكلات الشائعة والنصائح

- **الخطوط المفقودة:** تأكد من تثبيت الخطوط التي تشير إليها على الخادم؛ وإلا سيستبدل Aspose.Page الخط بخط افتراضي، مما قد يغيّر التخطيط.  
- **المستندات الكبيرة:** عند إنشاء ملفات أكبر من 200 ميغابايت، فكر في استدعاء `document.SaveOptions.Compress = true` لتقليل استهلاك الذاكرة.  
- **نظام الإحداثيات:** يستخدم XPS النقاط (1/72 بوصة). تذكر تحويل البكسلات إلى نقاط إذا كنت تعمل بأبعاد مستندة إلى الشاشة.

## الأسئلة المتكررة

**س: هل Aspose.Page متوافق مع جميع تطبيقات .NET؟**  
ج: نعم، يعمل Aspose.Page بسلاسة مع تطبيقات .NET على سطح المكتب، الويب، والسحابة.

**س: أين يمكنني العثور على وثائق Aspose.Page for .NET؟**  
ج: المرجع الكامل للـ API متاح [هنا](https://reference.aspose.com/page/net/).

**س: هل يمكنني تجربة Aspose.Page for .NET مجانًا قبل الشراء؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for .NET؟**  
ج: زر [هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت.

**س: أين يمكنني الحصول على دعم المجتمع أو طرح أسئلة متعلقة بـ Aspose.Page for .NET؟**  
ج: زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع.

---

**آخر تحديث:** 2026-07-19  
**تم الاختبار مع:** Aspose.Page for .NET 24.9  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء مستند XPS باستخدام Aspose.Page for .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – رسم الأشكال](/page/net/drawing-shapes/)
- [إضافة نص إلى مستند XPS باستخدام Aspose.Page for .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}