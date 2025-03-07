---
title: قم بتغيير القيم باستخدام Aspose.Page لـ .NET
linktitle: تغيير القيم
second_title: Aspose.Page .NET API
description: معالجة ملف EPS الرئيسي باستخدام Aspose.Page لـ .NET. قم بتغيير قيم بيانات تعريف XMP بسهولة.
weight: 17
url: /ar/net/eps-metadata-management/modify-eps-metadata-change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بتغيير القيم باستخدام Aspose.Page لـ .NET

## مقدمة

في العالم الديناميكي لمعالجة المستندات، تبرز Aspose.Page for .NET كأداة قوية توفر للمطورين القدرة على التعامل مع ملفات EPS دون عناء. في هذا البرنامج التعليمي، سوف نتعمق في عملية تغيير القيم داخل ملفات EPS باستخدام Aspose.Page لـ .NET. سواء كنت مطورًا متمرسًا أو مبتدئًا فضوليًا، فإن هذا الدليل خطوة بخطوة سيزودك بالمهارات اللازمة لتعديل بيانات تعريف XMP بكفاءة في ملفات EPS الخاصة بك.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

### 1. Aspose.Page لمكتبة .NET

تأكد من تثبيت مكتبة Aspose.Page for .NET في بيئة التطوير الخاصة بك. إذا لم يكن الأمر كذلك، يمكنك تنزيله[هنا](https://releases.aspose.com/page/net/).

### 2. دليل المستندات

قم بإعداد دليل لمستنداتك. سيكون هذا هو الموقع الذي يتم فيه تخزين ملفات EPS الخاصة بك.

الآن بعد أن قمنا بفرز متطلباتنا الأساسية، دعنا ننتقل إلى الخطوات الحاسمة التالية.

## استيراد مساحات الأسماء

في أي مشروع .NET، من الضروري استيراد مساحات الأسماء الضرورية للاستفادة من وظائف Aspose.Page. وإليك كيف يمكنك القيام بذلك:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## الخطوة 1: تهيئة دفق إدخال ملف EPS

```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// تهيئة دفق إدخال ملف EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## الخطوة 2: إنشاء مثيل PsDocument من الدفق

```csharp
//قم بإنشاء مثيل PsDocument من الدفق
PsDocument document = new PsDocument(psStream);
```

الآن بعد أن جهزنا المسرح، فلننتقل إلى جوهر البرنامج التعليمي الخاص بنا - وهو تغيير قيم بيانات تعريف XMP داخل ملف EPS.

## الخطوة 3: احصل على بيانات تعريف XMP

```csharp
// احصل على بيانات تعريف XMP. إذا كان ملف EPS لا يحتوي على بيانات تعريف XMP، فسنحصل على ملف جديد مملوء بالقيم من تعليقات بيانات تعريف PS (%%Creator، %%CreateDate، %%Title، وما إلى ذلك)
XmpMetadata xmp = document.GetXmpMetadata();
```

## الخطوة 4: تعديل قيم بيانات تعريف XMP

الآن، دعونا نغير بعض القيم الأساسية في بيانات تعريف XMP:

### الخطوة 4.1: تغيير قيمة ModifyDate

```csharp
// تغيير قيمة تاريخ التعديل
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### الخطوة 4.2: تغيير قيمة المنشئ

```csharp
// تغيير قيمة المنشئ
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### الخطوة 4.3: تغيير قيمة العنوان

```csharp
// تغيير قيمة العنوان
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

بعد إجراء هذه التغييرات، دعنا ننتقل إلى الخطوة الأخيرة - حفظ ملف EPS المعدل.

## الخطوة 5: احفظ ملف EPS مع بيانات تعريف XMP التي تم تغييرها

### الخطوة 5.1: إنشاء دفق الإخراج

```csharp
// إنشاء دفق الإخراج
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### الخطوة 5.2: حفظ ملف EPS

```csharp
// حفظ ملف EPS
document.Save(outPsStream);
```

أخيرًا، أغلق دفق الإدخال:

```csharp
finally
{
    psStream.Close();
}
```

تهانينا! لقد نجحت في تعديل قيم بيانات تعريف XMP في ملف EPS باستخدام Aspose.Page لـ .NET.

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا العملية السلسة لتغيير القيم داخل ملفات EPS باستخدام Aspose.Page لـ .NET. كمطور، لديك الآن أداة قوية تحت تصرفك لمعالجة المستندات بكفاءة.

## الأسئلة الشائعة

### س1: هل يمكنني استخدام Aspose.Page لـ .NET مع تنسيقات ملفات أخرى؟

A1: يركز Aspose.Page بشكل أساسي على معالجة ملف EPS. للحصول على تنسيقات أخرى، استكشف مجموعة منتجات Aspose المتنوعة.

### س2: هل هناك نسخة تجريبية متاحة؟

 ج2: نعم، يمكنك تجربة Aspose.Page لـ .NET مع توفر الإصدار التجريبي المجاني[هنا](https://releases.aspose.com/).

### س3: أين يمكنني العثور على الوثائق التفصيلية؟

 ج3: يمكن العثور على الوثائق الشاملة[هنا](https://reference.aspose.com/page/net/).

### س4: كيف يمكنني الحصول على ترخيص مؤقت؟

 ج4: يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).

### س5: هل يمكنني شراء Aspose.Page لـ .NET؟

 ج5: بالتأكيد! قم بزيارة صفحة الشراء[هنا](https://purchase.aspose.com/buy) لخيارات الترخيص.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
