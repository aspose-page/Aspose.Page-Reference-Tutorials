---
date: 2025-12-21
description: تعلم كيفية قراءة بيانات XMP الوصفية باستخدام Java مع Aspose.Page. يوضح
  لك هذا الدليل خطوة بخطوة كيفية قراءة تنسيق المستند XMP واستخراج الخصائص الرئيسية.
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: كيفية قراءة بيانات XMP الوصفية باستخدام Java – دليل Aspose.Page
url: /ar/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# الحصول على بيانات التعريف من XMP باستخدام Java

## كيفية قراءة XMP باستخدام Java

مرحبًا بك في دليلنا خطوة‑بخطوة الذي يوضح **كيفية قراءة XMP** باستخدام Java ومكتبة Aspose.Page. XMP (Extensible Metadata Platform) هو معيار واسع الاعتماد لتضمين بيانات تعريف غنية داخل المستندات. بحلول نهاية هذا الدليل ستتمكن من قراءة XMP لتنسيق المستند، استخراج معلومات المنشئ، الطوابع الزمنية، الصور المصغرة، والمزيد — مما يمكنك من بناء حلول تحليل مستندات أذكى.

## إجابات سريعة
- **ماذا يعني “how to read xmp”؟** يشير إلى استخراج بيانات XMP من الملفات برمجيًا.  
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (متاحة من صفحة تحميل Aspose).  
- **هل أحتاج إلى ترخيص؟** يلزم الحصول على ترخيص مؤقت أو كامل للاستخدام في الإنتاج؛ تتوفر نسخة تجريبية مجانية.  
- **ما نسخة Java المدعومة؟** Java 8 أو أعلى.  
- **هل يمكنني قراءة XMP من صيغ أخرى؟** نعم، يمكن لـ Aspose.Page التعامل مع EPS و PDF وعدة أنواع صور تضم XMP.

## المتطلبات المسبقة
قبل الغوص في الشيفرة، تأكد من وجود ما يلي:

- **Java Development Kit (JDK)** – Java 8+ مثبت ومُعد على جهازك.  
- **Aspose.Page for Java** – حمّل المكتبة من الموقع الرسمي [here](https://releases.aspose.com/page/java/).  
- ملف EPS يحتوي على بيانات تعريف XMP (مثل `xmp1.eps`).  

## استيراد الحزم
في مشروع Java الخاص بك، استورد الحزم اللازمة:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## الخطوة 1: تهيئة تدفق ملف EPS الإدخالي
ابدأ بتحديد مسار دليل المستندات وتهيئة تدفق ملف EPS الإدخالي.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## الخطوة 2: الحصول على بيانات XMP
استرجع بيانات XMP من ملف EPS. إذا كان الملف يفتقر إلى بيانات XMP، سيتم إنشاء واحدة جديدة بالقيم المستخلصة من تعليقات بيانات PS.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## الخطوة 3: استخراج معلومات CreatorTool
تحقق واطبع قيمة “CreatorTool” من بيانات XMP.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## الخطوة 4: استخراج معلومات CreateDate
تحقق واطبع قيمة “CreateDate” من بيانات XMP.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## الخطوة 5: استرجاع عرض الصورة المصغرة
إذا كانت هناك صور مصغرة، استخرج واطبع عرض أول صورة مصغرة.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## الخطوة 6: استخراج معلومات Format
تحقق واطبع قيمة “format” من بيانات XMP.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## الخطوة 7: الحصول على DocumentID
تحقق واطبع قيمة “DocumentID” من بيانات XMP.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## لماذا هذا مهم
تسمح لك قراءة بيانات XMP باكتشاف أصل المستند، تاريخ إنشائه، وسمات أساسية أخرى برمجيًا دون الحاجة لفتحه في عارض. هذا مفيد بشكل خاص للمعالجة الدفعية، أنظمة إدارة المحتوى، وخطوط أنابيب الأصول الرقمية حيث تقود البيانات الوصفية الفهرسة والبحث.

## الأخطاء الشائعة والنصائح
- **غياب XMP:** قد لا تحتوي بعض ملفات EPS على XMP. ستقوم الدالة `getXmpMetadata()` بإنشاء مجموعة قليلة من البيانات بناءً على تعليقات PS الموجودة، لكنك لن تحصل على بيانات تعريف كاملة إلا إذا كانت مضمّنة.  
- **مصفوفات الصور المصغرة:** المفتاح `xmp:Thumbnails` يمكن أن يحمل عدة مدخلات. المثال يستخرج الأولى فقط؛ قم بتكرار المصفوفة إذا كنت تحتاج جميع الصور المصغرة.  
- **الوعي بالمساحات الاسمية:** مفاتيح XMP تستخدم مساحات اسمية (مثل `xmp:`، `dc:`). تأكد من الإشارة إلى اسم المفتاح الدقيق؛ وإلا ستعيد `containsKey` القيمة false.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Page for Java مع لغات برمجة أخرى؟
نعم، يدعم Aspose.Page عدة لغات، بما في ذلك Java و .NET وغيرها. راجع [documentation](https://reference.aspose.com/page/java/) للمزيد من التفاصيل.

### هل تتوفر نسخة تجريبية مجانية لـ Aspose.Page for Java؟
نعم، يمكنك الوصول إلى النسخة التجريبية [here](https://releases.aspose.com/).

### أين يمكنني العثور على الدعم لـ Aspose.Page for Java؟
زر منتدى [Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع.

### كيف أحصل على ترخيص مؤقت لـ Aspose.Page for Java؟
يمكنك الحصول على ترخيص مؤقت [here](https://purchase.aspose.com/temporary-license/).

### هل هناك موارد إضافية لـ Aspose.Page for Java؟
استكشف [documentation](https://reference.aspose.com/page/java/) وحمّل المكتبة [here](https://releases.aspose.com/page/java/).

## أسئلة إضافية
**س: هل يعمل هذا النهج مع ملفات PDF التي تحتوي على XMP؟**  
ج: نعم، يمكن لـ Aspose.Page قراءة XMP من PDF و EPS وعدة صيغ صور.

**س: هل يمكنني تعديل بيانات XMP بعد قراءتها؟**  
ج: بالتأكيد. كائن `XmpMetadata` قابل للتعديل؛ يمكنك إضافة أو تحديث أو إزالة المفاتيح ثم حفظ المستند.

**س: هل هناك طريقة لاستخراج جميع الصور المصغرة، وليس الأبعاد فقط؟**  
ج: يمكنك استرجاع البيانات الثنائية من الخاصية `xmpGImg:data` لكل مدخل صورة مصغرة وكتابتها إلى ملف.

## الخلاصة
لقد أتقنت الآن **كيفية قراءة XMP** باستخدام Java و Aspose.Page. باتباع هذه الخطوات يمكنك استخراج أدوات الإنشاء، الطوابع الزمنية، الصور المصغرة، معلومات التنسيق، ومعرفات المستند — مما يمنحك رؤية كاملة للبيانات الوصفية المضمّنة في ملفات EPS الخاصة بك. لا تتردد في تجربة مساحات اسمية XMP إضافية لاستخراج بيانات أغنى لتطبيقاتك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose