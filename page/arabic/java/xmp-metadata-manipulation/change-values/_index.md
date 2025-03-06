---
title: تغيير القيم في XMP باستخدام Java
linktitle: تغيير القيم في XMP باستخدام Java
second_title: Aspose.Page جافا API
description: قم بتحسين مستندات EPS باستخدام Aspose.Page لـ Java. قم بتعديل بيانات تعريف XMP بسهولة للحصول على محتوى مخصص واحترافي. #تطوير جافا
weight: 17
url: /ar/java/xmp-metadata-manipulation/change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تغيير القيم في XMP باستخدام Java

## مقدمة
في مجال معالجة المستندات ومعالجتها، تبرز Aspose.Page for Java كأداة قوية. يتعمق هذا البرنامج التعليمي في عملية تغيير قيم XMP (منصة بيانات التعريف القابلة للتوسيع) في مستندات EPS (Encapsulated PostScript) باستخدام Java مع مكتبة Aspose.Page. باتباع الدليل الموضح خطوة بخطوة، ستتعلم كيفية تعديل البيانات التعريفية دون عناء، مما يضمن أن مستنداتك مصممة وفقًا لمتطلباتك المحددة.
## المتطلبات الأساسية
قبل الشروع في هذا البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1. بيئة تطوير Java: تأكد من أن لديك بيئة تطوير Java عاملة على جهازك.
2.  Aspose.Page لمكتبة Java: قم بتنزيل وتثبيت Aspose.Page لمكتبة Java. يمكنك العثور على الحزمة اللازمة[هنا](https://releases.aspose.com/page/java/).
## حزم الاستيراد
ابدأ باستيراد الحزم المطلوبة إلى مشروع Java الخاص بك. تعتبر هذه الحزم حيوية للتفاعل مع مستندات EPS ومعالجتها.
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
قم باسترجاع بيانات تعريف XMP من مستند EPS. إذا كان ملف EPS لا يحتوي على بيانات تعريف XMP، فسيتم إنشاء ملف جديد بقيم من تعليقات بيانات تعريف PS مثل %%Creator، و%%CreateDate، و%%Title.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// تهيئة دفق ملف EPS للإدخال
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// احصل على بيانات تعريف XMP. إذا كان ملف EPS لا يحتوي على بيانات تعريف XMP، فسيتم إنشاء ملف جديد بقيم من تعليقات بيانات تعريف PS
XmpMetadata xmp = document.getXmpMetadata();
```
## الخطوة 2: تغيير قيمة "تعديل التاريخ".
قم بتعديل قيمة "ModifyDate" في بيانات تعريف XMP لتعكس التاريخ المطلوب.
```java
// قم بتغيير قيمة "تعديل التاريخ".
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## الخطوة 3: تغيير قيمة "المنشئ".
قم بتحديث قيمة "المنشئ" في بيانات تعريف XMP لتحديد منشئ المستند.
```java
// تغيير قيمة "المنشئ".
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## الخطوة 4: تغيير قيمة "العنوان".
قم بتعديل قيمة "العنوان" في بيانات تعريف XMP لتعيين عنوان مناسب للمستند.
```java
//تغيير قيمة "العنوان".
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## الخطوة 5: احفظ المستند باستخدام بيانات تعريف XMP التي تم تغييرها
احفظ المستند مع بيانات تعريف XMP المحدثة في ملف EPS جديد.
```java
// تهيئة دفق ملف EPS الناتج
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//احفظ المستند باستخدام بيانات تعريف XMP التي تم تغييرها
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## خاتمة
تهانينا! لقد نجحت في اجتياز عملية تغيير قيم XMP في مستندات EPS باستخدام Aspose.Page لـ Java. لقد زودك هذا البرنامج التعليمي بالمعرفة اللازمة لتعديل البيانات التعريفية، مما يضمن توافق مستنداتك مع متطلباتك المحددة بسلاسة.
## الأسئلة الشائعة
### س: كيف يمكنني التعامل مع اعتبارات المنطقة الزمنية عند تعديل قيم XMP؟
 يستخدم`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` لضمان الاتساق في إعدادات المنطقة الزمنية.
### س: هل يمكنني تغيير قيم XMP متعددة في عملية واحدة؟
 نعم باستخدام`put` لكل قيمة مرغوبة، يمكنك تعديل قيم XMP متعددة بشكل متزامن.
### س: أين يمكنني العثور على وثائق إضافية لـ Aspose.Page لـ Java؟
 استكشاف الوثائق الشاملة[هنا](https://reference.aspose.com/page/java/).
### س: هل تتوفر نسخة تجريبية مجانية من Aspose.Page لـ Java؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ Java؟
 الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
