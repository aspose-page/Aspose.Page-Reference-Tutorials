---
date: 2026-03-21
description: تعلم كيفية ملء النص وإضافة نص إلى مستندات PS باستخدام Aspose.Page لـ .NET.
  دليل خطوة بخطوة مع أمثلة على الكود.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: كيفية تعبئة النص في مستندات PostScript (PS) باستخدام Aspose.Page
url: /ar/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية ملء النص في مستندات PostScript (PS) باستخدام Aspose.Page

## مقدمة

إذا كنت بحاجة إلى **كيفية ملء النص** داخل ملف PostScript (PS)، فإن Aspose.Page لـ .NET يجعل ذلك بسيطًا. سواءً كنت تولد تقارير أو فواتير أو رسومات مخصصة، فإن إضافة النص وتنسيقه يُعدّ متطلبًا أساسيًا. في هذا البرنامج التعليمي سنستعرض العملية بالكامل — من إعداد البيئة إلى حفظ مستند PS النهائي — حتى تتمكن من إضافة النص إلى ملفات PS بثقة في تطبيقات .NET الخاصة بك.

## إجابات سريعة
- **ماذا يعني “fill text”?** إنه يرسم الأحرف باستخدام فرشاة صلبة، يطلي الرموز مباشرةً على الصفحة.  
- **هل يمكنني استخدام خطوط مخصصة؟** نعم—يدعم Aspose.Page الخطوط المخصصة عبر ميزة `add custom font ps`.  
- **كيف أحفظ مستند PS؟** استدعِ `document.Save()` بعد إغلاق الصفحة؛ هذا يكتب الملف إلى القرص (`save ps document`).  
- **هل يتم دعم “fill and stroke text”؟** بالطبع؛ استخدم `FillAndStrokeText` لتطبيق كل من التعبئة والحد.  
- **ما إصدارات .NET المطلوبة؟** أي .NET Framework 4.5+ أو .NET Core/5/6+ runtime.

## ما هو “how to fill text” في مستند PS؟

يعني ملء النص طلاء الأحرف بلون صلب (أو فرشاة) دون حد. في PostScript، هذا يُشبه المشغل `fill`. يقوم Aspose.Page بتجريد ذلك إلى طرق سهلة الاستخدام مثل `FillText` و `FillAndStrokeText`.

## لماذا تستخدم Aspose.Page لإضافة custom font ps؟

- **دعم كامل للخطوط** – تعمل خطوط النظام والخطوط الخارجية TrueType/OpenType مباشرةً دون إعداد إضافي.  
- **تموضع دقيق** – يمكنك التحكم في إحداثيات X/Y، الحجم، والنمط.  
- **تنسيق غني** – اجمع بين التعبئات، الحدود، والأقلام للحصول على تأثيرات مثل “fill and stroke text”.  
- **متعدد المنصات** – يعمل على Windows و Linux و macOS باستخدام نفس الـ API.

## المتطلبات المسبقة

قبل البدء، تأكد من وجود:

- **Aspose.Page لـ .NET** – حمّل المكتبة من [توثيق Aspose.Page .NET](https://reference.aspose.com/page/net/).  
- **دليل المستندات** – مجلد على جهازك حيث ستوجد ملفات PS المصدرية والنهائية (المشار إليه بـ *Your Document Directory* في الشيفرة).  
- **مجلد الخطوط** – مجلد فرعي يحتوي على أي خطوط مخصصة تخطط لاستخدامها.

## استيراد مساحات الأسماء

أولاً، استورد مساحات الأسماء المطلوبة حتى يعرف المترجم أين يجد الفئات التي سنستخدمها:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## دليل خطوة بخطوة

### الخطوة 1: إنشاء تدفق إخراج لمستند PS  

نفتح `FileStream` سيحمل ملف PS المُولد، نُكوّن `PsSaveOptions` لتشير إلى مجلد الخطوط المخصص لدينا، ثم ننشئ كائنًا من `PsDocument`.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **نصيحة احترافية:** احتفظ بكتلة `using` لضمان إغلاق التدفق تلقائيًا، مما يُنهي ملف PS أيضًا (`save ps document`).

### الخطوة 2: ملء النص باستخدام خط نظام  

هنا نُظهر العملية الأساسية **كيفية ملء النص** باستخدام الخط المدمج *Times New Roman*.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### الخطوة 3: ملء النص باستخدام خط مخصص  

إذا كنت تحتاج إلى مظهر محدد، حمّل خطًا مخصصًا من مجلد الخطوط باستخدام `ExternalFontCache.FetchDrFont`. هذا يلبي متطلب **add custom font ps**.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### الخطوة 4: تحديد (Stroke) النص باستخدام خط نظام  

الرسم بالحد يرسم محيط الحرف. اجمعه مع التعبئة للحصول على تأثير “fill and stroke”.  

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **لماذا هذا مهم:** تُظهر استدعاءة `FillAndStrokeText` كيفية **ملء وتحديد النص** في خطوة واحدة، مما يمنحك تحكمًا طباعيًّا أغنى.

### الخطوة 5: تحديد النص باستخدام خط مخصص  

تقنية التحديد نفسها تعمل مع أي خط مخصص قمت بتحميله.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### الخطوة 6: إغلاق الصفحة وحفظ المستند  

الإنهاء بسيط: أغلق الصفحة الحالية واستدعِ `Save()` لكتابة ملف PS إلى القرص.

```csharp
document.ClosePage();
document.Save();
}
```

> **النتيجة:** ستجد `AddText_outPS.ps` في *Your Document Directory*، يحتوي على نص ملئ ومحدّد تم تصييره باستخدام الخطوط النظامية والمخصصة.

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| **لم يتم العثور على الخط المخصص** | تحقق من وجود ملف الخط (.ttf/.otf) في المجلد المشار إليه بـ `AdditionalFontsFolders`. |
| **النص يظهر في موضع خاطئ** | عدّل إحداثيات X/Y الممررة إلى `FillText`/`OutlineText`. تذكر أن PostScript يستخدم النقاط (1/72 بوصة). |
| **الألوان تبدو مختلفة** | تأكد من أنك تستخدم `SolidBrush` أو `Pen` مع قيم `Color` الصحيحة. |
| **المستند لا يتم حفظه** | تأكد من أن كتلة `using` تنتهي دون استثناءات وأن التطبيق يمتلك صلاحيات كتابة إلى المجلد المستهدف. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page مع مكتبات .NET أخرى؟**  
ج: نعم، يتكامل Aspose.Page بسلاسة مع مكونات .NET الأخرى، مما يتيح لك دمج مكتبات PDF أو الصور أو المخططات في نفس الحل.

**س: هل الخطوط المخصصة ضرورية لهذه العملية؟**  
ج: بينما تعمل خطوط النظام بشكل جيد، توفر الخطوط المخصصة حرية تصميم كاملة وتكون مفيدة عندما تكون الطباعة الخاصة بالعلامة التجارية مطلوبة.

**س: هل Aspose.Page مناسب لمعالجة المستندات على نطاق واسع؟**  
ج: بالتأكيد. المكتبة مُحسّنة لسيناريوهات الإنتاجية العالية ويمكنها معالجة آلاف ملفات PS بكفاءة.

**س: هل يمكنني تعديل موضع النص في مستند PS؟**  
ج: بالطبع—ما عليك سوى تغيير القيم الرقمية X/Y في استدعاءات `FillText` أو `OutlineText`.

**س: أين يمكنني طلب المساعدة بخصوص استفسارات Aspose.Page؟**  
ج: زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع والحصول على مساعدة خبراء.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-03-21  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET  
**المؤلف:** Aspose