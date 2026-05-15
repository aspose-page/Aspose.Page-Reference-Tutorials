---
date: 2026-05-15
description: استكشف دليل aspose.page xmp للغة Java — تعلم كيفية تغيير عناصر المصفوفة
  في بيانات XMP الوصفية، وتحديث عناوين EPS، والمؤلفين، والمزيد باستخدام بضع أسطر من
  الشيفرة فقط.
keywords:
- aspose.page xmp tutorial
- change array items java
- xmp metadata java
linktitle: تغيير عناصر المصفوفة في XMP باستخدام Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  headline: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  type: TechArticle
- description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  name: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  steps:
  - name: Get XMP Metadata
    text: Call `document.getXmpMetadata()` to retrieve the XMP metadata object associated
      with the EPS file.
  - name: Set "dc:title" Array Item
    text: Use `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` to replace the
      first title entry.
  - name: Set "dc:creator" Array Item
    text: Similarly, `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` updates
      the first creator entry.
  - name: Initialize Output EPS File Stream
    text: Create a `FileOutputStream` pointing to the destination EPS file to write
      the updated document.
  - name: Save Document with Changed XMP Metadata
    text: The `PsDocument` class represents an EPS document and provides the `save`
      method to write changes to a stream.
  type: HowTo
- questions:
  - answer: No. You must invoke `setArrayItem` for each index you wish to modify;
      the API does not provide a bulk‑update method.
    question: Can I update multiple array items in one call?
  - answer: Yes. Provide the full prefix (e.g., `myNS:customProp`) when calling `setArrayItem`
      or `removeArrayItem`.
    question: Does aspose.page xmp java support custom namespaces?
  - answer: Reload the EPS with `PsDocument`, call `getXmpMetadata()`, and inspect
      the returned values, or open the file in an XMP viewer.
    question: How do I verify that the metadata was updated correctly?
  - answer: Use `removeArrayItem(namespace, index)` to delete a specific entry from
      an XMP array.
    question: Is it possible to remove an array item entirely?
  - answer: No. XMP metadata is stored separately from the graphic content and does
      not alter how the EPS renders.
    question: Will the changes affect the visual appearance of the EPS?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'دليل aspose.page xmp: تغيير عناصر المصفوفة في XMP باستخدام Java'
url: /ar/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# دليل aspose.page xmp: تغيير عناصر المصفوفة في XMP باستخدام Java

## مقدمة
مرحبًا بكم في دليل **aspose.page xmp** الشامل. في هذا الدليل سنوضح لكم خطوة بخطوة كيفية تغيير عناصر المصفوفة في بيانات XMP الوصفية داخل ملفات EPS باستخدام Aspose.Page for Java. سواء كنت بحاجة إلى تحديث عنوان المستند، أو قائمة المؤلفين، أو أي مصفوفة XMP أخرى، فإن العملية بسيطة، برمجية بالكامل، وتعمل مع Java 8 +.

## إجابات سريعة
- **ما الذي يفعله aspose.page xmp java؟** يقوم بقراءة وكتابة بيانات XMP الوصفية في ملفات EPS مباشرةً من Java.  
- **هل أحتاج إلى ترخيص لتجربته؟** نعم — نسخة تجريبية مجانية لمدة 30 يومًا متاحة؛ يتطلب الترخيص التجاري للإنتاج.  
- **ما إصدار JDK المدعوم؟** Java 8 أو أحدث (بما في ذلك Java 11، 17، و21).  
- **هل يمكنني تعديل حقول وصفية أخرى؟** بالتأكيد — أي خاصية XMP، بما في ذلك المساحات الاسمية المخصصة، يمكن قراءتها أو تحديثها.  
- **هل الـ API آمن للخطوط المتعددة؟** معظم عمليات القراءة/الكتابة آمنة عندما يعمل كل خيط مع نسخة `PsDocument` الخاصة به.

## ما هو aspose.page xmp java؟
`aspose.page xmp java` هو مكوّن Aspose.Page for Java الذي ي抽象 منصة البيانات الوصفية القابلة للتوسيع (XMP) إلى كائنات Java سهلة الاستخدام. يتيح لك تعديل المصفوفات، والحقائب، والخصائص المهيكلة دون التعامل مع XML الخام. عمليًا، تعمل مع طرق عالية المستوى مثل `setArrayItem` و `removeArrayItem` لتعديل البيانات الوصفية فورًا.

## لماذا تستخدم aspose.page xmp java لبيانات وصفية EPS؟
يجب عليك استخدام هذه المكتبة عندما تحتاج إلى تحكم دقيق وآلي في بيانات وصفية EPS على نطاق واسع. يدعم Aspose.Page **أكثر من 30 حقلًا من مخطط XMP** ويمكنه معالجة ملفات تصل إلى **500 ميغابايت** دون تحميل المستند بالكامل في الذاكرة، مما يمنحك السرعة واستهلاكًا منخفضًا للذاكرة. كما يضمن الـ API أن التغييرات تحافظ على الرسومات الأصلية، لذا لا يتأثر العرض البصري.

## المتطلبات المسبقة
- مجموعة تطوير جافا (JDK) 8 أو أحدث مثبتة.  
- مكتبة Aspose.Page for Java. قم بتنزيل أحدث ملف JAR من [هنا](https://releases.aspose.com/page/java/).  
- ملف ترخيص Aspose صالح (أو ترخيص تجريبي) موضوع على مسار الفئة (classpath).

## كيفية تغيير عناصر المصفوفة باستخدام aspose.page xmp java
يوضح هذا القسم سير العمل الكامل: فتح ملف EPS، الحصول على كائن بيانات XMP الوصفية، تعديل إدخالات المصفوفة المحددة، وأخيرًا كتابة المستند المحدث إلى القرص. يتم توضيح كل خطوة باستخدام كود Java مختصر، مما يجعل من السهل دمجه في تطبيقاتك الخاصة.

### الخطوة 1: الحصول على بيانات XMP الوصفية
استدعِ `document.getXmpMetadata()` لاسترجاع كائن بيانات XMP الوصفية المرتبط بملف EPS.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

### الخطوة 2: تعيين عنصر مصفوفة "dc:title"
استخدم `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` لاستبدال الإدخال الأول للعنوان.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```

### الخطوة 3: تعيين عنصر مصفوفة "dc:creator"
وبالمثل، `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` يحدث الإدخال الأول للمنشئ.

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### الخطوة 4: تهيئة تدفق ملف EPS الناتج
أنشئ `FileOutputStream` يشير إلى ملف EPS الوجهة لكتابة المستند المحدث.

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### الخطوة 5: حفظ المستند مع بيانات XMP الوصفية المعدلة
تمثل الفئة `PsDocument` مستند EPS وتوفر طريقة `save` لكتابة التغييرات إلى تدفق.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

## المشكلات الشائعة والنصائح
- **فهرس خارج النطاق:** تحقق من وجود الفهرس المستهدف؛ وإلا ستطلق Aspose استثناء `ArrayIndexOutOfBoundsException`.  
- **إدارة التدفقات:** دائمًا أغلق التدفقات في كتلة `finally` أو استخدم try‑with‑resources لتجنب قفل الملفات.  
- **تفعيل الترخيص:** نسيان تطبيق ترخيص صالح يؤدي إلى ظهور علامة مائية على EPS في وضع التجربة.  
- **الملفات الكبيرة:** بالنسبة لملفات EPS التي تتجاوز 200 ميغابايت، فكر في زيادة حجم كومة JVM (`-Xmx2g`) لتجنب ضغط الذاكرة.

## الأسئلة المتكررة

**س: هل يمكنني تحديث عناصر مصفوفة متعددة في استدعاء واحد؟**  
ج: لا. يجب استدعاء `setArrayItem` لكل فهرس ترغب في تعديله؛ الـ API لا يوفر طريقة تحديث جماعي.

**س: هل يدعم aspose.page xmp java مساحات أسماء مخصصة؟**  
ج: نعم. قدم البادئة الكاملة (مثلاً `myNS:customProp`) عند استدعاء `setArrayItem` أو `removeArrayItem`.

**س: كيف يمكنني التحقق من أن البيانات الوصفية تم تحديثها بشكل صحيح؟**  
ج: أعد تحميل EPS باستخدام `PsDocument`، استدعِ `getXmpMetadata()`، وتفحص القيم المرجعة، أو افتح الملف في عارض XMP.

**س: هل يمكن إزالة عنصر مصفوفة بالكامل؟**  
ج: استخدم `removeArrayItem(namespace, index)` لحذف إدخال محدد من مصفوفة XMP.

**س: هل ستؤثر التغييرات على المظهر البصري للـ EPS؟**  
ج: لا. تُخزن بيانات XMP الوصفية بشكل منفصل عن محتوى الرسومات ولا تغير طريقة عرض الـ EPS.

## الخاتمة
لقد إتقنت الآن **دليل aspose.page xmp** للـ Java ويمكنك بثقة تغيير عناصر المصفوفة في بيانات XMP الوصفية لملفات EPS. تتيح لك هذه القدرة إنشاء خطوط معالجة مستندات آلية، وتحديثات جماعية للبيانات الوصفية، وإدارة أصول أفضل دون التأثير على البيانات البصرية.

---

**آخر تحديث:** 2026-05-15  
**تم الاختبار مع:** Aspose.Page for Java 24.11 (latest at time of writing)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## دروس ذات صلة

- [إضافة عناصر مصفوفة في بيانات XMP باستخدام Java](/page/java/xmp-metadata-manipulation/add-array-items/)
- [دليل aspose page xmp – تغيير القيمة المسماة في XMP باستخدام Java](/page/java/xmp-metadata-manipulation/change-named-value/)
- [كيفية قراءة بيانات XMP باستخدام Java – دليل Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}