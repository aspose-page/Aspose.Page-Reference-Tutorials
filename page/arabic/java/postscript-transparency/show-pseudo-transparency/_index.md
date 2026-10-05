---
date: 2026-10-04
description: تعلم كيفية إنشاء شفافية زائفة في Java باستخدام Aspose.Page. اتبع دليلنا
  خطوة بخطوة لإضافة رسومات حيوية في ملفات PostScript.
keywords:
- create pseudo transparency java
- Aspose.Page Java
- PostScript pseudo transparency
lastmod: 2026-10-04
linktitle: عرض الشفافية الزائفة في Java PostScript
og_description: أنشئ شفافية زائفة في Java باستخدام Aspose.Page لتوليد رسومات PostScript
  حيوية. يوضح لك هذا الدليل خطوات الإعداد، والشفرة، وحل المشكلات في دقائق.
og_image_alt: Aspose.Page Java tutorial showing pseudo transparency in PostScript
og_title: دليل إنشاء شفافية زائفة في Java باستخدام Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to create pseudo transparency java using Aspose.Page. Follow
    our step‑by‑step guide to add vibrant graphics in PostScript files.
  headline: How to create pseudo transparency java with Aspose.Page
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java is available for commercial use. You can purchase
      a license **[purchase Aspose.Page license](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: Yes, you can get a free trial **[download free trial](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Detailed documentation is available **[Aspose.Page Java documentation](https://reference.aspose.com/page/java/)**.
    question: Where can I find additional documentation?
  - answer: You can obtain a temporary license **[temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for testing purposes?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**.
    question: Need help or want to discuss Aspose.Page?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- pseudo transparency
- Aspose.Page
- Java PostScript
title: كيفية إنشاء شفافية زائفة في Java باستخدام Aspose.Page
url: /ar/java/postscript-transparency/show-pseudo-transparency/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# الشفافية الزائفة في Java PostScript باستخدام Aspose.Page

## مقدمة
في هذا الدرس الشامل ستقوم **إنشاء شفافية زائفة java** رسومات باستخدام Aspose.Page for Java. سنستعرض كل شيء — من تثبيت المكتبة إلى رسم مستطيلين متداخلين يحاكيان الشفافية في ملف PostScript. في النهاية ستعرف لماذا تعتبر الشفافية الزائفة مهمة، وكيفية تنفيذها، وكيفية تعديل الألوان والتدرجات لتصاميمك الخاصة.

## إجابات سريعة
- **ماذا يعني الشفافية الزائفة؟** إنها تحاكي الشفافية عن طريق دمج التدرجات شبه الشفافة.
- **ما المكتبة المطلوبة؟** Aspose.Page for Java.
- **هل أحتاج إلى ترخيص لتشغيل المثال؟** النسخة التجريبية المجانية تعمل للتطوير؛ يلزم ترخيص تجاري للإنتاج.
- **ما بيئة التطوير المتكاملة التي يمكنني استخدامها؟** أي IDE للـ Java (IntelliJ IDEA, Eclipse, VS Code) يدعم Java 8+.
- **كم من الوقت تستغرق التنفيذ؟** حوالي 10‑15 دقيقة لمثال أساسي.

## ما هي الشفافية الزائفة في Java PostScript؟
الشفافية الزائفة هي تقنية تستخدم تعبئات تدرجية شبه شفافة لإعطاء تأثير بصري كأن الأشياء شفافة. لأن PostScript التقليدي لا يدعم قنوات ألفا الحقيقية، تقوم Aspose.Page بمحاكاة ذلك عن طريق تراكب أشكال شفافة. من خلال تعديل قيم شفافية التدرج، يمكنك محاكاة درجات مختلفة من الشفافية دون الحاجة إلى دعم ألفا أصلي.

## لماذا نستخدم Aspose.Page للشفافية الزائفة؟
يدعم Aspose.Page **أكثر من 30 تنسيق إخراج** (بما في ذلك EPS, PDF, SVG, و PNG) ويمكنه عرض مستندات مئات الصفحات دون تحميل الملف بالكامل في الذاكرة. توفر واجهة برمجة التطبيقات Java المتعددة المنصات تحكمًا دقيقًا في الألوان والشفافية واتجاه التدرج، مما يضمن نتائج متسقة على أي طابعة أو عارض.

## المتطلبات المسبقة
- معرفة أساسية بـ Java.  
- الإلمام بمفاهيم PostScript.  
- مكتبة Aspose.Page for Java مثبتة. إذا لم تقم بتنزيلها بعد، احصل عليها **[download Aspose.Page for Java](https://releases.aspose.com/page/java/)**.  
- بيئة تطوير Java IDE أو أداة بناء (Maven/Gradle) جاهزة.

## استيراد الحزم
توفر الاستيرادات التالية إمكانية الوصول إلى الألوان، التدرجات، وكائن مستند PostScript.

الفئة `PsDocument` هي الكائن الأعلى مستوى في Aspose.Page الذي يمثل ملف PostScript في الذاكرة.  

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

## الخطوة 1: إنشاء مستند ps
أولاً، نقوم بإنشاء تدفق إخراج ونُهيئ كائن `PsDocument` جديد. يعمل هذا الكائن كقماش لجميع عمليات الرسم اللاحقة.

يأخذ مُنشئ `PsDocument` كلاً من `OutputStream` و `PageSize` لتحديد سطح الرسم.  

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "ShowPseudoTransparency_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 2: تعريف مستطيل بتعبئة تدرج غير شفاف
نرسم المستطيل الأول باستخدام تدرج غير شفاف بالكامل. سيعمل هذا كخلفية للطبقة الشفافة الزائفة لدينا.

الفئة `LinearGradientBrush` توفر طريقة لتعبئة الأشكال بتدرجات لونية خطية.  
الفئة `LinearGradientBrush` تنشئ فرشاة تدرج؛ معلمات `Color` الخاصة بها تقبل قيم RGBA حيث تتحكم القيمة الرابعة (alpha) في الشفافية.  

```java
float offsetX = 50;
float offsetY = 100;
float width = 200;
float height = 100;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create opaque gradient fill
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0), new Color(40, 128, 70)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## الخطوة 3: تعريف مستطيل بتعبئة تدرج شفاف
بعد ذلك، نضع مستطيلًا ثانيًا يستخدم تدرجًا بقيم ألفا. هذا يخلق تأثير **الشفافية الزائفة** عندما يتداخل مع الشكل الأول.

المُنشئ `Color` ينشئ لونًا بمكونات الأحمر، الأخضر، الأزرق، والألفا.  
المُنشئ `new Color(r, g, b, a)` يتيح لك تحديد قناة الألفا (0‑255)، حيث القيم الأقل تزيد الشفافية.  

```java
offsetX = 350;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create translucent gradient fill
paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## الخطوة 4: إغلاق الصفحة وحفظ المستند
أخيرًا، نقوم بإغلاق الصفحة الحالية وكتابة ملف PostScript إلى القرص.

طريقة `save` تكتب محتويات المستند إلى تدفق الإخراج المقدم.  
استدعاء `psDocument.save(outputStream)` يُنهي الملف ويفرغ جميع أوامر الرسم إلى التدفق الأساسي.  

```java
document.closePage();
document.save();
```

## المشكلات الشائعة & استكشاف الأخطاء
- **FileNotFoundException** – تحقق من أن `dataDir` يشير إلى مجلد موجود وأن تطبيقك يمتلك أذونات الكتابة.  
- **Incorrect colors** – تأكد من أنك تستخدم المُنشئ `Color(int r, int g, int b, int a)` للألوان الشفافة؛ المعامل الرابع هو الألفا (0‑255).  
- **Gradient not visible** – تحقق من أن معلمات `AffineTransform` تُطابق التدرج بشكل صحيح مع أبعاد المستطيل.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page for Java في المشاريع التجارية؟**  
نعم، Aspose.Page for Java متاح للاستخدام التجاري. يمكنك شراء ترخيص **[purchase Aspose.Page license](https://purchase.aspose.com/buy)**.

**س: هل هناك نسخة تجريبية مجانية متاحة؟**  
نعم، يمكنك الحصول على نسخة تجريبية مجانية **[download free trial](https://releases.aspose.com/)**.

**س: أين يمكنني العثور على وثائق إضافية؟**  
توفر وثائق مفصلة **[Aspose.Page Java documentation](https://reference.aspose.com/page/java/)**.

**س: كيف يمكنني الحصول على ترخيص مؤقت لأغراض الاختبار؟**  
يمكنك الحصول على ترخيص مؤقت **[temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/)**.

**س: هل تحتاج إلى مساعدة أو ترغب في مناقشة Aspose.Page؟**  
قم بزيارة **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**.

---

**آخر تحديث:** 2026-10-04  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (latest)  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء تدرج شعاعي في PostScript باستخدام Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [إنشاء نمط نسيج في PostScript باستخدام Aspose.Page for Java](/page/java/postscript-texture-patterns/)
- [كيفية تحويل PostScript إلى PDF باستخدام Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}