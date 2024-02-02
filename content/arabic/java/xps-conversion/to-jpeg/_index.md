---
title: تحويل XPS إلى JPEG في جافا
linktitle: تحويل XPS إلى JPEG في جافا
second_title: Aspose.Page جافا API
description: تعرف على كيفية تحويل XPS إلى JPEG في Java باستخدام Aspose.Page. دليل شامل يتضمن تعليمات خطوة بخطوة للتكامل السلس.
type: docs
weight: 11
url: /ar/java/xps-conversion/to-jpeg/
---
## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية تحويل ملفات XPS (مواصفات ورق XML) إلى صور JPEG باستخدام Aspose.Page لـ Java. Aspose.Page هي مكتبة Java قوية تتيح للمطورين العمل مع XPS وتنسيقات المستندات الأخرى بسلاسة. سيساعدك هذا الدليل التفصيلي خطوة بخطوة على فهم العملية وتنفيذها في تطبيقات Java الخاصة بك.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- بيئة تطوير Java: تأكد من إعداد بيئة تطوير Java على جهازك.
-  Aspose.Page لمكتبة Java: قم بتنزيل وتثبيت Aspose.Page لمكتبة Java. يمكنك العثور على المكتبة[هنا](https://releases.aspose.com/page/java/).
- نموذج مستند XPS: احصل على نموذج مستند XPS الذي تريد تحويله إلى JPEG.
## حزم الاستيراد
ابدأ باستيراد الحزم الضرورية إلى فئة Java الخاصة بك:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## الخطوة 1: تهيئة المسارات ومستند XPS
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// تهيئة دفق إدخال XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## الخطوة 2: قم بتعيين خيارات JpegSaveOptions
```java
// تهيئة كائن الخيارات بالمعلمات الضرورية.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## الخطوة 3: إنشاء جهاز العرض
```java
// إنشاء جهاز تقديم لتنسيق PDF
ImageDevice device = new ImageDevice();
```
## الخطوة 4: احفظ XPS بتنسيق JPEG
```java
document.save(device, options);
```
## الخطوة 5: تكرار وحفظ صفحات JPEG
```java
//التكرار عبر أقسام المستندات (المستندات الثابتة، بمصطلحات XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // التكرار من خلال صفحات التقسيم
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // تهيئة دفق إخراج الصورة
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // كتابة الصورة
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //أغلق الدفق
        imageStream.close();
    }
}
```
ستعمل سلسلة الخطوات هذه على تحويل مستند XPS الخاص بك إلى صور JPEG بشكل فعال، ويتم حفظ كل منها على حدة.
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تحويل XPS إلى JPEG في Java باستخدام Aspose.Page. تعتبر هذه العملية لا تقدر بثمن بالنسبة للمطورين الذين يعملون في مجال تحويل المستندات في تطبيقات Java.
## أسئلة مكررة

### س: هل Aspose.Page مناسب للمشاريع التجارية؟
 ج: نعم، Aspose.Page هو منتج تجاري مع خيارات ترخيص متاحة. يفحص[هنا](https://purchase.aspose.com/buy) للتفاصيل.
### س: هل يمكنني تجربة Aspose.Page قبل الشراء؟
 ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### س: أين يمكنني العثور على وثائق Aspose.Page؟
 ج: الوثائق متاحة[هنا](https://reference.aspose.com/page/java/).
### س: كيف يمكنني الحصول على الدعم لـ Aspose.Page؟
 ج: قم بزيارة[Aspose.صفحة المنتدى](https://forum.aspose.com/c/page/39) للدعم المجتمعي.
### س: هل أحتاج إلى ترخيص مؤقت للاختبار؟
 ج: نعم، يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).