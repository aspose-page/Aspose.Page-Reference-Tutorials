---
title: إضافة نمط تبليط الملمس في Java PostScript
linktitle: إضافة نمط تبليط الملمس في Java PostScript
second_title: Aspose.Page جافا API
description: يمكنك بسهولة إضافة أنماط تجانب النسيج إلى مستندات PostScript باستخدام Aspose.Page لـ Java. استكشف دليل التكامل السلس الخاص بنا للتعرف على الإمكانيات الإبداعية.
type: docs
weight: 10
url: /ar/java/postscript-texture-patterns/add-texture-tiling-pattern/
---
## مقدمة
في مجال تطوير Java، يعد إنشاء أنماط ومواد معقدة في مستندات PostScript مطلبًا شائعًا. أثبت Aspose.Page for Java أنه أداة قيمة في تحقيق هذه المهمة دون عناء. في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة نمط تجانب النسيج في مستند Java PostScript باستخدام Aspose.Page.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- الفهم الأساسي للغة البرمجة جافا.
- الإلمام ببنية مستند PostScript.
-  تم تثبيت Aspose.Page لمكتبة Java. يمكنك تنزيله[هنا](https://releases.aspose.com/page/java/).
## حزم الاستيراد
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
## الخطوة 1: إنشاء مستند بوستسكريبت
ابدأ بإنشاء مستند PostScript جديد، مع تحديد خيارات دفق الإخراج والحفظ. تأكد من تكوين المسارات اللازمة.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء دفق الإخراج لمستند بوستسكريبت
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// إنشاء خيارات الحفظ بحجم A4
PsSaveOptions options = new PsSaveOptions();
// قم بإنشاء مستند PS جديد مع فتح الصفحة
PsDocument document = new PsDocument(outPsStream, options, false);
// قم بإنشاء مستند PS جديد مع فتح الصفحة
PsDocument document = new PsDocument(outPsStream, options, false);
```
## الخطوة 2: إعداد بيئة الرسومات
قم بإعداد بيئة الرسومات عن طريق ترجمة الأصل وإنشاء صورة BufferedImage من ملف صورة النسيج.
```java
document.writeGraphicsSave();
document.translate(200, 100);
// قم بإنشاء كائن BufferedImage من ملف الصورة
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```
## الخطوة 3: إنشاء فرشاة الملمس
قم بتحديد فرشاة نسيج من الصورة، مع تحديد المنطقة التي سيتم تغطيتها بواسطة النسيج.
```java
// إنشاء مساحة صورة مضاعفة العرض
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// إنشاء فرشاة الملمس من الصورة
TexturePaint paint = new TexturePaint(image, imageArea);
```
## الخطوة 4: رسم وملء الأشكال
قم بإنشاء مستطيل واملأه بفرشاة الملمس المحددة. بالإضافة إلى ذلك، قم برسم الشكل وتحديده للحصول على جاذبية بصرية.
```java
// إنشاء مستطيل
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// قم بتعيين فرشاة الملمس هذه كطلاء حالي
document.setPaint(paint);
// ملء المستطيل
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```
## الخطوة 5: إضافة نص بنمط الملمس
أضف نصًا إلى المستند واملأه/حدده بنمط النسيج. قم بتخصيص الخط والموضع والمعلمات الأخرى حسب الحاجة.
```java
// املأ النص بنمط الملمس
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// الخطوط العريضة للنص مع نمط الملمس
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## الخطوة 6: حفظ وإغلاق
اختتم العملية عن طريق إغلاق الصفحة الحالية وحفظ المستند وضمان التنفيذ السلس.
```java
// إغلاق الصفحة الحالية
document.closePage();
// احفظ المستند
document.save();
```
## خاتمة
تهانينا! لقد نجحت في إضافة نمط تبليط نسيج إلى مستند Java PostScript باستخدام Aspose.Page لـ Java. لا تتردد في استكشاف المزيد من خيارات التخصيص وإطلاق العنان للإمكانات الكاملة لهذه المكتبة القوية.

## الأسئلة الشائعة
### هل Aspose.Page for Java مناسب للمبتدئين؟
قطعاً! يوفر Aspose.Page for Java وثائق شاملة، مما يجعله في متناول المطورين من جميع مستويات المهارة.
### هل يمكنني دمج Aspose.Page for Java في مشروع Java الحالي الخاص بي؟
 نعم، يمكنك بسهولة دمج Aspose.Page for Java في مشروعك عن طريق اتباع الوثائق المتوفرة[هنا](https://reference.aspose.com/page/java/).
### أين يمكنني العثور على الدعم أو مناقشة الاستفسارات المتعلقة بـ Aspose.Page؟
 قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع وطلب المساعدة.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page لـ Java؟
 نعم، يمكنك استكشاف النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ Java؟
 يزور[هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت.