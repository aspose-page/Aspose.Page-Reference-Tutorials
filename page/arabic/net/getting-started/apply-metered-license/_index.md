---
date: 2026-01-28
description: تعلم كيفية تحويل EPS إلى PNG باستخدام Aspose.Page لـ .NET وتطبيق ترخيص
  حسب الاستخدام لمعالجة المستندات بسلاسة.
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
title: تحويل EPS إلى PNG وتطبيق الترخيص القائم على الاستخدام مع Aspose.Page لـ .NET
url: /ar/net/getting-started/apply-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل EPS إلى PNG وتطبيق ترخيص مترّف مع Aspose.Page لـ .NET

## المقدمة

استفد من الإمكانات الكاملة لـ Aspose.Page لـ .NET عن طريق **تحويل EPS إلى PNG** وتطبيق ترخيص مترّف. يشرح هذا الدليل كل خطوة — من تحميل ملف EPS إلى حفظه كصورة PNG — حتى تتمكن من معالجة المستندات بكفاءة دون علامات مائية للتقييم.

## إجابات سريعة
- **ما الذي يغطيه هذا الدليل؟** تحويل ملفات EPS إلى صور PNG وتطبيق ترخيص مترّف مع Aspose.Page لـ .NET.  
- **هل أحتاج إلى ترخيص؟** نعم، يلزم ترخيص مترّف للاستخدام في الإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.  
- **كم تستغرق العملية؟** حوالي 10–15 دقيقة للتحويل الأساسي.  
- **هل يمكن تشغيله على Linux/macOS؟** بالتأكيد — Aspose.Page متعدد المنصات.

## ما هو “تحويل EPS إلى PNG”؟

يعني تحويل EPS إلى PNG تحويل ملف Encapsulated PostScript (EPS) القائم على المتجهات إلى صورة PNG نقطية. يكون ذلك مفيدًا عندما تحتاج إلى عرض أو تضمين الرسومات في صفحات الويب أو التقارير أو مكونات واجهة المستخدم التي لا تدعم EPS.

## لماذا استخدام ترخيص مترّف لتحويل EPS إلى صورة؟

يسمح لك الترخيص المترّف بالدفع فقط مقابل الصفحات التي تقوم بمعالجتها، وهو مثالي لأعباء العمل ذات الحجم المتغير. كما يزيل الشريط الأحمر للتقييم الذي يظهر عند استخدام النسخة التجريبية المجانية، مما يضمن مخرجات نظيفة للمستخدمين النهائيين.

## المتطلبات المسبقة

قبل الغوص في الخطوات، تأكد من توفر المتطلبات التالية:

- ترخيص Aspose.Page لـ .NET صالح: يمكنك الحصول عليه من [purchase.aspose.com](https://purchase.aspose.com/buy).
- مكتبة Aspose.Page مثبتة: راجع [documentation](https://reference.aspose.com/page/net/) للحصول على تعليمات التثبيت.
- بيئة تطوير .NET: تأكد من إعداد بيئة .NET تعمل على جهازك.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، استورد مساحات الأسماء اللازمة للوصول إلى وظائف Aspose.Page:

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

## كيفية تحويل EPS إلى PNG باستخدام ترخيص مترّف؟

فيما يلي دليل خطوة بخطوة يغطي كل ما تحتاج إلى معرفته.

### الخطوة 1: تعيين المفاتيح العامة والخاصة للترخيص المترّف

قم بتهيئة الفئة `Aspose.Page.Metered` وتعيين المفاتيح العامة والخاصة للترخيص المترّف. استبدل `<type public key here>` و `<type private key here>` بمفاتيحك الفعلية.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### الخطوة 2: تحميل ملف EPS وإنشاء المستند

حدد المسار إلى ملف EPS الخاص بك وأنشئ تدفقًا لقراءة محتواه. ثم، أنشئ مثيلًا من الفئة `PsDocument` من التدفق.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### الخطوة 3: تحويل EPS إلى صورة PNG

أنشئ `ImageDevice` لتحويل ملف EPS إلى صورة PNG. احفظ ملف EPS كصورة باستخدام `ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### الخطوة 4: استرجاع بايتات الصورة

احصل على بايتات الصورة، حيث تمثل كل مصفوفة بايت صفحة واحدة. في هذه الحالة لدينا صفحة واحدة.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### الخطوة 5: حفظ بايتات الصورة إلى ملف

احفظ بايتات الصورة إلى ملف، لضمان نجاح التحويل من EPS إلى PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### الخطوة 6: التحقق من الترخيص المترّف

تحقق بصريًا مما إذا تم تطبيق الترخيص المترّف بنجاح. إذا لم تحتوي الصورة الناتجة على رسالة التقييم الحمراء، فهذا يدل على أن الترخيص المترّف تم تطبيقه دون أي مشاكل.

الآن أنت جاهز للاستفادة من القدرات الكاملة لـ Aspose.Page لـ .NET مع ترخيص مترّف!

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| ما زال يظهر شريط التقييم الأحمر | الترخيص غير مُعيّن أو المفاتيح خاطئة | تحقق مرة أخرى من المفاتيح العامة/الخاصة وتأكد من استدعاء `SetMeteredKey` قبل أي معالجة للمستند |
| لم يتم إنشاء ملف إخراج | مسار `dataDir` غير صحيح أو أذونات الملف | تحقق من وجود الدليل وأن التطبيق لديه أذونات كتابة |
| لم يتم حفظ الصفحات المتعددة | تم كتابة الصفحة الأولى فقط | قم بالتكرار عبر `imagesBytes` واكتب كل مصفوفة إلى ملف PNG منفصل |

## الأسئلة المتكررة

**س: هل يمكنني استخدام الترخيص المترّف في خط أنابيب CI/CD؟**  
ج: نعم، يمكنك تخزين المفاتيح بأمان (مثلًا في متغيرات البيئة) واستدعاء `SetMeteredKey` أثناء عملية البناء.

**س: هل يدعم Aspose.Page الحفاظ على ملف تعريف اللون عند التحويل إلى PNG؟**  
ج: يحتفظ إخراج PNG بمعلومات اللون الأصلية، ولكن يمكنك تخصيصه أكثر عبر `ImageSaveOptions`.

**س: هل من الممكن تحويل EPS إلى صيغ نقطية أخرى (JPEG, BMP)؟**  
ج: بالتأكيد — فقط غير `ImageSaveOptions` إلى الصيغة المطلوبة.

**س: ما هو الحد الأقصى لحجم ملف EPS المدعوم؟**  
ج: يتعامل Aspose.Page مع الملفات الكبيرة، لكن استهلاك الذاكرة يزداد مع دقة الصورة. فكر في معالجة الصفحات بشكل فردي للوثائق الضخمة جدًا.

**س: كيف يمكنني برمجيًا استرجاع عدد الصفحات في ملف EPS؟**  
ج: استخدم `document.PagesCount` بعد تحميل `PsDocument`.

## الأسئلة المتكررة

### س1: كيف أحصل على ترخيص مترّف لـ Aspose.Page لـ .NET؟

ج1: زر [purchase.aspose.com](https://purchase.aspose.com/buy) للحصول على ترخيص صالح.

### س2: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page لـ .NET؟

ج2: راجع [Aspose.Page .NET](https://reference.aspose.com/page/net/) للحصول على وثائق شاملة.

### س3: هل هناك منتدى لمناقشات ودعم Aspose.Page؟

ج3: نعم، زر [forum](https://forum.aspose.com/c/page/39) للتفاعل مع المجتمع وطلب المساعدة.

### س4: هل يمكنني تجربة Aspose.Page لـ .NET قبل الشراء؟

ج4: بالتأكيد! الوصول إلى النسخة التجريبية المجانية عبر [here](https://releases.aspose.com/).

### س5: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ .NET؟

ج5: زر [temporary license/](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

---

**آخر تحديث:** 2026-01-28  
**تم الاختبار مع:** Aspose.Page 24.12 لـ .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}