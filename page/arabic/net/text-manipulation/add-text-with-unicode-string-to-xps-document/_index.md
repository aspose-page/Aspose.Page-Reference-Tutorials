---
date: 2026-03-21
description: تعلم كيفية إضافة نص يونيكود إلى مستند XPS باستخدام Aspose.Page لـ .NET.
  يوضح لك هذا الدليل كيفية إنشاء مستند XPS بلغة C# وإضافة نص باستخدام سلاسل يونيكود
  عبر Aspose.Page.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: كيفية إضافة نص يونيكود إلى مستند XPS باستخدام Aspose.Page
url: /ar/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة نص يونيكود إلى مستند XPS باستخدام Aspose.Page

## المقدمة

إذا كنت بحاجة إلى **how to add unicode** أحرف إلى ملف XPS، فقد وجدت المكان المناسب. في هذا البرنامج التعليمي سنستعرض الخطوات الدقيقة المطلوبة لإنشاء مستند XPS بأسلوب **create XPS document C#**‑style باستخدام Aspose.Page لـ .NET ونظهر قدرة **aspose page add text** مع سلسلة يونيكود. في النهاية ستحصل على مستند XPS يعمل بالكامل ويعرض نص يونيكود من اليمين إلى اليسار (RTL) بشكل صحيح.

## إجابات سريعة
- **What does the tutorial cover?** إضافة نص يونيكود إلى مستند XPS باستخدام Aspose.Page لـ .NET.  
- **Which language is used?** C# (متوافق مع .NET Framework و .NET Core).  
- **Do I need a license?** النسخة التجريبية المجانية تعمل للتطوير؛ يلزم الحصول على ترخيص تجاري للإنتاج.  
- **Can I change the font or size?** نعم – المثال يستخدم Arial 20 pt، ولكن أي خط مثبت يعمل.  
- **Is RTL support included?** ضبط `BidiLevel = 1` يتيح عرض من اليمين إلى اليسار لسلاسل يونيكود.

## ما هو “how to add unicode” في XPS؟

إضافة نص يونيكود يعني إدراج أحرف من أي لغة — العربية، العبرية، الصينية، إلخ — في مستند XPS. تتعامل فئة `XpsGlyphs` في Aspose.Page مع وضع الحروف على مستوى منخفض، بينما تتحكم خاصية `BidiLevel` في اتجاه النص للغات من اليمين إلى اليسار.

## لماذا تستخدم Aspose.Page لإضافة نص؟

- **Full .NET integration** – يعمل مع .NET Framework، .NET Core، .NET 5/6+.  
- **No external dependencies** – شفرة مُدارة خالصة، بدون تفاعل COM.  
- **Rich typography support** – الخطوط، الأنماط، الألوان، والنص ثنائي الاتجاه.  
- **High performance** – ينشئ ويحفظ ملفات XPS بسرعة، مثالي لإنشاء الخادم.

## المتطلبات المسبقة

- معرفة أساسية بـ C# وتطوير .NET.  
- Visual Studio (أي نسخة حديثة).  
- مكتبة Aspose.Page لـ .NET – حمّلها من [here](https://releases.aspose.com/page/net/).

## استيراد مساحات الأسماء

أولاً، استورد مساحات الأسماء التي تمنحك الوصول إلى نموذج XPS وأدوات الرسم.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## الخطوة 1: إعداد المستند – create XPS document C#

أنشئ مستند XPS جديد سيستضيف نص يونيكود.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## الخطوة 2: إضافة نص يونيكود – aspose page add text

الآن نضيف سلسلة يونيكود الفعلية. في هذا المثال نستخدم خط Arial بحجم 20، ونضع النص عند (400 f, 200 f). الخاصية `BidiLevel` بقيمة 1 تخبر المُعالج بمعاملة السلسلة من اليمين إلى اليسار.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## الخطوة 3: حفظ المستند

أخيرًا، احفظ ملف XPS على القرص.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

تهانينا! لقد نجحت في إضافة نص **how to add unicode** إلى مستند XPS باستخدام Aspose.Page لـ .NET.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| النص يظهر مشوشًا | الخط لا يدعم نطاق يونيكود | استخدم خطًا يحتوي على الحروف المطلوبة (مثل Arial Unicode MS). |
| النص RTL لا يزال من اليسار إلى اليمين | `BidiLevel` غير مضبوط أو مضبوط على 0 | تأكد من `glyphs.BidiLevel = 1;` للنصوص RTL. |
| الملف غير محفوظ | مسار `dataDir` غير صالح | تحقق من وجود الدليل وأن التطبيق لديه أذونات الكتابة. |

## الأسئلة المتكررة

**س: هل Aspose.Page متوافق مع أحدث أطر .NET؟**  
ج: نعم، يتم تحديث Aspose.Page بانتظام لدعم .NET Framework، .NET Core، و .NET 5/6+.

**س: هل يمكنني تخصيص نمط الخط وحجمه عند إضافة النص؟**  
ج: بالتأكيد! تسمح لك طريقة `AddGlyphs` بتحديد أي عائلة خط، حجم، و `FontStyle` تحتاجه.

**س: أين يمكنني العثور على وثائق إضافية لـ Aspose.Page؟**  
ج: يمكنك الرجوع إلى الوثائق [here](https://reference.aspose.com/page/net/) للحصول على تفاصيل شاملة حول الـ API.

**س: هل هناك موارد مجانية للبدء مع Aspose.Page؟**  
ج: نعم، استكشف منتدى المجتمع على [Aspose.Page forum](https://forum.aspose.com/c/page/39) للحصول على نصائح، أمثلة، ودعم من الأقران.

**س: هل هناك نسخة تجريبية متاحة قبل الشراء؟**  
ج: بالتأكيد! حمّل النسخة التجريبية المجانية من [here](https://releases.aspose.com/) لتقييم المكتبة.

**آخر تحديث:** 2026-03-21  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}