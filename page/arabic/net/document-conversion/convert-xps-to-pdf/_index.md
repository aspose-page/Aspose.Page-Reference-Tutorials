---
date: 2026-01-10
description: حوّل XPS إلى PDF بسهولة في .NET باستخدام Aspose.Page. حمّل المكتبة، استكشف
  الوثائق، واحصل على نسخة تجريبية مجانية.
linktitle: Convert XPS to PDF
second_title: Aspose.Page .NET API
title: تحويل XPS إلى PDF باستخدام Aspose.Page لـ .NET
url: /ar/net/document-conversion/convert-xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل XPS إلى PDF باستخدام Aspose.Page لـ .NET

## Introduction

في هذا البرنامج التعليمي ستتعلم **كيفية تحويل XPS إلى PDF** باستخدام مكتبة Aspose.Page لـ .NET. تحويل XPS إلى PDF هو طلب شائع عندما تحتاج إلى مشاركة مستندات XPS مع مستخدمين لديهم فقط قارئات PDF، أو عندما تريد تضمين محتوى XPS في سير عمل PDF أكبر. سنستعرض كل خطوة، نشرح لماذا كل إعداد مهم، ونظهر لك كيفية ضبط المخرجات بدقة—مثل ضبط جودة JPEG وتطبيق ضغط صور PDF.

## Quick Answers
- **ما هي المكتبة الأفضل لتحويل XPS إلى PDF؟** Aspose.Page for .NET
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم ترخيص تجاري؛ يتوفر نسخة تجريبية مجانية.
- **هل يمكنني التحكم في جودة الصورة؟** بالتأكيد—استخدم `JpegQualityLevel` و `PdfImageCompression`.
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.
- **هل يمكن تحويل ملفات XPS متعددة إلى PDF واحد؟** نعم، عبر تكرار الملفات ودمج النتائج.

## Prerequisites

قبل أن نبدأ رحلة التحويل هذه، تأكد من توفر المتطلبات التالية:

- **Aspose.Page for .NET Library** – تأكد من تثبيت مكتبة Aspose.Page لـ .NET في بيئة التطوير الخاصة بك. يمكنك تنزيلها من [Aspose.Page documentation](https://reference.aspose.com/page/net/).
- **Development Environment** – قم بإعداد بيئة تطوير .NET باستخدام Visual Studio أو أي بيئة تطوير متكاملة أخرى متوافقة.
- **XPS Document** – حضّر مستند XPS الذي تريد تحويله إلى PDF. يمكن أن يكون ملف XPS النموذجي المخزن في دليل مخصص.

## Import Namespaces

قبل الغوص في الكود، لنقم باستيراد مساحة الاسم اللازمة لجعل وظائف Aspose.Page لـ .NET متاحة في مشروعنا:

```csharp
using Aspose.Page.XPS;
```

## Step‑by‑Step Guide

### Step 1: Initialize Document Directory

حدد المجلد الذي يحتوي على ملف XPS المصدر وحيث سيتم حفظ ملف PDF الناتج.

```csharp
string dataDir = "Your Document Directory";
```

استبدل `"Your Document Directory"` بالمسار المطلق أو النسبي للمجلد الذي يحتوي على مستند XPS الخاص بك.

### Step 2: Open Streams for PDF Output and XPS Input

نستخدم تدفقين للملفات—أحدهما لقراءة ملف XPS والآخر لكتابة ملف PDF المُنشأ.

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

> **Pro tip:** تأكد من صحة المسارات وأن التطبيق يمتلك صلاحيات القراءة/الكتابة على المجلد المستهدف.

### Step 3: Load the XPS Document

أنشئ كائن `XpsDocument` من تدفق XPS. يتيح لك كائن `XpsLoadOptions` تحديد تفضيلات التحميل، لكن الإعداد الافتراضي يعمل في معظم السيناريوهات.

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### Step 4: Configure PDF Save Options

هنا نحدد تفضيلات إخراج PDF. لاحظ استخدام **ضغط صور PDF** (`PdfImageCompression.Jpeg`) و **جودة JPEG** (`JpegQualityLevel = 100`). هذه الإعدادات تؤثر مباشرة على حجم الملف وجودته البصرية.

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

- **`JpegQualityLevel`** – يتحكم في جودة صور JPEG المدمجة في PDF (كلما ارتفعت القيمة زادت الجودة وحجم الملف).
- **`ImageCompression`** – يختار خوارزمية الضغط؛ JPEG مثالية للصور الفوتوغرافية.
- **`TextCompression`** – ضغط Flate يقلل حجم PDF دون فقدان جودة النص.
- **`PageNumbers`** – يتيح لك **حفظ XPS كـ PDF** للصفحات المختارة فقط.

### Step 5: Create a PDF Rendering Device

يعمل `PdfDevice` كهدف للعرض الذي يكتب بيانات PDF إلى التدفق الذي فتحناه مسبقًا.

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Step 6: Save the Document to PDF

أخيرًا، استدعِ طريقة `Save`، مع تمرير جهاز العرض والإعدادات المكوّنة.

```csharp
document.Save(device, options);
```

عند انتهاء تنفيذ الكود، سيظهر الملف `XPStoPDF_out.pdf` في الدليل المحدد، يحتوي على الصفحات المحوّلة مع إعدادات الضغط والجودة التي حددتها.

## Why Convert XPS to PDF?

- **إتاحة شاملة** – مشغلات PDF مثبتة على كل جهاز تقريبًا، بينما قارئات XPS نادرة.
- **الحفاظ على التخطيط** – PDF يحتفظ بالتخطيط البصري الدقيق، الخطوط، والرسومات الأصلية لـ XPS.
- **معالجة إضافية** – بمجرد تحويله إلى PDF، يمكنك دمج، إضافة تعليقات، أو توقيع المستند رقميًا باستخدام مكتبات Aspose الأخرى.

## Common Use Cases

- **تقارير المؤسسات** – إنشاء تقارير XPS من الأنظمة القديمة وتحويلها إلى PDF للتوزيع.
- **الأرشفة** – حفظ المستندات كـ PDF للحفظ طويل الأمد مع القدرة على إنشائها من مصادر XPS.
- **خدمات الويب** – تقديم نقطة نهاية API تستقبل ملفات XPS وتعيد ملفات PDF فورًا.

## Troubleshooting & Tips

- **الملف غير موجود** – تحقق مرة أخرى من مسار `dataDir` وتأكد من تطابق اسم ملف XPS تمامًا.
- **أخطاء الصلاحيات** – شغّل Visual Studio كمسؤول أو امنح صلاحيات كتابة للمجلد الهدف.
- **ملفات PDF الكبيرة** – إذا كان PDF الناتج كبيرًا جدًا، قلل `JpegQualityLevel` أو غيّر `ImageCompression` إلى `PdfImageCompression.Zip`.

## FAQ's

### Q1: Can I convert multiple XPS files to a single PDF using Aspose.Page for .NET?

A1: نعم، يمكنك تكرار الملفات المتعددة واتباع نفس الخطوات لدمجها في PDF واحد.

### Q2: Are there other output formats supported by Aspose.Page for .NET?

A2: نعم، تدعم Aspose.Page لـ .NET صيغ إخراج متعددة، بما في ذلك TIFF، JPEG، PNG، وأكثر.

### Q3: How can I customize the appearance of the converted PDF document?

A3: يمكنك تعديل معلمات كائن الخيارات، مثل ضغط الصور وضغط النص، للحصول على المظهر المطلوب.

### Q4: Is there a trial version available for Aspose.Page for .NET?

A4: نعم، يمكنك استكشاف قدرات Aspose.Page لـ .NET بالحصول على نسخة تجريبية مجانية من [here](https://releases.aspose.com/).

### Q5: Where can I get community support for Aspose.Page for .NET?

A5: زر [Aspose.Page forum](https://forum.aspose.com/c/page/39) للمناقشات المجتمعية والحصول على الدعم.

## Frequently Asked Questions (AI‑Friendly)

**س: كيف أضبط جودة JPEG عند تحويل XPS إلى PDF؟**  
ج: استخدم الخاصية `JpegQualityLevel` داخل `PdfSaveOptions`. ضبطها على 100 يعطي أقصى جودة.

**س: ماذا يعني “ضغط صور PDF” في هذا السياق؟**  
ج: يشير إلى خيار `ImageCompression` الذي يحدد كيفية ضغط الصور داخل PDF (مثل JPEG، Zip).

**س: هل يمكنني إنشاء PDF برمجيًا دون مصدر XPS؟**  
ج: نعم، تدعم Aspose.Page أيضًا **c# generate pdf** مباشرة من أوامر الرسم، لكن هذا خارج نطاق هذا الدرس.

**س: هل هناك طريقة لتحويل XPS إلى PDF دون فقدان الرسومات المتجهة؟**  
ج: التحويل يحتفظ بالبيانات المتجهة؛ فقط تجنب تحويل الصور إلى نقطية بالحفاظ على `ImageCompression` مضبوطة على JPEG أو Zip حسب الحاجة.

**س: هل تدعم المكتبة .NET Core؟**  
ج: بالتأكيد – تعمل Aspose.Page لـ .NET مع .NET Core، .NET 5، .NET 6، والإصدارات الأحدث.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}