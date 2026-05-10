---
date: 2026-03-08
description: تعلم كيفية إضافة مساحة اسم XMP في ملفات EPS باستخدام Aspose.Page للـ
  Java – دليل خطوة بخطوة حول إضافة XMP ومساحة اسم XMP في دليل Java.
linktitle: Add Namespace in XMP using Java
second_title: Aspose.Page Java API
title: كيفية إضافة مساحة اسم XMP في ملفات EPS باستخدام Aspose.Page – دليل جافا
url: /ar/java/xmp-metadata-manipulation/add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة مساحة اسم XMP في ملفات EPS باستخدام Aspose.Page – دليل Java

إذا كنت بحاجة إلى تعديل أو إثراء بيانات التعريف لملفات EPS، فإن هذا **how to add xmp** يوضح لك بالضبط كيفية إضافة مساحة اسم XMP باستخدام Java و Aspose.Page. بنهاية الدليل ستحصل على نمط قابل لإعادة الاستخدام لإدخال بيانات تعريف مخصصة في أي مستند EPS.

## إجابات سريعة
- **ما هو الهدف الأساسي؟** إضافة مساحة اسم XMP مخصصة وخصائص إلى ملف EPS.  
- **ما المكتبة المطلوبة؟** Aspose.Page for Java.  
- **هل أحتاج إلى ترخيص للاختبار؟** نسخة تجريبية مجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **كم عدد التغييرات البرمجية المطلوبة؟** فقط خمس مقتطفات شفرة قصيرة—واحدة لكل خطوة.  
- **هل يمكن إعادة استخدام هذا النمط لمساحات اسم أخرى؟** نعم، فقط غير البادئة وURI في استدعاء `registerNamespaceURI`.

## ما هي مساحة اسم XMP؟

مساحة اسم XMP (Extensible Metadata Platform) هي معرف فريد يجمع خصائص البيانات الوصفية ذات الصلة تحت URI مشترك. تسجيل مساحة اسم يتيح لك تخزين بيانات مخصصة—مثل العلامات الخاصة—دون التعارض مع المعايير الموجودة.

## لماذا تستخدم Aspose.Page لمعالجة XMP؟

- **تحكم كامل** في بيانات EPS وPDF الوصفية دون الحاجة إلى أدوات Adobe.  
- **إنشاء تلقائي** لكتل XMP عندما لا تكون موجودة، بناءً على تعليقات PS.  
- **دعم Java متعدد المنصات**، مما يسهل دمجه في خطوط الأنابيب الحالية.

## المتطلبات المسبقة

- Aspose.Page for Java: تأكد من تثبيت المكتبة. يمكنك تنزيلها [here](https://releases.aspose.com/page/java/).  
- بيئة تطوير Java: قم بإعداد بيئة Java على نظامك.  
- ملف المستند: احصل على ملف EPS يحتوي على بيانات XMP الوصفية. إذا لم يحتوي على بيانات XMP، ستقوم المكتبة بإنشاء واحدة بناءً على تعليقات بيانات PS الوصفية.

## استيراد الحزم

لبدء العمل، استورد الحزم الضرورية إلى مشروع Java الخاص بك:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## الخطوة 1: الحصول على بيانات XMP الوصفية

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
الحصول على كائن `XmpMetadata` يمنحك مقبضًا مباشرًا لبيانات تعريف المستند، مما يسمح لك بقراءتها أو تعديلها أو توسيعها قبل الحفظ.

## الخطوة 2: تسجيل مساحة اسم جديدة *(how to add xmp namespace)*

```java
// Add new XML namespace "http://www.some.org/schema/tmp#" with prefix "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

### شرح
طريقة `registerNamespaceURI` تربط بادئة قصيرة (`tmp`) بـ URI كامل. هذه الخطوة أساسية للعملية التالية لأن خصائص XMP يجب أن تكون مؤهلة بمساحة اسم مسجلة.

## الخطوة 3: إضافة خاصية جديدة

```java
// Add new property "tmp:newKey" in the new XML namespace
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

### ما الذي يحدث؟
هنا ننشئ خاصية مخصصة تسمى `tmp:newKey` ونعيّن لها القيمة `"NewValue"`. يمكنك استبدال المفتاح والقيمة بأي شيء يتناسب مع منطق عملك.

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
دائمًا احيط استدعاء `save` بكتلة `try/finally` (أو استخدم `try‑with‑resources`) لضمان إغلاق تدفق الإخراج حتى لو حدث استثناء.

## الخطوة 5: إغلاق التدفقات

```java
// Close input EPS stream
psStream.close();
```

### أفضل ممارسة
إغلاق تدفق الإدخال يحرّر مقبض الملف فورًا، مما يمنع مشاكل قفل الملفات على أنظمة Windows.

## المشكلات الشائعة والحلول

| المشكلة | السبب المحتمل | الحل |
|-------|--------------|-----|
| لا يظهر كتلة XMP بعد الحفظ | ملف EPS الأصلي يفتقر إلى XMP وكانت التعليقات غير كافية | تأكد من أن EPS يحتوي على تعليقات PS القياسية (`%%Creator`, `%%Title`, إلخ) أو أنشئ يدويًا كائن `XmpMetadata` فارغ قبل تسجيل مساحة الاسم. |
| `registerNamespaceURI` يثير استثناء | البادئة مستخدمة بالفعل | اختر بادئة فريدة أو تحقق من مساحات الاسم الموجودة عبر `xmp.getRegisteredNamespaces()`. |
| الملف المحفوظ تالف | لم يتم تفريغ تدفق الإخراج | استخدم `try‑with‑resources` أو استدعِ صراحةً `outPsStream.flush()` قبل الإغلاق. |

## الخلاصة

باتباع هذا **how to add xmp** الآن لديك طريقة قابلة للتكرار لإضافة مساحات اسم وخصائص مخصصة إلى ملفات EPS باستخدام Aspose.Page for Java. تفتح هذه القدرة الباب أمام استراتيجيات بيانات تعريف أغنى—سواء كنت تُضمّن معرفات سير عمل، أو علامات مملوكة، أو بيانات تكامل للأنظمة اللاحقة.

## الأسئلة الشائعة

### هل يمكنني استخدام Aspose.Page للـ Java مع لغات برمجة أخرى؟
يدعم Aspose.Page أساسًا Java، لكن هناك إصدارات متاحة للغات أخرى مثل .NET.

### هل تتوفر نسخة تجريبية مجانية؟
نعم، يمكنك تجربة نسخة تجريبية مجانية [here](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق شاملة؟
راجع الوثائق [here](https://reference.aspose.com/page/java/).

### كيف يمكنني الحصول على ترخيص مؤقت؟
يمكنك الحصول على ترخيص مؤقت [here](https://purchase.aspose.com/temporary-license/).

### هل توجد منتديات مجتمع لـ Aspose.Page؟
نعم، يمكنك التفاعل مع المجتمع في [Aspose.Page forum](https://forum.aspose.com/c/page/39).

---

**آخر تحديث:** 2026-03-08  
**تم الاختبار مع:** Aspose.Page for Java 24.10 (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}