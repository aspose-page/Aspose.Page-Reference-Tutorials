---
date: 2026-09-04
description: تعلم كيفية إضافة gradient في Java PostScript باستخدام Aspose.Page Java،
  وإنشاء انتقالات لونية قطرية باستخدام LinearGradientPaint للحصول على مستندات حيوية.
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'كيفية إضافة gradient: gradient قطري في Java PostScript باستخدام Aspose.Page
  Java'
og_description: تعلم كيفية إضافة gradient في Java PostScript باستخدام Aspose.Page
  Java. يوضح لك هذا الدليل كيفية إنشاء gradient قطري باستخدام LinearGradientPaint
  في بضع خطوات فقط.
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: كيفية إضافة gradient في Java PostScript باستخدام Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'كيفية إضافة gradient: gradient قطري في Java PostScript باستخدام Aspose.Page
  Java'
url: /ar/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة تدرج قطري في Java PostScript باستخدام Aspose.Page Java

## مقدمة
إذا كنت تبحث عن إضفاء طابع غني على ملف PostScript من خلال انتقال لوني قطري سلس، يجعل **Aspose.Page Java** ذلك سهلًا بشكل مدهش. في هذا الدرس ستتعلم **كيفية إضافة تأثيرات التدرج** خطوة بخطوة، باستخدام الفئة `LinearGradientPaint` من Java 2D. في النهاية ستحصل على مقتطف جاهز للتنفيذ ينشئ مستند PostScript بتدرج قطري نابض بالحياة، وستفهم لماذا هذا النهج أكثر قابلية للصيانة مقارنةً بكتابة أوامر PostScript يدوياً.

## كيفية إضافة تدرج في Java PostScript
إضافة تدرج قد تبدو مهمة تتعلق بالرسومات فقط، ولكن مع Aspose.Page تحصل على تحكم كامل في أوامر PostScript الأساسية مع البقاء في Java النقية. يشرح هذا القسم لماذا يعمل هذا النهج وما الذي ستحصل عليه مقارنةً بكتابة أوامر PostScript يدوياً.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java.  
- **ما الفئة التي تنشئ التدرج؟** `LinearGradientPaint`.  
- **هل يمكنني تغيير الألوان؟** نعم – عدل مصفوفة `Color[]`.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يتطلب ترخيص تجاري؛ يتوفر نسخة تجريبية مجانية.  
- **كم من الوقت تستغرق التنفيذ؟** حوالي 10 دقائق لتدرج أساسي.

## ما هو Aspose.Page Java؟
Aspose.Page Java هو API شامل يتيح للمطورين إنشاء وتحرير وتحويل ملفات PostScript وPDF دون أي برنامج خارجي. تدعم المكتبة **أكثر من 50 تنسيقًا للمدخلات والإخراج** ويمكنها معالجة مستندات **أكثر من 500 صفحة** مع الحفاظ على استهلاك الذاكرة أقل من 100 ميغابايت.

## لماذا نستخدم تدرجًا قطريًا؟
يضيف التدرج القطري عمقًا واهتمامًا بصريًا إلى المخططات، اللافتات، أو أي عنصر رسومي يحتاج إلى مظهر حديث. نظرًا لأن التدرج يمتد من زاوية إلى الزاوية المقابلة، فهو يعمل جيدًا كخلفيات، أغطية الأزرار، والأشكال الزخرفية، مما يمنح مظهرًا احترافيًا دون الحاجة إلى ملفات صور إضافية.

## المتطلبات المسبقة
- Java Development Kit (JDK) 8 أو أعلى.  
- بيئة تطوير متكاملة (IDE) مثل Eclipse أو IntelliJ IDEA أو VS Code.  
- **مكتبة Aspose.Page for Java** – حمّل أحدث نسخة من [صفحة التحميل الرسمية](https://releases.aspose.com/page/java/).

## استيراد الحزم
توفر حزمة `java.awt` الفئات الأساسية للرسومات، بينما تمنحك حزمة `com.aspose.page` الوصول إلى واجهات برمجة التطبيقات الخاصة بـ PostScript.

الفئة `LinearGradientPaint` هي الجسر في Aspose.Page إلى وظائف التدرج في Java 2D.  
`AffineTransform` تمكّن من تدوير وتكبير التدرج بحيث يتماشى قطريًا.

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

## الخطوة 1: إنشاء تدفق إخراج لمستند PostScript
أولاً، حدد المجلد الذي سيُحفظ فيه الملف وافتح `FileOutputStream`. يتلقى هذا التدفق بيانات PostScript المُولدة.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## الخطوة 2: إنشاء خيارات الحفظ بحجم A4
`PsSaveOptions` يتيح لك تحديد حجم الصفحة، الدقة، وإعدادات الإخراج الأخرى. هنا نستخدم حجم A4 الافتراضي، وهو 595 × 842 نقطة بدقة 72 dpi.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## الخطوة 3: إنشاء مستند PS جديد
الفئة `PsDocument` تمثل مستند PostScript وتوفر طرقًا لإنشاء الصفحات ورسم الرسومات.  
أنشئ كائن `PsDocument` باستخدام تدفق الإخراج وخيارات الحفظ. العلامة `false` تخبر المُنشئ بعدم فتح صفحة جديدة تلقائيًا – سنقوم بذلك لاحقًا.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 4: إنشاء مستطيل
حدد المستطيل الذي سيستقبل تعبئة التدرج. تم اختيار موضع المستطيل (200, 100) وحجمه (200 × 100) لجعل التدرج واضحًا.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## الخطوة 5: إنشاء تحويل التدرج
`AffineTransform` يتيح لنا تدوير، تكبير، وتحريك التدرج بحيث يمتد قطريًا عبر المستطيل. تحسب المعادلات أدناه الوتر وتضبط نسبة التكبير وفقًا لذلك.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## الخطوة 6: إنشاء تدرج خطي قطري
`LinearGradientPaint` هي الفئة الأساسية التي تولد انتقال اللون. تمتد من أعلى اليسار للمستطيل إلى أسفل اليمين، باستخدام التحويل المحدد مسبقًا. يضمن `MultipleGradientPaint.CycleMethod.NO_CYCLE` عدم تكرار التدرج.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## الخطوة 7: تعيين اللون وتعبئة المستطيل
طبق لون التدرج على المستند واملأ شكل المستطيل. هذه الخطوة ترسم انتقال اللون القطري على صفحة PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## الخطوة 8: إغلاق الصفحة الحالية وحفظ المستند
أخيرًا، أغلق الصفحة، أفرغ التدفق، واحفظ الملف. يمكن فتح الملف الناتج `DiagonalGradient_outPS.ps` باستخدام أي عارض PostScript.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## المشكلات الشائعة والنصائح
- **التدرج يبدو مسطحًا** – تحقق مرة أخرى من زاوية الدوران؛ تدوير 45° يخلق تدرجًا قطريًا حقيقيًا.  
- **الألوان باهتة** – تأكد من استخدام `MultipleGradientPaint.ColorSpaceType.SRGB` للحصول على تمثيل لوني دقيق.  
- **خطأ ملف غير موجود** – تحقق من أن `dataDir` يشير إلى مجلد موجود وأن التطبيق يمتلك أذونات الكتابة.  
- **المستندات الكبيرة تسبب ارتفاعًا في الذاكرة** – استخدم `PsSaveOptions.setCompress(true)` لتقليل استهلاك الذاكرة.

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذه المكتبة لعمليات رسومية أخرى في Java؟**  
ج: نعم، توفر Aspose.Page for Java مجموعة كاملة من البدائل الرسومية، وعرض النص، وقدرات معالجة الصور.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page Java؟**  
ج: بالتأكيد. يمكنك تنزيل نسخة تجريبية كاملة الوظائف من [صفحة التجربة المجانية لـ Aspose](https://releases.aspose.com/).

**س: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page Java؟**  
ج: المرجع الرسمي لواجهة البرمجة متاح على [مرجع Aspose.Page Java API](https://reference.aspose.com/page/java/).

**س: كيف يمكنني شراء ترخيص لـ Aspose.Page Java؟**  
ج: يمكن شراء التراخيص مباشرة من [بوابة شراء Aspose](https://purchase.aspose.com/buy).

**س: هل تحتاج إلى مساعدة أو لديك أسئلة؟**  
ج: زر منتدى [Aspose.Page المجتمعي](https://forum.aspose.com/c/page/39) للحصول على مساعدة من مهندسي Aspose والمطورين الآخرين.

---

**آخر تحديث:** 2026-09-04  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (latest)  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء تدرج شعاعي في PostScript باستخدام Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [كيفية إضافة تدرج في Java PostScript باستخدام Linear Gradient Paint](/page/java/postscript-gradient-addition/horizontal/)
- [إنشاء تدرج PostScript في Java – إضافة تدرج عمودي](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}