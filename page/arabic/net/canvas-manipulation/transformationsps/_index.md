---
date: 2026-07-19
description: تعلم كيفية إنشاء مستند PostScript باستخدام ASP.NET و Aspose.Page لـ .NET،
  وتطبيق عدة تحولات، وحفظ الملف بكفاءة.
keywords:
- create postscript document asp.net
- aspose.page transformations
- postscript graphics .net
lastmod: 2026-07-19
linktitle: تحولات PS
og_description: إنشاء مستند PostScript باستخدام ASP.NET و Aspose.Page. تعلم تطبيق
  الترجمة، والتحجيم، والدوران، والقص، ثم حفظ الملف.
og_image_alt: Guide to creating and transforming PostScript documents using Aspose.Page
  for .NET
og_title: إنشاء مستند PostScript ASP.NET – دليل Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create PostScript document ASP.NET using Aspose.Page for
    .NET, apply multiple transformations, and save the file efficiently.
  headline: Create PostScript Document ASP.NET with Aspose.Page
  type: TechArticle
- questions:
  - answer: Use the `Transform` method with a custom `Matrix` that combines translation,
      scaling, rotation, or shearing in the order you need.
    question: How can I apply multiple transformations to a single object?
  - answer: Yes—render the `PsDocument` to an image using `PsDocument.Save("output.png",
      SaveFormat.Png)` or open the `.ps` file in a PostScript viewer to inspect the
      result before calling `Save()` for the final file.
    question: Can I preview the transformations before saving the document?
  - answer: Absolutely. Save the graphics state before drawing the element, apply
      the desired transformation, draw, then restore the state so later elements remain
      unaffected.
    question: Is it possible to apply transformations to specific elements in a document?
  - answer: Complex matrices increase CPU work. Keep transformations as simple as
      possible and reuse saved states when drawing many similar objects. Aspose.Page
      processes a 300‑page document with mixed transformations in under 2 seconds
      on a typical 3.2 GHz CPU.
    question: Are there any performance considerations when dealing with complex transformations?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community help, or contact Aspose support directly for priority assistance.
    question: How can I get support or seek assistance for Aspose.Page-related queries?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- aspose.page
- .net graphics
- transformations
title: إنشاء مستند PostScript ASP.NET باستخدام Aspose.Page
url: /ar/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مستند PostScript في ASP.NET باستخدام Aspose.Page

## المقدمة

في هذا الدليل خطوة بخطوة ستقوم **بإنشاء مستند PostScript في ASP.NET** باستخدام مكتبة Aspose.Page، وتطبيق مجموعة متنوعة من التحولات الرسومية، وأخيرًا حفظ النتيجة في ملف `.ps`. في نهاية الدليل ستفهم أين تدفع كل تحويل على مكدس حالة الرسومات، وكيفية دمجها بفعالية، وكيفية حفظ أوامر الرسم بحيث يمكن لأي مفسر PostScript عرضها. هذه المعرفة أساسية لإنشاء رسومات قابلة للطباعة، تقارير مخصصة، أو أصول جاهزة للطباعة بشكل ديناميكي مباشرةً من تطبيقات .NET.

## إجابات سريعة

- **ما الذي يمكنني إنشاؤه؟** مستند PostScript كامل المميزات مع رسومات محوّلة.  
- **ما المكتبة المطلوبة؟** Aspose.Page for .NET (قابلة للتنزيل من الموقع الرسمي).  
- **كيف أحفظ الملف؟** استخدم `PsDocument.Save()` بعد تكوين حالات الرسومات.  
- **هل يمكنني تطبيق تحولات متعددة؟** نعم – دمجها باستخدام `Transform` أو استدعاءات متسلسلة.  
- **هل تحتاج إلى ترخيص؟** نسخة تجريبية مجانية تعمل للتطوير؛ الترخيص التجاري مطلوب للإنتاج.

## ما هي عملية “حفظ ملف PostScript”؟

حفظ ملف PostScript يعني تخزين أوامر الرسم التي أنشأتها في الذاكرة إلى ملف `.ps` على القرص. يمكن بعد ذلك لأي مفسر PostScript أو طابعة أو عارض أن يعرض الملف، مما يجعله تمثيلًا محمولًا ومستقلًا عن الجهاز للرسومات المتجهة. عندما تستدعي طريقة `Save`، تقوم Aspose.Page بتسلسل حالة الرسومات بالكامل، بما في ذلك المسارات والفرش ومصفوفات التحويل، إلى صيغة PostScript صالحة تتوافق مع مواصفات Adobe®.

## لماذا نستخدم Aspose.Page لـ .NET لإنشاء مستند PostScript؟

توفر لك Aspose.Page لـ .NET واجهة برمجة تطبيقات قوية النوعية، موجهة للكائنات، تُجرد لغة PostScript منخفضة المستوى. تدير تلقائيًا مكدس حالة الرسومات، وتدعم أكثر من 50 طريقة متعلقة بالتحويلات، ويمكنها التعامل مع مستندات تتجاوز 500 صفحة دون تحميل الملف بالكامل إلى الذاكرة. هذا يقلل من وقت التطوير بنسبة تصل إلى 70 % مقارنةً بكتابة شفرة PostScript يدوياً ويضمن التوافق مع جميع الطابعات الرئيسية.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

- **Aspose.Page for .NET** مكتبة مدمجة في مشروعك. احصل عليها من [download link](https://releases.aspose.com/page/net/).  
- مجلد قابل للكتابة حيث سيتم تخزين ملف `.ps` المُولد. استبدل مسار العنصر النائب في الشيفرة بالدليل الفعلي الخاص بك.  
- .NET 6.0 أو أحدث (المكتبة تدعم أيضًا .NET Core 3.1 و .NET Framework 4.6+).

## استيراد مساحات الأسماء

فئة `PsDocument` موجودة في مساحة الأسماء `Aspose.Page.Drawing`، بينما مساعدات التحويل موجودة في `Aspose.Page.Drawing.Graphics`. استوردها في أعلى ملفك:

```csharp
using Aspose.Page.Drawing;
using Aspose.Page.Drawing.Graphics;
using Aspose.Page.Drawing.Shapes;
```

`PsDocument` هي الفئة الأساسية في Aspose.Page التي تمثل مستند PostScript في الذاكرة. بعد استيراد مساحات الأسماء يمكنك البدء في بناء سطح الرسم.

الآن دعنا نستكشف كل خطوة من التحولات خطوة بخطوة.

## بدون تحولات

`PsDocument` هو نقطة الدخول لجميع عمليات الرسم. المقتطف التالي ينشئ مستندًا جديدًا، يرسم مستطيلًا برتقاليًا بسيطًا، ويحفظه دون أي تحويل.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

هذا المقتطف ينشئ **مستند PostScript** بمستطيل برتقالي واحد و**يحفظ ملف PostScript** دون تطبيق أي تحولات.

## إزاحة

حفظ حالة الرسومات يتيح لك العودة بعد تحريك الكائنات. طريقة `SaveState` تدفع مصفوفة التحويل الحالية إلى المكدس الداخلي.

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

طريقة `Translate` تحرك نظام الإحداثيات بالإزاحات المحددة، مما يؤثر على جميع أوامر الرسم اللاحقة.

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

الآن يظهر مستطيل أزرق على بعد 250 نقطة إلى يمين المستطيل البرتقالي لأن مصفوفة الإزاحة نشطة.

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

إعادة الحالة تعيد نظام الإحداثيات إلى موقعه الأصلي، لذا لا تتأثر الرسومات اللاحقة بالإزاحة.

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

## التحجيم

`Scale` يغيّر حجم الكائنات المرسومة بتطبيق مصفوفة تحجيم على حالة الرسومات الحالية.

> *يمكنك اتباع النمط نفسه—حفظ الحالة، تطبيق `Scale`، الرسم، ثم الاستعادة.*  
> **نصيحة احترافية:** استخدم التحجيم غير المتساوي (`Scale(sx, sy)`) لتمديد الكائنات في اتجاه واحد فقط، وهو مفيد لإنشاء تأثيرات المخططات الشريطية.

## الدوران

`Rotate` يطبق مصفوفة دوران على حالة الرسومات الحالية، مما يدور الرسومات اللاحقة بالزاوية المحددة.

> *دوران حول الأصل أو نقطة محورية مخصصة باستخدام `Rotate(angle)`.*
> **نصيحة احترافية:** دمج `Translate` قبل الدوران للدوران حول نقطة محددة بدلاً من الأصل.

## القص

`Shear` يميل نظام الإحداثيات بالعوامل المحددة، مائلًا الكائنات المرسومة أفقيًا و/أو عموديًا.

> *تحويلات القص (`Shear(shx, shy)`) تميل الأشكال، مفيدة لتأثيرات المائل أو خدع المنظور.*

## التحولات المعقدة

`Transform` يطبق مصفوفة تحويل مخصصة على حالة الرسومات، يجمع عمليات متعددة في واحدة.

> *للحالات المتقدمة، أنشئ `Matrix` مخصصًا ومرره إلى `Transform(matrix)`.*
> هذا هو المكان الذي **تطبق فيه تحولات متعددة** في خطوة واحدة، مما يقلل عدد عمليات حفظ الحالة واستعادتها.

## كيف تحفظ ملف PostScript مع التحولات؟

`Save` يكتب الـ `PsDocument` الحالي إلى ملف بصيغة PostScript. حمّل الـ `PsDocument` الخاص بك، طبّق تسلسل التحولات المطلوب، واستدعِ `Save` مع المسار الهدف—Aspose.Page يكتب ملف `.ps` متوافق مع المعايير في تمريرة واحدة. المكتبة تغلق تلقائيًا أي حالة رسومات مفتوحة، لذا لا تحتاج إلى شفرة تنظيف إضافية. هذا النهج يعمل مع أي مجموعة من الإزاحة، التحجيم، الدوران، أو القص.

## حالات الاستخدام الشائعة

- **إنشاء تقارير ديناميكية** – إنشاء مخططات تتكيف مع حجم البيانات في وقت التشغيل.  
- **فواتير جاهزة للطباعة** – تضمين شعارات الشركة وتدويرها لتتناسب مع اتجاه الطابعة.  
- **تصميم ملصقات مخصصة** – تطبيق القص لمحاكاة تأثيرات النص البارز.

## الأسئلة المتكررة

**س: كيف يمكنني تطبيق تحولات متعددة على كائن واحد؟**  
ج: استخدم طريقة `Transform` مع `Matrix` مخصص يجمع الإزاحة، التحجيم، الدوران، أو القص بالترتيب الذي تحتاجه.

**س: هل يمكنني معاينة التحولات قبل حفظ المستند؟**  
ج: نعم—قم بتصيير `PsDocument` إلى صورة باستخدام `PsDocument.Save("output.png", SaveFormat.Png)` أو افتح ملف `.ps` في عارض PostScript لتفحص النتيجة قبل استدعاء `Save()` للملف النهائي.

**س: هل يمكن تطبيق التحولات على عناصر محددة في المستند؟**  
ج: بالتأكيد. احفظ حالة الرسومات قبل رسم العنصر، طبّق التحول المطلوب، ارسم، ثم استعد الحالة بحيث لا تتأثر العناصر اللاحقة.

**س: هل هناك اعتبارات أداء عند التعامل مع تحولات معقدة؟**  
ج: المصفوفات المعقدة تزيد من عبء المعالج. حافظ على التحولات بسيطة قدر الإمكان وأعد استخدام الحالات المحفوظة عند رسم العديد من الكائنات المتشابهة. Aspose.Page يعالج مستندًا من 300 صفحة مع تحولات مختلطة في أقل من ثانيتين على معالج 3.2 GHz نموذجي.

**س: كيف يمكنني الحصول على الدعم أو طلب المساعدة بخصوص استفسارات Aspose.Page؟**  
ج: زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على مساعدة المجتمع، أو تواصل مع دعم Aspose مباشرةً للحصول على مساعدة ذات أولوية.

---
**آخر تحديث:** 2026-07-19  
**تم الاختبار مع:** Aspose.Page 24.11 for .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

## دروس ذات صلة

- [إنشاء مستند PostScript .net – إضافة مستطيل باستخدام Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [إضافة صورة إلى مستند PostScript (PS) باستخدام Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [إضافة صفحة إلى مستند PostScript (PS) باستخدام Aspose.Page](/page/net/page-manipulation/add-page-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}