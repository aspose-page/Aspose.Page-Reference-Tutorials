---
date: 2026-03-21
description: تعلم كيفية إنشاء مستند PostScript باستخدام C# ونص Unicode عبر Aspose.Page
  لـ .NET – طريقة سريعة لتعزيز معالجة المستندات.
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: إنشاء مستند PostScript باستخدام C# ونص Unicode – Aspose.Page
url: /ar/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة نص بسلسلة يونيكود إلى PostScript (PS) باستخدام Aspose.Page

## المقدمة

إذا كنت بحاجة إلى **إنشاء مستند PostScript باستخدام C#** وتضمين أحرف يونيكود، فإن Aspose.Page لـ .NET يجعل العملية بسيطة. في هذا الدرس سنستعرض مثالًا عمليًا كاملًا يوضح لك كيفية إضافة نص ياباني (أو أي سلسلة يونيكود) إلى ملف PS، اختيار خط مخصص، وحفظ النتيجة. في النهاية ستحصل على قطعة شفرة قابلة لإعادة الاستخدام يمكنك إدراجها في أي مشروع C#.

## إجابات سريعة
- **ما الذي يغطيه هذا الدرس؟** إضافة نص يونيكود إلى ملف PostScript باستخدام Aspose.Page في C#.
- **ما المكتبة المطلوبة؟** Aspose.Page لـ .NET (أحدث نسخة).
- **هل أحتاج إلى خط خاص؟** أي خط TrueType/OpenType يدعم نطاق يونيكود المطلوب، مثل *Arial Unicode MS*.
- **كم عدد أسطر الشفرة؟** حوالي 30 سطرًا، مقسمة إلى خطوات واضحة.
- **هل يلزم الحصول على ترخيص؟** ترخيص مؤقت يكفي للتقييم؛ الترخيص الكامل مطلوب للإنتاج.

## ما هو “create postscript document c#”؟
إنشاء مستند PostScript في C# يعني توليد ملف .ps برمجيًا يتبع مواصفات لغة PostScript. تقوم Aspose.Page بتجريد التفاصيل منخفضة المستوى، مما يسمح لك بالتركيز على المحتوى مثل النصوص والرسومات والخطوط.

## لماذا نستخدم Aspose.Page للنصوص يونيكود؟
- **دعم كامل ليونيكود** – عرض الأحرف من أي لغة دون الحاجة إلى ترميز يدوي.
- **مستقل عن الجهاز** – نفس الشفرة تعمل مع مخرجات PS و EPS و PDF.
- **بدون تبعيات خارجية** – المكتبة تتعامل مع تحميل الخطوط وتطابق الحروف داخليًا.

## المتطلبات المسبقة

- إلمام أساسي بـ C# وتطوير .NET.
- تثبيت مكتبة Aspose.Page لـ .NET. يمكنك تحميلها من [توثيق Aspose.Page لـ .NET](https://reference.aspose.com/page/net/).
- مجلد يحتوي على الخطوط التي تنوي استخدامها (مثل *Arial Unicode MS*).

## استيراد المساحات الاسمية

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## الخطوة 1: إعداد دليل المستند ومجلد الخطوط

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## الخطوة 2: إنشاء تدفق إخراج لمستند PostScript

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## الخطوة 3: إضافة نص يونيكود بخط مخصص

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## الخطوة 4: إغلاق الصفحة الحالية

```csharp
document.ClosePage();
```

## الخطوة 5: إكمال وحفظ المستند

```csharp
document.Save();
```

## المشكلات الشائعة والحلول

- **الخط غير موجود** – تأكد من أن مسار `AdditionalFontsFolders` يشير إلى المجلد الذي يحتوي على ملفات .ttf/.otf وأن اسم الخط مطابق تمامًا.
- **ظهور رموز غير مفهومة** – تحقق من أن السلسلة المصدرية مشفرة كـ UTF‑8 في ملف C# (استخدم `#pragma warning disable 1591` إذا لزم الأمر).
- **عدم إنشاء الملف** – افحص صلاحيات الكتابة على `dataDir` وتأكد من أن التدفق يتم إغلاقه بشكل صحيح (كتلة `using` تتولى ذلك).

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page لـ .NET مع لغات برمجة أخرى؟**  
ج: Aspose.Page مصممة أساسًا لـ .NET، لكن هناك إصدارات مكافئة للغة Java متاحة.

**س: كيف أحصل على ترخيص مؤقت لـ Aspose.Page لـ .NET؟**  
ج: زر [Temporary License](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت.

**س: هل هناك منتدى مجتمع لمناقشات Aspose.Page؟**  
ج: نعم، زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع.

**س: ما الصيغ التي يدعمها Aspose.Page لـ .NET؟**  
ج: يدعم Aspose.Page صيغًا متعددة، بما في ذلك XPS، PS، EPS، PDF، وأكثر.

**س: هل يمكنني تخصيص مظهر النص المضاف؟**  
ج: نعم، يمكنك تخصيص الخط، الحجم، اللون، والخصائص الأخرى للنص في Aspose.Page.

## الخلاصة

في هذا الدرس أظهرنا كيفية **إنشاء مستند PostScript باستخدام C#** وتضمين نص يونيكود باستخدام Aspose.Page. باتباع الخطوات أعلاه يمكنك دمج عرض النصوص متعددة اللغات بسرعة في أي تطبيق .NET، مما يمنحك تحكمًا كاملاً في توليد المستندات وتنسيقها.

---

**آخر تحديث:** 2026-03-21  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}