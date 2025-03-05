---
title: دمج مستندات XPS في PDF باستخدام Aspose.Page لـ .NET
linktitle: دمج مستندات XPS في PDF
second_title: Aspose.Page .NET API
description: يمكنك دمج مستندات XPS بسهولة في ملفات PDF عالية الجودة باستخدام Aspose.Page لـ .NET. اتبع دليلنا خطوة بخطوة للحصول على تجربة تحويل مستند سلسة.
type: docs
weight: 11
url: /ar/net/document-merging/merge-xps-documents-into-pdf/
---
## مقدمة

في عالم معالجة المستندات دائم التطور، يظهر Aspose.Page for .NET كأداة قوية لدمج مستندات XPS بسلاسة في تنسيق PDF. سيرشدك هذا البرنامج التعليمي خلال العملية، مع تفصيل كل خطوة لضمان التنفيذ السلس والفعال.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Page لـ .NET: تأكد من تثبيت مكتبة Aspose.Page. يمكنك تنزيله من[هنا](https://releases.aspose.com/page/net/).

- ملفات المستندات: احصل على مستند XPS (`input.xps`) جاهز في الدليل المحدد.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، قم بتضمين مساحات الأسماء اللازمة للعمل مع Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

تضمن هذه الخطوة أن لديك حق الوصول إلى الفئات والأساليب المطلوبة لتحويل المستند.

## الخطوة 1: تهيئة التدفقات

```csharp
// البداية:3
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// تهيئة دفق إخراج PDF
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// تهيئة دفق إدخال XPS
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// النهاية:3
```

تتضمن هذه الخطوة إعداد تدفقات الإدخال والإخراج لملفات XPS وPDF. تأكد من استخدام المسارات وأسماء الملفات الصحيحة.

## الخطوة 2: تحميل مستند XPS

```csharp
// البداية:4
// قم بتحميل مستند XPS من الدفق
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// أو قم بتحميل مستند XPS مباشرة من الملف. ليست هناك حاجة إلى xpsStream بعد ذلك.
//XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// النهاية:4
```

 هنا، نقوم بتحميل مستند XPS في ملف`XpsDocument` الكائن، وإعداده لمزيد من المعالجة.

## الخطوة 3: تهيئة خيارات الحفظ

```csharp
// البداية:5
// تهيئة كائن الخيارات بالمعلمات الضرورية.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// النهاية:5
```

 تخصيص`PdfSaveOptions` الكائن بناءً على تفضيلاتك، مع تحديد المعلمات مثل ضغط الصور وضغط النص وأرقام الصفحات.

## الخطوة 4: إنشاء جهاز العرض

```csharp
// البداية:6
// إنشاء جهاز تقديم لتنسيق PDF
PdfDevice device = new PdfDevice(pdfStream);
// النهاية:6
```

 ال`PdfDevice` هي الأداة المسؤولة عن تحويل مستند XPS إلى تنسيق PDF.

## الخطوة 5: احفظ المستند

```csharp
// البداية:7
document.Save(device, options);
// النهاية:7
```

وأخيرًا، احفظ المستند باستخدام جهاز العرض والخيارات المحددة.

## خاتمة

تهانينا! لقد نجحت في دمج مستندات XPS في PDF باستخدام Aspose.Page لـ .NET. تضمن هذه العملية السلسة الحفاظ على جودة المستند وتنسيقه.

## الأسئلة الشائعة

### س1: هل يمكنني دمج ملفات XPS متعددة في ملف PDF واحد؟

 ج1: نعم يمكنك ذلك. ببساطة قم بضبط`PageNumbers` المعلمة في`PdfSaveOptions` لتضمين الصفحات المطلوبة من ملفات XPS المختلفة.

### س2: هل يتوفر ترخيص مؤقت لـ Aspose.Page لـ .NET؟

 ج2: نعم، يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/) لأغراض تجريبية.

### س3: هل توجد أي قيود على حجم الملف عند استخدام Aspose.Page لتحويل المستندات؟

A3: لا يفرض Aspose.Page for .NET قيودًا صارمة على حجم الملف، ولكن يتم تحقيق الأداء الأمثل بأحجام ملفات معقولة.

### س4: هل يمكنني تخصيص ملف PDF الناتج بشكل أكبر، مثل إضافة علامات مائية أو تعليقات توضيحية؟

ج4: نعم، يوفر Aspose.Page for .NET ميزات شاملة لمعالجة ملفات PDF. تحقق من الوثائق للحصول على خيارات التخصيص المتقدمة.

### س5: هل يدعم Aspose.Page for .NET التطوير عبر الأنظمة الأساسية؟

ج5: نعم، تم تصميم Aspose.Page for .NET للعمل بسلاسة عبر الأنظمة الأساسية المختلفة.