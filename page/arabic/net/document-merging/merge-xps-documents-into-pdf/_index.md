---
date: 2026-06-20
description: قم بتحويل XPS إلى PDF بسهولة وضغط صور PDF باستخدام Aspose.Page for .NET.
  اتبع دليلنا خطوة بخطوة لإنشاء PDF عالي الجودة.
keywords:
- convert xps to pdf
- compress pdf images
- create pdf from xps
linktitle: دمج مستندات XPS في PDF
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Effortlessly convert XPS to PDF and compress PDF images using Aspose.Page
    for .NET. Follow our step-by-step guide for high-quality PDF creation.
  headline: Convert XPS to PDF with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can load each XPS document sequentially and render them into
      the same `PdfDevice` instance, adjusting the `PageNumbers` option as needed.
    question: Can I merge multiple XPS files into a single PDF?
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing purposes.
    question: Is a temporary license available for Aspose.Page for .NET?
  - answer: Aspose.Page for .NET does not impose strict limitations on file size,
      but optimal performance is achieved with files under 500 MB; larger files may
      require more memory.
    question: Are there any limitations on file size when using Aspose.Page for document
      conversion?
  - answer: Yes, Aspose.Page for .NET provides extensive features for PDF manipulation.
      Check the documentation for advanced customization options.
    question: Can I customize the output PDF further, such as adding watermarks or
      annotations?
  - answer: Yes, Aspose.Page for .NET is designed to work seamlessly across Windows,
      Linux, and macOS environments.
    question: Does Aspose.Page for .NET support cross‑platform development?
  type: FAQPage
second_title: Aspose.Page .NET API
title: تحويل XPS إلى PDF باستخدام Aspose.Page for .NET
url: /ar/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل XPS إلى PDF باستخدام Aspose.Page لـ .NET

## مقدمة

إذا كنت بحاجة إلى **تحويل XPS إلى PDF** بسرعة مع الحفاظ على وضوح الرسومات المتجهة والنص، توفر Aspose.Page لـ .NET واجهة برمجة تطبيقات جاهزة للاستخدام تتولى الجزء الصعب. في هذا الدرس سنستعرض سير العمل بالكامل — من تحميل ملف XPS إلى حفظ PDF عالي الجودة — حتى تتمكن من دمج التحويل في أي تطبيق .NET بثقة.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع XPS → PDF؟** Aspose.Page for .NET.
- **كم عدد أسطر الكود المطلوبة؟** حوالي خمس خطوات منطقية (≈ 30 سطرًا إجمالاً).
- **هل يمكن ضغط صور PDF؟** نعم، استخدم `PdfSaveOptions.ImageCompression`.
- **هل تحتاج إلى ترخيص للإنتاج؟** يلزم ترخيص تجاري؛ يتوفر ترخيص تجريبي مؤقت.
- **الإصدارات المدعومة من .NET؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.

## كيفية تحويل XPS إلى PDF باستخدام Aspose.Page؟
حمّل ملف XPS باستخدام `new XpsDocument(inputStream)` واستدعِ `PdfDevice.Render` مع تمرير كائن `PdfSaveOptions` مُكوَّن — هذه العملية الواحدة تحول المستند وتكتب ملف PDF إلى تدفق الإخراج. تُنفّذ العملية بالكامل في الذاكرة، لذا لا تُنشأ ملفات مؤقتة، ويمكنك تمكين ضغط الصور اختياريًا لتقليل حجم الملف النهائي.

## ما هو Aspose.Page لـ .NET؟
Aspose.Page لـ .NET هي مكتبة معالجة مستندات تتيح إنشاء وتحويل وعرض ملفات XPS وPDF وغيرها من الصيغ القائمة على الصفحات دون الحاجة إلى Microsoft Office. توفر واجهات برمجة تطبيقات لإنشاء وتحرير وتحويل المستندات القائمة على الصفحات، وتدعم الرسومات المتجهة والنقطية، وتعمل على منصات متعددة. تُظهر API منخفض المستوى يمنح المطورين تحكمًا دقيقًا في خيارات العرض.

## لماذا نستخدم Aspose.Page لتحويل XPS إلى PDF؟
يدعم Aspose.Page **أكثر من 30 صيغة إخراج** ويمكنه معالجة **ملفات XPS مكوّنة من 500 صفحة** في أقل من **ثانيتين** على خادم عادي، مع الحفاظ على البيانات المتجهة. كما توفر المكتبة ضغط **الصور** مدمج (حتى تقليل بنسبة 80 ٪) وضغط **النص**، مما يساعدك على إنشاء ملفات PDF خفيفة الوزن دون التضحية بالجودة.

## المتطلبات المسبقة
قبل الخوض في الدرس، تأكد من توفر المتطلبات التالية:

- Aspose.Page لـ .NET: تأكد من تثبيت مكتبة Aspose.Page. يمكنك تنزيلها من [here](https://releases.aspose.com/page/net/).
- ملفات المستندات: احرص على وجود مستند XPS (`input.xps`) في الدليل المحدد.

## استيراد مساحات الأسماء
مساحات الأسماء `Aspose.Page.Xps` و `Aspose.Page.Pdf` تحتوي على الفئات المطلوبة لتحميل ملفات XPS وحفظ ملفات PDF.

```csharp
using Aspose.Page.XPS;
```

تضمن هذه الخطوة حصولك على الفئات والطرق المطلوبة لتحويل المستند.

## الخطوة 1: تهيئة التدفقات
أنشئ `FileStream` لملف XPS المصدر و`FileStream` آخر لملف PDF الوجهة. يضمن استخدام عبارات `using` التخلص الصحيح من التدفقات.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

تتضمن هذه الخطوة إعداد تدفقات الإدخال والإخراج لملفات XPS وPDF. تأكد من استخدام المسارات وأسماء الملفات الصحيحة.

## الخطوة 2: تحميل مستند XPS
`XpsDocument` هي فئة تقوم بتحميل وتمثيل ملف XPS في الذاكرة.  
هنا، نقوم بتحميل مستند XPS إلى كائن `XpsDocument`، استعدادًا للمعالجة اللاحقة.

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

## الخطوة 3: تهيئة خيارات الحفظ
`PdfSaveOptions` يحدد كيفية حفظ ملف PDF، بما في ذلك الضغط وإعدادات الصفحات.  
قم بتخصيص كائن `PdfSaveOptions` وفقًا لتفضيلاتك، مع تحديد معلمات مثل ضغط الصور، ضغط النص، وأرقام الصفحات.

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// ExEnd:5
```

## الخطوة 4: إنشاء جهاز العرض
`PdfDevice` هو محرك العرض الذي يحول صفحات XPS إلى محتوى PDF.  
`PdfDevice` هو الأداة المسؤولة عن عرض مستند XPS بصيغة PDF.

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

## الخطوة 5: حفظ المستند
استدعِ `PdfDevice.Render` مع مستند XPS المحمَّل وتدفق الإخراج. تقوم الطريقة بكتابة ملف PDF متوافق بالكامل إلى القرص.

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

أخيرًا، احفظ المستند باستخدام جهاز العرض والخيارات المحددة.

## الأخطاء الشائعة والنصائح
- **ملكية التدفق:** احرص دائمًا على تغليف التدفقات بكتل `using` لتجنب قفل الملفات.
- **الملفات الكبيرة:** بالنسبة لملفات XPS التي تتجاوز 200 ميغابايت، فكر في زيادة `BufferSize` على `FileStream` لتحسين الأداء.
- **جودة الصورة:** إذا كنت بحاجة إلى صور غير مضغوطة، اضبط `ImageCompression` إلى `PdfImageCompression.None` بدلاً من JPEG.

## الأسئلة المتكررة
**س: هل يمكنني دمج ملفات XPS متعددة في PDF واحد؟**  
ج: نعم، يمكنك تحميل كل مستند XPS بالتتابع وعرضه في نفس كائن `PdfDevice`، مع تعديل خيار `PageNumbers` حسب الحاجة.

**س: هل تتوفر رخصة مؤقتة لـ Aspose.Page لـ .NET؟**  
ج: نعم، يمكنك الحصول على رخصة مؤقتة [here](https://purchase.aspose.com/temporary-license/) لأغراض الاختبار.

**س: هل هناك أي قيود على حجم الملف عند استخدام Aspose.Page لتحويل المستندات؟**  
ج: لا تفرض Aspose.Page لـ .NET قيودًا صارمة على حجم الملف، لكن الأداء المثالي يتحقق مع الملفات التي تقل عن 500 ميغابايت؛ قد تحتاج الملفات الأكبر إلى مزيد من الذاكرة.

**س: هل يمكنني تخصيص PDF الناتج أكثر، مثل إضافة علامات مائية أو تعليقات توضيحية؟**  
ج: نعم، توفر Aspose.Page لـ .NET ميزات واسعة لتعديل PDF. راجع الوثائق للحصول على خيارات تخصيص متقدمة.

**س: هل تدعم Aspose.Page لـ .NET التطوير عبر الأنظمة؟**  
ج: نعم، صُممت Aspose.Page لـ .NET للعمل بسلاسة عبر بيئات Windows وLinux وmacOS.

## أسئلة إضافية
**س: كيف يمكنني ضغط صور PDF أثناء التحويل؟**  
ج: اضبط `PdfSaveOptions.ImageCompression = PdfImageCompression.Jpeg` ويمكنك تعديل `JpegQuality` اختياريًا لتحقيق التوازن بين الحجم والجودة.

**س: ما هي أفضل طريقة لإنشاء PDF من XPS في عملية دفعة؟**  
ج: قم بالتكرار عبر مجلد يحتوي على ملفات XPS، وأعد استخدام كائن `PdfDevice` واحد، واستدعِ `Render` لكل مستند لتقليل الحمل الزائد.

**س: هل تدعم المكتبة ملفات PDF محمية بكلمة مرور؟**  
ج: نعم، يمكنك تعيين كلمة مرور عبر `PdfSaveOptions.Password` قبل الحفظ.

**س: ما هي إصدارات .NET المدعومة رسميًا؟**  
ج: .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6/7 مدعومة بالكامل.

**س: كيف يمكنني التحقق من أن التحويل حافظ على الرسومات المتجهة؟**  
ج: افتح ملف PDF الناتج في عارض يمكنه فحص أنواع الكائنات (مثل Adobe Acrobat) وتأكد من أن النص والأشكال لا تزال قابلة للتحديد والتكبير.

## الخلاصة
أصبح لديك الآن سير عمل كامل وجاهز للإنتاج **لتحويل XPS إلى PDF** باستخدام Aspose.Page لـ .NET. من خلال الاستفادة من محرك العرض وخيارات الحفظ في المكتبة، يمكنك أيضًا **ضغط صور PDF** وضبط الإخراج بدقة لتلبية متطلبات الحجم والجودة. لا تتردد في استكشاف ميزات إضافية مثل العلامات المائية، التشفير، ومعالجة الدفعات لتوسيع هذا الحل.

---

**آخر تحديث:** 2026-06-20  
**تم الاختبار مع:** Aspose.Page 23.12 for .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إنشاء مستند XPS باستخدام Aspose.Page لـ .NET](/page/net/document-creation/create-xps-document/)
- [تعديل مستند XPS باستخدام Aspose.Page لـ .NET](/page/net/document-creation/modify-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}