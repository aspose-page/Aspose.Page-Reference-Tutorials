---
date: 2026-08-23
description: تعلم كيفية استخدام aspose.page لمعالجة الصور في Java لإدراج وتدوير الصور
  في ملفات PostScript مع أمثلة Java واضحة
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: إضافة صورة في PostScript باستخدام Java
og_description: تعلم كيفية استخدام aspose.page لمعالجة الصور في Java لإدراج وتدوير
  الصور في ملفات PostScript، مع أمثلة شفرة Java خطوة بخطوة
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: كيفية استخدام aspose.page لمعالجة الصور في Java لإضافة صورة
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: كيفية استخدام aspose.page لمعالجة الصور في Java لإضافة صورة
url: /ar/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استخدام aspose.page image manipulation java لإضافة صورة

## مقدمة
في هذا الدرس ستتعلم كيفية **use aspose.page image manipulation java** لإنشاء ملفات PostScript، وإدراج صور نقطية، وتطبيق تحويلات الترجمة والدوران. بنهاية الدليل ستكون قادرًا على توليد مخرجات PostScript دقيقة البكسل من Java—مثالية للتقارير الآلية، خطوط طباعة، أو أي سير عمل يتطلب وضعًا دقيقًا للصور داخل مستند PostScript.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **هل يمكنني إضافة صور متعددة؟** نعم – كرّر خطوات التحويل والرسم لكل صورة  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تعمل للاختبار؛ الترخيص مطلوب للإنتاج  
- **ما نسخة Java المدعومة؟** Java 8 وما بعدها  
- **هل يدعم تدوير الصورة؟** بالتأكيد – استخدم `AffineTransform.rotate()`

## ما هو aspose.page image manipulation java؟
`aspose.page image manipulation java` هو API من Aspose.Page يتيح لك بناء وتحرير وعرض مستندات PostScript برمجيًا من خلال كود Java، بما في ذلك التحكم الكامل في وضع الصورة، وتكبيرها، وتدويرها. باستخدام هذا API تتجنب صsyntax PostScript منخفض المستوى وتدع المكتبة تتعامل مع تحويل الصيغ والإدراج داخليًا.

## لماذا تستخدم aspose.page لمعالجة الصور؟
توفر Aspose.Page **50+ image formats** (بما في ذلك JPEG، PNG، BMP، TIFF) ويمكنها إدراجها في PostScript دون تحميل المستند بالكامل في الذاكرة، مما يتيح معالجة ملفات تحتوي على مئات الصفحات مع الحفاظ على استهلاك الذاكرة أقل من 100 MB على خادم نموذجي. API عالي المستوى يبسط أوامر PostScript المعقدة، لذا تكتب كود Java مختصر بدلاً من أوامر PS الخام.

## المتطلبات المسبقة
- Java Development Kit (JDK) 8 أو أحدث مثبت.  
- مكتبة Aspose.Page for Java – قم بتنزيلها من **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**.  
- إلمام أساسي بصياغة Java والبرمجة الكائنية.

## ما هو create postscript java؟
إنشاء ملف PostScript من Java يعني توليد مستند `.ps` برمجيًا يصف تخطيط الصفحة، الرسومات المتجهة، والصور النقطية باستخدام لغة PostScript. تقوم Aspose.Page بترجمة استدعاءات Java إلى تعليمات PostScript صالحة، مما يتيح لك إنتاج ملفات جاهزة للطباعة دون الحاجة إلى مفسر PostScript منفصل.

## كيفية إضافة صورة مع الترجمة والدوران خطوة بخطوة
حمّل صورتك، طبّق `AffineTransform`، وارسمها على الصفحة. الخطوات التالية توضح التسلسل الدقيق الذي يجب اتباعه.

### الخطوة 1: حفظ حالة الرسومات
حفظ حالة الرسومات يعزل التحويلات الخاصة بك حتى يمكنك الرجوع لاحقًا. هذا يعادل المشغل `gsave` في PostScript الخام.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### الخطوة 2: الترجمة والتحويل (ترجمة وتدوير الصورة)
أولاً، أنشئ `BufferedImage` من الملف المصدر، ثم أنشئ `AffineTransform` يترجم الصورة إلى الإحداثيات المطلوبة ويدورها حول مركزها. `AffineTransform.rotate` يتوقع زاوية بالراديان، لذا حوّل الدرجات باستخدام `Math.toRadians(degrees)`.

**AffineTransform** هو صف Java يمثل تحويلًا إحداثيًا ثنائي الأبعاد مثل الترجمة أو الدوران أو التحجيم أو القص.  
**BufferedImage** هو صف Java يخزن الصورة في الذاكرة كشبكة من البكسلات.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### الخطوة 3: إضافة صورة إلى المستند
بعد تكوين التحويل، ارسم الصورة على الصفحة الحالية. تقوم المكتبة تلقائيًا بتحويل `BufferedImage` إلى تدفق صورة PostScript مناسب.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### الخطوة 4: استعادة حالة الرسومات
استدعاء الاستعادة (`grestore`) يعيد حالة الرسومات إلى ما كانت عليه قبل الحفظ، مما يضمن أن أوامر الرسم اللاحقة لا تتأثر بالتحويل السابق.

```java
document.drawImage(image, transform, null);
```

### الخطوة 5: إغلاق الصفحة الحالية وحفظها
أكمل الصفحة، أغلق المستند، واكتب ملف الإخراج إلى القرص.

```java
document.writeGraphicsRestore();
```

يمكنك تكرار التسلسل أعلاه لإدراج صور إضافية، مع تعديل إحداثيات الترجمة وزاوية الدوران في كل مرة.

## المشكلات الشائعة والحلول
- **FileNotFoundException:** تحقق من أن `dataDir` ينتهي بفاصل ملف (`/` أو `\\`) وأن اسم ملف الصورة يطابق تمامًا.  
- **ImageIO.read returns null:** تأكد من أن تنسيق الصورة من القائمة المدعومة (JPEG، PNG، BMP، GIF، TIFF).  
- **Incorrect rotation angle:** `AffineTransform.rotate` يعمل بالراديان؛ استخدم `Math.toRadians(degrees)` للتحويل من الدرجات.  
- **Memory spikes on large pages:** استخدم `Document.save` مع `saveOptions.setCompress(true)` لتقليل استهلاك الذاكرة.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page for Java مع لغات برمجة أخرى؟**  
ج: المكتبة الأساسية مخصصة لـ Java فقط، لكن Aspose توفر واجهات برمجة تطبيقات مكافئة لـ .NET و C++ و Python، كلٌ مخصص لمنصته.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page for Java؟**  
ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية **[Aspose.Page free trial page](https://releases.aspose.com/)**.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟**  
ج: يمكنك الحصول على ترخيص مؤقت عبر **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

**س: أين يمكنني العثور على دعم المجتمع والنقاشات المتعلقة بـ Aspose.Page for Java؟**  
ج: زر **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** للحصول على مساعدة المجتمع.

**س: هل هناك موارد إضافية لشراء Aspose.Page for Java؟**  
ج: يمكنك شراء المكتبة عبر **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.

## الخلاصة
الآن لديك مثال كامل من البداية إلى النهاية لـ **aspose.page image manipulation java** ينشئ ملف PostScript، يترجم ويُدوّر صورة، ويحفظ النتيجة. استكشف **[documentation](https://reference.aspose.com/page/java/)** الكامل لاكتشاف الميزات المتقدمة مثل الرسومات المتجهة، أحجام الصفحات المخصصة، وعرض النص.

---

**آخر تحديث:** 2026-08-23  
**تم الاختبار مع:** Aspose.Page for Java 23.11  
**المؤلف:** Aspose  

```java
document.closePage();
document.save();
```

## دروس ذات صلة

- [كيفية تحويل PostScript إلى PDF باستخدام Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [كيفية إضافة تدرج: تدرج قطري في Java PostScript باستخدام Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [كيفية إضافة نمط تظليل في Java PostScript باستخدام Aspose.Page](/page/java/postscript-hatch-patterns/add-hatch-pattern/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}