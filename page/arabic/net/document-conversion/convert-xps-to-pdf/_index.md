---
title: قم بتحويل XPS إلى PDF باستخدام Aspose.Page لـ .NET
linktitle: تحويل XPS إلى PDF
second_title: Aspose.Page .NET API
description: قم بتحويل XPS إلى PDF بسهولة في .NET باستخدام Aspose.Page. قم بتنزيل المكتبة واستكشف الوثائق واحصل على نسخة تجريبية مجانية.
weight: 11
url: /ar/net/document-conversion/convert-xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بتحويل XPS إلى PDF باستخدام Aspose.Page لـ .NET

## مقدمة

في هذا البرنامج التعليمي، سوف نتعمق في عملية تحويل مستندات XPS (مواصفات ورق XML) إلى PDF (تنسيق المستندات المحمولة) باستخدام مكتبة Aspose.Page القوية لـ .NET. يوفر Aspose.Page for .NET مجموعة قوية من الميزات للعمل مع ملفات XPS، مما يتيح للمطورين تحويلها بسلاسة إلى تنسيق PDF مع خيارات التخصيص المتنوعة.

## المتطلبات الأساسية

قبل أن نبدأ رحلة التحويل هذه، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Page for .NET Library: تأكد من تثبيت Aspose.Page لمكتبة .NET في بيئة التطوير الخاصة بك. يمكنك تنزيله من[Aspose.Page الوثائق](https://reference.aspose.com/page/net/).

- بيئة التطوير: قم بإعداد بيئة تطوير .NET باستخدام Visual Studio أو أي بيئة تطوير متكاملة أخرى متوافقة.

- مستند XPS: قم بإعداد مستند XPS الذي تريد تحويله إلى PDF. يمكن أن يكون هذا هو نموذج ملف XPS الخاص بك والمخزن في دليل معين.

## استيراد مساحات الأسماء

قبل التعمق في التعليمات البرمجية، فلنستورد مساحات الأسماء الضرورية لتسهيل الوصول إلى وظائف Aspose.Page لـ .NET في التعليمات البرمجية الخاصة بنا:

```csharp
using Aspose.Page.XPS;
```

## الخطوة 1: تهيئة دليل المستندات

```csharp
string dataDir = "Your Document Directory";
```

استبدل "دليل المستندات الخاص بك" بالمسار إلى الدليل الذي يحتوي على مستند XPS الخاص بك.

## الخطوة 2: تهيئة تدفقات PDF وXPS

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

افتح التدفقات لكل من ملف PDF الناتج وملف XPS المدخل. تأكد من تعيين مسارات الملفات المناسبة.

## الخطوة 3: تحميل مستند XPS

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

قم بتحميل مستند XPS باستخدام Aspose.Page لمكتبة .NET.

## الخطوة 4: تهيئة خيارات حفظ PDF

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

قم بإعداد خيارات حفظ PDF، بما في ذلك المعلمات مثل مستوى جودة JPEG، وضغط الصور، وضغط النص، وأرقام الصفحات المحددة المراد تضمينها.

## الخطوة 5: إنشاء جهاز عرض PDF

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

قم بإنشاء جهاز عرض لتنسيق PDF باستخدام Aspose.Page لمكتبة .NET.

## الخطوة 6: حفظ المستند إلى PDF

```csharp
document.Save(device, options);
```

احفظ مستند XPS في ملف PDF باستخدام جهاز العرض والخيارات المحددة.

## خاتمة

تهانينا! لقد نجحت في تحويل مستند XPS إلى PDF باستخدام Aspose.Page لـ .NET. توفر هذه المكتبة متعددة الاستخدامات للمطورين مجموعة أدوات قوية للتعامل مع تنسيقات المستندات المختلفة دون عناء.

## الأسئلة الشائعة

### س١: هل يمكنني تحويل عدة ملفات XPS إلى ملف PDF واحد باستخدام Aspose.Page لـ .NET؟

ج1: نعم، يمكنك التنقل عبر ملفات XPS متعددة واتباع نفس الخطوات لدمجها في ملف PDF واحد.

### س2: هل هناك تنسيقات إخراج أخرى يدعمها Aspose.Page لـ .NET؟

ج2: نعم، يدعم Aspose.Page for .NET تنسيقات الإخراج المتنوعة، بما في ذلك TIFF وJPEG وPNG والمزيد.

### س3: كيف يمكنني تخصيص مظهر مستند PDF المحول؟

A3: يمكنك تعديل معلمات كائن الخيارات، مثل ضغط الصورة وضغط النص، لتحقيق المظهر المطلوب.

### س4: هل هناك إصدار تجريبي متاح لـ Aspose.Page لـ .NET؟

 ج4: نعم، يمكنك استكشاف إمكانيات Aspose.Page لـ .NET من خلال الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).

### س5: أين يمكنني الحصول على دعم المجتمع لـ Aspose.Page لـ .NET؟

 ج5: قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للمناقشات المجتمعية والدعم.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
