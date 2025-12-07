---
date: 2025-12-07
description: تعلم كيفية إضافة تدرج أفقي في Java PostScript باستخدام Linear Gradient
  Paint Java مع Aspose.Page for Java.
language: ar
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: إضافة تدرج في Java PostScript باستخدام Linear Gradient Paint Java
url: /java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة تدرج لوني في Java PostScript باستخدام Linear Gradient Paint Java

## المقدمة
في هذا الدرس الشامل ستكتشف كيفية إنشاء تدرج أفقي جميل في مستند PostScript باستخدام **Linear Gradient Paint Java**. تجعل Aspose.Page for Java من السهل العمل مع PostScript وPDF وغيرها من صيغ المتجهات، وتوفر فئة `LinearGradientPaint` تحكمًا دقيقًا في انتقالات الألوان. بحلول نهاية هذا الدليل، ستكون قادرًا على تطبيق التدرجات على الأشكال **و** النص، مما يمنح مستنداتك مظهرًا احترافيًا وجذابًا.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (يدعم Linear Gradient Paint Java).  
- **كم من الوقت تستغرق العملية؟** حوالي 10‑15 دقيقة لتدرج أساسي.  
- **هل أحتاج إلى رخصة؟** يلزم الحصول على رخصة مؤقتة أو كاملة للاستخدام في الإنتاج.  
- **ما نسخة JDK التي تعمل؟** Java 8 أو أحدث.  
- **هل يمكنني استخدام التدرج على الأشكال والنص معًا؟** نعم – يمكنك ملء الأشكال وتحديد أو ملء النص بنفس التدرج.

## المتطلبات المسبقة
قبل الغوص في الشيفرة، تأكد من توفر ما يلي:

- مجموعة تطوير جافا (JDK) مثبتة على جهازك.  
- مكتبة Aspose.Page for Java. يمكنك تنزيلها من [توثيق Aspose.Page Java](https://reference.aspose.com/page/java/).

## استيراد الحزم
ابدأ باستيراد الحزم الضرورية في مشروع Java الخاص بك. تتيح لك هذه الاستيرادات الوصول إلى primitive الرسومات، ومعالجة التدرجات، وواجهة Aspose.Page API.

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
هنا نبني كائن **Linear Gradient Paint Java** الذي يحدد انتقال ألوان أفقي. يقوم `AffineTransform` بتوسيع التدرج ليتطابق مع عرض وارتفاع المستطيل.

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
الآن قم بملء المستطيل بالتدرج الذي عرفناه للتو.

```java
// Fill the rectangle
document.fill(rectangle);
```

## الخطوة 4: ملء نص بالتدرج
يمكنك أيضًا تطبيق نفس التدرج على النص، مما يخلق تأثيرًا بصريًا مذهلًا.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## الخطوة 5: تحديد نص بالتدرج
أخيرًا، قم بتحديد النص باستخدام التدرج كلون للحد.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|---------|--------|------|
| التدرج يظهر ممدودًا | تحجيم `AffineTransform` غير صحيح | تأكد من أن عرض وارتفاع التحويل يتطابقان مع أبعاد المستطيل (200 × 100 في المثال). |
| الألوان باهتة | قيمة ألفا منخفضة جدًا | زيادة مكوّن ألفا (القيمة الرابعة في `new Color(r,g,b,alpha)`). |
| النص غير مرئي | لم يتم تعيين الطلاء قبل رسم النص | استدعِ `document.setPaint(paint)` **قبل** أي استدعاءات `fillAndStrokeText` أو `outlineText`. |

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Page for Java في المشاريع التجارية؟
نعم، يمكن استخدام Aspose.Page for Java في المشاريع التجارية. للحصول على تفاصيل الترخيص، زر [Aspose.Purchase](https://purchase.aspose.com/buy).

### هل يتوفر نسخة تجريبية مجانية؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Page for Java [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق ودعم إضافيين؟
قم بزيارة [توثيق Aspose.Page Java](https://reference.aspose.com/page/java/) للحصول على موارد شاملة. للدعم المجتمعي، راجع [منتدى Aspose.Page](https://forum.aspose.com/c/page/39).

### كيف يمكنني الحصول على رخصة مؤقتة؟
يمكنك الحصول على رخصة مؤقتة من [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

### ما هي متطلبات النظام لـ Aspose.Page for Java؟
ارجع إلى [التوثيق](https://reference.aspose.com/page/java/) للحصول على متطلبات النظام التفصيلية.

---

**آخر تحديث:** 2025-12-07  
**تم الاختبار مع:** Aspose.Page for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}