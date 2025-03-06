---
title: إتقان التدرجات الشعاعية في Java PostScript باستخدام Aspose.Page
linktitle: إتقان التدرجات الشعاعية في جافا
second_title: Aspose.Page جافا API
description: تعرف على كيفية إضافة تدرجات شعاعية مذهلة في Java PostScript باستخدام Aspose.Page لـ Java. ارفع مستوى مستندات PostScript الخاصة بك باستخدام هذا الدليل المفصّل خطوة بخطوة.
weight: 12
url: /ar/java/postscript-gradient-addition/radial1/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان التدرجات الشعاعية في Java PostScript باستخدام Aspose.Page

## مقدمة
مرحبًا بك في دليلنا خطوة بخطوة حول كيفية إضافة تدرج لوني شعاعي في Java PostScript باستخدام Aspose.Page. في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مستند PostScript بتدرج لوني نصف قطري جميل. Aspose.Page for Java هي مكتبة قوية تتيح لك العمل مع ملفات PostScript بسلاسة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- Java Development Kit (JDK): تأكد من تثبيت Java على نظامك.
-  Aspose.Page لـ Java: قم بتنزيل وتثبيت مكتبة Aspose.Page من[هنا](https://releases.aspose.com/page/java/).
- بيئة التطوير المتكاملة (IDE): اختر Java IDE المفضل لديك، مثل Eclipse أو IntelliJ.
## حزم الاستيراد
ابدأ باستيراد الحزم اللازمة للبدء في مشروع Java PostScript الخاص بك:
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## الخطوة 1: إنشاء مستطيل
لنبدأ بإنشاء مستطيل في مستند PostScript الخاص بنا:
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء دفق الإخراج لمستند بوستسكريبت
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// إنشاء خيارات الحفظ بحجم A4
PsSaveOptions options = new PsSaveOptions();
// قم بإنشاء مستند PS جديد مع فتح الصفحة
PsDocument document = new PsDocument(outPsStream, options, false);
//إنشاء مستطيل
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```
## الخطوة 2: تحديد الألوان والكسور
تحديد صفائف من الألوان والكسور للتدرج الشعاعي:
```java
// إنشاء صفائف من الألوان والكسور للتدرج
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```
## الخطوة 3: إنشاء طلاء متدرج شعاعي
قم بإنشاء طلاء متدرج شعاعي للمستطيل:
```java
// إنشاء طلاء متدرج شعاعي
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(300, 200), 100, new Point2D.Float(300, 200),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## الخطوة 4: اضبط الطلاء واملأ المستطيل
اضبط الطلاء واملأ المستطيل بالتدرج الشعاعي:
```java
// تعيين الطلاء
document.setPaint(paint);
// املأ المستطيل
document.fill(rectangle);
```
## الخطوة 5: إغلاق وحفظ
أخيرًا، أغلق الصفحة الحالية واحفظ المستند:
```java
// إغلاق الصفحة الحالية
document.closePage();
// احفظ المستند
document.save();
```
يؤدي هذا إلى إكمال عملية إضافة تدرج شعاعي إلى مستند Java PostScript الخاص بك باستخدام Aspose.Page.
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تحسين مستندات PostScript الخاصة بك باستخدام التدرجات الشعاعية باستخدام Aspose.Page لـ Java. قم بتجربة الألوان والتكوينات المختلفة لإنشاء تأثيرات بصرية مذهلة.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Page لـ Java في المشاريع التجارية؟
 نعم، يمكنك استخدام Aspose.Page for Java في المشاريع التجارية. للحصول على تفاصيل الترخيص، قم بزيارة[هنا](https://purchase.aspose.com/buy).
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page لـ Java؟
 الوثائق متاحة[هنا](https://reference.aspose.com/page/java/).
### هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على ترخيص مؤقت؟
 الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### هل تحتاج إلى دعم المجتمع؟
 انضم إلى مجتمع Aspose.Page[المنتدى](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
