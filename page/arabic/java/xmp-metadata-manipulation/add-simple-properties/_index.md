---
title: أضف خصائص بسيطة في XMP باستخدام Java
linktitle: أضف خصائص بسيطة في XMP باستخدام Java
second_title: Aspose.Page جافا API
description: قم بفتح Aspose.Page للاستفادة من إمكانات Java من خلال دليلنا حول إضافة خصائص إلى بيانات تعريف XMP في ملفات EPS. رفع مستوى معالجة المستندات دون عناء!
weight: 14
url: /ar/java/xmp-metadata-manipulation/add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# أضف خصائص بسيطة في XMP باستخدام Java

## مقدمة
في المشهد المتطور باستمرار لمعالجة المستندات، تعد إدارة البيانات التعريفية بكفاءة أمرًا بالغ الأهمية. يعمل Aspose.Page for Java على تمكين المطورين من معالجة بيانات منصة البيانات التعريفية القابلة للتوسيع (XMP) بسلاسة. في هذا البرنامج التعليمي، سنستكشف عملية إضافة خصائص بسيطة إلى XMP باستخدام Java، مما يوفر لك دليلاً شاملاً خطوة بخطوة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
-  تم تثبيت Aspose.Page لمكتبة Java. يمكنك تنزيله[هنا](https://releases.aspose.com/page/java/).
- ملف EPS نموذجي يحتوي على البيانات الوصفية. إذا لم يكن لديك واحد، فلا تتردد في استخدام الملف "xmp3.eps" المتوفر.
## حزم الاستيراد
تأكد من استيراد الحزم اللازمة لبدء مشروعك:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## الخطوة 1: احصل على بيانات تعريف XMP
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// تهيئة دفق ملف EPS للإدخال
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// احصل على بيانات تعريف XMP. إذا كان ملف EPS لا يحتوي على بيانات تعريف XMP، فسنحصل على ملف جديد مملوء بالقيم من تعليقات بيانات تعريف PS (%%Creator، %%CreateDate، %%Title، وما إلى ذلك)
XmpMetadata xmp = document.getXmpMetadata();
```
## الخطوة 2: إضافة خاصية التاريخ
```java
// أضف قيمة خاصية التاريخ "xmp:Date1".
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## الخطوة 3: إضافة خاصية عدد صحيح
```java
// أضف قيمة خاصية العدد الصحيح "xmp:Intg1".
xmp.put("xmp:Intg1", new XmpValue(111));
```
## الخطوة 4: إضافة خاصية مزدوجة
```java
// إضافة قيمة خاصية مزدوجة "xmp:Double1".
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## الخطوة 5: إضافة خاصية السلسلة
```java
// أضف قيمة خاصية السلسلة "xmp:String1".
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## الخطوة 6: حفظ المستند
```java
// تهيئة دفق ملف EPS الناتج
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//احفظ المستند باستخدام بيانات تعريف XMP التي تم تغييرها
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## الخطوة 7: إغلاق التدفقات
```java
// إغلاق دفق EPS المدخلات
psStream.close();
```
## خاتمة
يعمل Aspose.Page for Java على تبسيط عملية معالجة بيانات تعريف XMP في ملفات EPS. باتباع هذا الدليل المفصّل خطوة بخطوة، يمكنك بسهولة إضافة خصائص بسيطة لتحسين البيانات التعريفية لمستندك.
## أسئلة مكررة
### هل يمكنني استخدام Aspose.Page لـ Java مع لغات البرمجة الأخرى؟
يدعم Aspose.Page Java بشكل أساسي، ولكن هناك إصدارات متاحة للغات أخرى مثل .NET.
### هل يتوفر إصدار تجريبي مجاني لـ Aspose.Page لـ Java؟
 نعم، يمكنك استكشاف مميزات Aspose.Page من خلال الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق مفصلة عن Aspose.Page لـ Java؟
 الوثائق متاحة[هنا](https://reference.aspose.com/page/java/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ Java؟
 يمكن الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني شراء Aspose.Page لـ Java؟
 يمكنك شراء المنتج[هنا](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
