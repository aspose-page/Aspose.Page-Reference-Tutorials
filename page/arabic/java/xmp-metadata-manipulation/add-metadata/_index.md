---
date: 2025-12-20
description: تعلم كيفية إضافة بيانات XMP الوصفية إلى ملفات EPS باستخدام دليل Aspose
  Page للغة Java. اتبع هذا الدليل خطوة بخطوة لتعزيز إدارة مستنداتك.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: دورة Aspose Page Java – إضافة بيانات XMP الوصفية إلى ملفات EPS
url: /ar/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة بيانات التعريف في XMP باستخدام Java

## المقدمة
في هذا **دليل Aspose Page Java**، ستتعلم كيفية تحسين بيانات التعريف في مستندك عن طريق إضافة معلومات XMP باستخدام Java. يوجهك هذا الدليل خطوة بخطوة عبر قراءة ملف EPS موجود، استخراج بيانات التعريف XMP الخاصة به، وحفظ التغييرات مرة أخرى على القرص باستخدام مكتبة Aspose.Page for Java. في نهاية الدليل ستحصل على نمط ثابت وقابل لإعادة الاستخدام للعمل مع XMP في أي سير عمل EPS.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **هل يمكنني إضافة XMP إلى أي ملف EPS؟** نعم – تُنشئ الـ API كتلة XMP جديدة إذا لم تكن موجودة مسبقًا.  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تكفي للتقييم؛ يلزم ترخيص تجاري للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 وما بعدها.  
- **كم يستغرق تنفيذ العملية؟** عادةً أقل من 10 دقائق لتحديث بيانات تعريف أساسي.

## نظرة عامة على دليل Aspose Page Java
يعرض هذا الدليل الخطوات الأساسية التي تحتاجها للتعامل مع بيانات تعريف XMP في ملفات EPS. سيساعدك فهم هذه الخطوات على دمج معالجة البيانات التعريفية في خطوط معالجة المستندات الأكبر، تحسين قابلية البحث، والامتثال للمعايير الصناعية لإدارة الأصول الرقمية.

## المتطلبات المسبقة
قبل أن نبدأ الدليل، تأكد من توفر المتطلبات التالية:
- معرفة أساسية ببرمجة Java.  
- مكتبة Aspose.Page for Java مثبتة. يمكنك تنزيلها [هنا](https://releases.aspose.com/page/java/).  
- ملف EPS ترغب في تعديله.

## استيراد الحزم
أولاً، استورد الحزم الضرورية إلى برنامج Java الخاص بك:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## الخطوة 1: الحصول على بيانات تعريف XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

استبدل `"Your Document Directory"` بالمسار الفعلي حيث تُخزن مستنداتك.

## الخطوة 2: استرجاع قيمة CreatorTool
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## الخطوة 3: استرجاع قيمة CreateDate
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## الخطوة 4: استرجاع قيمة Title
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## الخطوة 5: استرجاع قيمة Format
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## الخطوة 6: استرجاع قيمة Creator
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## الخطوة 7: استرجاع قيمة MetadataDate
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## الخطوة 8: حفظ المستند مع بيانات تعريف XMP الجديدة
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

أخيرًا، لا تنس إغلاق تدفق EPS الإدخالي:

```java
// Close input EPS stream
psStream.close();
```

الآن، لقد أضفت بنجاح بيانات تعريف إلى ملف EPS باستخدام Aspose.Page for Java!

## الخلاصة
في هذا **دليل Aspose Page Java**، استكشفنا كيفية إضافة بيانات تعريف XMP إلى ملف EPS باستخدام مكتبة Aspose.Page for Java. تتيح لك هذه الـ API القوية تعديل بيانات تعريف المستند برمجيًا، مما يساعدك على تنظيم الأصول وجعلها قابلة للبحث بسهولة.

## الأسئلة المتكررة

**س: هل Aspose.Page for Java مجاني للاستخدام؟**  
ج: Aspose.Page for Java هو منتج تجاري. يمكنك استكشاف ميزاته من خلال نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

**س: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page for Java؟**  
ج: الوثائق متاحة [هنا](https://reference.aspose.com/page/java/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟**  
ج: يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: ما صيغ الملفات التي يدعمها Aspose.Page for Java؟**  
ج: يدعم Aspose.Page for Java صيغًا متعددة، بما في ذلك EPS و PDF و XPS.

**س: هل يمكنني شراء Aspose.Page for Java؟**  
ج: نعم، يمكنك شراء Aspose.Page for Java [هنا](https://purchase.aspose.com/buy).

**س: كيف أتعامل مع ملفات EPS الكبيرة عند إضافة بيانات التعريف؟**  
ج: عالج الملف بطريقة تدفقية (كما هو موضح) لتقليل استهلاك الذاكرة، وأغلق التدفقات فورًا.

**س: هل يمكنني تعديل حقول XMP الموجودة بدلاً من مجرد قراءتها؟**  
ج: بالتأكيد – يمكنك استخدام `xmp.put(key, value)` لتحديث أو إضافة إدخالات جديدة قبل الحفظ.

---

**آخر تحديث:** 2025-12-20  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (الأحدث)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}