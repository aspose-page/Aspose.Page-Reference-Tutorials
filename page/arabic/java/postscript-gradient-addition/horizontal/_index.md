---
date: 2026-09-04
description: تعلم كيفية إنشاء تدرج أفقي java في ملف PostScript باستخدام Linear Gradient
  Paint Java مع Aspose.Page for Java. كود خطوة بخطوة، الأخطاء الشائعة، والأسئلة المتكررة.
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: إنشاء تدرج أفقي java في PostScript باستخدام Aspose
og_description: إنشاء تدرج أفقي java في PostScript باستخدام Linear Gradient Paint
  Java. يوضح لك هذا الدرس من Aspose.Page الخطوات الدقيقة، المتطلبات، ونصائح استكشاف
  الأخطاء وإصلاحها في أقل من 15 دقيقة.
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: إنشاء تدرج أفقي java في PostScript باستخدام Aspose
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: إنشاء تدرج أفقي java في PostScript باستخدام Aspose
url: /ar/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة تدرج أفقي في Java PostScript باستخدام Linear Gradient Paint

## المقدمة
في هذا الدرس الشامل ستتعلم **كيفية إنشاء تدرج أفقي في Java** داخل مستند PostScript باستخدام فئة **Linear Gradient Paint Java** التي تأتي مع Aspose.Page for Java. سنستعرض كل خطوة — من إعداد المشروع إلى عرض التدرج على الأشكال والنصوص — لتتمكن من إنتاج رسومات مصقولة وجاهزة للطباعة في دقائق. سواءً كنت تبني محرك تقارير، أو أداة أتمتة تصميم، أو برنامج تشغيل طابعة مخصص، فإن هذا الدليل يزودك بالكود الدقيق الذي تحتاجه.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (يتضمن Linear Gradient Paint Java).  
- **كم يستغرق التنفيذ؟** حوالي 10‑15 دقيقة لتدرج أفقي أساسي.  
- **هل أحتاج إلى ترخيص؟** يلزم الحصول على ترخيص مؤقت أو كامل للاستخدام في الإنتاج.  
- **أي نسخة من JDK تعمل؟** Java 8 أو أحدث.  
- **هل يمكنني استخدام التدرج على الأشكال والنصوص معًا؟** نعم – يمكن لنفس كائن `LinearGradientPaint` ملء الأشكال وتطبيقه على حدود النص أو تعبئته.

## ما هو التدرج الأفقي ولماذا نستخدمه؟
التدرج الأفقي يمزج الألوان من الحافة اليسرى للكائن إلى حافته اليمنى، مخلقًا انتقالًا سلسًا يضيف عمقًا وجاذبية بصرية. إنه مثالي لمكونات واجهة المستخدم الحديثة، العناوين المميزة، أو الظلال الخلفية الخفيفة في تقارير PDF أو PostScript. يتيح لك استخدام **Linear Gradient Paint Java** التحكم بدقة في ألوان البداية والنهاية، الشفافية، والقياس، مما يضمن أن النتيجة تبدو واضحة على أي جهاز أو طابعة.

## المتطلبات المسبقة
قبل الغوص في الكود، تأكد من وجود ما يلي:

- مجموعة تطوير جافا (JDK) مثبتة على جهازك.  
- مكتبة Aspose.Page for Java. يمكنك تنزيلها من [وثائق Aspose.Page Java](https://reference.aspose.com/page/java/).

## استيراد الحزم
ابدأ باستيراد الحزم الضرورية في مشروع Java الخاص بك. هذه الاستيرادات تمنحك الوصول إلى الكائنات الرسومية، معالجة التدرجات، وواجهة Aspose.Page API.

تمثل الفئة `PsDocument` مستند PostScript يمكنك رسم الرسومات عليه.  

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## الخطوة 1: إنشاء مستطيل
أولاً، قم بإعداد تدفق الإخراج، المستند، ومستطيل سيستضيف التدرج.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## الخطوة 2: إنشاء تدرج خطي أفقي
`LinearGradientPaint` هي الفئة الأساسية التي تحدد انتقال اللون الخطي.  
تمثل الفئة `LinearGradientPaint` كائن طلاء يرسم تدرجًا على طول خط مستقيم؛ تحدد نقاط البداية/النهاية، نقاط التوقف اللونية، و`AffineTransform` اختياري لتكييفه مع الشكل الخاص بك.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## الخطوة 3: تعبئة المستطيل
الآن قم بتعبئة المستطيل بالتدرج الذي عرفناه للتو.

```java
// Fill the rectangle
document.fill(rectangle);
```

## الخطوة 4: تعبئة نص بالتدرج
يمكنك أيضًا تطبيق نفس التدرج على النص، مما يخلق تأثيرًا بصريًا رائعًا.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## الخطوة 5: رسم حدود النص بالتدرج
أخيرًا، ارسم حدود النص باستخدام التدرج كلون للخط.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## المشكلات الشائعة والحلول
| المشكلة | سبب حدوثها | الحل |
|-------|----------------|-----|
| التدرج يبدو ممدودًا | تحجيم `AffineTransform` غير صحيح | تأكد من أن عرض وارتفاع التحويل يتطابقان مع أبعاد المستطيل (200 × 100 في المثال). |
| الألوان باهتة | قيمة ألفا منخفضة جدًا | زيادة مكوّن ألفا (القيمة الرابعة في `new Color(r,g,b,alpha)`). |
| النص غير مرئي | لم يتم تعيين الطلاء قبل رسم النص | استدعِ `document.setPaint(paint)` **قبل** أي استدعاءات `fillAndStrokeText` أو `outlineText`. |

## الأسئلة المتكررة
**س:** هل يمكنني استخدام Aspose.Page for Java في المشاريع التجارية؟  
**ج:** نعم، يمكن استخدام Aspose.Page for Java في المشاريع التجارية. للحصول على تفاصيل الترخيص، زر صفحة [Aspose.Purchase](https://purchase.aspose.com/buy).

**س:** هل هناك نسخة تجريبية مجانية متاحة؟  
**ج:** نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Page for Java عبر صفحة [Aspose.Page for Java free trial](https://releases.aspose.com/).

**س:** أين يمكنني العثور على وثائق إضافية ودعم؟  
**ج:** زر [وثائق Aspose.Page Java](https://reference.aspose.com/page/java/) للحصول على موارد شاملة. للحصول على مساعدة المجتمع، راجع [منتدى Aspose.Page](https://forum.aspose.com/c/page/39).

**س:** كيف يمكنني الحصول على ترخيص مؤقت؟  
**ج:** يمكنك الحصول على ترخيص مؤقت من صفحة [ترخيص مؤقت Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

**س:** ما هي متطلبات النظام لـ Aspose.Page for Java؟  
**ج:** راجع [وثائق Aspose.Page Java](https://reference.aspose.com/page/java/) للحصول على متطلبات النظام التفصيلية.

---

**آخر تحديث:** 2026-09-04  
**تم الاختبار مع:** Aspose.Page for Java 24.11  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء تدرج PostScript في Java – إضافة تدرج عمودي](/page/java/postscript-gradient-addition/vertical/)
- [كيفية إضافة تدرج: تدرج قطري في Java PostScript باستخدام Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [إنشاء تدرج PostScript – تدرج شعاعي في Java](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}