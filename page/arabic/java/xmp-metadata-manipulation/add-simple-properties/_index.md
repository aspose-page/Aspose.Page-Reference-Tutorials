---
date: 2025-12-20
description: تعلم كيفية إنشاء بيانات تعريف XMP في ملفات EPS باستخدام Aspose.Page للغة
  Java. دليل خطوة بخطوة لإضافة خصائص XMP بسيطة برمجياً.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: كيفية إنشاء ملفات EPS لبيانات XMP الوصفية باستخدام Java
url: /ar/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة خصائص بسيطة في XMP باستخدام Java

## المقدمة
في سير عمل المستندات الحديثة، القدرة على **إنشاء ملفات XMP metadata EPS** برمجياً تمنحك التحكم الكامل في كيفية وصف الرسومات الخاصة بك، والبحث عنها، وأرشفتها. باستخدام Aspose.Page for Java يمكنك قراءة وتعديل وكتابة حزم XMP داخل مستندات EPS دون مغادرة بيئة Java. في هذا البرنامج التعليمي سنرشدك إلى الخطوات الدقيقة لإضافة خصائص XMP بسيطة إلى ملف EPS، بحيث يمكنك إثراء رسوماتك ببيانات تعريف مخصصة بسرعة وموثوقية.

## إجابات سريعة
- **ماذا يعني “create xmp metadata eps”؟** إضافة حزمة XMP (بيانات تعريف مبنية على XML) إلى ملف EPS.  
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (قابلة للتنزيل من موقع Aspose).  
- **هل أحتاج إلى ترخيص للاختبار؟** النسخة التجريبية المجانية تعمل للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **كم عدد أسطر الكود؟** أقل من 30 سطرًا من Java بالإضافة إلى بعض عبارات الاستيراد.  
- **هل يمكنني إضافة أنواع بيانات أخرى؟** نعم – التواريخ، الأعداد الصحيحة، الأعداد العشرية، السلاسل النصية، وحتى المصفوفات مدعومة.

## ما هو create xmp metadata eps؟
XMP (Extensible Metadata Platform) هو معيار لتضمين بيانات تعريف غنية داخل الملفات. عندما **create XMP metadata EPS**، تقوم بتضمين حزمة XML داخل مستند EPS (Encapsulated PostScript)، مما يسمح للتطبيقات اللاحقة بقراءة المؤلف، تاريخ الإنشاء، العلامات المخصصة، والمزيد.

## لماذا نضيف بيانات XMP إلى ملفات EPS؟
- **قابلية البحث:** تمكين الفهرسة التلقائية بواسطة أنظمة DAM.  
- **الامتثال:** تخزين المعلومات القانونية أو الترخيصية مباشرةً في الملف.  
- **الأتمتة:** السماح للأنابيب اللاحقة باتخاذ قرارات بناءً على البيانات المضمنة.  
- **القابلية للنقل:** تنتقل البيانات التعريفية مع ملف EPS، مما يضمن التناسق عبر المنصات.

## المتطلبات المسبقة
- معرفة أساسية ببرمجة Java.  
- مكتبة Aspose.Page for Java مثبتة. يمكنك تنزيلها **[هنا](https://releases.aspose.com/page/java/)**.  
- ملف EPS تجريبي يحتوي على بيانات تعريف. إذا لم يكن لديك، يمكنك استخدام ملف **`xmp3.eps`** المرفق.

## استيراد الحزم
أولاً، استورد الفئات التي ستحتاجها. تبقى عبارات الاستيراد كما هي تمامًا كما في المثال الأصلي:

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

## الخطوة 1: تحميل مستند EPS والحصول على بيانات XMP التعريفية
نفتح ملف EPS، ننشئ كائن `PsDocument`، ونسترجع (أو ننشئ) حزمة XMP.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## الخطوة 2: إضافة خاصية تاريخ
إضافة تاريخ بسيطة مثل إنشاء كائن `Date` ووضعه في خريطة XMP.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## الخطوة 3: إضافة خاصية عدد صحيح
يمكنك تخزين المعرفات الرقمية أو أرقام الإصدارات باستخدام قيمة عدد صحيح.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## الخطوة 4: إضافة خاصية عدد عشري
الأعداد العشرية مفيدة للقياسات أو التقييمات.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## الخطوة 5: إضافة خاصية سلسلة نصية
العلامات النصية المخصصة (مثل رموز المشاريع) تُخزن كسلاسل نصية.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## الخطوة 6: حفظ ملف EPS المحدث
بعد إضافة جميع الخصائص، اكتب المستند مرة أخرى إلى القرص.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## الخطوة 7: تنظيف الموارد
دائمًا أغلق تدفق الإدخال لتجنب تسرب مقبض الملف.

```java
// Close input EPS stream
psStream.close();
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **Null XMP metadata** | ملف EPS لا يحتوي على حزمة XMP ولم يتمكن المكتبة من استنتاج تعليقات PS. | تأكد من أن ملف EPS المصدر يحتوي على تعليق PS واحد على الأقل (مثل `%%Creator`). ستولد المكتبة حزمة XMP قليلة الحد أدنى تلقائيًا. |
| **Time zone mismatch** | تظهر التواريخ متأخرة عند فتحها في تطبيق آخر. | قم بتعيين `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` قبل إنشاء كائن `Date`، كما هو موضح في الخطوة 2. |
| **License exception** | وقت التشغيل يرمي استثناء `LicenseException`. | طبق ترخيص Aspose.Page صالح قبل استخدام الـ API، أو شغّل في وضع التجربة للتقييم. |

## الخلاصة
باتباع هذه الخطوات أصبحت الآن تعرف كيفية **إنشاء ملفات XMP metadata EPS** باستخدام Aspose.Page for Java. إضافة خصائص بسيطة مثل التواريخ، الأعداد الصحيحة، الأعداد العشرية، والسلاسل النصية أمر سهل، وتُحمل ملفات EPS الناتجة بيانات تعريف غنية وقابلة للبحث تفيد أي سير عمل لاحق.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Page for Java مع لغات برمجة أخرى؟
Aspose.Page يدعم أساسًا Java، ولكن هناك إصدارات متاحة للغات أخرى مثل .NET.

### هل تتوفر نسخة تجريبية مجانية لـ Aspose.Page for Java؟
نعم، يمكنك استكشاف ميزات Aspose.Page بالحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على الوثائق التفصيلية لـ Aspose.Page for Java؟
الوثائق متاحة [هنا](https://reference.aspose.com/page/java/).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟
يمكن الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### أين يمكنني شراء Aspose.Page for Java؟
يمكنك شراء المنتج [هنا](https://purchase.aspose.com/buy).

**آخر تحديث:** 2025-12-20  
**تم الاختبار مع:** Aspose.Page for Java 24.11 (الأحدث وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}