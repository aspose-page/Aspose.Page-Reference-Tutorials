---
date: 2026-01-10
description: تعلم كيفية دمج مستندات XPS باستخدام Aspose.Page لـ .NET. يوضح هذا الدليل
  خطوة بخطوة تقنيات معالجة الصفحات لتحقيق نتائج فعّالة.
linktitle: Manipulate Pages
second_title: Aspose.Page .NET API
title: دمج مستندات XPS باستخدام Aspose.Page لـ .NET
url: /ar/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# دمج مستندات XPS باستخدام Aspose.Page لـ .NET

## مقدمة

في هذا البرنامج التعليمي ستكتشف كيفية **دمج مستندات XPS** ومعالجة صفحاتها باستخدام مكتبة Aspose.Page في بيئة .NET. سواء كنت بحاجة إلى دمج تقارير متعددة في ملف XPS واحد أو إعادة ترتيب الصفحات للحصول على مخرجات مصقولة، يوضح لك هذا الدليل العملية خطوة بخطوة، مع شروحات واضحة وكود جاهز للتنفيذ.

## إجابات سريعة
- **ماذا يمكنني أن أفعل باستخدام Aspose.Page؟** دمج مستندات XPS، إدراج، إضافة أو إزالة الصفحات، وحفظ النتيجة.  
- **هل أحتاج إلى ترخيص للاختبار؟** ترخيص مؤقت متاح للتقييم.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.  
- **هل Visual Studio مطلوب؟** لا، أي بيئة تطوير تدعم C# تعمل، لكن يُنصح باستخدام Visual Studio.  
- **كم يستغرق الدمج من وقت؟** عادةً بضع ثوانٍ لملفات XPS ذات الحجم القياسي.

## ما هو دمج مستندات XPS؟
يعني دمج مستندات XPS أخذ صفحات من ملفين أو أكثر من ملفات XPS الموجودة ودمجها في مستند XPS واحد. هذا مفيد لإنشاء تقارير موحدة، تجميع أدلة متعددة الصفحات، أو إعداد حزم جاهزة للطباعة دون التحويل إلى تنسيق آخر.

## لماذا نستخدم Aspose.Page لـ .NET؟
توفر Aspose.Page **واجهة برمجة تطبيقات .NET صافية** تعمل مباشرة مع ملفات XPS—بدون الحاجة إلى أدوات خارجية أو مكونات طرف ثالث. تمنحك تحكمًا دقيقًا في ترتيب الصفحات، نقاط الإدراج، والحفاظ على المحتوى، مما يجعل عملية الدمج موثوقة وسريعة.

## المتطلبات المسبقة

- **Aspose.Page for .NET** – تحميل من [توثيق Aspose.Page لـ .NET](https://reference.aspose.com/page/net/).  
- **بيئة التطوير** – Visual Studio، Rider، أو أي بيئة تطوير تدعم C#.  
- **ملفات XPS الإدخال** – ثلاثة ملفات نموذجية (`input1.xps`, `input2.xps`, `input3.xps`) موجودة في مجلد معروف.

## استيراد مساحات الأسماء

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

تمنحك هذه المساحات الوصول إلى الفئات الأساسية لمستندات XPS، نماذج الصفحات، وأدوات الرسم الأساسية.

## الخطوة 1: تعيين دليل المستندات

```csharp
string dataDir = "Your Document Directory";
```

استبدل **Your Document Directory** بالمسار الكامل حيث تُخزن ملفات XPS، مثال: `C:\\Docs\\XpsFiles\\`.

## الخطوة 2: إنشاء مثيلات مستند XPS

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`، `doc2`، و`doc3` تمثل المستندات المصدر التي تريد دمجها.  
- `doc4` هو مستند XPS فارغ سيحمل النتيجة المدمجة.

## الخطوة 3: إدراج، إضافة، وإزالة الصفحات

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

إليك ما يفعله كل سطر:

1. **InsertPage(1, doc2.Page, false)** – يضع الصفحة الأولى من `doc2` في الموضع 1 داخل `doc4`.  
2. **AddPage(doc3.Page, false)** – يضيف الصفحة الأولى من `doc3` إلى نهاية `doc4`.  
3. **RemovePageAt(2)** – يزيل الصفحة الموجودة الآن في الفهرس 2 (مفيد لإزالة الصفحات غير المرغوب فيها).  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – يُدرج الصفحة الثالثة من `doc1` في الموضع 2، مكملًا عملية الدمج.

هذه العمليات توضح كيف يمكنك **دمج مستندات XPS** مع إعادة ترتيب أو حذف الصفحات حسب الحاجة.

## الخطوة 4: حفظ المستند المدمج

```csharp
doc4.Save(dataDir + "out.xps");
```

يتم كتابة ملف XPS المدمج النهائي (`out.xps`) إلى نفس الدليل. يمكنك الآن فتحه في أي عارض XPS أو معالجته أكثر باستخدام Aspose.Page.

## المشكلات الشائعة والحلول
- **File not found** – تحقق مرة أخرى من مسار `dataDir` وتأكد من وجود ملفات الإدخال.  
- **Invalid page index** – فهارس الصفحات تبدأ من 1؛ محاولة إدراج صفحة غير موجودة ستؤدي إلى استثناء.  
- **License errors** – استخدم ترخيصًا مؤقتًا أو كاملًا قبل النشر في بيئة الإنتاج.

## الأسئلة المتكررة

### س1: هل يمكنني تعديل الصفحات من مستندات XPS مختلفة؟
**ج1:** نعم، كما هو موضح في البرنامج التعليمي، يمكنك إدراج صفحات من مستندات XPS متعددة في مستند جديد.

### س2: كيف يمكنني إزالة صفحة معينة من مستند؟
**ج2:** استخدم طريقة `RemovePageAt`، مع تحديد فهرس الصفحة التي تريد إزالتها.

### س3: هل Aspose.Page متوافق مع Visual Studio؟
**ج3:** نعم، Aspose.Page متوافق تمامًا مع Visual Studio، مما يسهل دمجه في مشاريع .NET الخاصة بك.

### س4: هل هناك خيارات ترخيص متاحة؟
**ج4:** نعم، يمكنك استكشاف خيارات الترخيص والحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### س5: أين يمكنني الحصول على الدعم أو طرح الأسئلة؟
**ج5:** زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على الدعم والتفاعل مع المجتمع.

## أسئلة شائعة

**س: هل يمكنني دمج أكثر من ثلاثة ملفات XPS؟**  
ج: بالتأكيد. أنشئ مثيلات إضافية من `XpsDocument` واستخدم `InsertPage` أو `AddPage` بشكل متكرر لبناء مستند مدمج أكبر.

**س: هل يحافظ الدمج على التنسيق والرسومات الأصلية؟**  
ج: نعم. تقوم Aspose.Page بنسخ محتوى الصفحة بايتًا بايتًا، لذا يبقى النص، الصور، والرسومات المتجهة دون تغيير.

**س: كيف يمكنني إدراج صفحة في النهاية دون تحديد فهرس؟**  
ج: استخدم `AddPage(sourcePage, false)` الذي يضيف الصفحة إلى نهاية المستند.

**س: هل يمكن دمج مستندات XPS على خادم دون واجهة مستخدم؟**  
ج: الواجهة برمجة التطبيقات تعمل بالكامل بدون واجهة (headless)؛ يمكنك تشغيل نفس الكود في ASP.NET، Azure Functions، أو أي بيئة .NET على الخادم.

**س: ماذا لو كانت ملفات XPS محمية بكلمة مرور؟**  
ج: لا تدعم Aspose.Page حاليًا ملفات XPS المشفرة؛ يجب فك تشفيرها قبل الدمج.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Page for .NET 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}