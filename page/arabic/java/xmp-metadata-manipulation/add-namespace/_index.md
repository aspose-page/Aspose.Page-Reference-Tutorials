---
date: 2025-12-20
description: تعلم كيفية إضافة مساحة اسم XMP في ملفات EPS باستخدام Aspose.Page للغة
  Java في هذا الدرس الشامل حول aspose.page xmp.
linktitle: Add Namespace in XMP using Java
second_title: Aspose.Page Java API
title: دليل aspose.page XMP – إضافة مساحة اسم في XMP باستخدام Java
url: /ar/java/xmp-metadata-manipulation/add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp tutorial – إضافة مساحة اسم في XMP باستخدام Java

## المقدمة

إذا كنت بحاجة إلى تعديل أو إثراء بيانات التعريف لملفات EPS، فإن **aspose.page xmp tutorial** يوضح لك بالضبط **كيفية إضافة مساحة اسم XMP** باستخدام Java. في هذا الدليل سنستعرض كل خطوة — بدءًا من تحميل مستند EPS، وتسجيل مساحة اسم مخصصة، وإدراج خاصية جديدة، وأخيرًا حفظ الملف المحدث. في النهاية، ستحصل على نمط واضح وقابل لإعادة الاستخدام للعمل مع بيانات تعريف XMP في أي مشروع Java يدعم Aspose.Page.

## إجابات سريعة
- **ما هو الهدف الأساسي؟** إضافة مساحة اسم XMP مخصصة وخاصية إلى ملف EPS.  
- **ما المكتبة المطلوبة؟** Aspose.Page for Java.  
- **هل أحتاج إلى ترخيص للاختبار؟** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **كم عدد التغييرات البرمجية المطلوبة؟** فقط خمسة مقاطع شفرة قصيرة — واحدة لكل خطوة.  
- **هل يمكنني إعادة استخدام هذا النمط لمساحات اسم أخرى؟** نعم، فقط غير البادئة وURI في استدعاء `registerNamespaceURI`.

## ما هي مساحة اسم XMP؟

مساحة اسم XMP (Extensible Metadata Platform) هي معرف فريد يجمع خصائص البيانات الوصفية ذات الصلة تحت URI مشترك. تسجيل مساحة اسم يتيح لك تخزين بيانات مخصصة — مثل العلامات الخاصة — دون التعارض مع المعايير الموجودة.

## لماذا نستخدم Aspose.Page لمعالجة XMP؟

- **تحكم كامل** في بيانات تعريف EPS وPDF دون الحاجة إلى أدوات Adobe.  
- **إنشاء تلقائي** لكتل XMP عندما لا تكون موجودة، استنادًا إلى تعليقات PS.  
- **دعم Java متعدد المنصات**، مما يجعل من السهل دمجه في خطوط الأنابيب الحالية.

## المتطلبات المسبقة

- Aspose.Page for Java: تأكد من تثبيت المكتبة. يمكنك تنزيلها [هنا](https://releases.aspose.com/page/java/).  
- بيئة تطوير Java: قم بإعداد بيئة Java على نظامك.  
- ملف المستند: احصل على ملف EPS يحتوي على بيانات تعريف XMP. إذا لم يحتوي على بيانات تعريف XMP، ستقوم المكتبة بإنشاء واحدة استنادًا إلى تعليقات بيانات تعريف PS.

## استيراد الحزم

لبدء العمل، استورد الحزم الضرورية في مشروع Java الخاص بك:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## الخطوة 1: الحصول على بيانات تعريف XMP

```java

// The path to the documents directory.
String dataDir = "Your Document Directory";

// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, create a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

### لماذا هذا مهم
استرجاع كائن `XmpMetadata` يمنحك مقبضًا حيًا لبيانات تعريف المستند، مما يتيح لك قراءتها أو تعديلها أو توسيعها قبل الحفظ.

## الخطوة 2: تسجيل مساحة اسم جديدة *(كيفية إضافة مساحة اسم xmp)*

```java
// Add new XML namespace "http://www.some.org/schema/tmp#" with prefix "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

### شرح
طريقة `registerNamespaceURI` تقوم بربط بادئة قصيرة (`tmp`) بـ URI كامل. هذه الخطوة أساسية للعملية التالية لأن خصائص XMP يجب أن تكون مؤهلة باستخدام مساحة اسم مسجلة.

## الخطوة 3: إضافة خاصية جديدة

```java
// Add new property "tmp:newKey" in the new XML namespace
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

### ما الذي يحدث؟
هنا نقوم بإنشاء خاصية مخصصة تسمى `tmp:newKey` ونُعطيها القيمة `"NewValue"`. يمكنك استبدال المفتاح والقيمة بأي شيء يناسب منطق عملك.

## الخطوة 4: حفظ المستند

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

### نصيحة
دائمًا قم بلف استدعاء `save` داخل كتلة `try/finally` (أو استخدم try‑with‑resources) لضمان إغلاق تدفق الإخراج حتى لو حدث استثناء.

## الخطوة 5: إغلاق التدفقات

```java
// Close input EPS stream
psStream.close();
```

### أفضل ممارسة
إغلاق تدفق الإدخال يحرر مقبض الملف فورًا، مما يمنع مشاكل قفل الملفات على أنظمة Windows.

## المشكلات الشائعة والحلول

| المشكلة | السبب المحتمل | الحل |
|-------|--------------|-----|
| لا يظهر كتلة XMP بعد الحفظ | ملف EPS الأصلي يفتقر إلى XMP والتعليقات غير كافية | تأكد من أن EPS يحتوي على تعليقات PS قياسية (`%%Creator`, `%%Title`, إلخ) أو أنشئ يدويًا كائن `XmpMetadata` فارغ قبل تسجيل مساحة اسم. |
| `registerNamespaceURI` يثير استثناء | البادئة مستخدمة مسبقًا | اختر بادئة فريدة أو تحقق من مساحات الاسم الموجودة عبر `xmp.getRegisteredNamespaces()`. |
| الملف المحفوظ معطوب | تدفق الإخراج لم يتم تفريغه | استخدم `try‑with‑resources` أو استدعِ صراحةً `outPsStream.flush()` قبل الإغلاق. |

## الخاتمة

باتباع هذا **aspose.page xmp tutorial**، لديك الآن طريقة قابلة للتكرار لإضافة مساحات اسم وخصائص مخصصة إلى ملفات EPS باستخدام Aspose.Page for Java. تفتح هذه القدرة الباب أمام استراتيجيات بيانات تعريف أغنى — سواء كنت تدمج معرفات سير العمل، أو علامات مملوكة، أو بيانات تكامل للأنظمة اللاحقة.

## الأسئلة المتكررة

### هل يمكنني استخدام Aspose.Page for Java مع لغات برمجة أخرى؟
Aspose.Page يدعم أساسًا Java، ولكن هناك إصدارات متاحة للغات أخرى مثل .NET.

### هل هناك نسخة تجريبية مجانية متاحة؟
نعم، يمكنك تجربة نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق شاملة؟
راجع الوثائق [هنا](https://reference.aspose.com/page/java/).

### كيف يمكنني الحصول على ترخيص مؤقت؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### هل هناك منتديات مجتمع لـ Aspose.Page؟
نعم، يمكنك التفاعل مع المجتمع عبر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39).

---

**آخر تحديث:** 2025-12-20  
**تم الاختبار مع:** Aspose.Page for Java 23.12 (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}