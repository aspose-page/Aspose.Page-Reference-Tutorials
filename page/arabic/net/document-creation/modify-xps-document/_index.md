---
date: 2026-01-12
description: تعلم كيفية تعديل مستند XPS باستخدام Aspose.Page لـ .NET واكتشف كيفية
  إضافة نص إلى ملفات XPS بأمثلة شفرة بسيطة.
linktitle: Modify XPS Document
second_title: Aspose.Page .NET API
title: تعديل مستند XPS باستخدام Aspose.Page لـ .NET
url: /ar/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعديل مستند XPS باستخدام Aspose.Page لـ .NET

## مقدمة

مرحبًا بك في دليلنا خطوة بخطوة حول **كيفية تعديل ملفات مستند XPS** باستخدام Aspose.Page لـ .NET. سواء كنت بحاجة إلى إدراج توقيع، إضافة علامة مائية، أو ببساطة وضع نص مخصص على صفحة، يوضح لك هذا البرنامج التعليمي بالضبط **كيفية إضافة نص** إلى مستند XPS في بضع دقائق. سنستعرض كل سطر من الشيفرة، نشرح لماذا كل خطوة مهمة، ونقدم لك نصائح لتجنب المشكلات الشائعة.

### إجابات سريعة
- **ماذا يغطي هذا الدرس؟** إضافة نص توقيع ("Confirmed") إلى الصفحات المحددة من ملف XPS.  
- **ما المكتبة المطلوبة؟** Aspose.Page لـ .NET (أحدث نسخة).  
- **هل أحتاج إلى ترخيص؟** ترخيص مؤقت يكفي للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.  
- **كم يستغرق التنفيذ؟** حوالي 10 دقائق لإدراج توقيع أساسي.

## ما هو تعديل مستند XPS؟

XPS (XML Paper Specification) هو تنسيق مستند ثابت التخطيط من مايكروسوفت، يشبه PDF. تعديل مستند XPS يعني تغيير محتواه البصري برمجيًا—إضافة نصوص، صور، أو أشكال—دون تحويل الملف إلى تنسيق آخر. توفر Aspose.Page نموذج كائنات غني يتيح لك تحرير ملفات XPS مباشرة من كود .NET الخاص بك.

## لماذا نستخدم Aspose.Page لتعديل مستندات XPS؟

* **تحكم كامل** – العمل مع الصفحات، الرموز، الفرش، والتحويلات على مستوى منخفض.  
* **بدون تبعيات خارجية** – مكتبة .NET صافية، لا تحتاج إلى مكونات Office أو Adobe.  
* **متعددة المنصات** – تعمل على Windows، Linux، و macOS عبر .NET Core.  
* **أداء قوي** – تتعامل مع المستندات الكبيرة بكفاءة وتدعم الطباعة المتقدمة.

## المتطلبات المسبقة

قبل البدء، تأكد من وجود ما يلي:

- **Aspose.Page لـ .NET** – ثبّت حزمة NuGet أو حمّل المكتبة من الوثائق الرسمية **[هنا](https://reference.aspose.com/page/net/)**.  
- **ملف XPS الإدخالي** – احصل على مستند XPS تجريبي (مثل `input1.xps`) من **[صفحة إصدارات Aspose](https://releases.aspose.com/page/net/)**.  
- **دليل العمل** – أنشئ مجلدًا على جهازك لتخزين ملفات الإدخال والإخراج وسجل مساره الكامل؛ ستُعيّن هذا المسار للمتغيّر `dir` في الشيفرة.  
- **بيئة التطوير** – Visual Studio 2019/2022، .NET Framework 4.7.2 أو أحدث، أو أي مشروع .NET Core/5/6.

الآن بعد أن تم إعداد كل شيء، لنغص في الشيفرة.

## استيراد المساحات الاسمية

في مشروع .NET الخاص بك، ابدأ باستيراد المساحات الاسمية المطلوبة لـ Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## الخطوة 1: فتح تدفق مستند XPS

سنفتح ملف XPS المصدر كـ stream وننشئ كائن `XpsDocument` يمثل المستند بالكامل.

```csharp
// ExStart:3
// The path to the documents directory.
string dir = "Your Document Directory";
// Open a stream of XPS file
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Create PS document from stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Continue to the next step...
}
// ExEnd:3
```

*نصيحة احترافية:* غلف الـ stream داخل كتلة `using` لضمان تحرير مقبض الملف تلقائيًا.

## الخطوة 2: إنشاء نص التوقيع

بعد ذلك، ننشئ فرشاة صلبة اللون ستُستخدم لرسم رموز التوقيع.

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

يمكنك تغيير `Color.BlueViolet` إلى أي `System.Drawing.Color` يتناسب مع هوية علامتك التجارية.

## الخطوة 3: تحديد الصفحات وإضافة التوقيع

سنحدد الصفحات التي يجب أن تتلقى التوقيع ثم نضيف الرموز إلى كل صفحة.

```csharp
// ExStart:5
// Define pages where signature will be set
int[] pageNumbers = new int[] {1, 2, 3};

// For every defined page set signature "Confirmed" at coordinates x=650 and y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Define active page
    document.SelectActivePage(pageNumbers[i]);

    // Create glyphs object
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Define fill for glyphs
    glyphs.Fill = textFill;
}
// Continue to the next step...
// ExEnd:5
```

*لماذا هذه الإحداثيات؟* قيم X و Y تُقاس بالنقاط (1/72 إنش). عدّلها لتحديد موضع النص بدقة على تخطيط صفحتك.

## الخطوة 4: حفظ التغييرات إلى مستند XPS

أخيرًا، اكتب المستند المعدل مرة أخرى إلى القرص.

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

الملف الجديد `input1_out.xps` الآن يحتوي على توقيع “Confirmed” في الصفحات 1‑3.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|----------|
| **التوقيع غير مرئي** | إحداثيات خاطئة أو عدم اختيار الصفحة | تحقق من استدعاء `SelectActivePage` لكل صفحة واضبط قيم X/Y. |
| **استثناء عند `AddGlyphs`** | الخط غير مثبت على الخادم | تأكد من توفر الخط المحدد (مثل Arial)، أو أدمج خطًا مخصصًا باستخدام `document.AddFont`. |
| **ملف الإخراج معطوب** | عدم إغلاق الـ stream بشكل صحيح | استخدم عبارات `using` لجميع الـ streams واستدعِ `document.Dispose()` إذا لزم الأمر. |
| **تباطؤ الأداء مع ملفات كبيرة** | تحميل المستند بالكامل في الذاكرة | عالج الصفحات على دفعات أو استخدم `XpsLoadOptions` مع خيارات البث (إن توفرت في الإصدارات الأحدث). |

## الأسئلة المتكررة

**س: هل Aspose.Page متوافق مع أحدث إطارات .NET؟**  
ج: نعم، يتم تحديث Aspose.Page بانتظام لدعم .NET Framework 4.5+، .NET Core 3.1+، .NET 5، و .NET 6.

**س: هل يمكنني تخصيص الخط والنمط للنص المضاف؟**  
ج: بالتأكيد. غيّر معلمات `AddGlyphs` (اسم الخط، الحجم، `FontStyle`) لتتناسب مع تصميمك.

**س: هل هناك حدود لحجم ملفات XPS؟**  
ج: يمكن لـ Aspose.Page معالجة مستندات كبيرة، لكن استهلاك الذاكرة يزداد مع حجم الملف. للملفات الضخمة جدًا، يُفضَّل معالجة الصفحات بشكل فردي.

**س: كيف أحصل على ترخيص مؤقت لـ Aspose.Page؟**  
ج: يمكنك الحصول على ترخيص مؤقت **[هنا](https://purchase.aspose.com/temporary-license/)**.

**س: أين يمكنني طلب المساعدة أو التواصل مع مجتمع Aspose؟**  
ج: زر **[منتدى Aspose.Page](https://forum.aspose.com/c/page/39)** لطرح الأسئلة ومشاركة التجارب.

## الخاتمة

في هذا الدرس أظهرنا كيفية **تعديل ملفات XPS** بإضافة نص توقيع مخصص باستخدام Aspose.Page لـ .NET. الآن لديك أساس قوي لإدراج أي نص، علامة مائية، أو تعليق على صفحات محددة من ملف XPS. جرّب خطوطًا، ألوانًا، ومواقع مختلفة لتلبية متطلبات العلامة التجارية لتطبيقك، واستكشف واجهة برمجة التطبيقات الأوسع لـ Aspose.Page لإمكانيات رسومية وتخطيطية متقدمة.

---

**آخر تحديث:** 2026-01-12  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}