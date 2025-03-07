---
title: إضافة التدرج الأفقي في جافا بوستسكريبت
linktitle: إضافة التدرج الأفقي في جافا بوستسكريبت
second_title: Aspose.Page جافا API
description: تعرف على كيفية إضافة تدرج أفقي في Java PostScript باستخدام Aspose.Page لـ Java. قم بإنشاء مستندات مذهلة بصريًا دون عناء.
weight: 11
url: /ar/java/postscript-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة التدرج الأفقي في جافا بوستسكريبت

## مقدمة
مرحبًا بك في هذا البرنامج التعليمي الشامل حول إضافة تدرج أفقي في Java PostScript باستخدام Aspose.Page لـ Java. Aspose.Page هي مكتبة Java قوية تتيح للمطورين العمل مع PostScript وتنسيقات المستندات الأخرى. في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مستند PostScript بتدرج أفقي باستخدام أمثلة خطوة بخطوة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على جهازك.
- Aspose.Page لمكتبة جافا. يمكنك تنزيله من[وثائق Aspose.Page جافا](https://reference.aspose.com/page/java/).
## حزم الاستيراد
ابدأ باستيراد الحزم الضرورية في مشروع Java الخاص بك. تعتبر هذه الحزم ضرورية للعمل مع Aspose.Page.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## الخطوة 1: إنشاء مستطيل
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء دفق الإخراج لمستند بوستسكريبت
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// إنشاء خيارات الحفظ بحجم A4
PsSaveOptions options = new PsSaveOptions();
// قم بإنشاء مستند PS جديد مع فتح الصفحة
PsDocument document = new PsDocument(outPsStream, options, false);
//إنشاء مستطيل
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## الخطوة 2: إنشاء طلاء متدرج خطي أفقي
```java
// إنشاء طلاء متدرج خطي أفقي. يجب أن تكون مكونات القياس في التحويل مساوية لعرض المستطيل وارتفاعه.
// مكونات الترجمة هي إزاحات المستطيل.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// تعيين الطلاء
document.setPaint(paint);
```
## الخطوة 3: املأ المستطيل
```java
// املأ المستطيل
document.fill(rectangle);
```
## الخطوة 4: املأ النص بالتدرج
```java
// املأ النص بالتدرج
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## الخطوة 5: قم برسم النص باستخدام التدرج اللوني
```java
// قم بضرب النص باستخدام التدرج اللوني
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## خاتمة
تهانينا! لقد نجحت في إضافة تدرج أفقي في Java PostScript باستخدام Aspose.Page لـ Java. قدم لك هذا البرنامج التعليمي دليلاً مفصلاً خطوة بخطوة لمساعدتك في إنشاء مستندات PostScript جذابة بصريًا.
## أسئلة مكررة
### هل يمكنني استخدام Aspose.Page لـ Java في المشاريع التجارية؟
نعم، يمكن استخدام Aspose.Page for Java في المشاريع التجارية. للحصول على تفاصيل الترخيص، قم بزيارة[Aspose.Purchase](https://purchase.aspose.com/buy).
### هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.Page لـ Java[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق ودعم إضافي؟
 قم بزيارة[وثائق Aspose.Page جافا](https://reference.aspose.com/page/java/) للموارد الشاملة. للحصول على دعم المجتمع، تحقق من[منتدى Aspose.Page](https://forum.aspose.com/c/page/39).
### كيف يمكنني الحصول على ترخيص مؤقت؟
 يمكنك الحصول على ترخيص مؤقت من[Aspose.Purchase](https://purchase.aspose.com/temporary-license/).
### ما هي متطلبات النظام لـ Aspose.Page لـ Java؟
 الرجوع إلى[توثيق](https://reference.aspose.com/page/java/) لمتطلبات النظام التفصيلية.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
