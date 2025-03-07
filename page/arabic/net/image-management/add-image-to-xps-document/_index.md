---
title: إضافة صورة إلى مستند XPS باستخدام Aspose.Page لـ .NET
linktitle: إضافة صورة إلى مستند XPS
second_title: Aspose.Page .NET API
description: استكشف التكامل السلس للصور في مستندات XPS باستخدام Aspose.Page لـ .NET. اتبع دليلنا خطوة بخطوة للحصول على تجربة تطوير سلسة.
weight: 11
url: /ar/net/image-management/add-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة صورة إلى مستند XPS باستخدام Aspose.Page لـ .NET

## مقدمة

في عالم تطوير .NET، يعد دمج الصور في مستندات XPS متطلبًا شائعًا. يعمل Aspose.Page for .NET على تبسيط هذه العملية، حيث يقدم مجموعة أدوات قوية لمعالجة مستندات XPS وتحسينها بسهولة. سيرشدك هذا البرنامج التعليمي خلال خطوات إضافة صورة إلى مستند XPS باستخدام Aspose.Page لـ .NET.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Page for .NET Library: قم بتنزيل المكتبة وتثبيتها من[Aspose.Page .NET الوثائق](https://reference.aspose.com/page/net/).

2. بيئة التطوير: قم بإعداد بيئة تطوير .NET، مثل Visual Studio.

3. صورة نموذجية: احصل على ملف صورة نموذجي (على سبيل المثال، "QL_logo_color.tif") الذي تريد إضافته إلى مستند XPS.

## استيراد مساحات الأسماء

ابدأ باستيراد مساحات الأسماء الضرورية إلى مشروع .NET الخاص بك. تعد مساحات الأسماء هذه حيوية لاستخدام الميزات التي يوفرها Aspose.Page لـ .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## الخطوة 1: قم بتعيين دليل المستندات

ابدأ بتحديد المسار إلى دليل المستند الخاص بك. تضمن هذه الخطوة أن مشروعك يعرف مكان تحديد موقع الملفات وحفظها.

```csharp
// البداية:1
string dataDir = "Your Document Directory";
// النهاية:1
```

## الخطوة 2: إنشاء مستند XPS

قم بإنشاء مستند XPS جديد باستخدام Aspose.Page لـ .NET.

```csharp
// البداية:1
XpsDocument doc = new XpsDocument();
// النهاية:1
```

## الخطوة 3: إضافة صورة إلى مستند XPS

الآن، دعونا نضيف الصورة إلى مستند XPS. في هذا المثال، سنستخدم صورة نموذجية باسم "QL_logo_color.tif".

```csharp
// البداية:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// النهاية:1
```

## الخطوة 4: احفظ مستند XPS الناتج

احفظ مستند XPS مع الصورة المضافة.

```csharp
// البداية:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// النهاية:1
```

لقد نجحت الآن في إضافة صورة إلى مستند XPS باستخدام Aspose.Page لـ .NET!

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية الاستفادة من Aspose.Page لـ .NET لدمج الصور بسلاسة في مستندات XPS. يضمن هذا الدليل التفصيلي عملية تكامل سلسة، مما يعزز قدرات تطوير .NET لديك.

## الأسئلة الشائعة

### س1: هل يتوافق Aspose.Page for .NET مع أحدث إصدارات .NET Framework؟

 ج1: تم تصميم Aspose.Page for .NET ليكون متوافقًا مع نطاق واسع من إصدارات .NET Framework، بما في ذلك الإصدارات الأحدث. الرجوع إلى[توثيق](https://reference.aspose.com/page/net/) للحصول على تفاصيل محددة.

### س2: هل يمكنني استخدام Aspose.Page لـ .NET في بيئتي Windows وLinux؟

ج2: نعم، Aspose.Page for .NET مستقل عن النظام الأساسي، مما يجعله مناسبًا للاستخدام في بيئات Windows وLinux.

### س3: هل توجد أي خيارات ترخيص لـ Aspose.Page لـ .NET؟

 ج3: نعم، يمكنك استكشاف خيارات الترخيص وإجراء عملية شراء[هنا](https://purchase.aspose.com/buy).

### س4: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page لـ .NET؟

 ج4: نعم، يمكنك تجربة Aspose.Page لـ .NET مجانًا عن طريق الوصول إلى[تجربة مجانية](https://releases.aspose.com/).

### س5: أين يمكنني طلب المساعدة أو التواصل مع مجتمع Aspose.Page for .NET؟

 ج5: قم بزيارة[Aspose.Page لمنتدى .NET](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع والحصول على الدعم.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
