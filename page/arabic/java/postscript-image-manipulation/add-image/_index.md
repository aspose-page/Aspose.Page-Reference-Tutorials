---
date: 2026-02-15
description: تعرّف على كيفية إنشاء مستندات بوستسكريبت بلغة جافا وتوليد ملفات مستندات
  بوستسكريبت مع ترجمة الصور وتدويرها باستخدام Aspose.Page للـ Java.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: إنشاء PostScript Java – إضافة صورة في Java PostScript
url: /ar/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء PostScript Java – إضافة صورة في Java PostScript

## المقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية **إنشاء postscript java** المستندات وتضمين الصور باستخدام مكتبة Aspose.Page for Java. سنستعرض كل خطوة، بدءًا من تهيئة ملف PostScript جديد إلى تطبيق تحويلات **ترجمة وتدوير الصورة**. في النهاية، ستكون قادرًا على إنشاء ملفات PostScript برمجيًا والتحكم في وضع الصورة بدقة بكسل مثالية — مثالي للتقارير الآلية، سير عمل الطباعة، أو أي سيناريو تحتاج فيه إلى **إنشاء مستند postscript** من Java.

## إجابات سريعة
- **What library is required?** Aspose.Page for Java  
- **Can I add multiple images?** نعم – كرر خطوات التحويل والرسم  
- **Do I need a license for development?** إصدار تجريبي مجاني يعمل للاختبار؛ يلزم الحصول على ترخيص للإنتاج  
- **Which Java version is supported?** Java 8 and later  
- **Is image rotation supported?** بالطبع – استخدم `AffineTransform.rotate()`

## ما هو إنشاء postscript java؟
عملية **إنشاء postscript java** تنتج ملف وصف صفحة PostScript يُشفّر النصوص والرسومات المتجهة والصور النقطية. باستخدام Aspose.Page يمكنك بناء هذه الملفات مباشرةً من كود Java، مما يمنحك تحكمًا برمجيًا كاملاً في التخطيط، والتحجيم، والتدوير دون الحاجة إلى مفسر PostScript منفصل.

## لماذا تستخدم Aspose.Page لتعديل الصور؟
- **High‑level API:** يجمل أوامر PostScript منخفضة المستوى في طرق Java بسيطة.  
- **Cross‑platform:** يعمل على أي نظام تشغيل يدعم Java.  
- **Full graphics‑state control:** حفظ، استعادة، ترجمة، تحجيم، وتدوير الرسومات حسب الحاجة.  
- **No external dependencies:** يتعامل مع تحميل الصور، تحويل الصيغ، وتضمينها داخليًا.

## المتطلبات المسبقة
قبل أن نغوص في الكود، تأكد من أن لديك:

- Java Development Kit (JDK) مثبت على نظامك.  
- مكتبة Aspose.Page for Java. يمكنك تنزيلها [هنا](https://releases.aspose.com/page/java/).  
- فهم أساسي لبرمجة Java.

## استيراد الحزم
لبدء العمل، استورد الحزم اللازمة في مشروع Java الخاص بك. استخدم مقتطف الكود التالي كمرجع:

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
الخطوة الأولى تتضمن كتابة حفظ الرسومات إلى المستند. يضمن ذلك إمكانية التراجع عن أي تحويلات أو تعديلات تُجرى لاحقًا إذا لزم الأمر.

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
بعد ذلك، قم بترجمة المستند وإنشاء كائن `BufferedImage` من ملف الصورة. طبّق سلسلة من التحويلات مثل التحجيم والتدوير باستخدام `AffineTransform`. هنا يحدث عملية **ترجمة وتدوير الصورة**.

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
الآن، أضف الصورة المُحوَّلة إلى المستند.

```java
document.drawImage(image, transform, null);
```

## الخطوة 4: كتابة استعادة الرسومات
بعد إضافة الصورة، اكتب استعادة الرسومات لإنهاء التغييرات التي تم إجراؤها.

```java
document.writeGraphicsRestore();
```

## الخطوة 5: إغلاق الصفحة الحالية وحفظها
أغلق الصفحة الحالية واحفظ المستند.

```java
document.closePage();
document.save();
```

يمكنك تكرار هذه الخطوات لإضافة صور متعددة أو تخصيص التحويلات وفقًا لمتطلباتك.

## المشكلات الشائعة والحلول
- **FileNotFoundException:** تأكد من أن مسار `dataDir` ينتهي بفاصل ملفات (`/` أو `\\`) وأن اسم ملف الصورة مطابق تمامًا.  
- **ImageIO.read returns null:** تحقق من أن صيغة الصورة مدعومة (مثل JPEG، PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` يتوقع الزوايا بالراديان. حوّل الدرجات إلى راديان (`Math.toRadians(degrees)`) إذا لزم الأمر.

## الأسئلة المتكررة

**Q:** هل يمكنني استخدام Aspose.Page for Java مع لغات برمجة أخرى؟  
**A:** Aspose.Page يدعم أساسًا Java، لكن هناك إصدارات متاحة للغات برمجة أخرى أيضًا.

**Q:** هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page for Java؟  
**A:** نعم، يمكنك الوصول إلى النسخة التجريبية [هنا](https://releases.aspose.com/).

**Q:** كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟  
**A:** يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**Q:** أين يمكنني العثور على دعم المجتمع والنقاشات المتعلقة بـ Aspose.Page for Java؟  
**A:** زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع.

**Q:** هل هناك موارد إضافية لشراء Aspose.Page for Java؟  
**A:** يمكنك شراء المكتبة [هنا](https://purchase.aspose.com/buy).

## الخاتمة
تهانينا! لقد تعلمت بنجاح كيفية **إنشاء postscript java** المستندات وتضمين الصور باستخدام Aspose.Page for Java. استكشف [التوثيق](https://reference.aspose.com/page/java/) لمزيد من الميزات المتقدمة والوظائف، مثل الرسومات المتجهة، عرض النص، وأحجام الصفحات المخصصة.

---

**آخر تحديث:** 2026-02-15  
**تم الاختبار مع:** Aspose.Page for Java 23.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}