---
title: أضف نصًا باستخدام سلسلة Unicode إلى مستند XPS باستخدام Aspose.Page
linktitle: أضف نصًا بسلسلة Unicode إلى مستند XPS
second_title: Aspose.Page .NET API
description: اكتشف قوة Aspose.Page لـ .NET من خلال دليلنا خطوة بخطوة حول إضافة نص Unicode إلى مستندات XPS.
weight: 12
url: /ar/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# أضف نصًا باستخدام سلسلة Unicode إلى مستند XPS باستخدام Aspose.Page

## مقدمة

في مشهد تطوير .NET دائم التطور، تبرز Aspose.Page كأداة قوية للتعامل مع مستندات XPS. من بين ميزاته العديدة، تعد القدرة على إضافة نص باستخدام سلاسل Unicode إلى مستند XPS وظيفة قيمة. سيرشدك هذا الدليل المفصّل خطوة بخطوة خلال العملية، مما يضمن لك الاستفادة من هذه الإمكانية بفعالية.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

- فهم أساسي لتطوير .NET.
- تم تثبيت Visual Studio على جهازك.
-  Aspose.Page لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/page/net/).

## استيراد مساحات الأسماء

للبدء، تأكد من استيراد مساحات الأسماء الضرورية إلى مشروعك. سيوفر هذا الفئات والوظائف المطلوبة للعمل مع Aspose.Page. فيما يلي مساحات الأسماء الأساسية:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## الخطوة 1: إعداد المستند

أولاً، قم بإنشاء مستند XPS جديد حيث ستضيف نص Unicode. اتبع مقتطف الكود أدناه:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// قم بإنشاء مستند XPS جديد
XpsDocument doc = new XpsDocument();
```

## الخطوة 2: إضافة نص Unicode

الآن، دعونا نضيف نص Unicode إلى مستند XPS. يستخدم هذا المثال الخط Arial، ويضبط حجم الخط على 20، ويضع النص عند الإحداثيات (400f، 200f). سلسلة Unicode في هذه الحالة هي "TEN.rof SPX.esopsA". تحقق من مقتطف الكود أدناه:

```csharp
// إضافة نص
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## الخطوة 3: احفظ المستند

بمجرد إضافة نص Unicode، احفظ مستند XPS الناتج. ها هي الخطوة النهائية:

```csharp
// احفظ مستند XPS الناتج
doc.Save(dataDir + "AddTextRTL_out.xps");
```

تهانينا! لقد نجحت في إضافة نص Unicode إلى مستند XPS باستخدام Aspose.Page لـ .NET.

## خاتمة

في هذا البرنامج التعليمي، استكشفنا عملية إضافة نص Unicode إلى مستندات XPS باستخدام Aspose.Page لـ .NET. تفتح هذه الوظيفة الأبواب أمام إنشاء مستندات متنوعة وديناميكية داخل بيئة .NET.

## الأسئلة الشائعة

### س1: هل Aspose.Page متوافق مع أحدث أطر عمل .NET؟

ج1: نعم، يتم تحديث Aspose.Page بانتظام لضمان التوافق مع أحدث أطر عمل .NET.

### س2: هل يمكنني تخصيص نمط الخط وحجمه عند إضافة نص؟

ج2: بالتأكيد! يسمح لك رمز المثال المقدم بتخصيص نمط الخط وحجمه والسمات الأخرى بسهولة.

### س3: أين يمكنني العثور على وثائق إضافية لـ Aspose.Page؟

 ج3: يمكنك الرجوع إلى الوثائق[هنا](https://reference.aspose.com/page/net/) للحصول على معلومات وأمثلة شاملة.

### س 4: هل هناك أي موارد مجانية للبدء في استخدام Aspose.Page؟

 ج4: نعم، يمكنك استكشاف[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) لدعم المجتمع والمناقشات.

### س5: هل هناك نسخة تجريبية متاحة قبل إجراء عملية الشراء؟

 ج5: بالتأكيد! يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/) قبل إجراء عملية الشراء.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
