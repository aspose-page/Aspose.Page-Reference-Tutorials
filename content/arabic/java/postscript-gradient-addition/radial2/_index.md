---
title: جافا بوستسكريبت شعاعي التدرج مع Aspose.Page
linktitle: جافا بوستسكريبت شعاعي التدرج مع Aspose.Page
second_title: Aspose.Page جافا API
description: استكشف الدليل خطوة بخطوة لإضافة Radial Gradient في Java PostScript باستخدام Aspose.Page للحصول على رسومات مذهلة في تطبيقات Java الخاصة بك.
type: docs
weight: 13
url: /ar/java/postscript-gradient-addition/radial2/
---
## مقدمة
مرحبًا بك في دليلنا خطوة بخطوة حول إضافة Radial Gradient 2 في Java PostScript باستخدام Aspose.Page لـ Java. سيرشدك هذا البرنامج التعليمي خلال عملية إنشاء مستند PostScript بتدرج شعاعي جميل، مما يعزز تطبيقات Java الخاصة بك برسومات جذابة بصريًا.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- معرفة عملية ببرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على جهازك.
-  Aspose.Page لمكتبة Java، والتي يمكنك تنزيلها من[وثائق Aspose.Page جافا](https://reference.aspose.com/page/java/).
## حزم الاستيراد
في مشروع Java الخاص بك، قم باستيراد الحزم اللازمة لـ Aspose.Page:
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## الخطوة 1: إعداد دليل المستندات
حدد المسار إلى دليل المستندات الخاص بك:
```java
String dataDir = "Your Document Directory";
```
## الخطوة 2: إنشاء دفق الإخراج
قم بإنشاء دفق إخراج لمستند PostScript:
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## الخطوة 3: إنشاء خيارات الحفظ
إنشاء خيارات الحفظ بحجم A4:
```java
PsSaveOptions options = new PsSaveOptions();
```
## الخطوة 4: إنشاء مستند PS
قم بإنشاء مستند PS جديد مع فتح الصفحة:
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## الخطوة 5: إنشاء دائرة
حدد دائرة باستخدام فئة Ellipse2D.Float:
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## الخطوة 6: تحديد الألوان المتدرجة
قم بإنشاء صفائف من الألوان والكسور للتدرج الشعاعي:
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## الخطوة 7: إنشاء AffineTransform
قم بإنشاء AffineTransform للتدرج الشعاعي:
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## الخطوة 8: إنشاء طلاء متدرج شعاعي
قم بإنشاء RadialGradientPaint باستخدام المعلمات المحددة:
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## الخطوة 9: تعيين دائرة الطلاء والتعبئة
اضبط الطلاء واملأ الدائرة بالتدرج الشعاعي:
```java
document.setPaint(paint);
document.fill(circle);
```
## الخطوة 10: أغلق الصفحة واحفظ المستند
أغلق الصفحة الحالية واحفظ المستند:
```java
document.closePage();
document.save();
```
تهانينا! لقد نجحت في إضافة Radial Gradient 2 إلى Java PostScript باستخدام Aspose.Page لـ Java.
## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية تحسين تطبيقات Java الخاصة بك باستخدام التدرجات الشعاعية في مستندات PostScript. يوفر Aspose.Page for Java مجموعة قوية من الأدوات لإنشاء رسومات مذهلة، مما يسمح لك بالارتقاء بمشروعات Java الخاصة بك إلى المستوى التالي.
## الأسئلة الشائعة
### س: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page لـ Java؟
 ج: الوثائق متاحة[هنا](https://reference.aspose.com/page/java/).
### س: كيف يمكنني تنزيل Aspose.Page لـ Java؟
 ج: يمكنك تحميله من[صفحة الإصدارات](https://releases.aspose.com/page/java/).
### س: هل هناك نسخة تجريبية مجانية متاحة؟
 ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### س: هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ Java؟
 ج: نعم، يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني الحصول على دعم المجتمع والمشاركة في المناقشات؟
 ج: قم بزيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39).