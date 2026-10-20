---
date: 2026-10-20
description: تعلم كيفية تحجيم المستطيل باستخدام Aspose.Page for Java، وكيفية إزاحة
  الشكل، وتطبيق التحويل الأفيني لإنشاء مستندات PostScript.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: التحويلات في معالجة الصفحات بلغة Java
og_description: تعلم كيفية تحجيم المستطيل، إزاحة الشكل، وتطبيق التحويل الأفيني باستخدام
  Aspose.Page for Java لإنشاء ملفات PostScript بكفاءة.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: كيفية تحجيم المستطيل باستخدام Aspise.Page for Java – دليل خطوة بخطوة
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: كيفية تحجيم المستطيل باستخدام Aspose.Page for Java
url: /ar/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحجيم المستطيل باستخدام Aspose.Page for Java

## مقدمة
في هذا الدليل ستكتشف **how to scale rectangle** باستخدام Aspose.Page for Java، بالإضافة إلى تعلم كيفية نقل مواضع الأشكال، وتدوير الرسومات، وتطبيق عمليات التحويل الأفيني لإنتاج مخرجات PostScript عالية الجودة. تتيح لك هذه التقنيات بناء رسومات متقدمة غير معتمدة على الجهاز دون كتابة شفرة تصيير منخفضة المستوى، مما يجعل تطبيقات Java الخاصة بك أكثر قوة وسهولة في الصيانة.

## إجابات سريعة
`scale(sx, sy)` يوسع سياق الرسومات بالعوامل الأفقية والعمودية المحددة.  

- **How do I scale a rectangle in Java with Aspose.Page?** استدعِ طريقة `scale(sx, sy)` على سياق الرسومات قبل رسم المستطيل.  
- **Can I move (translate) a shape without affecting other graphics?** نعم—قم بلف عملية النقل بين استدعاءات `writeGraphicsSave()` و `writeGraphicsRestore()`.  
- **What class creates a PostScript file?** استخدم `PsDocument` مع `PsSaveOptions`.  
- **Do I need a license for production use?** يلزم وجود ترخيص Aspose.Page صالح للاستخدام التجاري.  
- **Which Java version is supported?** يدعم Aspose.Page Java 8 وما بعدها.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من أنك تمتلك:

- فهم قوي لأساسيات بنية Java ومفاهيم البرمجة الكائنية.  
- مكتبة Aspose.Page for Java مثبتة. يمكنك تنزيلها من [وثائق Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- بيئة تطوير Java (IntelliJ IDEA أو Eclipse أو VS Code) مُكوَّنة بملفات JAR الخاصة بالمكتبة على مسار الفئة.

## استيراد الحزم
`PsDocument` هي الفئة الرئيسية المستخدمة لإنشاء مستند PostScript، و`PsSaveOptions` تُحدد كيفية حفظ المستند.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ما هو “how to scale rectangle” في Aspose.Page؟
طريقة `scale(float sx, float sy)` تُطبق تحويل تحجيم أفيني على حالة الرسومات الحالية، وتُعيد تحجيم الرسومات اللاحقة وفق العوامل `sx` (أفقي) و `sy` (عمودي). هذه هي العملية الأساسية وراء كلمة **how to scale rectangle**. من خلال تطبيق هذا التحويل قبل الرسم، سيتم عرض أي أشكال لاحقة مثل المستطيلات بالأبعاد الجديدة مع الحفاظ على نسبها.

## كيفية نقل الشكل باستخدام Aspose.Page
`writeGraphicsSave()` يحفظ حالة الرسومات الحالية و`writeGraphicsRestore()` يستعيدها، مما يضمن أن التحويلات تؤثر فقط على الشكل المقصود. النقل يعيد تموضع أصل نظام الإحداثيات دون تغيير أبعاد الكائن. من خلال إحاطة `translate(dx, dy)` بـ `writeGraphicsSave()` / `writeGraphicsRestore()`، تضمن أن يتحرك الشكل المقصود فقط بينما تبقى الرسومات الأخرى دون تغيير، مما يوفر تحكمًا دقيقًا في العناصر الفردية.

## المثال 1: بدون تحويلات
المثال الأول يرسم مستطيلًا بدون أي تحويل، مما يحدد خط أساس للمقارنة البصرية مع الأمثلة اللاحقة.

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
في هذا المثال نقوم بنقل سياق الرسومات 250 وحدة إلى اليمين قبل رسم مستطيل ثانٍ، موضحين **how to translate shape**.

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
هنا نجيب على السؤال الأساسي **how to scale rectangle**. يتم تقليل عرض المستطيل إلى 50 % من عرضه الأصلي وارتفاعه إلى 75 % من ارتفاعه الأصلي باستخدام استدعاء `scale(0.5f, 0.75f)`.

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
`rotate(angle)` يدور نظام الإحداثيات بالزاوية المحددة بالدرجات. قم بتحميل `PsDocument` الخاص بك، استدعِ `rotate(angle)` على حالة الرسومات، ارسم الشكل، ثم استعد الحالة السابقة. هذا النمط يُطبق **rotate shape java** و **how to rotate rectangle** في كتلة واحدة قابلة لإعادة الاستخدام، مما يتيح لك تدوير الرسومات حول أي نقطة تختارها.

## لماذا هذا مهم – الفوائد العملية
- **Device‑independent output** – يمكن لـ Aspose.Page إنشاء ملفات PostScript و XPS تُظهر بنفس الشكل على أي طابعة أو عارض، مما يلغي الحاجة إلى تعديلات خاصة بالمنصة.  
- **Fine‑grained control** – اجمع بين النقل، التحجيم، القص، والتدوير لتلبية مواصفات التخطيط الدقيقة؛ يدعم API أكثر من 20 تركيبة تحويلية لكل صفحة.  
- **Performance‑oriented processing** – تعالج المكتبة المستندات بذاكرة أقل من 10 ميغابايت لتقارير مئة صفحة نموذجية، مما يجعل وظائف الدفعات سريعة وقابلة للتوسع.

## حالات الاستخدام الشائعة
- **Printable invoices** – ضع الشعارات، الباركود، والجداول بدقة باستخدام التحجيم والنقل لتتوافق مع إرشادات العلامة التجارية للشركة.  
- **Technical diagrams** – أنشئ مخططات حيث يجب تحجيم كل مكوّن وتحديد موقعه بنسب متناسبة.  
- **Automated multi‑page reports** – أنشئ تقارير PostScript تتطلب تحجيمًا متسقًا عبر الصفحات، مثل المواصفات الهندسية.

## المشكلات الشائعة والحلول
- **Transformation not resetting** – احرص دائمًا على إقران `writeGraphicsSave()` مع `writeGraphicsRestore()`؛ وإلا ستورث الرسومات اللاحقة التحويلات غير المرغوبة.  
- **Unexpected colors** – عيّن اللون (paint) بعد كل تحويل لأن حالة الرسومات لا تحتفظ بمعلومات اللون بعد الاستعادة.  
- **File size too large** – فعّل الضغط في `PsSaveOptions` وحدد دقة الصور النقطية المضمنة للحفاظ على حجم الملف النهائي أقل من 5 ميغابايت للوثائق النموذجية ذات 50 صفحة.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Page for Java لتنسيقات مستندات أخرى؟
تركز Aspose.Page أساسًا على معالجة الصفحات لتنسيقات PostScript و XPS، لكنها تقدم أيضًا إمكانيات تصدير PDF محدودة.

### أين يمكنني العثور على مزيد من الأمثلة والوثائق لـ Aspose.Page for Java؟
قم بزيارة [وثائق Aspose.Page for Java](https://reference.aspose.com/page/java/) للحصول على أدلة شاملة، مراجع API، ومشروعات نموذجية.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page for Java؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية عبر صفحة **Aspose free trial download**: [Aspose free trial download](https://releases.aspose.com/).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟
احصل على ترخيص مؤقت عبر **temporary license request page**: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### أين يمكنني الحصول على دعم المجتمع أو طرح أسئلة حول Aspose.Page for Java؟
قم بزيارة [منتدى Aspose.Page for Java](https://forum.aspose.com/c/page/39) للمناقشات المجتمعية، مقتطفات الشفرة، ونصائح حل المشكلات.

## الأسئلة المتكررة

**س: ما الفرق بين `translate` و `scale`؟**  
ج: `translate` ينقل أصل نظام الإحداثيات، بينما `scale` يغيّر حجم الكائنات المرسومة على المحور X و/أو Y.

**س: هل يمكنني دمج عدة تحويلات في حالة رسومات واحدة؟**  
ج: نعم—عن طريق استدعاء `translate`، `scale`، `rotate` أو `shear` بالتتابع قبل الرسم، تُنشئ تحويلًا أفينيًا مركبًا.

**س: كيف يمكنني إعادة تعيين التحويلات بعد رسم شكل؟**  
ج: استخدم `writeGraphicsRestore()` للعودة إلى حالة الرسومات المحفوظة مسبقًا.

**س: هل يمكن تدوير مستطيل حول مركزه؟**  
ج: بالتأكيد. انقل المستطيل إلى الأصل، طبّق `rotate(angle)`، ثم أعد نقله إلى موقعه الأصلي قبل الرسم.

**س: هل تدعم Aspose.Page تقنية anti‑aliasing للحصول على رسومات أكثر سلاسة؟**  
ج: نعم—قم بتعيين خيارات العرض المناسبة في `PsSaveOptions` لتمكين anti‑aliasing.

---

**آخر تحديث:** 2026-10-20  
**تم الاختبار باستخدام:** Aspose.Page for Java 24.12  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية رسم مستطيل في Java PostScript باستخدام Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [إنشاء تدرج شعاعي في PostScript باستخدام Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [معالجة صفحات Postscript](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}