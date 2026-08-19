---
date: 2026-03-03
description: تعلم كيفية تغيير حجم صور EPS في .NET باستخدام Aspose.Page – دليل خطوة
  بخطوة حول كيفية تغيير حجم EPS باستخدام النقاط أو البوصات أو المليمترات أو النسب
  المئوية.
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: كيفية تغيير حجم صور EPS باستخدام Aspose.Page لـ .NET
url: /ar/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تغيير حجم صور EPS باستخدام Aspose.Page لـ .NET

## المقدمة

هل تبحث عن **كيفية تغيير حجم صور EPS** بسهولة باستخدام Aspose.Page لـ .NET؟ هذا الدليل هو مرشدك الشامل لتعديل حجم صور EPS بسهولة باستخدام وحدات مختلفة مثل النقاط، والبوصات، والمليمترات، والنسب المئوية. يوفر Aspose.Page لـ .NET مجموعة قوية من الأدوات، وفي هذا الدرس سنرشدك خلال العملية خطوة بخطوة.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع تغيير حجم EPS؟** Aspose.Page for .NET  
- **ما الوحدات المدعومة؟** النقاط، البوصات، المليمترات، والنسب المئوية  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم – يلزم ترخيص تجاري  
- **هل يمكنني تغيير حجم ملفات متعددة في آن واحد؟** بالتأكيد – فقط قم بتكرار عبر الملفات  
- **هل .NET Core مدعوم؟** نعم، الـ API يعمل مع .NET Framework و .NET Core  

## ما هو تغيير حجم EPS؟

Encapsulated PostScript (EPS) هو تنسيق رسومات قائم على المتجهات يُستخدم عادةً في عمليات الطباعة وتصميم الجرافيك. تغيير حجم ملف EPS يغيّر صندوق الحدود دون تحويل الرسومات إلى نقطية، مما يحافظ على وضوحها عند أي مقياس.

## لماذا نعيد تحجيم صور EPS؟

- **الحفاظ على جودة الطباعة:** التحجيم المتجهي يحافظ على حدة الحواف.  
- **ملاءمة متطلبات التخطيط:** تعديل الأبعاد لتتناسب مع حجم الصفحة أو القماش.  
- **أتمتة عمليات الدفعات:** تغيير حجم العشرات من الملفات برمجياً في ثوانٍ.  

## المتطلبات المسبقة

قبل الغوص في سحر تغيير الحجم، تأكد من أن لديك المتطلبات المسبقة التالية جاهزة:

- مكتبة Aspose.Page لـ .NET: تأكد من تثبيت مكتبة Aspose.Page لـ .NET. يمكنك تنزيلها من [هنا](https://releases.aspose.com/page/net/).

- دليل المستندات: أنشئ دليلًا حيث ستحفظ ملف EPS الإدخالي والملفات المعاد تحجيمها.

الآن بعد أن أعددت كل شيء، دعنا نتابع لاستيراد المساحات الاسمية الضرورية ونغوص في الدليل خطوة بخطوة.

## استيراد المساحات الاسمية

في مشروع .NET الخاص بك، ابدأ باستيراد المساحات الاسمية الضرورية للعمل مع Aspose.Page. أضف الشيفرة التالية في بداية ملفك:

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

## كيفية تغيير حجم EPS بالنقاط

النقاط هي وحدة قياس قياسية في صناعة الطباعة. المثال أدناه يضاعف العرض والارتفاع الأصلي.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
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

## كيفية تغيير حجم EPS بالبوصات

البوصات تُستخدم كثيرًا من قبل مصممي الجرافيك عند إعداد الأصول للطباعة.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
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

## كيفية تغيير حجم EPS بالمليمترات

المليمترات شائعة في المناطق التي تستخدم النظام المتري.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
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

## كيفية تغيير حجم EPS باستخدام النسب المئوية

التغيير بناءً على النسبة المئوية يتيح لك تحجيم الصورة نسبةً إلى حجمها الأصلي.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
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

لا تتردد في دمج هذه الأساليب في مشروعك، وستتمكن من تغيير حجم صور EPS بسهولة. جرب وحدات مختلفة لتحقيق الأبعاد المطلوبة.

## المشكلات الشائعة والحلول
- **الملف غير موجود:** تحقق من أن `dataDir` يشير إلى المجلد الصحيح وأن `input.eps` موجود.  
- **حجم غير متوقع:** تذكر أن `Units.Percents` يتوقع قيمًا مثل 150 لـ 150 % من الحجم الأصلي.  
- **استثناء الترخيص:** إذا رأيت خطأ ترخيص، تأكد من تحميل ملف ترخيص Aspose.Page صالح قبل إنشاء `PsDocument`.

## الخاتمة

تهانينا! لقد أتقنت **كيفية تغيير حجم صور EPS** باستخدام Aspose.Page لـ .NET. هذه المكتبة القوية تفتح لك عالمًا من الإمكانات لتعديل الرسومات المتجهية. سواء كنت تصمم للطباعة أو للوسائط الرقمية، فإن Aspose.Page يمكّنك من تحقيق نتائج دقيقة ومخصصة.

## الأسئلة المتكررة

### س1: هل يمكنني تغيير حجم صور EPS متعددة في وقت واحد؟

A1: نعم، يمكنك التكرار عبر مجموعة من ملفات EPS وتطبيق أساليب تغيير الحجم وفقًا لذلك.

### س2: هل Aspose.Page متوافق مع صيغ صور أخرى؟

A2: يركز Aspose.Page أساسًا على صيغ PostScript و EPS. بالنسبة لصيغ صور أخرى، فكر في استخدام Aspose.Imaging.

### س3: هل هناك اعتبارات ترخيص للمشاريع التجارية؟

A3: نعم، تأكد من أن لديك ترخيصًا صالحًا. زر [هنا](https://purchase.aspose.com/buy) للحصول على تفاصيل الترخيص.

### س4: هل يمكنني تجربة Aspose.Page قبل الشراء؟

A4: بالتأكيد! يمكنك الحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

### س5: أين يمكنني طلب مساعدة إضافية أو مناقشة المشكلات؟

A5: زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع والحصول على المساعدة.

## الأسئلة المتداولة

**س: هل يعمل هذا الكود مع .NET Core 6؟**  
ج: نعم. الـ API متوافق مع .NET Framework 4.5+، .NET Core 3.1+، .NET 5+، و .NET 6+.

**س: كيف يمكنني الحفاظ على ملف تعريف اللون الأصلي؟**  
ج: طريقة `ResizeEps` لا تغير بيانات اللون؛ إنها فقط تغير صندوق الحدود.

**س: هل من الممكن تغيير حجم EPS دون تحميل الملف بالكامل في الذاكرة؟**  
ج: استخدام تدفق كما هو موضح يحافظ على استهلاك الذاكرة منخفضًا؛ يتم معالجة المستند مباشرة.

**س: هل يمكنني ربط عمليات تغيير حجم متعددة؟**  
ج: بالتأكيد. استدعِ `ResizeEps` بشكل متسلسل على نفس كائن `PsDocument`.

**س: ماذا يحدث للصور المدمجة داخل EPS؟**  
ج: يتم تحجيمها بشكل متناسب مع المحتوى المتجهي، مع الحفاظ على الجودة.

---

**آخر تحديث:** 2026-03-03  
**تم الاختبار مع:** Aspose.Page 24.12 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}