---
title: قم بتعديل مستند XPS باستخدام Aspose.Page لـ .NET
linktitle: تعديل مستند XPS
second_title: Aspose.Page .NET API
description: اكتشف قوة Aspose.Page لـ .NET لتعديل مستندات XPS بسهولة. اتبع دليلنا المفصّل خطوة بخطوة، وحسّن عملية معالجة مستنداتك، وأضف نصوص توقيع مخصصة.
type: docs
weight: 12
url: /ar/net/document-creation/modify-xps-document/
---
## مقدمة

مرحبًا بك في دليلنا خطوة بخطوة حول كيفية تعديل مستندات XPS باستخدام Aspose.Page لـ .NET. Aspose.Page هي مكتبة قوية تمكن المطورين من العمل مع ملفات XPS دون عناء. في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة نص التوقيع "مؤكد" إلى صفحات محددة في مستند XPS.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

- Aspose.Page لـ .NET: تأكد من تثبيت مكتبة Aspose.Page. يمكنك العثور على الوثائق[هنا](https://reference.aspose.com/page/net/).

-  تنزيل الملفات المطلوبة: قم بتنزيل الملفات الضرورية، بما في ذلك مستند XPS المدخل، من ملف[صفحة الإصدارات Aspose](https://releases.aspose.com/page/net/).

-  دليل المستندات: قم بإعداد دليل لمستنداتك وقم بتحديث ملف`dir` متغير في الكود بالمسار المناسب.

الآن بعد أن قمت بإعداد كل شيء، دعنا نتعمق في الدليل خطوة بخطوة.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، ابدأ باستيراد مساحات الأسماء المطلوبة لـ Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## الخطوة 1: افتح تدفق مستندات XPS

```csharp
// البداية:3
// المسار إلى دليل المستندات.
string dir = "Your Document Directory";
// افتح دفق ملف XPS
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // قم بإنشاء مستند PS من الدفق
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // انتقل إلى الخطوة التالية...
}
// النهاية:3
```

## الخطوة 2: إنشاء نص التوقيع

```csharp
// البداية:4
// إنشاء تعبئة نص التوقيع
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// انتقل إلى الخطوة التالية...
// النهاية:4
```

## الخطوة 3: تحديد الصفحات وإضافة التوقيع

```csharp
// البداية:5
// تحديد الصفحات التي سيتم تعيين التوقيع فيها
int[] pageNumbers = new int[] {1, 2, 3};

//لكل مجموعة صفحات محددة، يتم التوقيع "مؤكد" عند الإحداثيات x=650 وy=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // تحديد الصفحة النشطة
    document.SelectActivePage(pageNumbers[i]);

    // إنشاء كائن الحروف الرسومية
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // تحديد تعبئة الحروف الرسومية
    glyphs.Fill = textFill;
}
// انتقل إلى الخطوة التالية...
// النهاية:5
```

## الخطوة 4: حفظ التغييرات في مستند XPS

```csharp
// البداية:6
// احفظ مستند XPS الذي تم تغييره
document.Save(dir + "input1_out.xps");
// النهاية:6
```

تهانينا! لقد نجحت في تعديل مستند XPS باستخدام Aspose.Page لـ .NET. لا تتردد في استكشاف الميزات والوظائف الإضافية التي تقدمها Aspose.Page لتحسين معالجة المستندات الخاصة بك.

## خاتمة

في هذا البرنامج التعليمي، قمنا بتغطية الخطوات الأساسية لتعديل مستندات XPS باستخدام Aspose.Page لـ .NET. باتباع هذه الخطوات، يمكنك دمج نصوص التوقيع بسلاسة في صفحات محددة، مما يضيف لمسة شخصية إلى مستنداتك.

## الأسئلة الشائعة

### س1: هل Aspose.Page متوافق مع أحدث أطر عمل .NET؟

ج1: نعم، يتم تحديث Aspose.Page بانتظام لدعم أحدث أطر عمل .NET.

### س2: هل يمكنني تخصيص خط ونمط النص المضاف؟

ج2: بالتأكيد! يمكنك تعديل الخط والنمط والسمات الأخرى وفقًا لمتطلباتك.

### س3: هل هناك أي قيود على حجم المستند الذي يمكن لـ Aspose.Page التعامل معه؟

A3: تم تصميم Aspose.Page للتعامل مع المستندات ذات الأحجام المختلفة، ولكن يوصى دائمًا بمراجعة الوثائق للحصول على تفاصيل محددة.

### س4: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page؟

 ج4: يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).

### س5: أين يمكنني طلب المساعدة أو التواصل مع مجتمع Aspose؟

 ج5: قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) لطرح الأسئلة والتفاعل مع المجتمع.