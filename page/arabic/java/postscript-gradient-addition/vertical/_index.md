---
date: 2026-02-13
description: تعلم كيفية إنشاء تدرج PostScript في Java باستخدام Aspose.Page. يوضح لك
  هذا الدليل خطوة بخطوة كيفية إضافة تدرج عمودي إلى مستندات PostScript الخاصة بك بسهولة.
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: إنشاء تدرج PostScript في Java – إضافة تدرج عمودي
url: /ar/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء تدرج PostScript في Java – إضافة تدرج عمودي

## المقدمة
في هذا الدرس الشامل، ستتعلم كيفية **إنشاء تدرج PostScript في Java** باستخدام Aspose.Page for Java. إضافة تدرج عمودي يمكن أن يجعل مستنداتك أكثر حيوية واحترافية، ومع بضع أسطر من الشيفرة فقط يمكنك تحقيق تأثيرات بصرية مذهلة. سنرشدك خلال كل خطوة، نشرح لماذا كل جزء مهم، ونقدم لك نصائح عملية لتجنب الأخطاء الشائعة. في نهاية هذا الدليل ستكون قادرًا على توليد ملفات PostScript ذات انتقالات لونية عمودية سلسة وجذابة.

## الإجابات السريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **هل يمكنني تخصيص الألوان؟** نعم، يمكن استخدام أي `java.awt.Color`  
- **هل يدعم الدوران؟** نعم، يمكنك تدوير التدرج باستخدام `AffineTransform`  
- **ما صيغة الإخراج المنتجة؟** ملف PostScript قياسي (.ps)  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم الحصول على ترخيص تجاري  

## لماذا إضافة تدرج عمودي إلى مستند PostScript؟
تُضيف التدرجات العمودية عمقًا لصفحاتك دون زيادة حجم الملف. إنها مثالية لـ:

* رؤوس أو تذييلات التقارير التي تحتاج إلى خلفية خفيفة.  
* تمييز الأقسام في الأدلة التقنية أو الأوراق البيضاء.  
* إضفاء مظهر حديث على المخططات، الرسوم البيانية، أو النشرات الترويجية.

نظرًا لأن التدرج يُعرَّف بصيغة متجهية، يبقى الإخراج واضحًا عند أي دقة.

## المتطلبات المسبقة
قبل الغوص في الدرس، تأكد من توفر المتطلبات التالية:
- مجموعة تطوير جافا (JDK) مثبتة على جهازك.  
- مكتبة Aspose.Page for Java. يمكنك تنزيلها [هنا](https://releases.aspose.com/page/java/).

## استيراد الحزم
في مشروع Java الخاص بك، استورد الحزم اللازمة للبدء:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

الآن، دعنا نستعرض عملية إضافة تدرج عمودي خطوة بخطوة.

## كيفية إنشاء تدرج PostScript في Java
فيما يلي دليل خطوة بخطوة يوضح بالضبط كيفية **إنشاء تدرج PostScript في Java** باستخدام Aspose.Page API.

### الخطوة 1: إعداد دليل المستند الخاص بك
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### الخطوة 2: إنشاء تدفق إخراج لمستند PostScript
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### الخطوة 3: إنشاء خيارات الحفظ بحجم A4
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### الخطوة 4: إنشاء مستند PS جديد
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### الخطوة 5: إنشاء مستطيل
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### الخطوة 6: إعداد الألوان والكسرات للتدرج
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### الخطوة 7: إنشاء تحويل التدرج
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### الخطوة 8: إنشاء طلاء تدرج خطي عمودي
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### الخطوة 9: تعيين الطلاء وتعبئة المستطيل
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### الخطوة 10: إغلاق الصفحة الحالية وحفظ المستند
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

تهانينا! لقد أضفت بنجاح تدرجًا عموديًا إلى مستند PostScript الخاص بك باستخدام Aspose.Page for Java.

## المشكلات الشائعة والحلول
- **التدرج يبدو مسطحًا:** تأكد من أن مقياس `AffineTransform` يتطابق مع أبعاد المستطيل.  
- **الألوان باهتة:** تحقق من أنك تستخدم `ColorSpaceType` الصحيح (SRGB) وأن مصفوفة الكسرات مرتبة من 0.0 إلى 1.0.  
- **الملف لم يُنشأ:** تحقق من وجود دليل الإخراج (`dataDir`) وأن التطبيق لديه أذونات كتابة.  

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Page for Java مع مكتبات جافا أخرى؟
نعم، تم تصميم Aspose.Page for Java للعمل بسلاسة مع مكتبات جافا الأخرى.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page for Java؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق إضافية؟
توفر الوثائق التفصيلية [هنا](https://reference.aspose.com/page/java/).

### كيف يمكنني شراء Aspose.Page for Java؟
يمكنك شراء Aspose.Page for Java [هنا](https://purchase.aspose.com/buy).

### هل هناك منتدى لمناقشات Aspose.Page؟
نعم، يمكنك الانضمام إلى منتدى المجتمع [هنا](https://forum.aspose.com/c/page/39).

## أسئلة متكررة إضافية

**س: هل يمكنني إنشاء اتجاهات تدرج أخرى (أفقي، قطري؟)**  
ج: بالتأكيد. عدّل نقاط البداية والنهاية في `LinearGradientPaint` وعدّل زاوية الدوران في `AffineTransform`.

**س: هل يعمل هذا مع إخراج PDF أيضًا؟**  
ج: يمكن تطبيق نفس منطق التدرج عند الحفظ إلى PDF باستخدام `PdfSaveOptions` بدلاً من `PsSaveOptions`.

**س: كيف أغيّر حجم التدرج ديناميكيًا؟**  
ج: احسب أبعاد المستطيل في وقت التشغيل ومرّر تلك القيم لكل من `Rectangle2D` ومنشئ `AffineTransform`.

---

**آخر تحديث:** 2026-02-13  
**تم الاختبار مع:** Aspose.Page for Java 24.11 (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}