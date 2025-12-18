---
date: 2025-12-18
description: تعلم كيفية إضافة البيانات الوصفية عن طريق إدراج عناصر المصفوفة في بيانات
  XMP الوصفية لملفات EPS باستخدام Aspose.Page للغة Java. اتبع دليلنا خطوة بخطوة.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: كيفية إضافة البيانات الوصفية – إضافة عناصر المصفوفة في XMP (جافا)
url: /ar/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة عناصر المصفوفة في بيانات XMP الوصفية باستخدام Java

## كيفية إضافة البيانات الوصفية
مرحبًا بكم في دليلنا خطوة بخطوة حول **كيفية إضافة البيانات الوصفية** إلى ملفات EPS باستخدام Aspose.Page for Java. في هذا البرنامج التعليمي سنرشدكم إلى إضافة عناصر المصفوفة إلى بيانات XMP الوصفية — وهو طلب شائع عندما تحتاجون إلى إثراء معلومات المستند مثل العناوين أو المنشئين. في النهاية، ستفهمون لماذا XMP ذو قيمة، وكيفية التلاعب به برمجيًا، وكيفية حفظ ملف EPS المحدث.

## إجابات سريعة
- **ما المكتبة المستخدمة؟** Aspose.Page for Java  
- **ما تنسيق الملف المستهدف؟** EPS (Encapsulated PostScript)  
- **هل يمكنني إضافة عناوين متعددة؟** نعم، استخدم `xmp.addArrayItem("dc:title", ...)` بشكل متكرر  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم وجود ترخيص صالح لـ Aspose.Page  
- **هل الكود متوافق مع Java 8+؟** بالتأكيد، يعمل مع جميع إصدارات Java الحديثة  

## المتطلبات المسبقة
قبل أن نغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات المسبقة التالية:
- مكتبة Aspose.Page for Java مثبتة.
- فهم أساسي لبرمجة Java.
- ملف EPS صالح يحتوي على بيانات XMP الوصفية الحالية أو تعليقات بيانات PS الوصفية.

## استيراد الحزم
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

## الخطوة 1: الحصول على بيانات XMP الوصفية
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
في هذه الخطوة، نسترجع بيانات XMP الوصفية الموجودة من ملف EPS. إذا لم يحتوي ملف EPS على بيانات XMP الوصفية مسبقًا، فإن Aspose.Page ينشئ واحدة جديدة ويملأها بالقيم المستخرجة من تعليقات بيانات PS الوصفية.

## الخطوة 2: إضافة عنصر مصفوفة "dc:title"
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
الآن، نضيف عنصر مصفوفة جديد إلى الخاصية **dc:title** في بيانات XMP الوصفية. استبدل `"NewTitle"` بالعنوان المطلوب.

## الخطوة 3: إضافة عنصر مصفوفة "dc:creator"
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
وبالمثل، نضيف عنصر مصفوفة جديد إلى الخاصية **dc:creator** في بيانات XMP الوصفية. استبدل `"NewCreator"` بالمعلومات المطلوبة للمنشئ.

## الخطوة 4: تهيئة تدفق ملف EPS الناتج
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
قم بإعداد تدفق ملف EPS الناتج حيث سيتم حفظ المستند المعدل مع بيانات XMP الوصفية المحدثة.

## الخطوة 5: حفظ المستند مع بيانات XMP الوصفية المعدلة
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
احفظ المستند مع بيانات XMP الوصفية المحدثة إلى ملف EPS الناتج.

## الخلاصة
تهانينا! لقد تعلمت بنجاح **كيفية إضافة البيانات الوصفية** عن طريق إدراج عناصر المصفوفة في بيانات XMP الوصفية باستخدام Aspose.Page for Java. هذه المكتبة القوية تبسط عملية تعديل ملفات EPS وتوفر وظائف واسعة لمعالجة المستندات.

## الأسئلة المتكررة

### هل يمكنني استخدام Aspose.Page for Java مع صيغ مستندات أخرى؟
نعم، يدعم Aspose.Page صيغ مستندات متعددة، بما في ذلك EPS و PDF و XPS.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page for Java؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page for Java؟
الوثائق متاحة [هنا](https://reference.aspose.com/page/java/).

### كيف يمكنني شراء Aspose.Page for Java؟
يمكنك شراء المنتج [هنا](https://purchase.aspose.com/buy).

### هل تتوفر تراخيص مؤقتة لـ Aspose.Page for Java؟
نعم، يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

## أسئلة إضافية متكررة

**س: هل يمكنني إضافة أكثر من عنصر مصفوفة إلى نفس الخاصية؟**  
ج: بالتأكيد. استدعِ `xmp.addArrayItem` عدة مرات لنفس الخاصية لإنشاء قائمة من القيم.

**س: هل يعمل هذا النهج مع مخططات XMP الموجودة غير Dublin Core؟**  
ج: نعم، يمكنك إضافة عناصر مصفوفة إلى أي خاصية XMP طالما تم الإشارة إلى مساحة الاسم بشكل صحيح.

**س: كيف يمكنني التحقق من أن البيانات الوصفية قد أضيفت بشكل صحيح؟**  
ج: افتح ملف EPS الناتج في عارض يدعم XMP (مثل Adobe Bridge) أو استخرج البيانات الوصفية برمجيًا باستخدام طرق `XmpMetadata`.

---

**آخر تحديث:** 2025-12-18  
**تم الاختبار مع:** Aspose.Page for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}