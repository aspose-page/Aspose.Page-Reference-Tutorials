---
date: 2026-09-09
description: تعلم كيفية إنشاء تدرج لوني في Java PostScript وإضافة تدرج إلى الشكل باستخدام
  Aspose.Page. اتبع هذا الدليل خطوة بخطوة مع الشيفرة والنصائح.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Java PostScript Radial Gradient مع Aspose.Page
og_description: تعلم كيفية إنشاء تدرج لوني في Java PostScript وإضافة تدرج إلى الشكل
  باستخدام Aspose.Page. اتبع هذا الدليل خطوة بخطوة مع الشيفرة والنصائح.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: كيفية إنشاء تدرج لوني في Java PostScript مع radial fill
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: كيفية إنشاء تدرج لوني في Java PostScript مع radial fill
url: /ar/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء تدرج لوني في Java PostScript مع تعبئة شعاعية

## مقدمة
في هذا الدرس ستتعلم **كيفية إنشاء تدرج لوني** في مستند PostScript باستخدام Java و Aspose.Page. سنستعرض كل خطوة — من إعداد المشروع إلى رسم دائرة مملوءة بتدرج شعاعي سلس — حتى تتمكن من **إضافة تدرج إلى الشكل** فورًا وتحسين جودة الرسومات في تطبيقات Java الخاصة بك.

## إجابات سريعة
- **ما الذي ينشئه هذا الدرس؟** ملف PostScript (`.ps`) يحتوي على دائرة مملوءة بتدرج شعاعي.  
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (الإصدار الأحدث).  
- **كم من الوقت تستغرق عملية التنفيذ؟** تقريبًا 10‑15 دقيقة للحصول على مثال يعمل.  
- **هل أحتاج إلى ترخيص؟** يلزم الحصول على ترخيص مؤقت أو كامل للاستخدام في الإنتاج؛ النسخة التجريبية المجانية تكفي للتطوير.  
- **هل يمكن إعادة استخدام الكود لـ PDF أو SVG؟** نعم — يدعم Aspose.Page صيغ إخراج متعددة مع تغييرات قليلة.

## كيفية تعبئة الشكل بتدرج في PostScript
يمكنك تعبئة شكل بتدرج شعاعي في PostScript عن طريق إنشاء `PsDocument`، وتعريف `RadialGradientPaint`، وتطبيقه على الشكل المستهدف، ثم حفظ المستند. يتيح لك هذا سير العمل المختصر إنتاج رسومات متجهة ذات مظهر احترافي دون الحاجة إلى صور نقطية، ويمكن إعادة استخدام نفس الكود لإخراج PDF أو SVG. العملية بسيطة وتعمل بشكل ثابت عبر جميع الصيغ المدعومة.

## ما هو التدرج الشعاعي؟
التدرج الشعاعي يغيّر الألوان من نقطة مركزية إلى الخارج، مُنشئًا مزيجًا دائريًا ناعمًا. إنه مثالي للإضاءات، خلفيات الأزرار، أو أي عنصر بصري يحتاج إلى تأثير “توّهج” طبيعي. من خلال تعديل نقاط الألوان ونصف القطر، يمكنك محاكاة الإضاءة والعمق وخصائص المادة في شكل متجه نقي.

## لماذا نستخدم Aspose.Page للتدرجات الشعاعية؟
يتيح لك Aspose.Page إنشاء رسومات متجهة مستقلة عن الجهاز باستخدام واجهة برمجة تطبيقات Java واحدة. يدعم أكثر من 50 صيغة إدخال وإخراج — بما في ذلك PostScript و PDF و SVG — مع الحفاظ على دقة الألوان وإزالة التعرجات للحصول على إخراج عالي الدقة. كما توفر المكتبة فئات تدرج سهلة الاستخدام، مما يجعل تنفيذ التأثيرات البصرية المعقدة بسيطًا.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن لديك:

- إلمام أساسي ببرمجة Java.  
- JDK 8 أو أحدث مثبتًا على جهازك.  
- مكتبة Aspose.Page for Java (قم بتنزيلها من [توثيق Aspose.Page Java](https://reference.aspose.com/page/java/)).

## استيراد الحزم
أولاً، استورد الفئات التي سنحتاجها. تشمل هذه الأنواع القياسية للرسومات في AWT وواجهة برمجة تطبيقات Aspose.Page.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## الخطوة 1: إعداد دليل المستند
حدد المجلد الذي سيُحفظ فيه ملف PostScript المُولد. استبدل العنصر النائب بمسار فعلي على نظامك.

```java
String dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء تدفق الإخراج
يقوم FileOutputStream بكتابة البايتات الخام إلى ملف، مما يسمح بحفظ البيانات الثنائية. فتح تدفق يستهدف ملف `.ps` يتيح لـ Aspose.Page بث بيانات PostScript المُولدة مباشرة إلى القرص.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## الخطوة 3: إنشاء خيارات الحفظ
يقوم PsSaveOptions بتكوين طريقة حفظ ملف PostScript، بما في ذلك حجم الصفحة والضغط. يمكنك تخصيص هذه الإعدادات، لكن الإعدادات الافتراضية مناسبة لهذا المثال.

```java
PsSaveOptions options = new PsSaveOptions();
```

## الخطوة 4: إنشاء مستند ps
يمثل PsDocument مستند PostScript في الذاكرة ويوفر طرقًا لإضافة صفحات ورسومات.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 5: إنشاء دائرة
`Ellipse2D.Float` يصف شكل إهليلجي؛ عندما يكون العرض = الارتفاع يصبح دائرة مثالية. سيُستخدم هذا الكائن كقماش لتعبئة التدرج الخاص بنا.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## كيفية رسم دائرة بتدرج
لرسم دائرة بتدرج شعاعي، تقوم بتحميل `RadialGradientPaint` إلى سياق الرسومات ثم تعبئة الإهليلج المحدد مسبقًا. هذه العملية الواحدة تُلون الشكل بانتقال لوني ناعم من المركز إلى الخارج، مُنتجة تأثيرًا بصريًا جذابًا.

## الخطوة 6: تعريف ألوان التدرج
حضّر مصفوفتين: واحدة للألوان التي ستظهر في التدرج وأخرى للمواقع الكسرية المقابلة (0 = المركز، 1 = الحافة).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## الخطوة 7: إنشاء AffineTransform
AffineTransform هو مصفوفة يمكنها ترجمة، تدوير، تكبير/تصغير، أو قص كائنات الرسومات. هنا يتم تكبير وتدوير التدرج بحيث يتناسب بدقة داخل الدائرة.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## الخطوة 8: إنشاء RadialGradientPaint
RadialGradientPaint ينشئ تدرجًا لونيًا شعاعيًا يعتمد على نقطة المركز، نصف القطر، ونقاط الألوان.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## الخطوة 9: تعيين الطلاء وتعبئة الدائرة
طبق طلاء التدرج على المستند واملأ الدائرة المحددة مسبقًا. هذا هو جوهر **مثال التدرج الشعاعي** ويظهر كيفية **تعبئة الشكل بتدرج**.

```java
document.setPaint(paint);
document.fill(circle);
```

## الخطوة 10: إغلاق الصفحة وحفظ المستند
أكمل الصفحة، اكتب المحتوى إلى القرص، وأغلق التدفق. أصبح ملف PostScript الخاص بك جاهزًا للعرض باستخدام أي عارض PS.

```java
document.closePage();
document.save();
```

تهانينا! لقد نجحت في إنشاء مثال لتدرج شعاعي في Java PostScript باستخدام Aspose.Page. لديك الآن نمط قابل لإعادة الاستخدام لـ **تعبئة الشكل بتدرج** يمكن تعديله لأشكال وصيغ إخراج أخرى.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|---------|----------|
| **FileNotFoundException** عند فتح تدفق الإخراج | تحقق من أن `dataDir` يشير إلى مجلد موجود وأن لديك أذونات كتابة. |
| التدرج يبدو مسطحًا أو مفقودًا | تأكد من أن مصفوفة `fractions` تتطابق مع طول مصفوفة `colors` وأن `AffineTransform` يتم تكبيره بشكل صحيح. |
| الألوان تظهر مقلوبة | بدل ترتيب الألوان في مصفوفة `colors` أو عدل إحداثيات نقطة `focus`. |

## الأسئلة المتكررة

**س: أين يمكنني العثور على توثيق Aspose.Page for Java؟**  
ج: المرجع الكامل للـ API متاح في [توثيق Aspose.Page Java API](https://reference.aspose.com/page/java/).

**س: كيف يمكنني تنزيل Aspose.Page for Java؟**  
ج: احصل على أحدث ملف JAR من [صفحة الإصدارات](https://releases.aspose.com/page/java/).

**س: هل هناك نسخة تجريبية مجانية متاحة؟**  
ج: نعم — قم بتنزيل نسخة تجريبية من [صفحة تنزيل التجربة المجانية لـ Aspose](https://releases.aspose.com/).

**س: هل يمكنني الحصول على ترخيص مؤقت للاختبار؟**  
ج: بالطبع، اطلب واحدًا من [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني الحصول على دعم المجتمع؟**  
ج: انضم إلى النقاش في [منتدى Aspose.Page](https://forum.aspose.com/c/page/39).

## الخلاصة
في هذا الدليل بنينا مثالًا كاملًا لـ **التدرج الشعاعي** لمستند PostScript باستخدام Aspose.Page for Java. باتباع الخطوات لديك الآن نمط قابل لإعادة الاستخدام لـ **تعبئة الشكل بتدرج**، يمكن تعديله لـ PDF أو SVG أو أي صيغة أخرى يدعمها Aspose.Page. جرب ألوانًا، أنصاف أقطار، وأشكال مختلفة لإثراء مشاريع رسومات Java الخاصة بك.

---

**آخر تحديث:** 2026-09-09  
**تم الاختبار مع:** Aspose.Page for Java 24.11 (الأحدث وقت كتابة هذا الدليل)  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء تدرج PostScript في Java – إضافة تدرج عمودي](/page/java/postscript-gradient-addition/vertical/)
- [إنشاء نمط نسيج في PostScript باستخدام Aspose.Page for Java](/page/java/postscript-texture-patterns/)
- [دروس شفافية Aspose.Page – إضافة شفافية في Java PostScript](/page/java/postscript-transparency/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}