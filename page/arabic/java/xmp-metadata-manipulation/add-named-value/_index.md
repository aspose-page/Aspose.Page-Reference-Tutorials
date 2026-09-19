---
date: 2026-09-19
description: تعلم كيفية إضافة قيم مسماة XMP إلى ملفات EPS باستخدام Aspose.Page for
  Java – دليل خطوة بخطوة مع أمثلة على الشيفرة.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: إضافة قيمة مسماة في XMP باستخدام Java
og_description: كيفية إضافة قيم مسماة XMP إلى ملفات EPS باستخدام Aspose.Page for Java.
  اتبع هذا الدليل المختصر لإدخال بيانات تعريف مخصصة في دقائق.
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: كيفية إضافة قيمة مسماة XMP في ملفات EPS باستخدام Java
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: كيفية إضافة قيمة مسماة XMP في ملفات EPS باستخدام Java
url: /ar/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة قيمة مسماة في بيانات XMP الوصفية باستخدام Java

## المقدمة
في تطوير Java الحديث، يُعد تعلم **كيفية إضافة XMP** كبيانات وصفية داخل ملفات EPS أمرًا أساسيًا للحفاظ على أصل المستند وتحسين إمكانية البحث. باستخدام **Aspose.Page for Java**، يمكنك بسهولة حقن قيم مسماة مخصصة في حزمة XMP. يشرح هذا الدرس الخطوات الدقيقة—مع مقتطفات الشيفرة—حتى تتمكن من بدء إضافة بيانات XMP الوصفية إلى مستندات EPS الخاصة بك اليوم.

## الإجابات السريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (Aspose)  
- **ما نوع الملف المستهدف؟** EPS files containing XMP metadata  
- **حالة الاستخدام الأساسية؟** Add custom named values (e.g., page size limits) to XMP  
- **المتطلبات المسبقة؟** JDK 8+ and the Aspose.Page for Java library  
- **الوقت النموذجي للتنفيذ؟** 5–10 minutes once the library is set up  

## ما هو asp؟
Aspose هو الاختصار لـ Aspose، مجموعة من واجهات برمجة التطبيقات (APIs) التي تمكّن المطورين من إنشاء وتحرير وتحويل وعرض مجموعة واسعة من صيغ المستندات دون الحاجة إلى برامج خارجية. يركز مكوّن Aspose.Page for Java بشكل خاص على معالجة PostScript و EPS، موفرًا وصولًا برمجيًا إلى محتوى الصفحة والرسومات والبيانات الوصفية مثل XMP.

## لماذا إضافة قيم مسماة إلى بيانات XMP الوصفية؟
القيم المسماة تتيح لك تخزين أزواج مفتاح‑قيمة عشوائية مباشرة داخل حزمة XMP، مما يجعلها قابلة للقراءة فورًا بواسطة الأدوات اللاحقة. هذا يحسن صداقة محركات البحث، ويمكن أتمتة سير العمل، ويلبي متطلبات الامتثال عن طريق تضمين المعلومات التنظيمية دون تعديل المحتوى البصري.

## لماذا هذا مهم
إضافة قيم مسماة إلى XMP يتيح لك تخزين أزواج مفتاح‑قيمة عشوائية يمكن قراءتها دون الحاجة إلى تحليل ملف EPS بالكامل. هذه القدرة ذات قيمة خاصة في خطوط النشر الآلية، وأنظمة إدارة الأصول الرقمية، وسير العمل القائم على الامتثال حيث تدفع البيانات الوصفية الإجراءات اللاحقة.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر ما يلي:

- **Java Development Kit (JDK):** A recent JDK (8 or higher) installed on your machine.  
- **Aspose.Page for Java Library:** Download it from the official [Aspose.Page for Java download](https://releases.aspose.com/page/java/). Add the JAR to your project’s classpath.  
- **An EPS file** that either already contains XMP metadata or will have it generated automatically.

## استيراد الحزم
ابدأ باستيراد الحزم اللازمة في Java. هذه الاستيرادات تمنحك الوصول إلى تدفقات الملفات، نموذج مستند EPS، وفئات معالجة XMP.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## كيفية إضافة قيمة مسماة XMP في ملفات EPS باستخدام Java
لإضافة قيمة مسماة، قم بتحميل ملف EPS باستخدام `FileInputStream`، استرجع أو أنشئ كائن `XmpMetadata` الخاص به، أدخل `NamedValue` المطلوبة في مساحة الاسم المناسبة، ثم اكتب المستند المعدل مرة أخرى باستخدام `FileOutputStream`. يتعامل Aspose.Page تلقائيًا مع إنشاء حزمة XMP إذا كانت مفقودة، مما يضمن تضمين البيانات الوصفية الجديدة بشكل صحيح.

### الخطوة 1: تهيئة تدفق ملف EPS الإدخالي
**FileInputStream** هي فئة I/O في Java تقرأ البايتات الخام من ملف. قم بتحميل ملف EPS المصدر إلى `FileInputStream`. هذا التدفق يزود المستند إلى API الخاص بـ Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **نصيحة احترافية:** اجعل المتغيّر `dataDir` قابلاً للتكوين بحيث يعمل نفس الكود عبر البيئات.

### الخطوة 2: الحصول على بيانات XMP الوصفية
**XmpMetadata** تمثل حزمة XMP المرتبطة بمستند EPS. استرجع حزمة XMP الحالية؛ إذا كان ملف EPS يفتقر إلى واحدة، يقوم Aspose بإنشاء كائن XMP جديد مُعبأ من تعليقات PS.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### الخطوة 3: إضافة قيمة مسماة
**NamedValue** هو زوج مفتاح‑قيمة مخزن داخل مساحة اسم بيانات XMP الوصفية. أدخل قيمة مسماة مخصصة في بنية XMP. في هذا المثال نضيف مفتاحًا جديدًا تحت مساحة الاسم `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **لماذا هذا مهم:** القيم المسماة تتيح لك تخزين أزواج مفتاح‑قيمة عشوائية يمكن للتطبيقات اللاحقة قراءتها دون تحليل المستند بالكامل.

### الخطوة 4: تهيئة تدفق ملف EPS الإخراجي
**FileOutputStream** هي فئة I/O في Java تكتب البايتات الخام إلى ملف. حضّر `FileOutputStream` حيث سيتم حفظ ملف EPS المعدل.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### الخطوة 5: حفظ المستند
طريقة `save` تحافظ على التغييرات. إنها تكتب حزمة XMP المحدثة مرة أخرى إلى ملف EPS، مما يضمن أن القيمة المسماة الجديدة تصبح جزءًا من بيانات المستند الوصفية.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### الخطوة 6: إغلاق تدفق EPS الإدخالي
إغلاق مقبض الملف الأصلي يمنع تسرب الموارد ويضمن عدم قفل الملف للعمليات اللاحقة.

```java
psStream.close();
```

باتباع هذه الخطوات الست، لقد نجحت في **إضافة قيمة مسماة في بيانات XMP الوصفية** باستخدام **Aspose.Page for Java**.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|-----|
| `NullPointerException` on `xmp` | ملف EPS لا يحتوي على XMP و Aspose فشل في إنشاء واحد | تأكد من أن EPS يحتوي على تعليق PS واحد على الأقل أو أنشئ يدويًا كائن `XmpMetadata` جديد. |
| ملف الإخراج فارغ | تدفق الإخراج لم يُفرغ/يُغلق | تحقق من استدعاء `outPsStream.close()` داخل كتلة `finally` (كما هو موضح). |
| خطأ مفتاح مكرر | تم إضافة نفس القيمة المسماة مرتين | تحقق مما إذا كان المفتاح موجودًا بالفعل باستخدام `xmp.containsNamedValue(...)` قبل الإضافة. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page for Java مع مكتبات Java أخرى؟**  
ج: نعم، تم تصميم Aspose.Page for Java للعمل بسلاسة مع مكتبات Java الأخرى، مما يوفر مرونة في بيئة التطوير الخاصة بك.

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Page for Java؟**  
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Page for Java عبر [صفحة إصدارات Aspose](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟**  
ج: زر [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت لـ Aspose.Page for Java.

**س: أين يمكنني العثور على المزيد من الدروس والأمثلة لـ Aspose.Page for Java؟**  
ج: استكشف [الوثائق](https://reference.aspose.com/page/java/) للحصول على دروس شاملة وأمثلة.

**س: هل Aspose.Page for Java مناسب للمشاريع الكبيرة النطاق؟**  
ج: بالتأكيد، تم تصميم Aspose.Page for Java للتعامل مع المشاريع الكبيرة النطاق بكفاءة، وتوفير قدرات قوية لمعالجة المستندات.

## الخلاصة
في هذا الدليل، أظهرنا كيف تجعل **Aspose.Page for Java** من السهل **إضافة قيم مسماة إلى بيانات XMP الوصفية** داخل ملفات EPS. باستخدام الخطوات السابقة، يمكنك إثراء مستنداتك ببيانات وصفية مخصصة، تحسين إمكانية البحث، وتمكين معالجة ذكية للخطوات اللاحقة.

---

**آخر تحديث:** 2026-09-19  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (latest at time of writing)  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إضافة مساحة اسم XMP في ملفات EPS باستخدام Aspose.Page – دليل Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [إضافة بيانات XMP الوصفية إلى ملفات EPS باستخدام Java](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [قراءة XMP باستخدام Aspose.Page – دليل Java](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}