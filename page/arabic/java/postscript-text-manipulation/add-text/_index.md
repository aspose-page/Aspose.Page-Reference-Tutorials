---
title: Aspose.Page معالجة نص جافا
linktitle: إضافة نص في جافا بوستسكريبت
second_title: Aspose.Page جافا API
description: اكتشف قوة Aspose.Page لـ Java في برنامجنا التعليمي حول إضافة نص إلى مستندات PostScript. تعلم كيفية استخدام النظام والخطوط المخصصة بسهولة.
weight: 10
url: /ar/java/postscript-text-manipulation/add-text/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page معالجة نص جافا

## مقدمة
مرحبًا بك في دليلنا خطوة بخطوة حول إضافة نص في Java PostScript باستخدام Aspose.Page لـ Java. Aspose.Page for Java هي مكتبة قوية تتيح للمطورين التعامل مع مستندات PostScript بسهولة. في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة النص، واستخدام خطوط النظام والخطوط المخصصة، وتحديد النص، ودمج الحدود للحصول على نتيجة جذابة بصريًا.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
-  تم تثبيت Aspose.Page لمكتبة Java. يمكنك تنزيله من[Aspose.Page لصفحة تنزيل Java](https://releases.aspose.com/page/java/).
-  الخطوط الضرورية المتوفرة في المجلد المحدد. يمكنك العثور على معلومات إضافية في[Aspose.Page لوثائق جافا](https://reference.aspose.com/page/java/).
## حزم الاستيراد
في مشروع Java الخاص بك، قم باستيراد الحزم اللازمة لـ Aspose.Page لـ Java:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## الخطوة 1: إعداد المستند
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// إنشاء دفق الإخراج لمستند بوستسكريبت
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// إنشاء خيارات الحفظ بحجم A4
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// نص للكتابة إلى ملف PS
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// قم بإنشاء مستند PS جديد مكون من صفحة واحدة
PsDocument document = new PsDocument(outPsStream, options, false);
```
## الخطوة 2: استخدام خط النظام لملء النص
```java
// استخدام خط النظام لملء النص
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// تعبئة النص باللون الافتراضي أو المحدد بالفعل (أسود)
document.fillText(str, font, 50, 100);
// تعبئة النص باللون الأزرق
document.fillText(str, font, 50, 150, Color.BLUE);
```
## الخطوة 3: استخدام الخط المخصص لملء النص
```java
// استخدام الخط المخصص لملء النص
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// تعبئة النص باللون الافتراضي أو المحدد بالفعل (أسود)
document.fillText(str, drFont, 50, 200);
// تعبئة النص باللون الأزرق
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## الخطوة 4: تحديد النص باستخدام خط النظام
```java
// استخدام خط النظام لتحديد النص
document.outlineText(str, font, 50, 300);
// مخطط تفصيلي للنص بقلم باللون الأزرق البنفسجي بعرض نقطتين
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// املأ النص باللون البرتقالي وحدده بقلم أزرق بعرض نقطتين
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## الخطوة 5: تحديد النص بخط مخصص
```java
// استخدام الخط المخصص لتحديد النص
document.outlineText(str, drFont, 50, 450);
// مخطط تفصيلي للنص بقلم باللون الأزرق البنفسجي بعرض نقطتين
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// املأ النص باللون البرتقالي وحدده بقلم أزرق بعرض نقطتين
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## الخطوة 6: احفظ المستند
```java
// إغلاق الصفحة الحالية
document.closePage();
// احفظ المستند
document.save();
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة نص في Java PostScript باستخدام Aspose.Page لـ Java. قم بتجربة الخطوط والألوان وخيارات المخطط التفصيلي المختلفة لتحسين المستند بشكل أكبر.
## أسئلة مكررة
### هل يمكنني استخدام الخطوط المخصصة الخاصة بي مع Aspose.Page لـ Java؟
 نعم، يمكنك استخدام الخطوط المخصصة عن طريق تحديد اسم الخط وحجمه في ملف`DrFont` فصل.
### كيف يمكنني تغيير لون النص؟
 يمكنك ضبط اللون المطلوب باستخدام`Color` الفصل عند ملء النص أو تحديده.
### هل من الممكن إضافة صفحات متعددة إلى مستند PostScript؟
قطعاً! يمكنك إنشاء صفحات متعددة عن طريق تكرار خطوات إنشاء المستند وحفظه.
###  ما هو الغرض من`ExternalFontCache` class?
`ExternalFontCache` يُستخدم لجلب الخطوط المخصصة، مما يضمن توفرها لمعالجة النص.
### هل يمكنني تطبيق حدود مختلفة على النص المحدد؟
 نعم، يمكنك تخصيص عرض ولون الحد باستخدام`Stroke` الطبقة و`Color` الطبقة، على التوالي.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
