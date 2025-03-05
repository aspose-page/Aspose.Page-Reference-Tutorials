---
title: إضافة عناصر المصفوفة في بيانات تعريف XMP باستخدام Java
linktitle: إضافة عناصر المصفوفة في بيانات تعريف XMP باستخدام Java
second_title: Aspose.Page جافا API
description: قم بتحسين ملفات EPS باستخدام Aspose.Page لـ Java. تعلم كيفية إضافة عناصر المصفوفة إلى بيانات تعريف XMP دون عناء. اتبع دليلنا خطوة بخطوة الآن!
type: docs
weight: 10
url: /ar/java/xmp-metadata-manipulation/add-array-items/
---
## مقدمة
مرحبًا بك في دليلنا خطوة بخطوة حول استخدام Aspose.Page لـ Java لإضافة عناصر المصفوفة في بيانات تعريف XMP. Aspose.Page هي مكتبة Java قوية تتيح لك التعامل مع تنسيقات المستندات المختلفة والعمل معها، بما في ذلك ملفات EPS. في هذا البرنامج التعليمي، سنركز على المهمة المحددة المتمثلة في إضافة عناصر المصفوفة في بيانات تعريف XMP باستخدام Java.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- تم تثبيت Aspose.Page لمكتبة Java.
- الفهم الأساسي لبرمجة جافا.
- ملف EPS صالح يحتوي على بيانات تعريف XMP موجودة أو تعليقات بيانات تعريف PS.
## حزم الاستيراد
للبدء، تحتاج إلى استيراد الحزم اللازمة للعمل مع Aspose.Page. قم بتضمين الأسطر التالية في بداية ملف Java الخاص بك:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
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
في هذه الخطوة، نقوم باسترداد بيانات تعريف XMP الموجودة من ملف EPS. إذا كان ملف EPS لا يحتوي بالفعل على بيانات تعريف XMP، فسيقوم Aspose.Page بإنشاء بيانات جديدة وتعبئتها بالقيم من تعليقات بيانات تعريف PS.
## الخطوة 2: إضافة عنصر الصفيف "dc:title".
```java
// قم بإضافة عنصر صفيف "dc:title" آخر
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
الآن، نقوم بإضافة عنصر مصفوفة جديد إلى خاصية "dc:title" في بيانات تعريف XMP. استبدل "NewTitle" بالعنوان المطلوب.
## الخطوة 3: إضافة عنصر المصفوفة "dc:creator".
```java
// قم بإضافة عنصر صفيف "dc:creator" آخر
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
وبالمثل، نقوم بإضافة عنصر مصفوفة جديد إلى خاصية "dc:creator" في بيانات تعريف XMP. استبدل "NewCreator" بمعلومات المنشئ المطلوبة.
## الخطوة 4: تهيئة دفق ملف EPS للإخراج
```java
// تهيئة دفق ملف EPS الناتج
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
قم بإعداد دفق ملف EPS الناتج حيث سيتم حفظ المستند المعدل مع بيانات تعريف XMP المحدثة.
## الخطوة 5: احفظ المستند باستخدام بيانات تعريف XMP التي تم تغييرها
```java
//احفظ المستند باستخدام بيانات تعريف XMP التي تم تغييرها
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
احفظ المستند باستخدام بيانات تعريف XMP المحدثة في ملف EPS الناتج.
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة عناصر المصفوفة في بيانات تعريف XMP باستخدام Aspose.Page لـ Java. تعمل هذه المكتبة القوية على تبسيط عملية معالجة ملفات EPS وتوفر وظائف واسعة النطاق لمعالجة المستندات.
## أسئلة مكررة

### هل يمكنني استخدام Aspose.Page لـ Java مع تنسيقات المستندات الأخرى؟
نعم، يدعم Aspose.Page تنسيقات المستندات المختلفة، بما في ذلك EPS وPDF وXPS.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page لـ Java؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page لـ Java؟
 الوثائق متاحة[هنا](https://reference.aspose.com/page/java/).
### كيف يمكنني شراء Aspose.Page لجافا؟
 يمكنك شراء المنتج[هنا](https://purchase.aspose.com/buy).
### هل التراخيص المؤقتة متاحة لـ Aspose.Page لـ Java؟
 نعم يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).