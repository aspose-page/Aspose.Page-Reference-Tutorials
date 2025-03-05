---
title: إضافة بيانات التعريف في XMP باستخدام Java
linktitle: إضافة بيانات التعريف في XMP باستخدام Java
second_title: Aspose.Page جافا API
description: استكشف التكامل السلس لـ Aspose.Page لـ Java وتعرف على كيفية إضافة بيانات تعريف XMP إلى ملفات EPS الخاصة بك دون عناء. ارفع مستوى لعبة إدارة المستندات الخاصة بك اليوم!
type: docs
weight: 11
url: /ar/java/xmp-metadata-manipulation/add-metadata/
---
## مقدمة
هل تتطلع إلى تحسين البيانات التعريفية لمستندك عن طريق إضافة معلومات XMP باستخدام Java؟ لا مزيد من البحث! سيرشدك هذا الدليل خطوة بخطوة خلال عملية إضافة بيانات التعريف إلى ملف EPS باستخدام مكتبة Aspose.Page for Java. Aspose.Page هي أداة قوية تعمل على تبسيط مهام معالجة المستندات في تطبيقات Java.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
-  تم تثبيت Aspose.Page لمكتبة Java. يمكنك تنزيله[هنا](https://releases.aspose.com/page/java/).
- ملف EPS الذي تريد تعديله.
## حزم الاستيراد
أولاً، قم باستيراد الحزم اللازمة لبرنامج Java الخاص بك:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## الخطوة 1: احصل على بيانات تعريف XMP
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// تهيئة دفق ملف EPS للإدخال
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// احصل على بيانات تعريف XMP. إذا كان ملف EPS لا يحتوي على بيانات تعريف XMP، فسيتم إنشاء ملف جديد باستخدام قيم من تعليقات بيانات تعريف PS (%%Creator، %%CreateDate، %%Title، وما إلى ذلك)
XmpMetadata xmp = document.getXmpMetadata();
```
تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي حيث يتم تخزين مستنداتك.

## الخطوة 2: استرداد قيمة أداة CreatorTool
```java
// احصل على قيمة "CreatorTool".
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## الخطوة 3: استرداد قيمة تاريخ الإنشاء
```java
// احصل على قيمة "تاريخ الإنشاء".
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## الخطوة 4: استرداد قيمة العنوان
```java
// احصل على قيمة "العنوان".
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## الخطوة 5: استرداد قيمة التنسيق
```java
//احصل على قيمة "التنسيق".
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## الخطوة 6: استرداد قيمة المنشئ
```java
// احصل على قيمة "الخالق".
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## الخطوة 7: استرداد قيمة MetadataDate
```java
// احصل على قيمة "MetadataDate".
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## الخطوة 8: احفظ المستند باستخدام بيانات تعريف XMP الجديدة
```java
// تهيئة دفق ملف EPS الناتج
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// احفظ المستند باستخدام بيانات تعريف XMP الجديدة
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
وأخيرًا، لا تنس إغلاق دفق EPS للإدخال:
```java
// إغلاق دفق EPS المدخلات
psStream.close();
```
لقد نجحت الآن في إضافة البيانات التعريفية إلى ملف EPS الخاص بك باستخدام Aspose.Page لـ Java!
## خاتمة
في هذا البرنامج التعليمي، اكتشفنا عملية إضافة بيانات تعريف XMP إلى ملف EPS باستخدام مكتبة Aspose.Page for Java. تمكنك هذه الأداة القوية من التعامل مع المستندات بسلاسة، مما يعزز تجربة إدارة المستندات بشكل عام.
## الأسئلة الشائعة
### س: هل Aspose.Page لـ Java مجاني للاستخدام؟
 ج: Aspose.Page for Java هو منتج تجاري. يمكنك استكشاف ميزاته من خلال نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### س: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page لـ Java؟
 ج: الوثائق متاحة[هنا](https://reference.aspose.com/page/java/).
### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page لـ Java؟
 ج: يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### س: ما هي تنسيقات الملفات التي يدعمها Aspose.Page لـ Java؟
ج: يدعم Aspose.Page for Java العديد من التنسيقات، بما في ذلك EPS وPDF وXPS.
### س: هل يمكنني شراء Aspose.Page لـ Java؟
 ج: نعم، يمكنك شراء Aspose.Page لـ Java[هنا](https://purchase.aspose.com/buy).