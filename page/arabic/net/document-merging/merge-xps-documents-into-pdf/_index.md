---
date: 2026-01-20
description: أضف أرقام الصفحات إلى ملفات PDF بسهولة أثناء دمج مستندات XPS في ملفات
  PDF عالية الجودة باستخدام Aspose.Page لـ .NET. اتبع دليلنا خطوة بخطوة لتحويل XPS
  إلى PDF.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: إضافة أرقام الصفحات إلى PDF – دمج XPS إلى PDF باستخدام Aspose.Page
url: /ar/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة أرقام الصفحات إلى PDF – دمج XPS إلى PDF باستخدام Aspose.Page

## المقدمة

إذا كنت بحاجة إلى **إضافة أرقام الصفحات إلى PDF** أثناء دمج ملفات XPS، فإن Aspose.Page for .NET يجعل العملية سهلة. في هذا البرنامج التعليمي سنستعرض مثالًا كاملاً وجاهزًا للإنتاج يحول مستند XPS إلى PDF عالي الجودة، يتيح لك التحكم في ضغط الصور، ويضيف أرقام الصفحات تلقائيًا إلى PDF النهائي. في النهاية ستحصل على مقتطف يمكن إعادة استخدامه وإدراجه في أي مشروع C#.

## إجابات سريعة
- **هل يمكنني إضافة أرقام الصفحات عند دمج XPS إلى PDF؟** نعم – خاصية `PdfSaveOptions.PageNumbers` تقوم بذلك بالضبط.  
- **أي مكتبة تتولى التحويل؟** Aspose.Page for .NET.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يلزم وجود ترخيص صالح لـ Aspose.Page؛ يتوفر ترخيص مؤقت للاختبار.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6+.  
- **هل يمكن الحصول على صور عالية الجودة؟** بالتأكيد – اضبط `JpegQualityLevel` إلى 100 واختر `PdfImageCompression.Jpeg`.

## المتطلبات المسبقة

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات التالية:

- Aspose.Page for .NET: تأكد من تثبيت مكتبة Aspose.Page. يمكنك تنزيلها من [here](https://releases.aspose.com/page/net/).

- ملفات المستند: احرص على وجود مستند XPS (`input.xps`) في الدليل المحدد.

## استيراد المساحات الاسمية

في مشروع .NET الخاص بك، أدرج المساحات الاسمية الضرورية للعمل مع Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

تضمن هذه الخطوة إمكانية الوصول إلى الفئات والطرق المطلوبة لتحويل المستند.

## كيفية إضافة أرقام الصفحات إلى PDF عند دمج مستندات XPS

تسمح مجموعة `PdfSaveOptions.PageNumbers` بتحديد الصفحات (أو نطاقات الصفحات) التي يجب أن تظهر في PDF الناتج. من خلال تعبئتها بأرقام الصفحات المطلوبة، يضيف Aspose.Page الأرقام تلقائيًا.

### الخطوة 1: تهيئة التدفقات

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

### الخطوة 2: تحميل مستند XPS

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

هنا نقوم بتحميل مستند XPS إلى كائن `XpsDocument`، استعدادًا للمعالجة اللاحقة.

### الخطوة 3: تهيئة خيارات الحفظ (دمج XPS إلى PDF)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

قم بتخصيص كائن `PdfSaveOptions` وفقًا لتفضيلاتك، مع تحديد معلمات مثل ضغط الصور، ضغط النص، و**أرقام الصفحات** التي تريد ظهورها في PDF النهائي. ضبط `JpegQualityLevel` إلى 100 يضمن **صور PDF عالية الجودة**.

### الخطوة 4: إنشاء جهاز العرض

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice` هو الأداة المسؤولة عن تحويل مستند XPS إلى صيغة PDF.

### الخطوة 5: حفظ المستند (C# XPS إلى PDF)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

أخيرًا، احفظ المستند باستخدام جهاز العرض والخيارات المحددة. سيحتوي PDF الناتج على الصفحات المختارة مع أرقام الصفحات المضافة تلقائيًا.

## لماذا نستخدم Aspose.Page لهذا التحويل؟

- **الموثوقية** – يتعامل مع ميزات XPS المعقدة دون فقدان الدقة.  
- **الأداء** – المعالجة المستندة إلى التدفقات تتجنب تحميل الملفات بالكامل في الذاكرة.  
- **المرونة** – تحكم دقيق في جودة الصورة، الضغط، وترقيم الصفحات.  
- **متعدد المنصات** – يعمل على Windows، Linux، و macOS مع .NET Core.

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| **PDF الناتج فارغ** | تحقق من صحة مسار ملف XPS وأنه غير تالف. |
| **أرقام الصفحات لا تظهر** | تأكد من ضبط `PageNumbers` على مؤشرات الصفحات الصفرية الصحيحة (مثل `new int[] {1,2,6}`). |
| **صور منخفضة الجودة** | زد من `JpegQualityLevel` واختر `PdfImageCompression.Jpeg`. |
| **ملفات XPS الكبيرة تسبب ضغطًا على الذاكرة** | عالج XPS على أجزاء أصغر أو زد من حد الذاكرة للتطبيق. |

## الأسئلة المتكررة

### س1: هل يمكنني دمج ملفات XPS متعددة في PDF واحد؟

ج1: نعم. ما عليك سوى تعديل معامل `PageNumbers` في `PdfSaveOptions` لتضمين الصفحات المطلوبة من ملفات XPS المختلفة، أو تحميل كل XPS على التوالي واستدعاء `document.Save` على نفس `PdfDevice`.

### س2: هل يتوفر ترخيص مؤقت لـ Aspose.Page for .NET؟

ج2: نعم، يمكنك الحصول على ترخيص مؤقت [here](https://purchase.aspose.com/temporary-license/) لأغراض الاختبار.

### س3: هل هناك حدود لحجم الملف عند استخدام Aspose.Page لتحويل المستندات؟

ج3: لا تفرض Aspose.Page for .NET حدودًا صارمة لحجم الملف، لكن الأداء المثالي يتحقق مع ملفات ذات حجم معقول. بالنسبة لمستندات XPS الكبيرة جدًا، يُفضَّل معالجتها عبر التدفقات لتقليل استهلاك الذاكرة.

### س4: هل يمكنني تخصيص PDF الناتج أكثر، مثل إضافة علامات مائية أو تعليقات؟

ج4: نعم، توفر Aspose.Page for .NET ميزات واسعة لمعالجة PDF. بعد التحويل، يمكنك استخدام مكتبة Aspose.PDF لإضافة علامات مائية، تعليقات، أو تحسينات أخرى.

### س5: هل يدعم Aspose.Page for .NET التطوير متعدد المنصات؟

ج5: نعم، صُممت Aspose.Page for .NET للعمل بسلاسة عبر مختلف المنصات، بما في ذلك Windows، Linux، و macOS، عند استخدامها مع .NET Core أو .NET 5/6.

---

**آخر تحديث:** 2026-01-20  
**تم الاختبار مع:** Aspose.Page 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}