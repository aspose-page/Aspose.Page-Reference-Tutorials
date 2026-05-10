---
date: 2026-01-12
description: تعلم كيفية إنشاء مستندات PostScript في .NET باستخدام Aspose.Page. يوضح
  هذا الدليل خطوة بخطوة كيفية إنشاء ملفات PostScript، وتعيين حجم صفحة PostScript،
  وتخصيص الهوامش لتحقيق تكامل سلس.
linktitle: Create PostScript Document
second_title: Aspose.Page .NET API
title: كيفية إنشاء مستند PostScript باستخدام Aspose.Page لـ .NET
url: /ar/net/document-creation/create-postscript-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء مستند PostScript باستخدام Aspose.Page لـ .NET

## مقدمة

مرحبًا! في هذا الدرس الشامل ستكتشف **كيفية إنشاء مستندات PostScript** برمجيًا باستخدام Aspose.Page لـ .NET. سواءً كنت تُنشئ فواتير، ملصقات شحن، أو أي مخرجات طباعة قائمة على المتجهات، سيوضح لك هذا الدليل كل خطوة—من إعداد البيئة إلى حفظ الملف النهائي بصيغة *.ps*. هيا نغوص ونرى مدى سهولة إنتاج ملف PostScript عالي الجودة في بضع أسطر من C# فقط.

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.Page for .NET  
- **هل يمكنني ضبط حجم الصفحة؟** نعم – استخدم `options.PageSize` (انظر “set PostScript page size”).  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للاختبار؛ الترخيص مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.  
- **كم من الوقت تستغرق عملية التنفيذ؟** عادةً أقل من 10 دقائق لإنشاء مستند أساسي.

## ما هو “كيفية إنشاء PostScript” في .NET؟
توفر Aspose.Page واجهة برمجة تطبيقات غنية تُجردك من تفاصيل صيغة EPS/PostScript منخفضة المستوى، مما يتيح لك التركيز على تخطيط الصفحة، الرسومات، والنص. باستخدام المكتبة تتجنب كتابة كود PS يدوي وتستفيد من دعم الخطوط، الصور، والقياسات الدقيقة.

## لماذا تستخدم Aspose.Page لإنشاء PostScript؟
- **تحكم كامل** في أبعاد الصفحة، الهوامش، والرسومات الأولية.  
- **لا توجد تبعيات خارجية** – كل شيء يعمل داخل عملية .NET الخاصة بك.  
- **دعم متعدد المنصات** لنظام Windows، Linux، و macOS.  
- **معالجة خطوط قوية**، بما في ذلك مجلدات الخطوط المخصصة.

## المتطلبات المسبقة

- مكتبة Aspose.Page for .NET: تأكد من تثبيت مكتبة Aspose.Page for .NET. يمكنك تنزيلها من [هنا](https://releases.aspose.com/page/net/).
- بيئة .NET: تأكد من وجود بيئة .NET جاهزة على جهازك.
- محرر نصوص أو IDE: استخدم محرر النصوص أو بيئة التطوير المتكاملة (IDE) المفضلة لديك للبرمجة.

الآن بعد أن أصبح كل شيء جاهزًا، لنبدأ بإنشاء المستند.

## استيراد المساحات الاسمية

أولًا، استورد المساحات الاسمية التي تمنحك الوصول إلى الفئات الأساسية في Aspose.Page.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.IO;
```

تُتيح لك هذه المساحات الاسمية الوصول إلى `PsDocument`، `PsSaveOptions`، والفئات المساعدة المستخدمة طوال الدرس.

## الخطوة 1: تحديد مسار المستند

```csharp
string dir = "Your Document Directory";
```

استبدل `"Your Document Directory"` بالمسار المطلق أو النسبي حيث ترغب في حفظ ملف **PostScript** النهائي.

## الخطوة 2: إنشاء تدفق الإخراج

```csharp
using (Stream outPsStream = new FileStream(dir + "document.ps", FileMode.Create))
```

يفتح `FileStream` تدفقًا قابلًا للكتابة باسم **document.ps**. سيتم كتابة جميع أوامر الرسم اللاحقة إلى هذا التدفق.

## الخطوة 3: إنشاء خيارات الحفظ

```csharp
PsSaveOptions options = new PsSaveOptions();
```

يتيح لك `PsSaveOptions` ضبط كيفية عرض المستند وحفظه.

## الخطوة 4: ضبط حجم صفحة PostScript والهوامش

```csharp
options.PageSize = PageConstants.GetSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT);
options.Margins = PageConstants.GetMargins(PageConstants.MARGINS_ZERO);
```

هنا نقوم **بتعيين حجم صفحة PostScript** إلى A4 عموديًا وإزالة جميع الهوامش. يمكنك استبدال `SIZE_A4` بثوابت أخرى (مثل `SIZE_LETTER`) لتلبية متطلبات التخطيط الخاصة بك.

## الخطوة 5: تحديد مجلدات الخطوط الإضافية

```csharp
options.AdditionalFontsFolders = new string[] { dir };
```

إذا كان المستند يستخدم خطوطًا مخصصة غير مثبتة على النظام، قم بتوجيه Aspose.Page إلى المجلد الذي يحتوي على ملفات الخطوط تلك.

## الخطوة 6: إنشاء مستند متعدد الصفحات

```csharp
bool multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

تمثل كائن `PsDocument` مستند PostScript. ضبط `multiPaged` على `false` يُنشئ مستندًا بصفحة واحدة (يمكنك تغييره إلى `true` لإنشاء مستند متعدد الصفحات).

## الخطوة 7: الإغلاق والحفظ

```csharp
document.ClosePage();
document.Save();
```

استدعاء `ClosePage()` يُنهي محتوى الصفحة، و`Save()` يكتب تدفق PostScript الكامل إلى القرص.

تهانينا! لقد تعلمت الآن **كيفية إنشاء مستندات PostScript** باستخدام Aspose.Page لـ .NET.

## المشكلات الشائعة والحلول

- **أخطاء مسار الملف** – تأكد من أن المتغير `dir` ينتهي بفاصل مسار (`\` أو `/`) أو استخدم `Path.Combine`.  
- **الخطوط المفقودة** – إذا ظهر النص بخطوط افتراضية، تحقق من أن `options.AdditionalFontsFolders` يشير إلى الدليل الصحيح.  
- **حجم الصفحة غير صحيح** – راجع الثوابت الممررة إلى `PageConstants.GetSize`؛ يمكنك أيضًا تمرير أبعاد مخصصة عبر `new SizeF(width, height)`.

## الأسئلة المتكررة

### س1: أين يمكنني العثور على وثائق Aspose.Page لـ .NET؟
ج1: الوثائق متاحة [هنا](https://reference.aspose.com/page/net/).

### س2: كيف يمكنني تنزيل Aspose.Page لـ .NET؟
ج2: يمكنك تنزيله من [هذا الرابط](https://releases.aspose.com/page/net/).

### س3: أين يمكنني شراء ترخيص لـ Aspose.Page لـ .NET؟
ج3: يمكنك شراء ترخيص [هنا](https://purchase.aspose.com/buy).

### س4: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Page لـ .NET؟
ج4: نعم، يمكنك العثور على النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

### س5: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟
ج5: احصل على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### س6: هل يمكنني إنشاء ملفات PostScript متعددة الصفحات؟
ج6: بالتأكيد. اضبط `bool multiPaged = true` عند إنشاء `PsDocument` واستدعِ `document.NewPage()` لكل صفحة إضافية.

### س7: هل يدعم Aspose.Page إدارة الألوان؟
ج7: نعم، يمكنك تضمين ملفات تعريف ICC عبر `PsSaveOptions.ColorProfile` إذا لزم الأمر.

---

**آخر تحديث:** 2026-01-12  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}