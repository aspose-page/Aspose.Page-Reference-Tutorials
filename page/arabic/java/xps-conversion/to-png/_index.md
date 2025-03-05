---
title: تحويل XPS إلى PNG في جافا
linktitle: تحويل XPS إلى PNG في جافا
second_title: Aspose.Page جافا API
description: يمكنك بسهولة تحويل XPS إلى PNG في Java باستخدام Aspose.Page. قم بتبسيط مهام المستندات باستخدام هذا الحل الموثوق والصديق للمطورين.
type: docs
weight: 13
url: /ar/java/xps-conversion/to-png/
---
## مقدمة
في العالم الديناميكي لتطوير البرمجيات، تبرز الحاجة بشكل متكرر إلى تحويل مستندات XPS (مواصفات ورق XML) إلى صور PNG (رسومات الشبكة المحمولة). لإنجاز هذه المهمة بسلاسة في Java، يوفر Aspose.Page حلاً قويًا. في هذا البرنامج التعليمي، سنتعرف على عملية تحويل XPS إلى PNG باستخدام Aspose.Page لـ Java.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من إعداد المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Page لـ Java: قم بتنزيل وتثبيت مكتبة Aspose.Page. يمكنك العثور على رابط التحميل[هنا](https://releases.aspose.com/page/java/).
3. بيئة التطوير المتكاملة (IDE): اختر بيئة تطوير متكاملة متوافقة مع Java مثل IntelliJ IDEA أو Eclipse.
## حزم الاستيراد
في مشروع Java الخاص بك، قم باستيراد الحزم اللازمة للاستفادة من وظائف Aspose.Page. أضف عبارات الاستيراد التالية في بداية ملف Java الخاص بك:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## الخطوة 1: قم بتعيين دليل المستندات
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
```
## الخطوة 2: تحميل مستند XPS
```java
// قم بتحميل مستند XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## الخطوة 3: تهيئة الخيارات
```java
// تهيئة كائن الخيارات بالمعلمات الضرورية.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## الخطوة 4: إنشاء جهاز العرض
```java
// إنشاء جهاز تقديم لتنسيق PDF
ImageDevice device = new ImageDevice();
```
## الخطوة 5: الحفظ والتكرار
```java
// احفظ مستند XPS إلى PNG باستخدام الخيارات والجهاز
document.save(device, options);
//التكرار عبر أقسام المستندات (المستندات الثابتة، بمصطلحات XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // التكرار من خلال صفحات التقسيم
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // تهيئة دفق إخراج الصورة
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // كتابة الصورة
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // أغلق الدفق
        imageStream.close();
    }
}
```
باتباع هذه الخطوات، يمكنك بسهولة تحويل مستندات XPS إلى صور PNG باستخدام Aspose.Page لـ Java.
## خاتمة
في الختام، يعمل Aspose.Page for Java على تبسيط عملية تحويل XPS إلى PNG، مما يوفر للمطورين أداة موثوقة وفعالة. قم بدمج هذه المكتبة في مشاريع Java الخاصة بك لتبسيط مهام معالجة المستندات.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Page لـ Java في المشاريع التجارية؟
 نعم، Aspose.Page هو منتج تجاري. يمكنك العثور على معلومات الترخيص[هنا](https://purchase.aspose.com/buy).
### هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، يمكنك استكشاف النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page لـ Java؟
 الوثائق الشاملة متاحة[هنا](https://reference.aspose.com/page/java/).
### كيف يمكنني الحصول على ترخيص مؤقت لأغراض الاختبار؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### هل توجد منتديات مجتمعية لمناقشات Aspose.Page؟
 نعم، قم بزيارة منتديات المجتمع[هنا](https://forum.aspose.com/c/page/39).