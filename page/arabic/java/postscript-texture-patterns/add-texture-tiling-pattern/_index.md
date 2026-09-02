---
date: 2026-05-05
description: تعلم كيفية إضافة أنماط تكرار القوام إلى مستندات PostScript باستخدام Aspose.Page
  للغة Java. يوضح هذا الدليل كيفية إضافة القوام بكفاءة واستكشاف الإمكانيات الإبداعية.
keywords:
- how to add texture
- fill shape with texture
- fill rectangle with texture
linktitle: إضافة نمط تجانب القوام في جافا بوستسكريبت
second_title: Aspose.Page Java API
title: كيفية إضافة نمط تجانب القوام في Java PostScript
url: /ar/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة نمط تجانب القوام في Java PostScript

## مقدمة
في مجال تطوير Java، تعلم **كيفية إضافة القوام** إلى مستندات PostScript هو طلب شائع. تجعل Aspose.Page for Java هذه المهمة بسيطة، مما يتيح لك التركيز على التصميم بدلاً من صsyntax PostScript منخفض المستوى. في هذا الدرس، سنستعرض كل خطوة ضرورية لإضافة نمط تجانب القوام، وتعبئة الأشكال، وحتى إضافة قوام للنص في مستند Java PostScript.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **ما هي الكلمة المفتاحية الأساسية التي يستهدفها هذا الدليل؟** *كيفية إضافة القوام*  
- **هل أحتاج إلى ترخيص للاختبار؟** يتوفر إصدار تجريبي مجاني؛ الترخيص مطلوب للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أعلى.  
- **هل يمكن إعادة استخدام فرشاة القوام لأشكال متعددة؟** نعم – أنشئ `TexturePaint` مرة واحدة وطبقها على أي شكل.  
- **كيف أملأ مستطيلًا بالقوام؟** استخدم `document.fill(shape)` بعد تعيين `TexturePaint` كطلاء حالي.

## ما هو نمط تجانب القوام؟
نمط تجانب القوام يكرر صورة صغيرة (البلاطة) عبر مساحة أكبر، مما يتيح لك **تعبئة الشكل بالقوام** دون الحاجة إلى رسم كل بلاطة يدويًا. هذه التقنية مثالية للخلفيات، والتعبئات، وتأثيرات النص الزخرفية في PostScript.

## لماذا نستخدم Aspose.Page for Java؟
- **عرض بدون تبعيات** – لا حاجة لمفسرات PostScript الخارجية.  
- **تحكم كامل في الرسومات** – دمج الأشكال المتجهية، النص، وقوام الصور النقطية.  
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java.  

## المتطلبات المسبقة
قبل الغوص في الدرس، تأكد من توفر المتطلبات التالية:
- فهم أساسي للغة برمجة Java.  
- إلمام بهيكل مستند PostScript.  
- مكتبة Aspose.Page for Java مثبتة. يمكنك تنزيلها [هنا](https://releases.aspose.com/page/java/).

## استيراد الحزم
ابدأ باستيراد الحزم اللازمة لمشروع Java الخاص بك:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## كيفية إضافة نمط تجانب القوام في Java PostScript
فيما يلي دليل خطوة بخطوة. كل خطوة تتضمن شرحًا مختصرًا يليه الكود الدقيق الذي تحتاج إلى نسخه.

### الخطوة 1: إنشاء مستند PostScript
ابدأ بإنشاء مستند PostScript جديد، مع تحديد تدفق الإخراج وخيارات الحفظ. تأكد من تكوين المسارات اللازمة.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### الخطوة 2: إعداد بيئة الرسومات
قم بترجمة الأصل إلى موقع مناسب وحمّل الصورة النقطية التي ستعمل كبلاطة القوام.

```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```

### الخطوة 3: إنشاء فرشاة القوام
عرّف `TexturePaint` الذي يكرر الصورة النقطية عبر مساحة الشكل. عدّل حجم المستطيل إذا أردت أن تظهر البلاطة أكبر أو أصغر.

```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```

### الخطوة 4: رسم وتعبئة الأشكال
أنشئ مستطيلًا و**املأ المستطيل بالقوام** باستخدام الفرشاة. ثم ارسم حدود الشكل لجعل النتيجة مميزة بصريًا.

```java
// Create rectangle
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// Set this texture brush as current paint
document.setPaint(paint);
// Fill rectangle
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```

### الخطوة 5: إضافة نص بنمط القوام
يمكنك أيضًا تطبيق نفس القوام على حروف النص. هذا يوضح **كيفية تعبئة القوام** على الأحرف مع القدرة على رسم حدودها.

```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

### الخطوة 6: حفظ وإغلاق
أخيرًا، أغلق الصفحة، احفظ المستند، وحرّر الموارد.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## المشكلات الشائعة والنصائح
- **ملف القوام مفقود** – تحقق من صحة المسار إلى `TestTexture.bmp` وأن الملف قابل للوصول.  
- **أبعاد الصورة غير صحيحة** – إذا ظهر القوام مشوهًا، عدّل `imageArea` لتطابق حجم الصورة الأصلية.  
- **الأداء** – أعد استخدام نفس كائن `TexturePaint` لأشكال متعددة لتجنب إنشاء كائنات غير ضرورية.  
- **نصيحة احترافية:** استخدم صورة نقطية عالية الدقة للبلاطة للحفاظ على وضوح القوام عند التكبير.

## الأسئلة المتكررة

**س: هل Aspose.Page for Java مناسب للمبتدئين؟**  
ج: بالتأكيد! توفر Aspose.Page for Java وثائق شاملة، مما يجعلها سهلة الوصول للمطورين من جميع مستويات المهارة.

**س: هل يمكنني دمج Aspose.Page for Java في مشروعي Java الحالي؟**  
ج: نعم، يمكنك بسهولة دمج Aspose.Page for Java في مشروعك باتباع الوثائق المتوفرة [هنا](https://reference.aspose.com/page/java/).

**س: أين يمكنني العثور على الدعم أو مناقشة استفسارات متعلقة بـ Aspose.Page؟**  
ج: زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتفاعل مع المجتمع وطلب المساعدة.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page for Java؟**  
ج: نعم، يمكنك تجربة النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟**  
ج: زر [هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت.

## الخلاصة
تهانينا! لقد تعلمت بنجاح **كيفية إضافة القوام** إلى أنماط تجانب القوام في مستند Java PostScript باستخدام Aspose.Page for Java. لا تتردد في تجربة بلاطات نقطية مختلفة، وعوامل التكبير، والعمليات المركبة لإطلاق الإمكانات الإبداعية الكاملة لتعبئات القوام.

---

**آخر تحديث:** 2026-05-05  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (latest)  
**المؤلف:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}