---
date: 2026-03-08
description: تعلم كيفية إضافة بيانات XMP الوصفية إلى ملفات EPS باستخدام دليل Aspose
  Page للغة Java. اتبع هذا الدليل خطوة بخطوة لتعزيز إدارة مستنداتك.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: دروس Aspose Page Java – إضافة بيانات XMP الوصفية إلى ملفات EPS
url: /ar/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

 keep markdown formatting.

Let's produce the translated content.

We'll keep the shortcodes exactly.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة بيانات التعريف في XMP باستخدام Java

## المقدمة
في هذا **aspose page java tutorial**، ستتعلم كيفية تحسين بيانات التعريف في مستندك بإضافة معلومات XMP باستخدام Java. يوضح هذا الدليل خطوة بخطوة كيفية قراءة ملف EPS موجود، استخراج بيانات التعريف XMP الخاصة به، وحفظ التغييرات مرة أخرى على القرص باستخدام مكتبة Aspose.Page for Java. في نهاية الدرس ستحصل على نمط ثابت وقابل لإعادة الاستخدام للعمل مع XMP في أي سير عمل EPS.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **هل يمكنني إضافة XMP إلى أي ملف EPS؟** نعم – تُنشئ الـ API كتلة XMP جديدة إذا لم تكن موجودة بالفعل.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص التجاري مطلوب للإنتاج.  
- **أي إصدارات Java مدعومة؟** Java 8 وما فوق.  
- **كم يستغرق تنفيذ العملية؟** عادةً أقل من 10 دقائق لتحديث بيانات تعريف أساسي.

## ما هو Aspose Page Java؟
Aspose.Page for Java (المعروفة غالبًا باسم **aspose page java**) هي API عالية الأداء تتيح للمطورين إنشاء وتعديل وتحويل ملفات PostScript و EPS دون الحاجة إلى برامج Adobe. كما توفر وصولًا كاملاً إلى بيانات التعريف XMP، مما يمكنك من تضمين معلومات قابلة للبحث مباشرة داخل ملفات الرسومات الخاصة بك.

## لماذا نضيف بيانات تعريف XMP إلى ملفات EPS؟
إدراج بيانات تعريف XMP يحسن إدارة الأصول، وقابلية البحث، والامتثال للمعايير الصناعية مثل IPTC و Dublin Core. عندما تضيف حقولًا مثل المُنشئ، العنوان، أو تاريخ الإنشاء، يمكن للأنظمة اللاحقة (DAMs، محركات البحث، أو سير عمل الطباعة) فهرسة وتنظيم أصول EPS تلقائيًا.

## نظرة عامة على درس Aspose Page Java
يعرض هذا الدرس الخطوات الأساسية التي تحتاجها للتعامل مع بيانات تعريف XMP في ملفات EPS. سيساعدك فهم هذه الخطوات على دمج معالجة البيانات التعريفية في خطوط معالجة المستندات الأكبر، وتحسين قابلية البحث، والامتثال للمعايير الصناعية لإدارة الأصول الرقمية.

## المتطلبات المسبقة
قبل أن نبدأ الدرس، تأكد من توفر المتطلبات التالية:
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

## المشكلات الشائعة والحلول
- **عدم وجود كتلة XMP** – تقوم الـ API بإنشائها تلقائيًا، لكن تأكد من أن ملف EPS غير تالف.  
- **الأحرف غير المدعومة** – يجب أن تكون قيم XMP بتنسيق UTF‑8؛ تجنّب الرموز غير القياسية في حقول البيانات التعريفية.  
- **ملفات EPS الكبيرة** – عالج الملف باستخدام التدفقات (كما هو موضح) للحفاظ على استهلاك الذاكرة منخفضًا، وتأكد دائمًا من إغلاق التدفقات في كتلة `finally`.

## الخلاصة
في هذا **aspose page java tutorial**، استعرضنا كيفية إضافة بيانات تعريف XMP إلى ملف EPS باستخدام مكتبة Aspose.Page for Java. تتيح لك هذه الـ API القوية تعديل بيانات تعريف المستند برمجيًا، مما يساعدك على تنظيم الأصول وجعلها قابلة للبحث بسهولة.

## الأسئلة المتكررة

**س: هل Aspose.Page for Java مجانية للاستخدام؟**  
ج: Aspose.Page for Java منتج تجاري. يمكنك استكشاف ميزاته من خلال نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

**س: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Page for Java؟**  
ج: الوثائق متاحة [هنا](https://reference.aspose.com/page/java/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟**  
ج: يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: ما صيغ الملفات التي يدعمها Aspose.Page for Java؟**  
ج: يدعم Aspose.Page for Java صيغًا متعددة، بما في ذلك EPS و PDF و XPS.

**س: هل يمكنني شراء Aspose.Page for Java؟**  
ج: نعم، يمكنك شراء Aspose.Page for Java [هنا](https://purchase.aspose.com/buy).

**س: كيف أتعامل مع ملفات EPS الكبيرة عند إضافة بيانات تعريف؟**  
ج: عالج الملف بطريقة التدفق (كما هو موضح) للحفاظ على استهلاك الذاكرة منخفضًا، وأغلق التدفقات فورًا.

**س: هل يمكنني تعديل حقول XMP الموجودة بدلاً من قراءتها فقط؟**  
ج: بالتأكيد – يمكنك استخدام `xmp.put(key, value)` لتحديث أو إضافة إدخالات جديدة قبل الحفظ.

---

**آخر تحديث:** 2026-03-08  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}