---
date: 2026-02-07
description: تعلم كيفية تحجيم المستطيل باستخدام Aspose.Page للغة Java، وكيفية إزاحة
  الشكل، وتطبيق التحويل الأفيني لإنشاء مستندات PostScript.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: كيفية تحجيم المستطيل باستخدام Aspose.Page للـ Java
url: /ar/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحجيم المستطيل باستخدام Aspose.Page للـ Java

## مقدمة
مرحبًا بك في دليل شامل حول الاستفادة من الميزات القوية لـ **Aspose.Page للـ Java** لإجراء مجموعة متنوعة من تحويلات الصفحات. في هذا البرنامج التعليمي ستتعلم **كيفية تحجيم المستطيل**، نقل الأشكال، تدوير الكائنات، و**تطبيق تحويل أفيني** أثناء إنشاء **مستند PostScript**. تتيح لك هذه القدرات بناء تطبيقات Java غنية بالرسومات دون الحاجة إلى التعامل مع شفرة التقديم منخفضة المستوى.

## إجابات سريعة
- **كيف يمكنني تحجيم مستطيل في Java باستخدام Aspose.Page؟** استخدم طريقة `document.scale()` قبل رسم الشكل.  
- **هل يمكنني نقل (ترجمة) شكل دون التأثير على الرسومات الأخرى؟** نعم — احفظ حالة الرسومات، استدعِ `document.translate(x, y)`، ارسم، ثم استعد الحالة.  
- **ما هو الصنف الذي ينشئ ملف PostScript؟** `PsDocument` مع `PsSaveOptions`.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يلزم وجود ترخيص Aspose.Page صالح للنشر التجاري.  
- **ما نسخة Java المدعومة؟** Aspose.Page يعمل مع Java 8 وما بعدها.

## المتطلبات المسبقة
قبل أن نغوص في الدليل خطوة بخطوة، تأكد من توفر المتطلبات التالية:

- معرفة أساسية ببرمجة Java.  
- مكتبة Aspose.Page للـ Java مثبتة. يمكنك تنزيلها من [توثيق Aspose.Page للـ Java](https://reference.aspose.com/page/java/).  
- بيئة تطوير متكاملة (IDE) للـ Java مُعدّة على جهازك.

## استيراد الحزم
في مشروع Java الخاص بك، استورد الحزم اللازمة لاستخدام Aspose.Page للـ Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ما هو “كيفية تحجيم المستطيل” في Aspose.Page؟
تحجيم المستطيل يغيّر حجمه على محوري X و Y مع الحفاظ على شكله. تُظهر Aspose.Page طريقة `scale(float sx, float sy)`، التي تُطبق **تحويل أفيني** على حالة الرسومات الحالية. هذه هي التقنية الأساسية وراء كلمة **how to scale rectangle**.

## كيفية نقل الشكل باستخدام Aspose.Page
النقل يحرك الشكل إلى موقع جديد دون تعديل أبعاده. هذا هو جوهر **how to translate shape**. بحفظ حالة الرسومات، تطبيق `translate(dx, dy)`, الرسم، ثم استعادة الحالة، تظل الكائنات الأخرى غير متأثرة.

## المثال 1: بدون تحويلات
المثال الأول يرسم مستطيلًا بسيطًا دون أي تحويل مطبق. يُستخدم هذا كأساس للمقارنة مع الأمثلة اللاحقة.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## المثال 2: الترجمة
هنا نوضح **how to translate shape** بنقل سياق الرسومات 250 وحدة إلى اليمين قبل رسم مستطيل ثانٍ.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## المثال 3: التحجيم
هذا المثال يجيب على السؤال الأساسي **how to scale rectangle**. نقوم بتقليل عرض المستطيل إلى 50 % من عرضه الأصلي وارتفاعه إلى 75 % من ارتفاعه الأصلي.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## كيفية تدوير الشكل في Java (rotate shape java)
التدوير هو عملية أفينية شائعة أخرى. بينما تم حذف مقتطفات الشيفرة الخاصة بالتدوير لتقليل الطول، النمط هو نفسه: احفظ حالة الرسومات، استدعِ `document.rotate(angle)`, ارسم الشكل، ثم استعد. هذا يوضح **rotate shape java** و**how to rotate rectangle** عمليًا.

## لماذا هذا مهم – الفوائد العملية
- **إخراج مستقل عن الجهاز** – اكتب مرة واحدة وولّد PostScript أو XPS دون تعديل خاص بالمنصة.  
- **تحكم دقيق** – اجمع بين النقل، التحجيم، القص، والتدوير لتلبية متطلبات التخطيط الدقيقة.  
- **موجه للأداء** – API منخفض الحمل مثالي لمعالجة دفعات من المستندات الكبيرة الحجم.  

## حالات الاستخدام الشائعة
- إنشاء فواتير قابلة للطباعة – على سبيل المثال، حل **printable invoice java** يضع الشعارات والباركود بدقة.  
- إنشاء مخططات تقنية حيث يتطلب التحجيم والتموضع الدقيق.  
- أتمتة إنتاج تقارير متعددة الصفحات بصيغة PostScript.  

## المشكلات الشائعة والحلول
- **التحويل لا يعيد التعيين** – احرص دائمًا على إقران `document.writeGraphicsSave()` مع `document.writeGraphicsRestore()` لتجنب تأثيرات النقل غير المرغوب فيها.  
- **ألوان غير متوقعة** – تأكد من ضبط الطلاء بعد كل تحويل؛ حالة الرسومات لا تحتفظ بإعدادات اللون السابقة بعد الاستعادة.  
- **حجم الملف كبير جدًا** – استخدم `PsSaveOptions` لتمكين الضغط أو خفض دقة الصورة عند تضمين رسومات نقطية.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Page للـ Java لتنسيقات مستندات أخرى؟
Aspose.Page يركز أساسًا على معالجة الصفحات لتنسيقات PostScript و XPS.

### أين يمكنني العثور على المزيد من الأمثلة والتوثيق لـ Aspose.Page للـ Java؟
تفضل بزيارة [توثيق Aspose.Page للـ Java](https://reference.aspose.com/page/java/) للحصول على معلومات شاملة.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page للـ Java؟
نعم، يمكنك الوصول إلى نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page للـ Java؟
احصل على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### أين يمكنني طلب الدعم المجتمعي أو طرح أسئلة حول Aspose.Page للـ Java؟
تفضل بزيارة [منتدى Aspose.Page للـ Java](https://forum.aspose.com/c/page/39) للمناقشات المجتمعية.

## الأسئلة المتكررة

**س: ما الفرق بين `translate` و `scale`؟**  
ج: `translate` ينقل أصل نظام الإحداثيات، بينما `scale` يغيّر حجم الكائنات المرسومة على محوري X و/أو Y.

**س: هل يمكنني دمج عدة تحويلات في حالة رسومات واحدة؟**  
ج: نعم — باستدعاء `translate`، `scale`، `rotate` أو `shear` بالتتابع قبل الرسم، يمكنك إنشاء تحويل أفيني مركب.

**س: كيف أعيد تعيين التحويلات بعد رسم شكل؟**  
ج: استخدم `document.writeGraphicsRestore()` للعودة إلى حالة الرسومات المحفوظة مسبقًا.

**س: هل من الممكن تدوير مستطيل حول مركزه؟**  
ج: بالتأكيد. انقل المستطيل إلى الأصل، طبّق `rotate(angle)`، ثم أعد نقله إلى موقعه الأصلي قبل الرسم.

**س: هل يدعم Aspose.Page مضاد التعرج (anti‑aliasing) للرسومات الأكثر سلاسة؟**  
ج: نعم — اضبط خيارات العرض المناسبة في `PsSaveOptions` لتمكين مضاد التعرج.

---

**آخر تحديث:** 2026-02-07  
**تم الاختبار مع:** Aspose.Page للـ Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}