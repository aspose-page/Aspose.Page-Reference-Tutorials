---
date: 2026-03-05
description: تعلم كيفية إضافة عناصر مصفوفة dc:title في بيانات XMP الوصفية لملفات EPS
  باستخدام Aspose.Page للـ Java. اتبع هذا الدليل خطوةً بخطوة للحصول على نتائج سريعة.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: كيفية إضافة عناصر مصفوفة dc:title في بيانات XMP الوصفية باستخدام Java
url: /ar/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة عناصر المصفوفة في بيانات XMP الوصفية باستخدام Java

## المقدمة
في هذا الدرس ستكتشف **كيفية إضافة dc:title** (وعناصر مصفوفة أخرى) إلى بيانات XMP الوصفية داخل ملف EPS باستخدام Aspose.Page for Java. تحديث بيانات XMP الوصفية مفيد عندما تحتاج إلى تضمين معلومات قابلة للبحث—مثل العناوين، المنشئين، أو الكلمات المفتاحية—مباشرةً في ملفات الرسومات الخاصة بك. سنستعرض كل خطوة، نشرح لماذا كل سطر مهم، ونظهر لك كيفية التحقق من التغييرات.

## إجابات سريعة
- **ماذا تمثل “dc:title”؟** إنها خاصية العنوان في Dublin Core المخزنة كمصفوفة XMP.  
- **لماذا تعديل بيانات XMP الوصفية؟** يتيح إدارة أصول أفضل، قابلية بحث أعلى، والامتثال للمعايير.  
- **هل أحتاج إلى كتلة XMP موجودة؟** لا—ستقوم Aspose.Page بإنشاء واحدة من تعليقات PS إذا كانت مفقودة.  
- **ما إصدار المكتبة المطلوب؟** أي إصدار حديث من Aspose.Page for Java (تم الاختبار مع أحدث بناء 2026).  
- **هل يمكنني إضافة خصائص مصفوفة أخرى؟** نعم—استخدم نفس طريقة `addArrayItem` للخصائص مثل `dc:creator`.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود:

- مكتبة Aspose.Page for Java مثبتة (أضف ملف JAR إلى مسار classpath الخاص بالمشروع).  
- خبرة أساسية في تطوير Java (يوصى بـ JDK 8+).  
- ملف EPS يحتوي بالفعل على بيانات XMP الوصفية أو على الأقل تعليقات بيانات PS (مثل `%%Title`، `%%Creator`).  

## استيراد الحزم
لبدء العمل، استورد الفئات المطلوبة لقراءة ملفات EPS ومعالجتها وحفظها:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## الخطوة 1: تحميل مستند EPS واسترجاع بيانات XMP الوصفية
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

هنا نفتح ملف EPS ونطلب من Aspose.Page كتلة XMP الخاصة به. إذا كان الملف يفتقر إلى XMP، تقوم المكتبة بإنشاء واحدة تلقائيًا باستخدام تعليقات PS الموجودة، مما يضمن أن لديك دائمًا حاوية بيانات وصفية للعمل معها.

## الخطوة 2: إضافة عنصر مصفوفة **dc:title** جديد  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

هذا السطر يوضح **كيفية إضافة dc:title**. استبدل `"NewTitle"` بالعنوان الفعلي الذي تريد تضمينه. تقوم الطريقة بإلحاق القيمة إلى مصفوفة العنوان الحالية، مع الحفاظ على أي عناوين سابقة.

## الخطوة 3: إضافة عنصر مصفوفة **dc:creator** جديد  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

وبالمثل، يمكنك إثراء خاصية `dc:creator`. يمكن تخزين عدة منشئين؛ كل استدعاء يضيف مدخلاً آخر.

## الخطوة 4: إعداد تدفق الإخراج  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

نقوم بإنشاء تدفق للملف EPS المعدل. استخدام اسم ملف مختلف (`xmp3_changed.eps`) يحافظ على الملف الأصلي دون تعديل.

## الخطوة 5: حفظ المستند مع بيانات XMP الوصفية المحدثة  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

استدعاء `save` يكتب بيانات EPS مع كتلة XMP المحدثة. تضمن كتلة `finally` تحرير مقبض الملف حتى في حال حدوث استثناء.

## لماذا هذا مهم
إدراج قيم `dc:title` و `dc:creator` الدقيقة يحسن:

- **قابلية البحث** في أنظمة إدارة الأصول الرقمية (DAM).  
- **الامتثال** لمعايير النشر التي تتطلب بيانات وصفية.  
- **التعاون**، حيث يمكن للزملاء التعرف بسرعة على محتوى الملف دون فتح EPS.

## المشكلات الشائعة والنصائح
- **المشكلة:** الكتابة فوق عناصر المصفوفة الموجودة عن غير قصد.  
  **النصيحة:** استخدم `xmp.getArrayItems("dc:title")` لفحص القيم الحالية قبل إضافة جديدة.  
- **المشكلة:** نسيان إغلاق التدفقات، مما يؤدي إلى قفل الملفات.  
  **النصيحة:** احرص دائمًا على تغليف عمليات الإدخال/الإخراج باستخدام try‑with‑resources أو كتلة `finally` كما هو موضح.  
- **النصيحة:** يمكنك ربط عدة استدعاءات `addArrayItem` لإضافة عدة عناوين أو منشئين في خطوة واحدة.

## الأسئلة المتكررة

### هل يمكنني استخدام Aspose.Page for Java مع صيغ مستندات أخرى؟
نعم، تدعم Aspose.Page صيغ مستندات متعددة، بما في ذلك EPS و PDF و XPS.

### هل توجد نسخة تجريبية مجانية متاحة لـ Aspose.Page for Java؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page for Java؟
الوثائق متاحة [هنا](https://reference.aspose.com/page/java/).

### كيف يمكنني شراء Aspose.Page for Java؟
يمكنك شراء المنتج [هنا](https://purchase.aspose.com/buy).

### هل تتوفر تراخيص مؤقتة لـ Aspose.Page for Java؟
نعم، يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

---

**آخر تحديث:** 2026-03-05  
**تم الاختبار مع:** Aspose.Page for Java (أحدث إصدار 2026)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}