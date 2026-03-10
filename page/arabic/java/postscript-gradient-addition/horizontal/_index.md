---
date: 2026-02-13
description: تعلم كيفية إضافة تدرج لوني في Java PostScript باستخدام Linear Gradient
  Paint Java مع Aspose.Page للغة Java.
linktitle: How to Add Gradient in Java PostScript with Linear Gradient Paint
second_title: Aspose.Page Java API
title: كيفية إضافة تدرج لوني في Java PostScript باستخدام طلاء التدرج الخطي
url: /ar/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة تدرج لوني في Java PostScript باستخدام Linear Gradient Paint

## المقدمة
في هذا الدرس الشامل ستكتشف **كيفية إضافة تدرج لوني** إلى مستند PostScript باستخدام Java. سنستعرض إنشاء تدرج أفقي جميل من خلال الاستفادة من **Linear Gradient Paint Java**، وهي فئة تمنحك تحكمًا دقيقًا في انتقالات الألوان. باستخدام Aspose.Page for Java يمكنك عرض التدرجات على كل من الأشكال **و** النص، مما يمنح مستنداتك مظهرًا مصقولًا وجذابًا يبرز.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (يدعم Linear Gradient Paint Java).  
- **كم من الوقت تستغرق العملية؟** حوالي 10‑15 دقيقة لتدرج أساسي.  
- **هل أحتاج إلى ترخيص؟** يلزم الحصول على ترخيص مؤقت أو كامل للاستخدام في الإنتاج.  
- **أي نسخة من JDK تعمل؟** Java 8 أو أحدث.  
- **هل يمكنني استخدام التدرج على كل من الأشكال والنص؟** نعم – يمكنك ملء الأشكال أو رسم أو ملء النص بنفس التدرج.

## ما هو التدرج الأفقي ولماذا يستخدم؟
التدرج الأفقي يدمج الألوان بسلاسة من اليسار إلى اليمين عبر شكل أو نص. إنه مثالي لإنشاء عناصر واجهة مستخدم حديثة، عناوين مميزة، أو تأثيرات خلفية خفيفة في التقارير. باستخدام **Linear Gradient Paint Java** يمكنك تحديد ألوان البداية والنهاية بدقة، بالإضافة إلى الشفافية والقياس، بحيث يكون الناتج واضحًا على أي جهاز.

## المتطلبات المسبقة
قبل الغوص في الكود، تأكد من وجود ما يلي:

- Java Development Kit (JDK) مثبت على جهازك.  
- مكتبة Aspose.Page for Java. يمكنك تنزيلها من [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## استيراد الحزم
ابدأ باستيراد الحزم الضرورية في مشروع Java الخاص بك. هذه الاستيرادات تمنحك الوصول إلى الرسوميات الأساسية، معالجة التدرجات، وواجهة Aspose.Page API.

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

## الخطوة 2: إنشاء Linear Gradient Paint أفقي
هنا نقوم بإنشاء كائن **Linear Gradient Paint Java** الذي يحدد انتقال لون أفقي. يقوم `AffineTransform` بتحجيم التدرج ليتطابق مع عرض وارتفاع المستطيل.

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

## الخطوة 3: ملء المستطيل
الآن قم بملء المستطيل بالتدرج الذي عرّفناه للتو.

```java
// Fill the rectangle
document.fill(rectangle);
```

## الخطوة 4: ملء نص بالتدرج
يمكنك أيضًا تطبيق نفس التدرج على النص، مما يخلق تأثيرًا بصريًا ملفتًا.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## الخطوة 5: رسم حدود نص بالتدرج
أخيرًا، ارسم حدود النص باستخدام التدرج كلون للخط.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## المشكلات الشائعة والحلول
| المشكلة | سبب حدوثها | الحل |
|-------|----------------|-----|
| التدرج يبدو مشدودًا | تحجيم `AffineTransform` غير صحيح | تأكد من أن عرض وارتفاع التحويل يطابق أبعاد المستطيل (200 × 100 في المثال). |
| الألوان باهتة | قيمة ألفا منخفضة جدًا | قم بزيادة مكوّن ألفا (القيمة الرابعة في `new Color(r,g,b,alpha)`). |
| النص غير مرئي | لم يتم تعيين الطلاء قبل رسم النص | استدعِ `document.setPaint(paint)` **قبل** أي استدعاءات `fillAndStrokeText` أو `outlineText`. |

## الأسئلة المتكررة
**س:** هل يمكنني استخدام Aspose.Page for Java في المشاريع التجارية؟  
**ج:** نعم، يمكن استخدام Aspose.Page for Java في المشاريع التجارية. للحصول على تفاصيل الترخيص، زر [Aspose.Purchase](https://purchase.aspose.com/buy).

**س:** هل هناك نسخة تجريبية مجانية متاحة؟  
**ج:** نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Page for Java [هنا](https://releases.aspose.com/).

**س:** أين يمكنني العثور على وثائق إضافية ودعم؟  
**ج:** زر [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) للحصول على موارد شاملة. للدعم المجتمعي، تفقد [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**س:** كيف يمكنني الحصول على ترخيص مؤقت؟  
**ج:** يمكنك الحصول على ترخيص مؤقت من [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

**س:** ما هي متطلبات النظام لـ Aspose.Page for Java؟  
**ج:** راجع [documentation](https://reference.aspose.com/page/java/) للحصول على متطلبات النظام التفصيلية.

---

**آخر تحديث:** 2026-02-13  
**تم الاختبار مع:** Aspose.Page for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}