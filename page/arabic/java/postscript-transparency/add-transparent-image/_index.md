---
title: إضافة صورة شفافة في Java PostScript
linktitle: إضافة صورة شفافة في Java PostScript
second_title: Aspose.Page جافا API
description: استكشف التكامل السلس للصور الشفافة في مستندات Java PostScript باستخدام Aspose.Page لـ Java. ارفع مستوى تصورات المستندات الخاصة بك دون عناء.
type: docs
weight: 10
url: /ar/java/postscript-transparency/add-transparent-image/
---
## مقدمة
في عالم Java PostScript، غالبًا ما يتضمن تحسين المظهر المرئي للمستندات إضافة صور شفافة. سيرشدك هذا البرنامج التعليمي خلال عملية دمج الصور الشفافة في مستندات Java PostScript باستخدام مكتبة Aspose.Page القوية لـ Java.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت أحدث إصدار من JDK على جهازك.
2.  Aspose.Page for Java: قم بتنزيل وتثبيت مكتبة Aspose.Page for Java من[موقع إلكتروني](https://releases.aspose.com/page/java/).
3. دليل المستندات: قم بإنشاء دليل على نظامك حيث ستقوم بتخزين مستندات Java PostScript الخاصة بك.
4. ملف صورة نصف شفاف: قم بإعداد ملف صورة نصف شفاف (على سبيل المثال، "mask1.png") لاستخدامه في البرنامج التعليمي.
## حزم الاستيراد
في مشروع Java الخاص بك، قم باستيراد الحزم اللازمة للاستفادة من الوظائف التي يوفرها Aspose.Page لـ Java. فيما يلي نموذج لمقتطف التعليمات البرمجية:
```java
import java.awt.Color;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## الخطوة 1: تعيين لون الخلفية
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء دفق الإخراج لمستند بوستسكريبت
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTransparentImage_outPS.ps");
// إنشاء خيارات الحفظ بحجم A4
PsSaveOptions options = new PsSaveOptions();
// قم بإنشاء مستند PS جديد مع فتح الصفحة
PsDocument document = new PsDocument(outPsStream, options, false);
// أضف مستطيلًا أحمر أسفل الصور للتباين البصري
document.setPaint(new Color(211, 8, 48));
document.fill(new Rectangle2D.Float(0, 0, (int) options.getPageSize().getWidth(), 300));
```
## الخطوة 2: ترجمة الإحداثيات
```java
// ترجمة إلى موضع معين على الصفحة
document.writeGraphicsSave();
document.translate(20, 100);
```
## الخطوة 3: إنشاء كائن الصورة
```java
// قم بإنشاء صورة من ملف الصورة الشفاف
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```
## الخطوة 4: إضافة صورة معتمة
```java
// أضف الصورة إلى المستند كصورة RGB غير شفافة
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```
## الخطوة 5: إضافة صورة شفافة
```java
// أضف الصورة إلى المستند كصورة شفافة
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```
## الخطوة 6: حفظ وإغلاق
```java
// احفظ الوثيقة وأغلقها
document.writeGraphicsRestore();
document.closePage();
document.save();
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة صور شفافة إلى مستندات Java PostScript باستخدام Aspose.Page لـ Java. قم بتجربة الصور والمواضع المختلفة لإنشاء مستندات مذهلة بصريًا.
## أسئلة مكررة
### هل يمكنني استخدام Aspose.Page لـ Java مع مكتبات Java الأخرى؟
نعم، يمكن دمج Aspose.Page for Java بسلاسة مع مكتبات Java الأخرى لتعزيز إمكانات معالجة المستندات.
### هل يتوفر إصدار تجريبي مجاني لـ Aspose.Page لـ Java؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.Page لـ Java من[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ Java؟
 يمكنك الحصول على ترخيص مؤقت من[هذا الرابط](https://purchase.aspose.com/temporary-license/).
### هل هناك أي منتديات لـ Aspose.Page لدعم Java؟
 نعم قم بزيارة[Aspose.Page لمنتدى جافا](https://forum.aspose.com/c/page/39) لدعم المجتمع والمناقشات.
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page لـ Java؟
 الرجوع إلى الشامل[توثيق](https://reference.aspose.com/page/java/) للحصول على معلومات تفصيلية حول Aspose.Page لـ Java.