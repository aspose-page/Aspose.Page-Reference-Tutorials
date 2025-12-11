---
date: 2025-12-09
description: تعلم كيفية إنشاء مستند PostScript باستخدام Java وكيفية نقل وتدوير الصورة
  باستخدام Aspose.Page لتعديل الصور بسلاسة.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: إنشاء مستند PostScript بجافا – إضافة صورة في PostScript بجافا
url: /ar/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مستند PostScript باستخدام Java – إضافة صورة في PostScript Java

## المقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية **إنشاء مستند PostScript باستخدام Java** وإدراج الصور باستخدام مكتبة Aspose.Page for Java. سنستعرض كل خطوة، بدءًا من إعداد المستند إلى تطبيق التحويلات مثل عمليات **ترجمة وتدوير الصورة**. في النهاية، ستكون قادرًا على إنشاء ملفات PostScript غنية برمجيًا وتخصيص موضع الصورة لتناسب احتياجات التخطيط الدقيقة الخاصة بك.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **هل يمكنني إضافة صور متعددة؟** نعم – كرر خطوات التحويل والرسم  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تعمل للاختبار؛ يلزم الترخيص للإنتاج  
- **ما نسخة Java المدعومة؟** Java 8 وما بعدها  
- **هل يدعم تدوير الصورة؟** بالتأكيد – استخدم `AffineTransform.rotate()`

## ما هو إنشاء مستند PostScript باستخدام Java؟
مستند PostScript هو ملف لغة وصف الصفحات يصف النصوص والرسومات والصور. باستخدام Aspose.Page، يمكنك إنشاء هذه الملفات برمجيًا في Java، مما يمنحك تحكمًا كاملاً في التخطيط وحالة الرسومات ومعالجة الصور دون الحاجة إلى مفسر PostScript.

## لماذا نستخدم Aspose.Page لمعالجة الصور؟
- **واجهة برمجة تطبيقات عالية المستوى:** تبسط أوامر PostScript المعقدة.  
- **متعددة المنصات:** تعمل على أي نظام تشغيل يدعم Java.  
- **تحكم كامل في حالة الرسومات:** احفظ، استعد، ترجم، قسّم، ودور الرسومات بسهولة.  
- **بدون تبعيات خارجية:** يتعامل مع تحميل الصور وتحويلها داخليًا.

## المتطلبات المسبقة
قبل الغوص في الشيفرة، تأكد من وجود ما يلي:
- Java Development Kit (JDK) مثبت على نظامك.  
- مكتبة Aspose.Page for Java. يمكنك تنزيلها [هنا](https://releases.aspose.com/page/java/).  
- فهم أساسي لبرمجة Java.

## استيراد الحزم
لبدء العمل، استورد الحزم الضرورية في مشروع Java الخاص بك. استخدم مقتطف الشيفرة التالي كمرجع:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## الخطوة 1: كتابة حفظ الرسومات
الخطوة الأولى تتضمن كتابة حفظ الرسومات إلى المستند. هذا يضمن أنه يمكن التراجع عن أي تحويلات أو تعديلات تم إجراؤها لاحقًا إذا لزم الأمر.

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

## الخطوة 2: الترجمة والتحويل (ترجمة وتدوير الصورة)
بعد ذلك، قم بترجمة المستند وإنشاء كائن `BufferedImage` من ملف الصورة. طبق سلسلة من التحويلات مثل التحجيم والتدوير باستخدام `AffineTransform`. هنا يحدث عملية **ترجمة وتدوير الصورة**.

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

## الخطوة 3: إضافة الصورة إلى المستند
الآن، أضف الصورة المحوّلة إلى المستند.

```java
document.drawImage(image, transform, null);
```

## الخطوة 4: كتابة استعادة الرسومات
بعد إضافة الصورة، اكتب استعادة الرسومات لإنهاء التغييرات التي تم إجراؤها.

```java
document.writeGraphicsRestore();
```

## الخطوة 5: إغلاق الصفحة الحالية وحفظ المستند
أغلق الصفحة الحالية واحفظ المستند.

```java
document.closePage();
document.save();
```

يمكنك تكرار هذه الخطوات لإضافة صور متعددة أو تخصيص التحويلات وفقًا لمتطلباتك.

## المشكلات الشائعة والحلول
- **FileNotFoundException:** تأكد من أن مسار `dataDir` ينتهي بفاصل ملفات (`/` أو `\\`) وأن اسم ملف الصورة مطابق تمامًا.  
- **ImageIO.read returns null:** تحقق من أن تنسيق الصورة مدعوم (مثل JPEG، PNG).  
- **زاوية التدوير غير صحيحة:** `AffineTransform.rotate` يتوقع الراديان. حوّل الدرجات إلى راديان (`Math.toRadians(degrees)`) إذا لزم الأمر.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page for Java مع لغات برمجة أخرى؟**  
ج: Aspose.Page يدعم أساسًا Java، ولكن هناك إصدارات متاحة للغات برمجة أخرى أيضًا.

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Page for Java؟**  
ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟**  
ج: يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني العثور على دعم المجتمع والنقاشات المتعلقة بـ Aspose.Page for Java؟**  
ج: زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع.

**س: هل هناك موارد إضافية لشراء Aspose.Page for Java؟**  
ج: يمكنك شراء المكتبة [هنا](https://purchase.aspose.com/buy).

## الخلاصة
تهانينا! لقد تعلمت بنجاح كيفية **إنشاء مستند PostScript باستخدام Java** وإدراج الصور باستخدام Aspose.Page for Java. استكشف [التوثيق](https://reference.aspose.com/page/java/) للحصول على ميزات ووظائف متقدمة أكثر، مثل الرسومات المتجهية، عرض النص، وأحجام الصفحات المخصصة.

---

**آخر تحديث:** 2025-12-09  
**تم الاختبار مع:** Aspose.Page for Java 23.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}