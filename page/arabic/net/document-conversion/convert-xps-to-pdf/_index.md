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

## مقدمة

في هذا البرنامج التعليمي ستتعلم **كيفية تحويل XPS إلى PDF** باستخدام مكتبة Aspose.Page لـ .NET. تحويل XPS إلى PDF هو طلب شائع عندما تحتاج إلى مشاركة مستندات XPS مع مستخدمين فقط قارئات PDF، أو عندما تريد تضمين محتوى XPS في سير عمل PDF أكبر. سنستعرض كل خطوة، نشرح لماذا كل إعداد مهم، ونظهر لك كيفية ضبط المخرج بدقة — مثل ضبط جودة JPEG وتطبيق ضغط صور PDF.

## إجابات سريعة
- **ما هي المكتبة الشاملة لتحويل XPS إلى PDF؟** Aspose.Page for .NET
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، اطلب ترخيص تجاري؛ نسخة مجانية مجانية.
- **هل يمكنني التحكم في جودة الصورة؟** بالتأكيد—استخدم `JpegQualityLevel` و `PdfImageCompression`.
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.
- **هل يمكن تحويل ملفات XPS المتعددة إلى PDF واحد؟** نعم، عبر تسجيلات الملفات والنتائج المدمجة.

## المتطلبات الأساسية

قبل أن تبدأ الرحلة لتبديل هذه، تأكد من ضرورة المتطلبات التالية:

- **Aspose.Page for .NET Library** – تأكد من تثبيت مكتبة Aspose.Page لـ .NET في بيئة التطوير الخاص بك. يمكنك تنزيلها من [وثائق Aspose.Page](https://reference.aspose.com/page/net/).
- **بيئة التطوير** – يجب أن نسعى إلى تطوير .NET باستخدام Visual Studio أو أي بيئة متكاملة أخرى متوافقة.
- **مستند XPS** – حضّر مستند XPS الذي تريد تحويله إلى PDF. يمكن أن يكون ملف XPS النموذجي مخزنًا في دليل مخصص.

## استيراد مساحات الأسماء

قبل الغوص في الكود، لنقم باستيراد مساحة الاسم اللازمة لجعل وظائف Aspose.Page لـ .NET متاحة في مشروعنا:

```csharp
using Aspose.Page.XPS;
```

## دليل خطوة بخطوة

### الخطوة 1: تهيئة مجلد المستندات

حدد المجلد الذي يحتوي على ملف XPS المصدر وحيث سيتم حفظ ملف PDF الناتج.

```csharp
string dataDir = "Your Document Directory";
```

استبدل `"Your Document Directory"` بالمسار المطلق أو النسبي للمجلد الذي يحتوي على مستند XPS الخاص بك.

### الخطوة 2: فتح مسارات إخراج ملفات PDF وإدخال ملفات XPS

نستخدم تدفقين للملفات—أحدهما لقراءة ملف XPS والآخر لكتابة ملف PDF المُنشأ.

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

> **Pro tip:** تأكد من صحة المسارات وأن التطبيق يمتلك صلاحيات القراءة/الكتابة على المجلد المستهدف.

### الخطوة 3: تحميل مستند XPS

أنشئ كائن `XpsDocument` من تدفق XPS. يتيح لك كائن `XpsLoadOptions` تحديد تفضيلات التحميل، لكن الإعداد الافتراضي يعمل في معظم السيناريوهات.

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### الخطوة 4: ضبط خيارات حفظ ملف PDF

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

### الخطوة 5: إنشاء جهاز عرض PDF

يعمل `PdfDevice` كهدف للعرض الذي يكتب بيانات PDF إلى التدفق الذي فتحناه مسبقًا.

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### الخطوة 6: حفظ المستند بصيغة PDF

أخيرًا، استدعِ طريقة `Save`، مع تمرير جهاز العرض والإعدادات المكوّنة.

```csharp
document.Save(device, options);
```

عند انتهاء تنفيذ الكود، سيظهر الملف `XPStoPDF_out.pdf` في الدليل المحدد، يحتوي على الصفحات المحوّلة مع إعدادات الضغط والجودة التي حددتها.

## لماذا تحويل XPS إلى PDF؟

- **إتاحة شاملة** – مشغل PDF مثبتة على كل جهاز تقريبًا، بينما قارئات XPS نادرة.
- **الحفاظ على التخطيط** – دقة PDF بالتخطيط البصري الدقيق، الخطوط، الرسوم الأصلية لـ XPS.
- **معالجة إضافية** – بمجرد تحويله إلى PDF، يمكنك دمج، إضافة تعليقات، أو توقيع المستند الرقمي باستخدام مكتبات أخرى.

## حالات الاستخدام الشائعة

- ** تقارير المؤسسات** – إنشاء تقارير XPS من التحويلات القديمة وتحويلها إلى PDF للتوزيع.
- **الأرشفة** – حفظ المستندات كـ PDF للحفظ لفترة طويلة مع القدرة على إنشاءها من مصادر XPS.
- **خدمات الويب** – تقديم نقطة نهاية API لاستقبال ملفات XPS وتعيد ملفات PDF فورًا.

## استكشاف الأخطاء وإصلاحها ونصائح

- **الملف غير موجود** – تحقق مرة أخرى من مسار `dataDir` وتأكد من تطابق اسم ملف XPS تمامًا.
- **أخطاء الصلاحيات** – شغّل Visual Studio كمسؤول أو امنح صلاحيات كتابة لجلد الهدف.
- **ملفات PDF كبيرة** – إذا كان PDF مناسبًا بدرجة معقولة جدًا، قلل `JpegQualityLevel` أو غيّر `ImageCompression` إلى `PdfImageCompression.Zip`.

## الأسئلة المتداولة (صديقة للذكاء الاصطناعي)

**س: كيف أضبط جودة JPEG عند تحويل XPS إلى PDF؟**
ج: استخدم الخاصة `JpegQualityLevel` داخل `PdfSaveOptions`. ضبطها على 100 يعطي أقصى جودة.

**س: ماذا يعني “ضغط صور PDF” في هذا السياق؟**
ج: يشير إلى الخيار `ImageCompression` الذي يحدد كيفية ضغط الصور داخل PDF (مثل JPEG، Zip).

**س: هل يمكنني إنشاء PDF برمجيًا دون مصدر XPS؟**
ج: نعم، تدعم Aspose.Page أيضًا **c# create pdf** مباشرة من الأوامر الرسم، لكن هذا خارج نطاق هذا الدرس.

**س: هل هناك طريقة لإرسال XPS إلى PDF دون روعة الرسومات المتجه؟**
ج: تغيير بالبيانات المتجهة؛ فقط تجنب تحويل الصور إلى نقطية بالحفاظ على `ImageCompression` مضبوطًا على JPEG أو Zip حسب الحاجة.

**س: هل تدعم المكتبة .NET Core؟**
ج: بالتأكيد – تعمل Aspose.Page لـ .NET مع .NET Core، .NET 5، .NET 6، وإصدارات انترنت.

---

**آخر تحديث:** 10-01-2026
**تم الاختبار باستخدام:** Aspose.Page 24.11 لـ .NET
**المؤلف:** اطرح  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}