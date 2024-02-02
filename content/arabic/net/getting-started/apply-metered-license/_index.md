---
title: قم بتطبيق الترخيص المقنن باستخدام Aspose.Page لـ .NET
linktitle: تطبيق الترخيص المقنن
second_title: Aspose.Page .NET API
description: استكشف التكامل السلس لـ Aspose.Page for .NET مع هذا الدليل التفصيلي خطوة بخطوة حول تطبيق ترخيص مقنن. تحسين معالجة المستندات دون عناء.
type: docs
weight: 10
url: /ar/net/getting-started/apply-metered-license/
---
## مقدمة

أطلق العنان للإمكانات الكاملة لـ Aspose.Page لـ .NET من خلال تطبيق ترخيص مقنن. سيرشدك هذا البرنامج التعليمي خلال عملية إعداد الترخيص المحدود وتطبيقه، مما يضمن الاستخدام السلس والأمثل لمكتبة .NET القوية هذه.

## المتطلبات الأساسية

قبل الغوص في الخطوات، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Page صالح لترخيص .NET: يمكنك الحصول عليه من[buy.aspose.com](https://purchase.aspose.com/buy).
-  تم تثبيت مكتبة Aspose.Page: ارجع إلى[توثيق](https://reference.aspose.com/page/net/) للحصول على تعليمات التثبيت.
- بيئة تطوير .NET: تأكد من إعداد بيئة .NET عاملة على جهازك.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، قم باستيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Page:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## الخطوة 1: قم بتعيين المفاتيح العامة والخاصة المقيسة

 تهيئة`Aspose.Page.Metered` فئة وتعيين المفاتيح العامة والخاصة المقننة. يستبدل`<type public key here>` و`<type private key here>` بمفاتيحك الفعلية.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## الخطوة 2: تحميل ملف EPS وإنشاء مستند

 حدد المسار إلى ملف EPS الخاص بك وقم بإنشاء دفق لقراءة محتواه. ثم قم بإنشاء مثيل لـ`PsDocument` فئة من الدفق.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## الخطوة 3: تحويل EPS إلى صورة PNG

 يخترع`ImageDevice` لتحويل ملف EPS إلى صورة PNG. احفظ ملف EPS كصورة باستخدام ملف`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## الخطوة 4: استرداد بايتات الصورة

احصل على بايتات الصورة، حيث يمثل كل مصفوفة بايت صفحة واحدة. في هذه الحالة لدينا صفحة واحدة.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## الخطوة 5: حفظ بايت الصورة إلى الملف

احفظ بايت الصورة في ملف، مما يضمن التحويل الناجح من EPS إلى PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## الخطوة 6: التحقق من الترخيص المقنن

تحقق بصريًا من تطبيق الترخيص المقنن بنجاح. إذا كانت الصورة الناتجة لا تحتوي على رسالة التقييم الحمراء، فهذا يشير إلى أن الترخيص المقنن مطبق دون أي مشاكل.

أنت الآن جاهز للاستفادة من الإمكانات الكاملة لـ Aspose.Page لـ .NET بترخيص محدود!

## خاتمة

لقد زودك هذا الدليل المفصّل خطوة بخطوة بالمعرفة اللازمة لتطبيق الترخيص المقنن بسلاسة باستخدام Aspose.Page for .NET. عزز قدرات معالجة المستندات لديك واستكشف الميزات الواسعة التي توفرها هذه المكتبة القوية.

## الأسئلة الشائعة

### س1: كيف يمكنني الحصول على ترخيص محدود لـ Aspose.Page لـ .NET؟

 ج1: زيارة[buy.aspose.com](https://purchase.aspose.com/buy) للحصول على ترخيص ساري المفعول.

### س٢: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page لـ .NET؟

 ج2: راجع[Aspose.Page.NET](https://reference.aspose.com/page/net/) للتوثيق الشامل.

### س3: هل يوجد منتدى للمناقشات والدعم في Aspose.Page؟

 ج3: نعم قم بالزيارة[المنتدى](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع وطلب المساعدة.

### س4: هل يمكنني تجربة Aspose.Page لـ .NET قبل الشراء؟

 ج4: بالتأكيد! الوصول إلى النسخة التجريبية المجانية في[هنا](https://releases.aspose.com/).

### س5: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟

 ج5: زيارة[ترخيص مؤقت/](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت.