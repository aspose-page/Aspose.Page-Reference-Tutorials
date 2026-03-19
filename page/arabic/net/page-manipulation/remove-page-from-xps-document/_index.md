---
date: 2026-03-19
description: تعلم كيفية **إزالة صفحة XPS** من المستندات و**حذف الصفحة عند الفهرس**
  باستخدام Aspose.Page لـ .NET – دليل شامل خطوة بخطوة مع المتطلبات المسبقة، عينات
  الكود، والأسئلة الشائعة.
linktitle: Remove Page from XPS Document
second_title: Aspose.Page .NET API
title: إزالة صفحة من مستند XPS باستخدام Aspose.Page لـ .NET
url: /ar/net/page-manipulation/remove-page-from-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إزالة صفحة من مستند XPS باستخدام Aspose.Page لـ .NET

## مقدمة

إذا كنت بحاجة إلى **remove page xps** الملفات برمجيًا، فإن Aspose.Page لـ .NET يوفر لك طريقة نظيفة وموثوقة للقيام بذلك. في هذا البرنامج التعليمي سنستعرض الخطوات الدقيقة المطلوبة لحذف صفحة محددة من مستند XPS، نشرح لماذا هذه العملية مهمة، ونظهر لك كيفية حفظ الملف المحدث مرة أخرى على القرص.

## إجابات سريعة
- **ماذا يعني “remove page xps”?** يشير إلى حذف صفحة واحدة من مستند XPS (XML Paper Specification).  
- **أي طريقة تحذف صفحة؟** استخدم `RemovePageAt(index)` حيث يكون الفهرس يبدأ من الصفر.  
- **هل يمكنني حذف صفحة في أي موضع؟** نعم – يمكنك **delete page at index** 0، 1، 2، إلخ، حسب الحاجة.  
- **هل أحتاج إلى ترخيص لـ Aspose.Page؟** يلزم ترخيص مؤقت للاختبار؛ ويحتاج الترخيص الكامل للإنتاج.  
- **هل الكود متوافق مع .NET 6؟** بالتأكيد – يدعم Aspose.Page .NET Framework و .NET Core و .NET 5/6.

## ما هو “remove page xps”؟
إزالة صفحة من مستند XPS يعني استخراج إحدى صفحات المستند مع الحفاظ على باقي المحتوى والتخطيط والبيانات الوصفية. هذه العملية مفيدة عندما تحتاج إلى تقليص ملفات PDF، أو إنشاء تقارير مخصصة، أو الالتزام بحدود حجم المستند.

## لماذا تستخدم Aspose.Page لـ .NET؟
- **لا توجد تبعيات خارجية** – مكتبة .NET خالصة.  
- **دقة عالية** – تحتفظ بالرسومات المتجهية ودقة التخطيط.  
- **متعدد المنصات** – يعمل على Windows و Linux و macOS.  
- **واجهة برمجة تطبيقات بسيطة** – استدعاء طريقة واحدة (`RemovePageAt`) يتولى العملية الثقيلة.

## المتطلبات المسبقة

قبل الغوص في الكود، تأكد من أن لديك:

- **Aspose.Page لـ .NET** – قم بتنزيله من [توثيق Aspose.Page لـ .NET](https://reference.aspose.com/page/net/).  
- بيئة تطوير **.NET** (Visual Studio أو VS Code أو أي IDE تفضله).  
- مستند XPS **عينة** (مثلاً `Sample.xps`) موجود في مجلد يمكنك الإشارة إليه من مشروعك.

## استيراد مساحات الأسماء

أضف مساحات الأسماء المطلوبة في أعلى ملف C# الخاص بك حتى يعرف المترجم أين يجد فئات XPS.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## الخطوة 1: تعيين دليل المستند

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **نصيحة احترافية:** استخدم `Path.Combine` لبناء المسارات عبر الأنظمة.

## الخطوة 2: إنشاء مستند XPS جديد

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument(dataDir + "Sample.xps");
// ExEnd:4
```

هذا السطر يحمل ملف XPS الموجود (`Sample.xps`) إلى كائن `XpsDocument`، جاهز للتعديل.

## الخطوة 3: حذف صفحة عند الفهرس

```csharp
// ExStart:5
// Remove the first page (at index 1).
doc.RemovePageAt(1);
// ExEnd:5
```

طريقة `RemovePageAt` **تحذف الصفحة عند الفهرس المحدد**. تذكر أن الفهرسة تبدأ من 0، لذا `1` يحذف الصفحة الثانية. عدل الفهرس لاستهداف الصفحة التي تحتاج إلى حذفها.

## الخطوة 4: حفظ مستند XPS الناتج

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "Sample_out.xps");
// ExEnd:6
```

بعد الإزالة، يتم حفظ المستند كـ `Sample_out.xps`. يمكنك الآن فتح هذا الملف للتحقق من أن الصفحة غير المرغوب فيها قد اختفت.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **Index out of range** | محاولة حذف صفحة غير موجودة. | تحقق من عدد الصفحات باستخدام `doc.Pages.Count` قبل استدعاء `RemovePageAt`. |
| **File locked** | ملف XPS مفتوح في برنامج آخر. | أغلق أي عارضات أو تأكد من أن الملف غير مستخدم قبل تشغيل الكود. |
| **License not applied** | استخدام المكتبة بدون ترخيص صالح في بيئة الإنتاج. | قم بتطبيق ترخيص مؤقت أو دائم باستخدام `License license = new License(); license.SetLicense("Aspose.Page.lic");` |

## الأسئلة المتكررة

**س1: هل يمكنني إزالة صفحات متعددة مرة واحدة باستخدام Aspose.Page لـ .NET؟**  
ج1: نعم، ما عليك سوى استدعاء `RemovePageAt` بشكل متكرر أو التكرار عبر قائمة من الفهارس (تذكر أن تحذف من أعلى فهرس إلى أدنى فهرس للحفاظ على صلاحية الفهارس المتبقية).

**س2: هل Aspose.Page متوافق مع أحدث إصدارات .NET framework؟**  
ج2: يتم تحديث Aspose.Page بانتظام لدعم أحدث إصدارات .NET، بما في ذلك .NET 6 و .NET 7.

**س3: هل يمكنني استخدام Aspose.Page في التطبيقات التجارية؟**  
ج3: بالتأكيد. للحصول على تفاصيل الترخيص، زر صفحة [Aspose.Purchase](https://purchase.aspose.com/buy).

**س4: أين يمكنني العثور على دعم إضافي ومناقشات حول Aspose.Page؟**  
ج4: انضم إلى المجتمع في [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على نصائح وأمثلة ومساعدة في حل المشكلات.

**س5: هل أحتاج إلى ترخيص مؤقت لاختبار Aspose.Page؟**  
ج5: نعم، يمكنك الحصول على [ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) لتقييم المكتبة قبل الشراء.

**س6: كيف أحافظ على البيانات الوصفية للمستند بعد إزالة صفحة؟**  
ج6: طريقة `RemovePageAt` تحتفظ بالبيانات الوصفية الأصلية تلقائيًا. إذا كنت بحاجة لتعديلها، استخدم مجموعة `doc.DocumentProperties`.

## الخلاصة

لقد تعلمت الآن كيفية **remove page xps** المستندات و**delete page at index** باستخدام Aspose.Page لـ .NET. هذه الطريقة المختصرة تتيح لك دمج منطق إزالة الصفحات مباشرةً في تطبيقات .NET الخاصة بك، مما يمنحك التحكم الكامل في محتوى مستند XPS.

---

**آخر تحديث:** 2026-03-19  
**تم الاختبار مع:** Aspose.Page 24.12 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}