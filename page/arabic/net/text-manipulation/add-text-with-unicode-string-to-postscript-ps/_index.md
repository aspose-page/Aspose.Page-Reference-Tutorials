---
title: إضافة نص باستخدام سلسلة Unicode إلى PostScript (PS) باستخدام Aspose.Page
linktitle: إضافة نص باستخدام سلسلة Unicode إلى PostScript (PS)
second_title: Aspose.Page .NET API
description: تعرف على كيفية إضافة نص Unicode إلى ملفات PostScript باستخدام Aspose.Page لـ .NET. تعزيز معالجة المستندات بسهولة.
weight: 11
url: /ar/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة نص باستخدام سلسلة Unicode إلى PostScript (PS) باستخدام Aspose.Page

## مقدمة

في مجال معالجة المستندات، تبرز Aspose.Page for .NET كمكتبة قوية تمكن المطورين من إنشاء تنسيقات المستندات المختلفة وتحريرها وتحويلها. إحدى ميزاته القوية هي القدرة على إضافة نص باستخدام سلاسل Unicode إلى ملفات PostScript (PS). في هذا البرنامج التعليمي، سنستكشف دليلًا خطوة بخطوة حول إنجاز هذه المهمة، مما يوفر تجربة سلسة للمطورين الذين يعملون مع Aspose.Page.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:

- معرفة عملية بلغة البرمجة C#.
-  تم تثبيت Aspose.Page لمكتبة .NET. يمكنك تنزيله من[Aspose.Page لوثائق .NET](https://reference.aspose.com/page/net/).
- بيئة تطوير تم إعدادها بالتكوينات الضرورية.

## استيراد مساحات الأسماء

في كود C# الخاص بك، قم باستيراد مساحات الأسماء المطلوبة لاستخدام Aspose.Page لوظائف .NET:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## الخطوة 1: إعداد دليل المستندات ومجلد الخطوط

```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## الخطوة 2: إنشاء دفق الإخراج لمستند PostScript

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // إنشاء خيارات الحفظ بحجم A4
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (يمكن ضبط الخيارات الإضافية هنا)
    
    // قم بإنشاء مستند PS جديد مكون من صفحة واحدة
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (سيتم شرح المزيد من الخطوات أدناه)
    
    // احفظ المستند
    document.Save();
}
```

## الخطوة 3: إضافة نص Unicode بخط مخصص

```csharp
string str = "試してみます.";  // نص يونيكود
int fontSize = 48;

// استخدام الخط المخصص لملء النص
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## الخطوة 4: أغلق الصفحة الحالية

```csharp
document.ClosePage();
```

## الخطوة 5: إنهاء وحفظ المستند

```csharp
document.Save();
```

## خاتمة

في هذا البرنامج التعليمي، تناولنا عملية إضافة نص Unicode إلى مستند PostScript باستخدام Aspose.Page لـ .NET. ومن خلال الاستفادة من إمكاناته القوية، يمكن للمطورين تحسين سير عمل معالجة المستندات لديهم، مما يضمن المرونة والدقة.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.Page لـ .NET مع لغات برمجة أخرى؟

ج1: تم تصميم Aspose.Page بشكل أساسي لـ .NET، ولكن هناك إصدارات أخرى متوفرة لـ Java.

### س2: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟

 ج2: زيارة[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت.

### س3: هل يوجد منتدى مجتمعي لمناقشات Aspose.Page؟

 ج3: نعم، قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) لدعم المجتمع.

### س 4: ما هي التنسيقات التي يمكن أن يعمل بها Aspose.Page لـ .NET؟

A4: يدعم Aspose.Page التنسيقات المختلفة، بما في ذلك XPS وPS وEPS وPDF والمزيد.

### س5: هل يمكنني تخصيص مظهر النص المضاف؟

ج5: نعم، يمكنك تخصيص الخط والحجم واللون والخصائص الأخرى للنص في Aspose.Page.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
