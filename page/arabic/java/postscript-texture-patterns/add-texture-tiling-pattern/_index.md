---
date: 2025-12-17
description: تعرّف على كيفية إضافة أنماط تكرار القوام إلى مستندات PostScript باستخدام
  Aspose.Page للغة Java. يوضح هذا الدليل كيفية إضافة القوام بكفاءة واستكشاف إمكانيات
  إبداعية.
linktitle: Add Texture Tiling Pattern in Java PostScript
second_title: Aspose.Page Java API
title: كيفية إضافة نمط تجانب القوام في Java PostScript
url: /ar/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة نمط تكرار القوام في Java PostScript

## المقدمة
في عالم تطوير Java، يُعد تعلم **كيفية إضافة القوام** إلى مستندات PostScript مطلبًا شائعًا. تُثبت Aspose.Page for Java أنها أداة قيمة لتحقيق هذه المهمة بسهولة. في هذا البرنامج التعليمي، سنرشدك إلى عملية إضافة نمط تكرار القوام في مستند Java PostScript باستخدام Aspose.Page.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **ما الكلمة المفتاحية الأساسية التي يستهدفها هذا الدليل؟** *how to add texture*  
- **هل أحتاج إلى ترخيص للاختبار؟** تتوفر نسخة تجريبية مجانية؛ يلزم الترخيص للإنتاج.  
- **ما إصدار Java المدعوم؟** Java 8 أو أعلى.  
- **هل يمكنني إعادة استخدام فرشاة القوام لأشكال متعددة؟** نعم – أنشئ `TexturePaint` مرة واحدة وطبقها على أي شكل.

## ما هو نمط تكرار القوام؟
نمط تكرار القوام يكرر صورة صغيرة (البلاطة) عبر مساحة أكبر، مما يتيح لك **ملء الشكل بالقوام** دون الحاجة إلى رسم كل بلاطة يدويًا. هذه التقنية مثالية للخلفيات، والملء، وتأثيرات النص الزخرفية في PostScript.

## لماذا نستخدم Aspose.Page for Java؟
- **عرض بدون تبعيات** – لا حاجة لمفسرات PostScript خارجية.  
- **تحكم كامل في الرسومات** – دمج الأشكال المتجهية، والنص، وقوام الصور النقطية.  
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java.  

## المتطلبات المسبقة
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات التالية:
- فهم أساسي للغة برمجة Java.  
- إلمام ببنية مستند PostScript.  
- تثبيت مكتبة Aspose.Page for Java. يمكنك تحميلها [هنا](https://releases.aspose.com/page/java/).

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

## الخطوة 1: إنشاء مستند PostScript
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

## الخطوة 2: إعداد بيئة الرسومات
قم بإعداد بيئة الرسومات عن طريق نقل الأصل وإنشاء `BufferedImage` من ملف صورة القوام.

```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```

## الخطوة 3: إنشاء فرشاة القوام
عرّف فرشاة القوام من الصورة، مع تحديد المنطقة التي سيغطيها القوام.

```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```

## الخطوة 4: رسم وتعبئة الأشكال
أنشئ مستطيلًا و**املأ الشكل بالقوام** باستخدام الفرشاة المعرفة. بالإضافة إلى ذلك، ارسم حدود الشكل لإضفاء مظهر بصري جذاب.

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

## الخطوة 5: إضافة نص بنمط القوام
أضف نصًا إلى المستند وبيّن **كيفية ملء القوام** على الأحرف. خصّص الخط، والموقع، وغيرها من المعلمات حسب الحاجة.

```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## الخطوة 6: الحفظ والإغلاق
اختم العملية بإغلاق الصفحة الحالية، وحفظ المستند، وضمان تنفيذ سلس.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## المشكلات الشائعة والنصائح
- **ملف القوام مفقود** – تحقق من صحة المسار إلى `TestTexture.bmp` وأن الملف قابل للوصول.  
- **أبعاد الصورة غير صحيحة** – إذا ظهر القوام مشوهًا، عدّل `imageArea` لتطابق حجم الصورة الأصلي.  
- **الأداء** – أعد استخدام نفس كائن `TexturePaint` لأشكال متعددة لتجنب إنشاء كائنات غير ضرورية.

## الأسئلة المتكررة

**س: هل Aspose.Page for Java مناسبة للمبتدئين؟**  
ج: بالتأكيد! توفر Aspose.Page for Java وثائق شاملة، مما يجعلها سهلة الوصول للمطورين من جميع المستويات.

**س: هل يمكنني دمج Aspose.Page for Java في مشروعي Java الحالي؟**  
ج: نعم، يمكنك دمج Aspose.Page for Java بسهولة في مشروعك باتباع الوثائق المتوفرة [هنا](https://reference.aspose.com/page/java/).

**س: أين يمكنني العثور على الدعم أو مناقشة استفسارات Aspose.Page؟**  
ج: زر منتدى [Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع وطلب المساعدة.

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Page for Java؟**  
ج: نعم، يمكنك تجربة نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟**  
ج: زر [هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت.

## الخاتمة
تهانينا! لقد تعلمت بنجاح **كيفية إضافة القوام** بنمط تكرار إلى مستند Java PostScript باستخدام Aspose.Page for Java. لا تتردد في استكشاف خيارات تخصيص إضافية—جرب بلاطات bitmap مختلفة، وعوامل مقياس، وعمليات تركيب لإطلاق الإمكانات الإبداعية الكاملة لتعبئات القوام.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2025-12-17  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (latest)  
**المؤلف:** Aspose  

---