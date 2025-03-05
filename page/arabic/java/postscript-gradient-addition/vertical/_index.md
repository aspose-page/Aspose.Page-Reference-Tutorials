---
title: إضافة التدرج العمودي في جافا بوستسكريبت
linktitle: إضافة التدرج العمودي في جافا بوستسكريبت
second_title: Aspose.Page جافا API
description: استكشف الدليل خطوة بخطوة لإضافة التدرجات الرأسية في Java PostScript باستخدام Aspose.Page لـ Java. قم بتحسين مستنداتك دون عناء باستخدام صور نابضة بالحياة.
type: docs
weight: 14
url: /ar/java/postscript-gradient-addition/vertical/
---
## مقدمة
مرحبًا بك في هذا الدليل التفصيلي خطوة بخطوة حول إضافة تدرج رأسي في Java PostScript باستخدام Aspose.Page لـ Java. إذا كنت ترغب في تحسين المستند الخاص بك بتدرجات لافتة للنظر، فهذا البرنامج التعليمي مناسب لك. يوفر Aspose.Page for Java أدوات قوية لمعالجة مستندات PostScript بسلاسة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على جهازك.
-  Aspose.Page لمكتبة جافا. يمكنك تنزيله[هنا](https://releases.aspose.com/page/java/).
## حزم الاستيراد
في مشروع Java الخاص بك، قم باستيراد الحزم اللازمة للبدء:
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
الآن، دعونا نقسم عملية إضافة التدرج الرأسي في Java PostScript إلى خطوات متعددة.
## الخطوة 1: قم بإعداد دليل المستندات الخاص بك
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
```
## الخطوة 2: إنشاء دفق الإخراج لمستند PostScript
```java
// إنشاء دفق الإخراج لمستند بوستسكريبت
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## الخطوة 3: إنشاء خيارات الحفظ بحجم A4
```java
// إنشاء خيارات الحفظ بحجم A4
PsSaveOptions options = new PsSaveOptions();
```
## الخطوة 4: إنشاء مستند PS جديد
```java
// قم بإنشاء مستند PS جديد مع فتح الصفحة
PsDocument document = new PsDocument(outPsStream, options, false);
```
## الخطوة 5: إنشاء مستطيل
```java
//إنشاء مستطيل
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## الخطوة 6: إعداد الألوان والكسور للتدرج
```java
// إنشاء صفائف من الألوان والكسور للتدرج.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## الخطوة 7: إنشاء تحويل التدرج
```java
// إنشاء تحويل التدرج. يجب أن تكون مكونات القياس في التحويل مساوية لعرض المستطيل وارتفاعه.
// مكونات الترجمة هي إزاحات المستطيل.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// قم بتدوير التدرج بمقدار 90 درجة حول الأصل
transform.rotate(90 * (Math.PI / 180));
```
## الخطوة 8: إنشاء طلاء متدرج خطي عمودي
```java
// إنشاء طلاء متدرج خطي عمودي.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## الخطوة 9: اضبط الطلاء واملأ المستطيل
```java
// تعيين الطلاء
document.setPaint(paint);
// املأ المستطيل
document.fill(rectangle);
```
## الخطوة 10: أغلق الصفحة الحالية واحفظ المستند
```java
// إغلاق الصفحة الحالية
document.closePage();
// احفظ المستند
document.save();
```
تهانينا! لقد نجحت في إضافة تدرج عمودي إلى مستند Java PostScript الخاص بك باستخدام Aspose.Page for Java.
## خاتمة
في هذا البرنامج التعليمي، استكشفنا عملية تحسين مستنداتك باستخدام تدرجات رأسية نابضة بالحياة باستخدام Aspose.Page لـ Java. الآن، يمكنك الارتقاء بمعالجة المستندات الخاصة بك إلى المستوى التالي من خلال دمج صور مذهلة.
## أسئلة مكررة
### هل يمكنني استخدام Aspose.Page لـ Java مع مكتبات Java الأخرى؟
نعم، تم تصميم Aspose.Page for Java للعمل بسلاسة مع مكتبات Java الأخرى.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page لـ Java؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق إضافية؟
 الوثائق التفصيلية متاحة[هنا](https://reference.aspose.com/page/java/).
### كيف يمكنني شراء Aspose.Page لجافا؟
 يمكنك شراء Aspose.Page لجافا[هنا](https://purchase.aspose.com/buy).
### هل يوجد منتدى لمناقشات Aspose.Page؟
 نعم، يمكنك الانضمام إلى منتدى المجتمع[هنا](https://forum.aspose.com/c/page/39).