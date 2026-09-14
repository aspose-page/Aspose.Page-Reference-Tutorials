---
date: 2026-09-14
description: تعلم كيفية إنشاء تدرج postscript java باستخدام Aspose.Page. يوضح لك هذا
  الدليل خطوة بخطوة كيفية إضافة vertical gradient إلى ملف PostScript في بضع أسطر من
  كود Java فقط.
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: إضافة Vertical Gradient في Java PostScript
og_description: تعلم كيفية إنشاء تدرج postscript java باستخدام Aspose.Page. يوضح لك
  هذا الدليل خطوة بخطوة كيفية إضافة vertical gradient إلى ملف PostScript في بضع أسطر
  من كود Java فقط.
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: إنشاء تدرج postscript java – vertical gradient
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: إنشاء تدرج postscript java – vertical gradient
url: /ar/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء تدرج بوستسكريبت جافا – تدرج عمودي

## مقدمة
Aspose.Page for Java هي مكتبة تمكّن من إنشاء ومعالجة ملفات PostScript و PDF برمجياً. في هذا الدرس الشامل ستتعلم كيفية **create postscript gradient java** باستخدام تلك المكتبة. إضافة تدرج عمودي يمكن أن يجعل مستنداتك أكثر حيوية واحترافية، ومع بضع أسطر من الشيفرة يمكنك تحقيق تأثيرات بصرية مذهلة. سنرشدك خلال كل خطوة، نشرح لماذا كل جزء مهم، ونقدم لك نصائح عملية لتجنب الأخطاء الشائعة. بنهاية هذا الدليل ستكون قادرًا على توليد ملفات PostScript ذات انتقالات لونية عمودية سلسة وجذابة.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **هل يمكنني تخصيص الألوان؟** نعم، any `java.awt.Color` can be used  
- **هل يدعم الدوران؟** نعم، you can rotate the gradient with an `AffineTransform`  
- **ما صيغة الإخراج المنتجة؟** A standard PostScript (.ps) file  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، a commercial license is required  

## لماذا إضافة تدرج عمودي إلى مستند PostScript؟
إضافة تدرج عمودي يمنح صفحاتك عمقًا، ويحسن التسلسل البصري، ويحافظ على حجم الملف منخفضًا لأن التدرج يُعرّف بصيغة متجهة بدلاً من الصور النقطية. هذه التقنية مثالية لعناوين التقارير، الأدلة التقنية، أو أي نشرة تحتاج إلى مظهر حديث دون التضحية بالقابلية للتوسع.

## المتطلبات المسبقة
قبل الغوص في الدرس، تأكد من توفر المتطلبات التالية:
- Java Development Kit (JDK) مثبت على جهازك.  
- مكتبة Aspose.Page for Java. يمكنك تنزيلها من [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).

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

الآن، دعنا نتبع عملية إضافة تدرج عمودي خطوة بخطوة.

## كيفية إنشاء تدرج بوستسكريبت جافا
حمّل بيئة Java الخاصة بك، أنشئ كائن `PsSaveOptions`، واستدعِ `Document.save` – هذه هي السلسلة الأساسية التي تنشئ ملف PostScript مع تدرج عمودي. تتولى الـ API معالجة استيفاء الألوان، وتحويلات الإحداثيات، وتفريغ الصفحة لك، لذا عليك فقط التركيز على تعريف المستطيل ومعلمات التدرج.

### الخطوة 1: إعداد دليل المستند الخاص بك
`File` تمثل المجلد الذي سيُكتب فيه الناتج. يجب أن يكون الدليل موجودًا قبل فتح الدفق، وإلا سيتم رمي `IOException`.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### الخطوة 2: إنشاء تدفق إخراج لمستند PostScript
`FileOutputStream` يكتب بيانات PostScript الثنائية إلى القرص. استخدام كتلة `try‑with‑resources` يضمن إغلاق التدفق حتى إذا حدث استثناء.
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### الخطوة 3: إنشاء خيارات الحفظ بحجم A4
`PsSaveOptions` يتيح لك تحديد حجم الصفحة، DPI، وما إذا كان يجب تضمين الخطوط. ضبط الحجم إلى A4 (595 × 842 نقطة) يتطابق مع معظم المستندات القابلة للطباعة.
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### الخطوة 4: إنشاء مستند PS جديد
`Document` هو الكائن الأعلى مستوى الذي يمثل ملف PostScript واحد في الذاكرة. جميع أوامر الرسم تُصدر ضد هذا الكائن.
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### الخطوة 5: إنشاء مستطيل
`Rectangle2D.Double` يحدد المنطقة التي سيُملأها التدرج. إحداثيات المستطيل تُعبّر بالنقاط (1 نقطة = 1/72 بوصة).
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### الخطوة 6: إعداد الألوان والنسب للتدرج
مصفوفة `float[]` تحدد موضع كل نقطة لون (من 0.0 إلى 1.0). كائنات `Color` تحتفظ بالقيم الفعلية لـ RGB. يمكنك استخدام أي `java.awt.Color` ترغب به.
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### الخطوة 7: إنشاء تحويل التدرج
`AffineTransform` يقيّم ويُدوّر التدرج. للحصول على تدرج عمودي نقي، تحتاج فقط إلى تكبير محور Y؛ يمكن إضافة الدوران لاحقًا إذا رغبت.
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### الخطوة 8: إنشاء تلوين تدرج خطي عمودي
`LinearGradientPaint` يربط بين المستطيل، نقاط اللون، والتحويل. يتم تمرير هذا الكائن لاحقًا إلى سياق الرسومات.
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### الخطوة 9: تعيين اللون وتعبئة المستطيل
`Graphics2D.setPaint` يطبق التدرج، و`fill` يرسمه داخل المستطيل الذي حددته مسبقًا.
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### الخطوة 10: إغلاق الصفحة الحالية وحفظ المستند
استدعاء `document.save` يكتب كامل تدفق PostScript إلى ملف الإخراج ويحرّر جميع الموارد الأصلية.
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

تهانينا! لقد أضفت بنجاح تدرجًا عموديًا إلى مستند PostScript الخاص بك في Java باستخدام Aspose.Page for Java.

## المشكلات الشائعة والحلول
- **التدرج يبدو مسطحًا:** تأكد من أن مقياس `AffineTransform` يطابق أبعاد المستطيل.  
- **الألوان باهتة:** تحقق من أنك تستخدم `ColorSpaceType` الصحيح (SRGB) وأن مصفوفة النسب مرتبة من 0.0 إلى 1.0.  
- **الملف غير مُنشأ:** افحص أن دليل الإخراج (`dataDir`) موجود وأن التطبيق يمتلك أذونات الكتابة.  

## الأسئلة المتكررة
**س: هل يمكنني استخدام Aspose.Page for Java مع مكتبات Java الأخرى؟**  
ج: نعم، Aspose.Page for Java صُممت للعمل بسلاسة جنبًا إلى جنب مع مكتبات Java الأخرى مثل Apache Commons أو Spring.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page for Java؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية [free trial download page](https://releases.aspose.com/).

**س: أين يمكنني العثور على وثائق إضافية؟**  
ج: الوثائق التفصيلية متاحة [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**س: كيف يمكنني شراء Aspose.Page for Java؟**  
ج: يمكنك شراء Aspose.Page for Java من [Aspose.Page purchase page](https://purchase.aspose.com/buy).

**س: هل هناك منتدى لمناقشات Aspose.Page؟**  
ج: نعم، يمكنك الانضمام إلى منتدى المجتمع [Aspose.Page community forum](https://forum.aspose.com/c/page/39).

## أسئلة متكررة إضافية
**س: هل يمكنني إنشاء اتجاهات تدرج أخرى (أفقي، قطري)؟**  
ج: بالتأكيد. عدّل نقاط البداية والنهاية في `LinearGradientPaint` وعدّل زاوية الدوران في `AffineTransform`.

**س: هل يعمل هذا مع إخراج PDF أيضًا؟**  
ج: يمكن تطبيق نفس منطق التدرج عند الحفظ إلى PDF باستخدام `PdfSaveOptions` بدلاً من `PsSaveOptions`.

**س: كيف يمكنني تغيير حجم التدرج ديناميكيًا؟**  
ج: احسب أبعاد المستطيل أثناء التشغيل ومرّر تلك القيم إلى كل من مُنشئ `Rectangle2D` و`AffineTransform`.

---

**آخر تحديث:** 2026-09-14  
**تم الاختبار مع:** Aspose.Page for Java 24.11 (latest)  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء تدرج شعاعي في PostScript باستخدام Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [كيفية تحويل PostScript إلى PDF باستخدام Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [دروس شفافية Aspose.Page – إضافة شفافية في Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}