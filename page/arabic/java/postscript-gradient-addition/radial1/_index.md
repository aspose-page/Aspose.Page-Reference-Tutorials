---
date: 2026-09-09
description: تعلم كيفية إنشاء radial gradient في Java PostScript باستخدام Aspose.Page.
  يوضح لك هذا الدليل خطوة بخطوة كيفية إضافة color stops gradient، ضبط radii، وإنشاء
  ملف PS بسرعة.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: إتقان radial gradients في Java
og_description: تعلم كيفية إنشاء radial gradient في Java PostScript باستخدام Aspose.Page.
  يشرح هذا الدليل كيفية إضافة color stops gradient، ضبط radii، وإنشاء ملف PS خلال
  دقائق.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: كيفية إنشاء radial gradient في Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: كيفية إنشاء radial gradient في Java PostScript
url: /ar/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء تدرج شعاعي في Java PostScript باستخدام Aspose.Page

## المقدمة
إذا كنت بحاجة إلى **إنشاء تدرج شعاعي** داخل ملف PostScript، فأنت في المكان الصحيح. في هذا الدرس سنستعرض كل خطوة مطلوبة لتوليد مستند PostScript يحتوي على تدرج شعاعي ناعم، باستخدام **Aspose.Page for Java**. في النهاية ستفهم الـ API، وترى مثالًا كاملاً قابلًا للتنفيذ، وتعرف كيف تعدّل الألوان، المواقع، ونصف القطر لأي سيناريو تصميم.

## إجابات سريعة
- **ما المكتبة التي تنشئ تدرجات شعاعية في PostScript؟** Aspose.Page for Java.  
- **كم يستغرق تنفيذ ذلك؟** حوالي 10‑15 دقيقة للمثال الأساسي.  
- **هل أحتاج إلى رخصة لتشغيل الكود؟** نسخة تجريبية مجانية تكفي للتطوير؛ يلزم الحصول على رخصة تجارية للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أعلى.  
- **هل يمكنني تغيير شكل التدرج؟** نعم – عدّل نصف القطر ونقطة المركز في مُنشئ `RadialGradientPaint`.

## كيفية إنشاء تدرج شعاعي في Java

حمّل مشروع Java الخاص بك، استورد الفئات المطلوبة، واتبع الدليل خطوة بخطوة أدناه. الجواب الأساسي هو أنك تنشئ كائن `RadialGradientPaint` مع نقاط الألوان ثم تطبّقه على مستطيل مرسوم على `PsDocument`. هذه المقاربة ذات الكائنين تتولى جميع أوامر PostScript منخفضة المستوى نيابةً عنك.

## ما هو التدرج الشعاعي؟
`RadialGradientPaint` هي فئة من Java AWT تُعرّف انتقالًا لونيًا دائريًا من نقطة مركزية إلى الخارج. تُنشئ مزيجًا ناعمًا من عدة نقاط لون، مما يجعلها مثالية للأضواء المسلطة، الخلفيات الناعمة، أو أي تأثير حيث تتشع الألوان من نقطة محورية.

## لماذا نستخدم Aspose.Page للتدرجات الشعاعية؟
Aspose.Page يمنحك تحكمًا برمجيًا كاملاً في مخرجات PostScript بينما يتولى العبء الثقيل للتركيب النحوي منخفض المستوى. يدعم **أكثر من 50 تنسيقًا للإدخال والإخراج**، ويمكنه معالجة مستندات مئات الصفحات دون تحميل الملف بالكامل في الذاكرة، ويعمل على أي نظام تشغيل يدعم Java 8+. هذه القدرة الكمية تجعل منه خيارًا موثوقًا لتوليد الرسومات على مستوى المؤسسات.

## المتطلبات المسبقة
- **Java Development Kit (JDK) 8+** – تحقق باستخدام `java -version`.  
- **Aspose.Page for Java** – حمّل أحدث JAR من [صفحة تحميل Aspose.Page الرسمية](https://releases.aspose.com/page/java/).  
- **IDE من اختيارك** – Eclipse، IntelliJ IDEA، أو VS Code مع ملحقات Java.  
- **مجلد قابل للكتابة** – حيث سيتم حفظ ملف `.ps` المُولَّد.

## استيراد الحزم
أولاً، استورد الفئات التي سنحتاجها. حزمة `java.awt` توفر كائنات طلاء التدرج، بينما تحتوي `com.aspose.eps` على فئات معالجة مستندات PostScript.

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
`PsDocument` هي فئة Aspose.Page التي تمثّل مستند PostScript وتوفر طرقًا لرسم الأشكال والنصوص والصور. نبدأ بإنشاء تدفق إخراج، ضبط حجم الصفحة (A4 افتراضيًا)، وتعريف مستطيل سيستضيف التدرج.

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

> **نصيحة احترافية:** عدّل إحداثيات المستطيل (`200, 100, 200, 200`) لتحديد موقع التدرج في أي مكان على الصفحة.

### الخطوة 2: تعريف الألوان والنسب
يُبنى التدرج الشعاعي من *نقاط اللون* (الألوان) و*النسب* (المواقع النسبية لتلك النقاط). هنا ننشئ مصفوفة من ستة ألوان ونسبها المقابلة.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **لماذا هذا مهم:** من خلال تعديل `fractions` تتحكم في سرعة انتقال الألوان، مما يتيح تأثيرات دقيقة أو دراماتية.

### الخطوة 3: إنشاء طلاء تدرج شعاعي
`RadialGradientPaint` هي الفئة الأساسية التي تصف تدرجًا لونيًا شعاعيًا، بما في ذلك نقطة المركز، نصف القطر، نقطة التركيز، النسب، الألوان، طريقة الدورة، ومساحة اللون. الآن نبني كائن `RadialGradientPaint` باستخدام المصفوفات المعرفة أعلاه.

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

في هذه المرحلة تحتوي صفحة PostScript على مستطيل مملوء بسلاسة بالتدرج الشعاعي الذي ضبطناه.

### الخطوة 5: إغلاق وحفظ المستند
أخيرًا، أغلق الصفحة الحالية واكتب الملف إلى القرص.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

افتح `RadialGradient1_outPS.ps` في أي عارض PostScript (مثل Ghostscript) وسترى التدرج مُظهرًا كما عُرِّف.

## المشكلات الشائعة والحلول
| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| التدرج يظهر كلون صلب | مصفوفة `fractions` لا تبدأ بـ `0.0f` أو لا تنتهي بـ `1.0f` | تأكد من أن أول نسبة هي `0.0f` وآخرها `1.0f`. |
| الألوان تبدو باهتة | استخدام `ColorSpaceType` الخطأ | غيّر إلى `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` للحصول على إخراج أكثر حيوية. |
| لم يتم إنشاء ملف الإخراج | مسار `FileOutputStream` غير صالح أو غير قابل للكتابة | تحقق من وجود `dataDir` وأن التطبيق لديه أذونات الكتابة. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page for Java في المشاريع التجارية؟**  
ج: نعم. يتطلب الاستخدام في الإنتاج رخصة تجارية. يمكنك شراء واحدة من [صفحة ترخيص Aspose](https://purchase.aspose.com/buy).

**س: أين يمكنني العثور على مرجع الـ API الرسمي؟**  
ج: الوثائق الكاملة متاحة في [مرجع Aspose.Page Java API](https://reference.aspose.com/page/java/).

**س: هل تتوفر نسخة تجريبية مجانية للاختبار؟**  
ج: بالتأكيد. حمّل نسخة تجريبية من [صفحة إصدارات Aspose.Page](https://releases.aspose.com/).

**س: كيف أحصل على رخصة مؤقتة للتقييم؟**  
ج: يمكن طلب رخصة مؤقتة من [صفحة طلب الرخصة المؤقتة](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني الحصول على دعم المجتمع؟**  
ج: انضم إلى منتدى مجتمع Aspose.Page على [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## الخاتمة
أنت الآن تعرف **كيفية إنشاء تدرج شعاعي** في مستند Java PostScript باستخدام Aspose.Page. من خلال تعديل حجم المستطيل، نقاط اللون، ونصف قطر التدرج يمكنك إنشاء عدد لا يحصى من التأثيرات البصرية—من تعبئة خلفيات ناعمة إلى رسومات إضاءة جريئة. لا تتردد في تجربة قيم `AffineTransform` مختلفة لتدوير أو إمالة التدرج، ودمج هذه التقنية مع النصوص والصور للحصول على مخرجات PDF أو EPS أغنى.

---

**آخر تحديث:** 2026-09-09  
**تم الاختبار مع:** Aspose.Page for Java أحدث نسخة (حسب كتابة هذه الوثيقة)  
**المؤلف:** Aspose

## دروس ذات صلة

- [Fill Shape with Gradient: Java PostScript Radial Example](/page/java/postscript-gradient-addition/radial2/)
- [Create PostScript Gradient in Java – Add Vertical Gradient](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page Transparency Tutorial – Add Transparency in Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}