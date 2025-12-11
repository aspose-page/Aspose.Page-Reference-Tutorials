---
date: 2025-12-07
description: تعلم كيفية تحجيم المستطيل، نقل الشكل، وتطبيق التحويل الأفيني في جافا
  باستخدام Aspose.Page لإنشاء مستندات PostScript.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: كيفية تحجيم المستطيل وتطبيق التحويلات باستخدام Aspose.Page
url: /ar/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحجيم المستطيل وتطبيق التحويلات باستخدام Aspose.Page

## المقدمة
مرحبًا بكم في دليل شامل حول الاستفادة من الميزات القوية لـ **Aspose.Page for Java** لإجراء مجموعة متنوعة من تحويلات الصفحات. في هذا البرنامج التعليمي ستتعلم **كيفية تحجيم المستطيل**، نقل الأشكال، تدوير الكائنات، و**تطبيق تحويل أفيني** أثناء إنشاء **مستند PostScript**. تتيح لك هذه القدرات بناء تطبيقات Java غنية ومكثفة الرسوميات دون الحاجة إلى التعامل مع شفرة العرض منخفضة المستوى.

## إجابات سريعة
- **كيف يمكنني تحجيم مستطيل في Java باستخدام Aspose.Page؟** استخدم طريقة `document.scale()` قبل رسم الشكل.  
- **هل يمكنني نقل (ترجمة) شكل دون التأثير على الرسومات الأخرى؟** نعم — احفظ حالة الرسومات، استدعِ `document.translate(x, y)`، ارسم، ثم استعد الحالة.  
- **ما هو الصنف الذي ينشئ ملف PostScript؟** `PsDocument` مع `PsSaveOptions`.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يلزم وجود ترخيص Aspose.Page صالح للنشر التجاري.  
- **ما نسخة Java المدعومة؟** يعمل Aspose.Page مع Java 8 وما بعدها.

## المتطلبات المسبقة
قبل أن نغوص في دليل الخطوة بخطوة، تأكد من توفر المتطلبات المسبقة التالية:

- معرفة أساسية ببرمجة Java.  
- مكتبة Aspose.Page for Java مثبتة. يمكنك تنزيلها من [توثيق Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- بيئة تطوير متكاملة (IDE) للـ Java مُعدة على جهازك.

## استيراد الحزم
في مشروع Java الخاص بك، استورد الحزم الضرورية لاستخدام Aspose.Page for Java:

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
تحجيم المستطيل يغيّر حجمه على محوري X و Y مع الحفاظ على شكله. تُظهر Aspose.Page طريقة `scale(float sx, float sy)`، التي تُطبق **تحويلًا أفينيًا** على حالة الرسومات الحالية. هذه هي التقنية الأساسية وراء كلمة **كيفية تحجيم المستطيل**.

## كيفية نقل الشكل باستخدام Aspose.Page
النقل يحرك الشكل إلى موقع جديد دون تعديل أبعاده. هذه هي جوهر **كيفية نقل الشكل**. عن طريق حفظ حالة الرسومات، تطبيق `translate(dx, dy)`, الرسم، ثم استعادة الحالة، تبقى الكائنات الأخرى غير متأثرة.

## المثال 1: بدون تحويلات
المثال الأول يرسم مستطيلًا بسيطًا دون أي تحويل مطبق. يُستخدم كخط أساس للمقارنة مع الأمثلة اللاحقة.

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

## المثال 2: النقل
هنا نوضح **كيفية نقل الشكل** عن طريق تحريك سياق الرسومات 250 وحدة إلى اليمين قبل رسم مستطيل ثانٍ.

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
هذا المثال يجيب على السؤال الأساسي **كيفية تحجيم المستطيل**. نقوم بتصغير المستطيل إلى 50 % من عرضه الأصلي و75 % من ارتفاعه.

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
التدوير هو عملية أفينية شائعة أخرى. بينما تم حذف مقتطفات الشيفرة للتدوير لتقليل الحجم، النمط هو نفسه: احفظ حالة الرسومات، استدعِ `document.rotate(angle)`, ارسم الشكل، ثم استعد. يوضح هذا **rotate shape java** و**كيفية تدوير المستطيل** عمليًا.

## لماذا نستخدم Aspose.Page لهذه التحويلات؟
- **مستقل عن الجهاز**: اكتب مرة واحدة، أنشئ PostScript أو XPS دون شفرة خاصة بالمنصة.  
- **تحكم دقيق**: الوصول المباشر إلى حالة الرسومات يتيح لك دمج النقل، التحجيم، القص، والتدوير.  
- **الأداء**: واجهة برمجة تطبيقات منخفضة الحمل مناسبة لمعالجة دفعات من المستندات الكبيرة.  

## حالات الاستخدام الشائعة
- إنشاء فواتير قابلة للطباعة مع باركودات وشعارات ديناميكية.  
- إنشاء مخططات تقنية حيث يتطلب التحجيم والتموضع الدقيق.  
- أتمتة إنتاج تقارير متعددة الصفحات بتنسيق PostScript.  

## الخاتمة
في هذا البرنامج التعليمي، استكشفنا مختلف التحويلات في معالجة صفحات Java باستخدام Aspose.Page for Java، مع التركيز على **كيفية تحجيم المستطيل**، **كيفية نقل الشكل**، وغيرها من العمليات الأفينية. باتباع هذه الأمثلة، يمكنك تحسين تطبيقات Java الخاصة بك بقدرات متقدمة لمعالجة الصفحات و**إنشاء مستندات PostScript** تتوافق مع معايير النشر الاحترافية.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Page for Java لتنسيقات مستندات أخرى؟
تركز Aspose.Page أساسًا على معالجة الصفحات لتنسيقات PostScript و XPS.

### أين يمكنني العثور على المزيد من الأمثلة والتوثيق لـ Aspose.Page for Java؟
قم بزيارة [توثيق Aspose.Page for Java](https://reference.aspose.com/page/java/) للحصول على معلومات شاملة.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page for Java؟
نعم، يمكنك الوصول إلى نسخة تجريبية مجانية [من هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟
احصل على ترخيص مؤقت [من هنا](https://purchase.aspose.com/temporary-license/).

### أين يمكنني الحصول على دعم المجتمع أو طرح أسئلة حول Aspose.Page for Java؟
قم بزيارة [منتدى Aspose.Page for Java](https://forum.aspose.com/c/page/39) للمناقشات المجتمعية.

## الأسئلة المتكررة
**س: ما الفرق بين `translate` و `scale`؟**  
ج: `translate` ينقل أصل نظام الإحداثيات، بينما `scale` يغيّر حجم الكائنات المرسومة على محوري X و/أو Y.

**س: هل يمكنني دمج عدة تحويلات في حالة رسومات واحدة؟**  
ج: نعم — عن طريق استدعاء `translate`، `scale`، `rotate` أو `shear` بالتتابع قبل الرسم، تُنشئ تحويلًا أفينيًا مركبًا.

**س: كيف أعيد تعيين التحويلات بعد رسم شكل؟**  
ج: استخدم `document.writeGraphicsRestore()` للعودة إلى حالة الرسومات التي تم حفظها مسبقًا.

**س: هل من الممكن تدوير مستطيل حول مركزه؟**  
ج: بالتأكيد. انقل المستطيل إلى الأصل، طبّق `rotate(angle)`، ثم أعده إلى موقعه الأصلي قبل الرسم.

**س: هل تدعم Aspose.Page تقنية مضاد التعرجات (anti‑aliasing) للحصول على رسومات أكثر سلاسة؟**  
ج: نعم — اضبط خيارات العرض المناسبة في `PsSaveOptions` لتمكين مضاد التعرجات.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}