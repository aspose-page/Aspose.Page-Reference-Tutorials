---
title: إضافة صورة في جافا بوستسكريبت
linktitle: إضافة صورة في جافا بوستسكريبت
second_title: Aspose.Page جافا API
description: استكشف التكامل السلس لـ Aspose.Page Java في هذا البرنامج التعليمي حول إضافة الصور إلى مستندات PostScript. ارفع قدرات معالجة المستندات لديك.
type: docs
weight: 10
url: /ar/java/postscript-image-manipulation/add-image/
---
## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية إضافة صور إلى مستند Java PostScript باستخدام مكتبة Aspose.Page for Java. Aspose.Page هي مكتبة قوية توفر ميزات متنوعة للعمل مع ملفات PostScript، مما يسمح للمطورين بمعالجة مستنداتهم وتحسينها بسلاسة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Page لمكتبة جافا. يمكنك تنزيله[هنا](https://releases.aspose.com/page/java/).
- الفهم الأساسي لبرمجة جافا.
## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية في مشروع Java الخاص بك. استخدم مقتطف الشفرة التالي كمرجع:
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
تتضمن الخطوة الأولى كتابة الرسومات المحفوظة في المستند. وهذا يضمن إمكانية التراجع عن أي تحويلات أو تعديلات تم إجراؤها بعد ذلك إذا لزم الأمر.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء دفق الإخراج لمستند بوستسكريبت
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// إنشاء خيارات الحفظ بحجم A4
PsSaveOptions options = new PsSaveOptions();
// قم بإنشاء مستند PS جديد مع فتح الصفحة
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```
## الخطوة 2: الترجمة والتحويل
بعد ذلك، قم بترجمة المستند وإنشاء كائن BufferedImage من ملف الصورة. قم بتطبيق سلسلة من التحويلات مثل القياس والتدوير باستخدام AffineTransform.
```java
document.translate(100, 100);
// قم بإنشاء كائن BufferedImage من ملف الصورة
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// إنشاء تحويل الصورة
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```
## الخطوة 3: إضافة صورة إلى المستند
الآن قم بإضافة الصورة المحولة إلى المستند.
```java
document.drawImage(image, transform, null);
```
## الخطوة 4: كتابة استعادة الرسومات
بعد إضافة الصورة، قم بكتابة استعادة الرسومات لإنهاء التغييرات التي تم إجراؤها.
```java
document.writeGraphicsRestore();
```
## الخطوة 5: أغلق الصفحة الحالية واحفظها
أغلق الصفحة الحالية واحفظ المستند.
```java
document.closePage();
document.save();
```
كرر هذه الخطوات لإضافة صور متعددة أو قم بتخصيص التحويلات بناءً على متطلباتك.
## خاتمة
 تهانينا! لقد تعلمت بنجاح كيفية إضافة الصور إلى مستند Java PostScript باستخدام Aspose.Page لـ Java. اكتشف ال[توثيق](https://reference.aspose.com/page/java/) لمزيد من الميزات والوظائف المتقدمة.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Page لـ Java مع لغات البرمجة الأخرى؟
يدعم Aspose.Page Java بشكل أساسي، ولكن هناك إصدارات متاحة للغات برمجة أخرى أيضًا.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page لـ Java؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ Java؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على دعم المجتمع والمناقشات المتعلقة بـ Aspose.Page for Java؟
 قم بزيارة[Aspose.صفحة المنتدى](https://forum.aspose.com/c/page/39) لدعم المجتمع.
### هل هناك أي موارد إضافية لشراء Aspose.Page لـ Java؟
 يمكنك شراء المكتبة[هنا](https://purchase.aspose.com/buy).