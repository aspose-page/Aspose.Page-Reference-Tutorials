---
date: 2026-02-13
description: تعلم كيفية إنشاء تدرج PostScript باستخدام تدرج نقاط اللون الدائرية باستخدام
  Aspose.Page للغة Java. يوضح لك هذا الدليل خطوة بخطوة كيفية إضافة تدرج نقاط اللون
  في مستنداتك.
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: إنشاء تدرج PostScript – التدرج الشعاعي في جافا
url: /ar/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة تدرج شعاعي في Java PostScript باستخدام Aspose.Page

## المقدمة
إذا احتجت يومًا إلى **إنشاء PostScript gradient** مع انتقال لوني سلس وجذاب، فإن تعلم كيفية إضافة تدرج شعاعي هو المكان المثالي للبدء. في هذا الدرس سنستعرض كل خطوة مطلوبة لإنشاء ملف PostScript يحتوي على تدرج شعاعي جميل، باستخدام مكتبة **Aspose.Page for Java**. في النهاية ستفهم الـ API، وترى مثالًا كاملاً قابلًا للتنفيذ، وتعرف كيف تعدّل الألوان، المواقع، والأنصاف لتناسب أي تصميم.

## إجابات سريعة
- **ما المكتبة التي تُنشئ تدرجات شعاعية في PostScript؟** Aspose.Page for Java.  
- **كم من الوقت تستغرق العملية؟** حوالي 10‑15 دقيقة للمثال الأساسي.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** النسخة التجريبية المجانية تعمل للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أعلى.  
- **هل يمكنني تغيير شكل التدرج؟** نعم – عدّل نصف القطر ونقطة المركز في مُنشئ `RadialGradientPaint`.

## كيفية إنشاء تدرج PostScript مع تعبئة شعاعية
فيما يلي ستجد دليلًا مختصرًا خطوة بخطوة يوضح بالضبط كيفية **إنشاء PostScript gradient** باستخدام تعبئة شعاعية. كل خطوة تتضمن شرحًا قصيرًا يليه كتلة الكود الأصلية (بدون تعديل).

## ما هو التدرج الشعاعي؟
يُظهر التدرج الشعاعي ألوانًا تنتشر من نقطة مركزية إلى الخارج، مع مزج تدريجي نحو الحواف. على عكس التدرجات الخطية، ينتقل اللون وفق نمط دائري (أو بيضاوي)، وهو مثالي للإبرازات، الأضواء المسلطة، أو تعبئة الخلفيات الناعمة.

## لماذا نستخدم Aspose.Page للتدرجات الشعاعية؟
- **تحكم كامل في مخرجات PostScript** – لا حاجة لكتابة أوامر PS منخفضة المستوى يدويًا.  
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java.  
- **إدارة ألوان غنية** – يدعم عدة نقاط لون، مساحات ألوان مختلفة، وطرق دورة.  
- **جاهز للتكامل** – يمكن دمجه مع ميزات Aspose.Page الأخرى مثل النصوص، الصور، والأشكال المتجهية.

## المتطلبات المسبقة
قبل الغوص في الكود، تأكد من أن لديك ما يلي جاهزًا:

- **Java Development Kit (JDK) 8+** – تحقق باستخدام `java -version`.  
- **Aspose.Page for Java** – حمّل أحدث ملف JAR من [صفحة تحميل Aspose.Page الرسمية](https://releases.aspose.com/page/java/).  
- **بيئة تطوير متكاملة (IDE) حسب اختيارك** – Eclipse، IntelliJ IDEA، أو VS Code مع امتدادات Java.  
- **مجلد قابل للكتابة** – حيث سيتم حفظ ملف `.ps` المُولَّد.

## استيراد الحزم
أولًا، استورد الفئات التي سنحتاجها. حزمة `java.awt` توفر كائنات طلاء التدرج، بينما تحتوي `com.aspose.eps` على فئات معالجة مستندات PostScript.

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

> **نصيحة احترافية:** عدّل إحداثيات المستطيل (`200, 100, 200, 200`) لتحديد موقع التدرج في أي مكان على الصفحة.

### الخطوة 2: تعريف الألوان والكسرات
يتكوّن التدرج الشعاعي من *نقاط اللون* (الألوان) و*الكسرات* (المواقع النسبية لتلك النقاط). هنا ننشئ مصفوفة من ستة ألوان والكسرات المقابلة لها.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **لماذا هذا مهم:** من خلال تعديل `fractions` يمكنك التحكم في سرعة انتقال الألوان، مما يتيح تأثيرات دقيقة أو درامية.

### إضافة تدرج نقاط اللون إلى تعبئتك الشعاعية
عندما تحتاج إلى **إضافة تدرج نقاط اللون**، تكون مصفوفات `colors` و `fractions` هي المفتاح. لا تتردد في إعادة ترتيب أو إضافة أو إزالة العناصر لتناسب تصميمك البصري.

### الخطوة 3: إنشاء RadialGradientPaint
الآن نبني كائن `RadialGradientPaint`. يأخذ المُنشئ نقطة مركز التدرج، نصف القطر، نقطة التركيز، الكسرات، الألوان، طريقة الدورة، مساحة اللون، وتحويل اختياري.

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

> **ملاحظة:** يمكن أن يكون `transform` `null` إذا لم تكن بحاجة إلى تحجيم أو دوران إضافي. لا تتردد في تجربة `AffineTransform` للحصول على تدرجات مائلة.

### الخطوة 4: تعيين الطلاء وتعبئة المستطيل
بعد تجهيز الطلاء، نخبر `PsDocument` باستخدامه ثم نملأ المستطيل الذي عرّفناه مسبقًا.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

في هذه المرحلة تحتوي صفحة PostScript على مستطيل مملوء بسلاسة بالتدرج الشعاعي الذي قمنا بتكوينه.

### الخطوة 5: إغلاق وحفظ المستند
أخيرًا، أغلق الصفحة الحالية واكتب الملف إلى القرص.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

افتح `RadialGradient1_outPS.ps` في أي عارض PostScript (مثل Ghostscript) وسترى التدرج يُعرض تمامًا كما تم تعريفه.

## المشكلات الشائعة والحلول
| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| التدرج يظهر كلون صلب | مصفوفة `fractions` لا تبدأ بـ `0.0f` أو لا تنتهي بـ `1.0f` | تأكد من أن أول قيمة في `fractions` هي `0.0f` وآخرها هي `1.0f`. |
| الألوان تبدو باهتة | استخدام `ColorSpaceType` غير الصحيح | غيّر إلى `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` للحصول على مخرجات أكثر حيوية. |
| لم يتم إنشاء ملف إخراج | مسار `FileOutputStream` غير صالح أو غير قابل للكتابة | تحقق من وجود `dataDir` وأن التطبيق لديه صلاحيات كتابة. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page for Java في المشاريع التجارية؟**  
ج: نعم. يلزم الحصول على ترخيص تجاري للاستخدام في الإنتاج. يمكنك شراء واحد من [صفحة ترخيص Aspose](https://purchase.aspose.com/buy).

**س: أين يمكنني العثور على مرجع الـ API الرسمي؟**  
ج: الوثائق الكاملة متاحة [هنا](https://reference.aspose.com/page/java/).

**س: هل تتوفر نسخة تجريبية مجانية للاختبار؟**  
ج: بالتأكيد. حمّل نسخة تجريبية من [صفحة إصدارات Aspose.Page](https://releases.aspose.com/).

**س: كيف أحصل على ترخيص مؤقت للتقييم؟**  
ج: يمكن طلب ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني الحصول على دعم المجتمع؟**  
ج: انضم إلى منتدى مجتمع Aspose.Page على [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## الخلاصة
أنت الآن تعرف **كيفية إضافة تدرج شعاعي** إلى مستند Java PostScript باستخدام Aspose.Page. من خلال تعديل حجم المستطيل، نقاط اللون، ونصف قطر التدرج يمكنك إنشاء عدد لا يحصى من التأثيرات البصرية — من تعبئة خلفيات ناعمة إلى رسومات إضاءة جريئة. لا تتردد في تجربة قيم `AffineTransform` المختلفة لتدوير أو إمالة التدرج، ودمج هذه التقنية مع النصوص والصور للحصول على مخرجات PDF أو EPS أغنى.

---

**آخر تحديث:** 2026-02-13  
**تم الاختبار باستخدام:** Aspose.Page for Java latest (as of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}