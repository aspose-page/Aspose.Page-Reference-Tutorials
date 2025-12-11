---
date: 2025-12-08
description: تعلم كيفية إضافة تدرج شعاعي في Java PostScript باستخدام Aspose.Page.
  يوضح لك هذا الدليل خطوة بخطوة كيفية إنشاء تأثيرات تدرج مذهلة في مستنداتك.
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: كيفية إضافة تدرج شعاعي في Java PostScript باستخدام Aspose.Page
url: /ar/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة تدرج شعاعي في Java PostScript باستخدام Aspose.Page

## المقدمة
إذا احتجت يومًا إلى إعطاء مخرجات PostScript الخاصة بك انتقالًا سلسًا وجذابًا للألوان، فإن تعلم **كيفية إضافة تدرج شعاعي** هو المكان المثالي للبدء. في هذا البرنامج التعليمي سنستعرض كل خطوة مطلوبة لإنشاء ملف PostScript يحتوي على تدرج شعاعي جميل، باستخدام مكتبة **Aspose.Page for Java**. في النهاية ستفهم الـ API، وسترى مثالًا كاملاً قابلًا للتنفيذ، وستعرف كيف تعدل الألوان، المواقع، ونصف القطر لتناسب أي تصميم.

## إجابات سريعة
- **ما المكتبة التي تنشئ تدرجات شعاعية في PostScript؟** Aspose.Page for Java.  
- **كم يستغرق تنفيذ المثال؟** حوالي 10‑15 دقيقة للمثال الأساسي.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** نسخة تجريبية مجانية تكفي للتطوير؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أعلى.  
- **هل يمكنني تغيير شكل التدرج؟** نعم – عدل نصف القطر ونقطة المركز في مُنشئ `RadialGradientPaint`.

## ما هو التدرج الشعاعي؟
التدرج الشعاعي يرسم ألوانًا تتناثر من نقطة مركزية، مع مزج تدريجي نحو الحواف. على عكس التدرجات الخطية، ينتقل الانتقال اللوني وفق نمط دائري (أو بيضاوي)، وهو مثالي للإبرازات، الأضواء المسلطة، أو ملء الخلفيات الناعمة.

## لماذا نستخدم Aspose.Page للتدرجات الشعاعية؟
- **تحكم كامل في مخرجات PostScript** – لا حاجة لكتابة أوامر PS منخفضة المستوى يدويًا.  
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java.  
- **إدارة ألوان غنية** – يدعم عدة نقاط توقف لونية، مساحات ألوان مختلفة، وطرق دورة.  
- **جاهز للتكامل** – يمكن دمجه مع ميزات Aspose.Page الأخرى مثل النصوص، الصور، والأشكال المتجهة.

## المتطلبات المسبقة
قبل الغوص في الكود، تأكد من توفر ما يلي:

- **مجموعة تطوير Java (JDK) 8+** – تحقق باستخدام `java -version`.  
- **Aspose.Page for Java** – حمّل أحدث JAR من [صفحة تنزيل Aspose.Page الرسمية](https://releases.aspose.com/page/java/).  
- **بيئة تطوير متكاملة** – Eclipse، IntelliJ IDEA، أو VS Code مع ملحقات Java.  
- **مجلد قابل للكتابة** – حيث سيتم حفظ ملف `.ps` المُولد.

## استيراد الحزم
أولًا، استورد الفئات التي سنحتاجها. حزمة `java.awt` توفر كائنات تدرج الطلاء، بينما تحتوي `com.aspose.eps` على فئات معالجة مستندات PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## دليل خطوة بخطوة

### الخطوة 1: إنشاء مستطيل وفتح مستند PS
نبدأ بإنشاء تدفق إخراج، ضبط حجم الصفحة (A4 افتراضيًا)، وتعريف مستطيل سيستضيف التدرج.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **نصيحة احترافية:** عدل إحداثيات المستطيل (`200, 100, 200, 200`) لتحديد موقع التدرج في أي مكان على الصفحة.

### الخطوة 2: تعريف الألوان والنسب
التدرج الشعاعي يُبنى من *نقاط توقف لونية* (الألوان) و*نسب* (المواقع النسبية لتلك النقاط). هنا ننشئ مصفوفة من ستة ألوان ونسبها المقابلة.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **لماذا هذا مهم:** من خلال تعديل `fractions` تتحكم في سرعة انتقال الألوان، ما يتيح تأثيرات دقيقة أو دراماتيكية.

### الخطوة 3: إنشاء كائن RadialGradientPaint
الآن نبني كائن `RadialGradientPaint`. المُنشئ يأخذ مركز التدرج، نصف القطر، نقطة التركيز، النسب، الألوان، طريقة الدورة، مساحة اللون، وتحويل اختياري.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **ملاحظة:** يمكن أن يكون `transform` `null` إذا لم تحتاج إلى تحجيم أو دوران إضافي. لا تتردد في تجربة `AffineTransform` لتدرجات مائلة.

### الخطوة 4: ضبط الطلاء وتعبئة المستطيل
بعد تجهيز الطلاء، نخبر `PsDocument` باستخدامه ثم نملأ المستطيل الذي عرّفناه مسبقًا.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

في هذه المرحلة يحتوي صفحة PostScript على مستطيل مملوء بسلاسة بالتدرج الشعاعي الذي ضبطناه.

### الخطوة 5: إغلاق وحفظ المستند
أخيرًا، أغلق الصفحة الحالية واكتب الملف إلى القرص.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

افتح `RadialGradient1_outPS.ps` في أي عارض PostScript (مثل Ghostscript) وسترى التدرج يُعرض تمامًا كما عُرّف.

## المشكلات الشائعة والحلول
| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| يظهر التدرج كلون ثابت | مصفوفة `fractions` لا تبدأ بـ `0.0f` أو لا تنتهي بـ `1.0f` | تأكد أن أول نسبة هي `0.0f` وآخرها `1.0f`. |
| الألوان باهتة | استخدام `ColorSpaceType` غير المناسب | غيّر إلى `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` للحصول على مخرجات أكثر حيوية. |
| لا يتم إنشاء ملف الإخراج | مسار `FileOutputStream` غير صالح أو غير قابل للكتابة | تحقق من وجود `dataDir` وأن التطبيق يملك صلاحيات الكتابة. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page for Java في المشاريع التجارية؟**  
ج: نعم. يلزم الحصول على ترخيص تجاري للاستخدام في بيئة الإنتاج. يمكنك شراء الترخيص من [صفحة ترخيص Aspose](https://purchase.aspose.com/buy).

**س: أين يمكنني العثور على مرجع API الرسمي؟**  
ج: الوثائق الكاملة متاحة [هنا](https://reference.aspose.com/page/java/).

**س: هل تتوفر نسخة تجريبية مجانية للاختبار؟**  
ج: بالتأكيد. حمّل نسخة تجريبية من [صفحة إصدارات Aspose.Page](https://releases.aspose.com/).

**س: كيف أحصل على ترخيص مؤقت للتقييم؟**  
ج: يمكن طلب ترخيص مؤقت [من هنا](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني الحصول على دعم المجتمع؟**  
ج: انضم إلى منتدى مجتمع Aspose.Page على [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## الخاتمة
أنت الآن تعرف **كيفية إضافة تدرج شعاعي** إلى مستند Java PostScript باستخدام Aspose.Page. من خلال تعديل حجم المستطيل، نقاط التوقف اللونية، ونصف قطر التدرج يمكنك إنشاء عدد لا يحصى من التأثيرات البصرية—من ملء خلفيات ناعمة إلى رسومات إضاءة جريئة. لا تتردد في تجربة قيم `AffineTransform` مختلفة لتدوير أو إمالة التدرج، ودمج هذه التقنية مع النصوص والصور للحصول على مخرجات PDF أو EPS أغنى.

---

**آخر تحديث:** 2025-12-08  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}