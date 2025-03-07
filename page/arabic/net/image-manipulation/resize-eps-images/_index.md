---
title: قم بتغيير حجم صور EPS باستخدام Aspose.Page لـ .NET
linktitle: تغيير حجم صور EPS
second_title: Aspose.Page .NET API
description: استكشف العملية السلسة لتغيير حجم صور EPS في .NET باستخدام Aspose.Page. حقق الدقة في النقاط والبوصات والمليمترات والنسب المئوية دون عناء.
weight: 11
url: /ar/net/image-manipulation/resize-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بتغيير حجم صور EPS باستخدام Aspose.Page لـ .NET

## مقدمة

هل تتطلع إلى تغيير حجم صور EPS بسهولة باستخدام Aspose.Page لـ .NET؟ هذا البرنامج التعليمي هو دليلك الشامل للتعامل بسهولة مع حجم صور EPS بوحدات مختلفة مثل النقاط والبوصات والمليمترات والنسب المئوية. يوفر Aspose.Page for .NET مجموعة قوية من الأدوات، وفي هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل الغوص في سحر تغيير الحجم، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Page لمكتبة .NET: تأكد من تثبيت Aspose.Page لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/page/net/).

- دليل المستندات: قم بإنشاء دليل حيث يمكنك تخزين ملف EPS المدخل وإخراج الملفات التي تم تغيير حجمها.

الآن بعد أن قمت بإعداد كل شيء، فلنتابع استيراد مساحات الأسماء الضرورية ونتعمق في الدليل خطوة بخطوة.

## استيراد مساحات الأسماء

في مشروع .NET الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية للعمل مع Aspose.Page. أضف الكود التالي في بداية ملفك:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## الخطوة 1: تغيير الحجم بالنقاط

لنبدأ بتغيير حجم صورة EPS بالنقاط. النقاط هي وحدة قياس قياسية في صناعة الطباعة.

```csharp
public static void ResizeInPoints()
{
    // دليل المستندات الخاص بك
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## الخطوة 2: تغيير الحجم بالبوصة

الآن، دعونا نغير حجم صورة EPS بالبوصة، وهي وحدة شائعة تستخدم في التصميم الجرافيكي.

```csharp
public static void ResizeInInches()
{
    // دليل المستندات الخاص بك
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## الخطوة 3: تغيير الحجم بالملليمتر

الآن، دعونا نغير حجم صورة EPS بالملليمتر، وهي وحدة أخرى تستخدم على نطاق واسع في التصميم والطباعة.

```csharp
public static void ResizeInMillimeters()
{
    // دليل المستندات الخاص بك
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## الخطوة 4: تغيير الحجم بالنسب المئوية

أخيرًا، دعنا نغير حجم صورة EPS باستخدام النسب المئوية، مما يوفر أسلوبًا مرنًا لضبط حجم الصورة.

```csharp
public static void ResizeInPercents()
{
    // دليل المستندات الخاص بك
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

لا تتردد في دمج هذه الأساليب في مشروعك، وسوف تتمكن من تغيير حجم صور EPS دون عناء. تجربة مع وحدات مختلفة لتحقيق الأبعاد المطلوبة.

## خاتمة

تهانينا! لقد أتقنت فن تغيير حجم صور EPS باستخدام Aspose.Page لـ .NET. تفتح هذه المكتبة القوية عالمًا من الإمكانيات لمعالجة الرسومات المتجهة. سواء كنت تصمم للوسائط المطبوعة أو الرقمية، فإن Aspose.Page يمكّنك من تحقيق نتائج دقيقة ومخصصة.

## الأسئلة الشائعة

### Q1: هل يمكنني تغيير حجم صور EPS متعددة في وقت واحد؟

A1: نعم، يمكنك التكرار عبر مجموعة من ملفات EPS، وتطبيق أساليب تغيير الحجم وفقًا لذلك.

### س2: هل Aspose.Page متوافق مع تنسيقات الصور الأخرى؟

A2: يركز Aspose.Page بشكل أساسي على تنسيقات PostScript وEPS. بالنسبة لتنسيقات الصور الأخرى، فكر في استخدام Aspose.Imaging.

### س3: هل هناك اعتبارات ترخيصية للمشاريع التجارية؟

 ج3: نعم، تأكد من أن لديك ترخيصًا صالحًا. يزور[هنا](https://purchase.aspose.com/buy) للحصول على تفاصيل الترخيص.

### س4: هل يمكنني تجربة Aspose.Page قبل الشراء؟

 ج4: بالتأكيد! يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).

### س5: أين يمكنني طلب مساعدة إضافية أو مناقشة المشكلات؟

 ج5: قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع والحصول على المساعدة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
