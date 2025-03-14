---
title: قم بإزالة الصفحة من مستند XPS باستخدام Aspose.Page لـ .NET
linktitle: إزالة الصفحة من مستند XPS
second_title: Aspose.Page .NET API
description: استكشف برنامجًا تعليميًا شاملاً حول إزالة الصفحات من مستندات XPS باستخدام Aspose.Page لـ .NET. تعرف على العملية خطوة بخطوة والمتطلبات الأساسية والأسئلة الشائعة للتعامل السلس مع المستندات.
weight: 12
url: /ar/net/page-manipulation/remove-page-from-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بإزالة الصفحة من مستند XPS باستخدام Aspose.Page لـ .NET

## مقدمة

في هذا البرنامج التعليمي، سنستكشف عملية إزالة صفحة من مستند XPS باستخدام Aspose.Page لـ .NET. Aspose.Page هي مكتبة قوية تمكن مطوري .NET من العمل مع مستندات XPS (مواصفات ورق XML) بسلاسة. إذا وجدت نفسك في موقف تحتاج فيه إلى إزالة صفحة معينة من مستند XPS الخاص بك، فسيرشدك هذا الدليل خطوة بخطوة خلال العملية.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Page لمكتبة .NET: تأكد من تثبيت مكتبة Aspose.Page. يمكنك تنزيله من[Aspose.Page لوثائق .NET](https://reference.aspose.com/page/net/).

- بيئة تطوير .NET: قم بإعداد بيئة تطوير .NET عاملة على جهازك.

- نموذج مستند XPS: قم بإعداد نموذج مستند XPS الذي ستستخدمه لاختبار عملية الإزالة.

## استيراد مساحات الأسماء

في تطبيق .NET الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية للعمل مع Aspose.Page. أضف الأسطر التالية إلى أعلى ملف التعليمات البرمجية الخاص بك:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## الخطوة 1: قم بتعيين دليل المستندات

```csharp
// البداية:3
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// النهاية:3
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي لدليل المستندات الخاص بك.

## الخطوة 2: إنشاء مستند XPS جديد

```csharp
// البداية:4
// قم بإنشاء مستند XPS جديد
XpsDocument doc = new XpsDocument(dataDir + "Sample.xps");
// النهاية:4
```

يقوم هذا الرمز بتهيئة مستند XPS جديد استنادًا إلى الملف النموذجي المقدم.

## الخطوة 3: إزالة الصفحة

```csharp
// البداية:5
// قم بإزالة الصفحة الأولى (في الفهرس 1).
doc.RemovePageAt(1);
// النهاية:5
```

حدد فهرس الصفحة التي تريد إزالتها. في هذا المثال، تقوم التعليمات البرمجية بإزالة الصفحة الموجودة في الفهرس 1.

## الخطوة 4: احفظ مستند XPS الناتج

```csharp
// البداية:6
// احفظ مستند XPS الناتج
doc.Save(dataDir + "Sample_out.xps");
// النهاية:6
```

احفظ مستند XPS المعدل بالصفحة التي تمت إزالتها.

## خاتمة

تهانينا! لقد نجحت في إزالة صفحة من مستند XPS باستخدام Aspose.Page لـ .NET. يمكن دمج هذه العملية المباشرة بسلاسة في تطبيقات .NET الخاصة بك، مما يوفر المرونة في إدارة مستندات XPS.

## الأسئلة الشائعة

### س1: هل يمكنني إزالة صفحات متعددة مرة واحدة باستخدام Aspose.Page لـ .NET؟

A1: نعم، يمكنك تعديل التعليمات البرمجية لإزالة صفحات متعددة عن طريق الاتصال بـ`RemovePageAt` الطريقة عدة مرات

### س2: هل Aspose.Page متوافق مع أحدث إصدار من .NET Framework؟

ج2: يتم تحديث Aspose.Page بانتظام لضمان التوافق مع أحدث إصدارات إطار عمل .NET.

### س3: هل يمكنني استخدام Aspose.Page للتطبيقات التجارية؟

 ج3: نعم، يمكنك استخدام Aspose.Page لأغراض تجارية. يزور[Aspose.Purchase](https://purchase.aspose.com/buy) للحصول على تفاصيل الترخيص.

### س4: أين يمكنني العثور على دعم ومناقشات إضافية حول Aspose.Page؟

 ج4: انضم إلى[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع وطلب المساعدة.

### س5: هل أحتاج إلى ترخيص مؤقت لاختبار Aspose.Page؟

 ج5: نعم يمكنك الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) لأغراض تجريبية.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
