---
date: 2026-03-21
description: تعلم كيفية إنشاء مستند XPS باستخدام .NET و Aspose.Page وإضافة نص باستخدام
  Aspose.Page for .NET. دليل خطوة بخطوة لمطوري .NET.
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: إنشاء مستند XPS باستخدام .NET وإضافة نص باستخدام Aspose.Page
url: /ar/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مستند XPS باستخدام .NET وإضافة نص باستخدام Aspose.Page

## الإجابات السريعة
- **ماذا يغطي هذا الدرس؟** إضافة نص إلى مستند XPS تم إنشاؤه حديثًا باستخدام Aspose.Page لـ .NET.  
- **كم من الوقت يستغرق؟** حوالي 5‑10 دقائق للتنفيذ الأساسي.  
- **ما هي المتطلبات المسبقة؟** بيئة تطوير .NET ومكتبة Aspose.Page.  
- **هل يلزم وجود ترخيص؟** نعم، يلزم وجود ترخيص Aspose.Page صالح للاستخدام في الإنتاج.  
- **هل يمكن تشغيله على .NET Core / .NET 6+؟** بالتأكيد – يدعم Aspose.Page جميع إصدارات .NET الحديثة.

## ما هو إنشاء مستند XPS باستخدام .NET؟

إنشاء مستند XPS في .NET يعني توليد ملف تخطيط ثابت يحافظ على المظهر الدقيق لمحتواك عبر الأجهزة والطابعات. XPS (XML Paper Specification) هو المعيار المفتوح من مايكروسوفت لوصف الصفحات، مشابه لـ PDF لكنه مبني بالكامل على XML.

## لماذا نستخدم Aspose.Page لإضافة نص؟

يوفر Aspose.Page واجهة برمجة تطبيقات عالية المستوى وموجهة للكائنات تُجرد علامات XPS منخفضة المستوى. يمكنك إضافة نص، رسومات، وأشكال دون التعامل مع XML الخام، مما يجعل عملية التطوير أسرع وأقل عرضة للأخطاء.

## المتطلبات المسبقة

- Aspose.Page for .NET: تأكد من تثبيت مكتبة Aspose.Page. يمكنك تنزيلها من [توثيق Aspose.Page for .NET](https://reference.aspose.com/page/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET الخاصة بك. إذا لم تقم بذلك بعد، اتبع تعليمات التثبيت الموجودة في [التوثيق](https://reference.aspose.com/page/net/).
- دليل المستندات: أنشئ دليلًا لتخزين مستنداتك. استبدل "Your Document Directory" في المقتطف البرمجي بالمسار الفعلي.

الآن بعد أن غطينا الأساسيات، دعنا نتعمق في الكود.

## استيراد المساحات الاسمية

أولاً، استورد المساحات الاسمية الضرورية لبدء المشروع:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## الخطوة 1: إنشاء مستند XPS باستخدام .NET

أنشئ مستند XPS جديد سيعمل كقماش للنص الخاص بنا.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## الخطوة 2: إنشاء فرشاة للنص

عرّف فرشاة صلبة اللون تحدد لون النص. هنا نستخدم اللون الأسود.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## الخطوة 3: إضافة الرموز (aspose.page add text)

الرموز هي تمثيل منخفض المستوى للأحرف في مستند XPS. هذه الدالة تضيف النص “Hello World!” عند الإحداثيات المحددة.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## الخطوة 4: حفظ مستند XPS الناتج

احفظ المستند على القرص لتتمكن من عرضه أو طباعته لاحقًا.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

باتباع هذه الخطوات، تكون قد نجحت في **إنشاء مستند XPS باستخدام .NET** وأضفت نصًا مخصصًا باستخدام Aspose.Page.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|-----|
| **الملف غير موجود** عند الحفظ | `dataDir` يشير إلى مجلد غير موجود | تأكد من وجود المجلد أو استخدم `Directory.CreateDirectory(dataDir)` قبل الحفظ. |
| **النص غير مرئي** | لون الفرشاة يطابق الخلفية | غيّر `Color.Black` إلى لون متباين آخر. |
| **خط غير مدعوم** | الخط غير مثبت على الجهاز | استخدم خطًا مضمونًا وجوده، أو اضف الخط باستخدام ميزات تضمين الخط في Aspose.Page. |

## الأسئلة المتكررة

### س1: هل يمكنني تخصيص الخط وحجم النص المضاف؟

**ج1:** نعم، لديك التحكم الكامل في الخط والحجم. عدّل المعلمات في طريقة `AddGlyphs` وفقًا لذلك.

### س2: هل Aspose.Page متوافق مع .NET Core؟

**ج2:** بالتأكيد! يدعم Aspose.Page .NET Core، مما يضمن التوافق مع أحدث تقنيات .NET.

### س3: هل هناك متطلبات ترخيص لاستخدام Aspose.Page؟

**ج3:** نعم، تحتاج إلى ترخيص صالح. استكشف خيارات الترخيص [هنا](https://purchase.aspose.com/buy).

### س4: كيف يمكنني الحصول على الدعم أو المساعدة؟

**ج4:** زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع والحصول على المساعدة.

### س5: هل هناك نسخة تجريبية مجانية متاحة؟

**ج5:** بالطبع! يمكنك الحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

**أسئلة وإجابات إضافية**

**س: هل يمكنني إضافة عدة كتل نصية في نفس الصفحة؟**  
**ج:** نعم، ما عليك سوى استدعاء `doc.AddGlyphs` عدة مرات مع إحداثيات مختلفة.

**س: هل يسمح Aspose.Page بتدوير النص؟**  
**ج:** يمكنك تطبيق مصفوفة تحويل على كائن `XpsGlyphs` لتدوير أو إمالة النص.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**آخر تحديث:** 2026-03-21  
**تم الاختبار مع:** Aspose.Page 24.11 لـ .NET  
**المؤلف:** Aspose  

---