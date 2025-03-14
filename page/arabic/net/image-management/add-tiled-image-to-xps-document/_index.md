---
title: أضف صورة متجانبة إلى مستند XPS باستخدام Aspose.Page لـ .NET
linktitle: إضافة صورة متجانبة إلى مستند XPS
second_title: Aspose.Page .NET API
description: استكشف إضافة الصور المتجانبة إلى مستندات XPS دون عناء باستخدام Aspose.Page for .NET. تعزيز المظهر المرئي وإنشاء مستندات مذهلة.
weight: 12
url: /ar/net/image-management/add-tiled-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# أضف صورة متجانبة إلى مستند XPS باستخدام Aspose.Page لـ .NET

## مقدمة

هل تتطلع إلى تحسين مستندات XPS الخاصة بك عن طريق إضافة صور متجانبة جذابة بصريًا؟ يعمل Aspose.Page for .NET على تمكين المطورين من تحقيق ذلك بسلاسة. في هذا الدليل التفصيلي خطوة بخطوة، سنرشدك خلال عملية إضافة صورة متجانبة إلى مستند XPS باستخدام Aspose.Page لـ .NET.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Page لـ .NET: تأكد من تثبيت مكتبة Aspose.Page. يمكنك العثور على وثائق مفصلة وتنزيل المكتبة[هنا](https://reference.aspose.com/page/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET المفضلة لديك، مثل Visual Studio.

## استيراد مساحات الأسماء

للبدء، قم باستيراد مساحات الأسماء الضرورية إلى مشروعك. وهذا يضمن أن لديك إمكانية الوصول إلى الفئات والأساليب المطلوبة للعمل مع Aspose.Page. أضف مساحات الأسماء التالية في بداية التعليمات البرمجية الخاصة بك:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

الآن، دعونا نقسم المثال إلى خطوات متعددة.

## الخطوة 1: تحديد دليل المستندات

```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
```

تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي الذي تريد حفظ مستند XPS الخاص بك فيه.

## الخطوة 2: إنشاء مستند XPS جديد

```csharp
// قم بإنشاء مستند XPS جديد
XpsDocument doc = new XpsDocument();
```

 قم بإنشاء مثيل لمستند XPS جديد باستخدام الملف`XpsDocument` فصل.

## الخطوة 3: إضافة صورة متجانبة

```csharp
// صورة البلاط
// ملأ ImageBrush المستطيل في الجزء العلوي الأيمن أدناه
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

تضيف هذه الخطوة صورة متجانبة إلى مستند XPS. اضبط الإحداثيات ومسار ملف الصورة وفقًا لمتطلباتك.

## الخطوة 4: احفظ مستند XPS الناتج

```csharp
// احفظ مستند XPS الناتج
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

احفظ مستند XPS المعدل في الدليل المحدد.

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية إضافة صورة متجانبة إلى مستند XPS باستخدام Aspose.Page لـ .NET. تتيح لك هذه الميزة البسيطة والقوية تحسين المظهر المرئي لمستنداتك دون عناء.

## الأسئلة الشائعة

### س1: هل Aspose.Page متوافق مع كافة بيئات تطوير .NET؟

A1: نعم، تم تصميم Aspose.Page للعمل بسلاسة مع بيئات تطوير .NET المتنوعة، بما في ذلك Visual Studio.

### س2: هل يمكنني ضبط عتامة الصورة المتجانبة؟

ج2: بالتأكيد، كما هو موضح في المثال، يمكنك ضبط عتامة المستطيل المعبأ باستخدام`Opacity` ملكية.

### س3: هل هناك أوضاع تجانب أخرى متوفرة في Aspose.Page لـ .NET؟

 A3: نعم، يوفر Aspose.Page أوضاعًا مختلفة للتجانب. في هذا البرنامج التعليمي، استخدمنا`XpsTileMode.Tile`، ولكن يمكنك استكشاف خيارات أخرى في الوثائق.

### س٤: كيف يمكنني التعامل مع التراخيص المؤقتة لـ Aspose.Page؟

 ج4: راجع[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) صفحة على موقع Aspose للحصول على إرشادات حول الحصول على التراخيص المؤقتة وتنفيذها.

### س5: أين يمكنني طلب المساعدة أو التواصل مع مجتمع Aspose.Page؟

 ج5: قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع وطرح الأسئلة وإيجاد الحلول.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
