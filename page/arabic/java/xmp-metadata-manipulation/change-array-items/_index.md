---
title: تغيير عناصر المصفوفة في XMP باستخدام Java
linktitle: تغيير عناصر المصفوفة في XMP باستخدام Java
second_title: Aspose.Page جافا API
description: تعرف على كيفية تغيير عناصر المصفوفة في XMP باستخدام Aspose.Page لـ Java. قم بتعديل البيانات الوصفية دون عناء باستخدام دليلنا خطوة بخطوة. قم بتحسين مستندات EPS الخاصة بك الآن!
weight: 15
url: /ar/java/xmp-metadata-manipulation/change-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تغيير عناصر المصفوفة في XMP باستخدام Java

## مقدمة
مرحبًا بك في دليلنا الشامل حول تغيير عناصر المصفوفة في XMP باستخدام Aspose.Page لـ Java! Aspose.Page هي مكتبة Java قوية تتيح لك العمل مع بيانات تعريف XMP في ملفات EPS بسلاسة. في هذا البرنامج التعليمي، سنرشدك خلال عملية تعديل عناصر المصفوفة ضمن بيانات تعريف XMP، مما يساعدك على تحسين مستندات EPS وتخصيصها.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على نظامك.
-  مكتبة Aspose.Page لجافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/page/java/).
## حزم الاستيراد
للبدء، دعنا نستورد الحزم الضرورية في مشروع Java الخاص بك. تأكد من تضمين مكتبة Aspose.Page في مشروعك.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;

```
## الخطوة 1: احصل على بيانات تعريف XMP
أولاً، قم باسترداد بيانات تعريف XMP من ملف EPS الخاص بك. إذا كان ملف EPS لا يحتوي بالفعل على بيانات تعريف XMP، فسيتم إنشاء ملف جديد بقيم من تعليقات بيانات تعريف PS مثل %%Creator، و%%CreateDate، و%%Title، وما إلى ذلك.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// تهيئة دفق ملف EPS للإدخال
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// احصل على بيانات تعريف XMP. إذا كان ملف EPS لا يحتوي على بيانات تعريف XMP، فسيتم ملء ملف جديد بقيم من تعليقات بيانات تعريف PS.
XmpMetadata xmp = document.getXmpMetadata();
```
## الخطوة 2: قم بتعيين عنصر المصفوفة "dc:title".
الآن، لنقم بتعيين عنصر المصفوفة "dc:title" عند الفهرس 0 بقيمة جديدة.
```java
// قم بتعيين عنصر الصفيف "dc: title" حسب الفهرس 0
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```
## الخطوة 3: قم بتعيين عنصر المصفوفة "dc:creator".
وبالمثل، قم بتعيين عنصر الصفيف "dc:creator" عند الفهرس 0 بقيمة منشئ جديدة.
```java
// قم بتعيين عنصر الصفيف "dc:creator" حسب الفهرس 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```
## الخطوة 4: تهيئة دفق ملف EPS للإخراج
قم بإعداد دفق ملف EPS الناتج حيث سيتم حفظ المستند المعدل.
```java
// تهيئة دفق ملف EPS الناتج
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
## الخطوة 5: احفظ المستند باستخدام بيانات تعريف XMP التي تم تغييرها
احفظ المستند باستخدام بيانات تعريف XMP المحدثة.
```java
//احفظ المستند باستخدام بيانات تعريف XMP التي تم تغييرها
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تغيير عناصر المصفوفة في XMP باستخدام Aspose.Page لـ Java. قدم هذا البرنامج التعليمي إرشادات خطوة بخطوة، مما يضمن أنه يمكنك تحسين مستندات EPS الخاصة بك بسهولة باستخدام البيانات التعريفية المخصصة.

## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Page لـ Java مع لغات البرمجة الأخرى؟
تم تصميم Aspose.Page بشكل أساسي لـ Java، لكن Aspose يوفر مكتبات مماثلة للغات الأخرى.
### أين يمكنني العثور على وثائق مفصلة عن Aspose.Page لـ Java؟
 الوثائق متاحة[هنا](https://reference.aspose.com/page/java/).
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page لـ Java؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ Java؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني شراء الإصدار الكامل من Aspose.Page لـ Java؟
 يمكنك شراء النسخة الكاملة[هنا](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
