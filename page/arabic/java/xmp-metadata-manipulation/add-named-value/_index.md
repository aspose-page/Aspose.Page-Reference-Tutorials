---
date: 2026-05-05
description: تعلم كيفية إضافة قيم XMP المسماة إلى ملفات EPS باستخدام Aspose.Page للغة
  Java – دليل خطوة بخطوة مع أمثلة على الشيفرة.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
linktitle: إضافة قيمة مسماة في XMP باستخدام Java
second_title: Aspose.Page Java API
title: كيفية إضافة قيمة XMP مسماة في ملفات EPS باستخدام Java
url: /ar/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة قيمة مسماة في بيانات XMP الوصفية باستخدام Java

## مقدمة
في تطوير Java الحديث، يعتبر تعلم **كيفية إضافة XMP** إلى ملفات EPS أمرًا أساسيًا للحفاظ على أصل المستند وتحسين إمكانية البحث. باستخدام **asp** (Aspose.Page for Java)، يمكنك بسهولة حقن قيم مسماة مخصصة في حزمة XMP. يوضح هذا البرنامج التعليمي الخطوات الدقيقة—مع مقتطفات الشيفرة—حتى تتمكن من بدء إضافة بيانات XMP الوصفية إلى مستندات EPS الخاصة بك اليوم.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (asp)  
- **ما نوع الملف المستهدف؟** ملفات EPS التي تحتوي على بيانات XMP الوصفية  
- **حالة الاستخدام الأساسية؟** إضافة قيم مسماة مخصصة (مثل حدود حجم الصفحة) إلى XMP  
- **المتطلبات المسبقة؟** JDK 8+ ومكتبة Aspose.Page for Java  
- **الوقت المتوقع للتنفيذ؟** 5–10 دقائق بمجرد إعداد المكتبة  

## ما هو asp؟
*asp* هو الشكل المختصر لـ **Aspose**، مجموعة من واجهات برمجة التطبيقات .NET و Java التي تبسط معالجة المستندات. يتيح مكوّن Aspose.Page for Java إنشاء وتحرير وتحويل ملفات PostScript و EPS مع توفير وصول برمجي كامل إلى بياناتها الوصفية، بما في ذلك XMP.

## لماذا نضيف قيمًا مسماة إلى بيانات XMP الوصفية؟
- **ملاءمة محركات البحث:** العلامات المخصصة تحسن إمكانية الاكتشاف.  
- **أتمتة سير العمل:** يمكن للأدوات اللاحقة قراءة القيم المخصصة لاتخاذ قرارات.  
- **الامتثال:** تضمين معلومات تنظيمية مباشرةً في حزمة المستند.  

## لماذا هذا مهم
إضافة قيم مسماة إلى XMP تتيح لك تخزين أزواج مفتاح‑قيمة عشوائية يمكن قراءتها دون الحاجة إلى تحليل ملف EPS بالكامل. هذه القدرة ذات قيمة خاصة في خطوط النشر الآلية، وأنظمة إدارة الأصول الرقمية، وسير العمل القائم على الامتثال حيث تقود البيانات الوصفية الإجراءات اللاحقة.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر ما يلي:

- **مجموعة تطوير Java (JDK):** نسخة حديثة من JDK (8 أو أعلى) مثبتة على جهازك.  
- **مكتبة Aspose.Page for Java:** قم بتنزيلها من [رابط التحميل الرسمي](https://releases.aspose.com/page/java/). أضف ملف JAR إلى مسار الفئة (classpath) في مشروعك.  
- **ملف EPS** يحتوي إما على بيانات XMP الوصفية مسبقًا أو سيتم إنشاؤه تلقائيًا.

## استيراد الحزم
ابدأ باستيراد حزم Java الضرورية. تمنحك هذه الاستيرادات الوصول إلى تدفقات الملفات، نموذج مستند EPS، وفئات معالجة XMP.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## كيفية إضافة قيمة مسماة في XMP إلى ملفات EPS باستخدام Java
فيما يلي دليل مختصر مرقم يوضح بالضبط **كيفية إضافة XMP** قيمًا مسماة إلى مستند EPS.

### الخطوة 1: تهيئة تدفق ملف EPS الإدخالي
حمّل ملف EPS المصدر في `FileInputStream`. يزود هذا التدفق المستند إلى API الخاصة بـ Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **نصيحة احترافية:** اجعل المتغيّر `dataDir` قابلًا للتكوين بحيث يعمل نفس الشيفرة عبر بيئات مختلفة.

### الخطوة 2: الحصول على بيانات XMP الوصفية
استرجع حزمة XMP الحالية. إذا كان ملف EPS لا يحتوي على واحدة، يقوم Aspose بإنشاء كائن XMP جديد مُعبّأ من تعليقات PS.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### الخطوة 3: إضافة قيمة مسماة
أدرج قيمة مسماة مخصصة في بنية XMP. في هذا المثال نضيف مفتاحًا جديدًا تحت مساحة الاسم `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **لماذا هذا مهم:** القيم المسماة تتيح لك تخزين أزواج مفتاح‑قيمة عشوائية يمكن للتطبيقات اللاحقة قراءتها دون تحليل المستند بالكامل.

### الخطوة 4: تهيئة تدفق ملف EPS الإخراجي
جهّز `FileOutputStream` حيث سيتم حفظ ملف EPS المعدل.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### الخطوة 5: حفظ المستند
احفظ التغييرات. تستدعي الدالة `save` كتابة حزمة XMP المحدثة مرة أخرى إلى ملف EPS.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### الخطوة 6: إغلاق تدفق EPS الإدخالي
حرّر مقبض الملف الأصلي لتجنب تسرب الموارد.

```java
psStream.close();
```

باتباع هذه الخطوات الست، تكون قد نجحت في **إضافة قيمة مسماة في بيانات XMP الوصفية** باستخدام **asp** (Aspose.Page for Java).

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|-----|
| `NullPointerException` على `xmp` | ملف EPS لا يحتوي على XMP وفشل Aspose في إنشاء واحدة | تأكد من أن EPS يحتوي على تعليق PS واحد على الأقل أو أنشئ كائن `XmpMetadata` جديد يدويًا. |
| ملف الإخراج فارغ | لم يتم تفريغ/إغلاق تدفق الإخراج | تحقق من استدعاء `outPsStream.close()` داخل كتلة `finally` (كما هو موضح). |
| خطأ مفتاح مكرر | تم إضافة نفس القيمة المسماة مرتين | تحقق مما إذا كان المفتاح موجودًا بالفعل باستخدام `xmp.containsNamedValue(...)` قبل الإضافة. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page for Java مع مكتبات Java أخرى؟**  
ج: نعم، تم تصميم Aspose.Page for Java للعمل بسلاسة مع مكتبات Java أخرى، مما يوفر مرونة في بيئة التطوير الخاصة بك.

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Page for Java؟**  
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Page for Java [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟**  
ج: زر [هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت لـ Aspose.Page for Java.

**س: أين يمكنني العثور على المزيد من البرامج التعليمية والأمثلة لـ Aspose.Page for Java؟**  
ج: استكشف [التوثيق](https://reference.aspose.com/page/java/) للحصول على برامج تعليمية شاملة وأمثلة.

**س: هل Aspose.Page for Java مناسب للمشاريع الكبيرة النطاق؟**  
ج: بالتأكيد، تم تصميم Aspose.Page for Java للتعامل مع المشاريع الكبيرة بكفاءة، مع توفير قدرات قوية لمعالجة المستندات.

## الخاتمة
في هذا الدليل أظهرنا كيف يجعل **asp** (Aspose.Page for Java) من السهل **إضافة قيم مسماة إلى بيانات XMP الوصفية** داخل ملفات EPS. باستخدام الخطوات أعلاه، يمكنك إثراء مستنداتك ببيانات وصفية مخصصة، تحسين إمكانية البحث، وتمكين معالجة ذكية للخطوات اللاحقة.

---

**آخر تحديث:** 2026-05-05  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}