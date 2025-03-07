---
title: إضافة التدرج القطري في Java PostScript
linktitle: إضافة التدرج القطري في Java PostScript
second_title: Aspose.Page جافا API
description: قم بتحسين مستندات Java PostScript الخاصة بك باستخدام التدرجات القطرية باستخدام Aspose.Page for Java. اتبع دليلنا خطوة بخطوة لإضافة انتقالات ألوان نابضة بالحياة دون عناء.
weight: 10
url: /ar/java/postscript-gradient-addition/diagonal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة التدرج القطري في Java PostScript

## مقدمة
مرحبًا بك في دليلنا خطوة بخطوة حول إضافة تدرج قطري في Java PostScript باستخدام Aspose.Page لـ Java. في هذا البرنامج التعليمي، سنرشدك خلال العملية، مع تقسيم كل مثال إلى خطوات متعددة. باعتباري كاتبًا ماهرًا في مجال تحسين محركات البحث (SEO)، سأتأكد من أن المحتوى ليس مفيدًا فحسب، بل مُحسّن أيضًا لمحركات البحث، مما يسهل على المطورين والمتحمسين المتابعة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على نظامك.
- بيئة التطوير المتكاملة (IDE) مثل Eclipse أو IntelliJ.
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
## الخطوة 1: إنشاء دفق الإخراج لمستند PostScript
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء دفق الإخراج لمستند بوستسكريبت
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```
## الخطوة 2: إنشاء خيارات الحفظ بحجم A4
```java
// إنشاء خيارات الحفظ بحجم A4
PsSaveOptions options = new PsSaveOptions();
```
## الخطوة 3: إنشاء مستند PS جديد
```java
// قم بإنشاء مستند PS جديد مع فتح الصفحة
PsDocument document = new PsDocument(outPsStream, options, false);
```
## الخطوة 4: إنشاء مستطيل
```java
//إنشاء مستطيل
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## الخطوة 5: إنشاء تحويل التدرج
```java
//إنشاء تحويل التدرج. يجب أن تكون مكونات المقياس مساوية لعرض المستطيل وارتفاعه.
// مكونات الترجمة هي إزاحات المستطيل.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// قم بتدوير التدرج، ثم قم بقياسه وترجمته للحصول على انتقال لوني مرئي
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```
## الخطوة 6: إنشاء طلاء متدرج خطي قطري
```java
// قم بإنشاء طلاء متدرج خطي قطري
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```
## الخطوة 7: اضبط الطلاء واملأ المستطيل
```java
// اضبط الطلاء واملأ المستطيل
document.setPaint(paint);
document.fill(rectangle);
```
## الخطوة 8: أغلق الصفحة الحالية واحفظ المستند
```java
// أغلق الصفحة الحالية واحفظ المستند
document.closePage();
document.save();
```
باتباع هذه الخطوات، ستنجح في إضافة تدرج قطري في Java PostScript باستخدام Aspose.Page for Java.
## خاتمة
تهانينا! لقد تعلمت كيفية تحسين مستندات Java PostScript الخاصة بك باستخدام التدرجات القطرية باستخدام Aspose.Page لـ Java. قم بتجربة معلمات مختلفة لتحقيق تأثيرات بصرية فريدة.
## أسئلة مكررة
### س: هل يمكنني استخدام هذه المكتبة لعمليات رسومية أخرى في Java؟
ج: نعم، يوفر Aspose.Page for Java مجموعة من الميزات للعمل مع PostScript والعناصر الرسومية الأخرى.
### س: هل تتوفر نسخة تجريبية مجانية من Aspose.Page لـ Java؟
 ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### س: أين يمكنني العثور على وثائق Aspose.Page لـ Java؟
 ج: الوثائق متاحة[هنا](https://reference.aspose.com/page/java/).
### س: كيف يمكنني شراء ترخيص Aspose.Page لـ Java؟
 ج: يمكنك شراء ترخيص[هنا](https://purchase.aspose.com/buy).
### س: هل تحتاج إلى مساعدة أو لديك أسئلة؟
 ج: قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
