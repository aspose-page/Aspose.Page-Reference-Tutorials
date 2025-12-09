---
date: 2025-11-29
description: تعلم كيفية دمج ملفات XPS في Java بسلاسة باستخدام Aspose.Page. اتبع دليلنا
  خطوةً بخطوة للتلاعب الفعّال بالمستندات وتعزيز مهارات تطوير Java الخاصة بك.
linktitle: Convert XPS to XPS in Java
second_title: Aspose.Page Java API
title: كيفية دمج ملفات XPS في جافا باستخدام Aspose.Page
url: /ar/java/file-merging/xps-to-xps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية دمج ملفات XPS في Java باستخدام Aspose.Page

دمج مستندات XPS هو مهمة روتينية عندما تحتاج إلى دمج تقارير أو عروض تقديمية أو أي مجموعة من ملفات XPS في حزمة واحدة سهلة المشاركة. في هذا الدرس ستتعلم **كيفية دمج ملفات xps** باستخدام Aspose.Page for Java API، مع شروحات واضحة، ونصائح عملية، ومقاطع كود جاهزة للتنفيذ.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع دمج XPS؟** Aspose.Page for Java.  
- **كم من الوقت تستغرق العملية؟** تقريبًا 10‑15 دقيقة لدمج أساسي.  
- **هل أحتاج إلى ترخيص للاختبار؟** نعم – ترخيص تجريبي مؤقت متاح من Aspose.  
- **هل يمكنني دمج ملفات بعدد صفحات مختلف؟** بالتأكيد؛ Aspose.Page يدمج أي مستندات XPS صالحة.  
- **ما إصدارات Java المدعومة؟** Java 8 وما فوق (يوصى بـ JDK 11+).

## ما هو دمج ملفات XPS؟
XPS (XML Paper Specification) هو تنسيق المستندات الثابت التخطيط من مايكروسوفت. دمج ملفات XPS يعني ربط عدة مستندات XPS في ملف واحد مع الحفاظ على تخطيط كل صفحة، الخطوط، والرسومات.

## لماذا دمج ملفات XPS في Java؟
- **الأتمتة:** إنشاء تقرير واحد من عدة وحدات دون تدخل يدوي.  
- **الاتساق:** الحفاظ على الدقة البصرية الدقيقة لصفحات XPS الأصلية.  
- **الأداء:** تقليل عدد الملفات التي تحتاج إلى نقلها أو تخزينها.  
- **متعدد المنصات:** يتيح لك Java تشغيل عملية الدمج على خوادم Windows أو Linux أو macOS.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن لديك ما يلي:

- **Java Development Kit (JDK):** تأكد من تثبيت JDK على نظامك. يمكنك تنزيله [هنا](https://www.oracle.com/java/technologies/javase-downloads.html).  
- **Aspose.Page for Java:** قم بتنزيل وتثبيت مكتبة Aspose.Page for Java من [موقع Aspose](https://purchase.aspose.com/buy).  
- **بيئة التطوير المتكاملة (IDE):** اختر IDE المفضلة لديك؛ الخيارات الشائعة تشمل Eclipse أو IntelliJ IDEA أو NetBeans.

الآن بعد أن تم إعداد كل شيء، دعنا نغوص في الكود.

## استيراد الحزم
في مشروع Java الخاص بك، ابدأ باستيراد الحزم الضرورية لاستخدام Aspose.Page for Java. أضف الأسطر التالية في بداية ملف Java الخاص بك:

```java
import java.io.FileOutputStream;

import com.aspose.xps.XpsDocument;
```

## الخطوة 1: إعداد مشروعك
أنشئ مشروع Java جديد في IDE الذي اخترته وأضف ملفات Aspose.Page JAR إلى مسار بناء المشروع. هذا يضمن أن المترجم يمكنه العثور على الفئة `XpsDocument`.

## الخطوة 2: تهيئة تدفق إخراج XPS
قم بإعداد تدفق الإخراج لملف XPS المدمج. حدد الدليل الذي تريد حفظ الملف المدمج فيه.

```java
String dataDir = "Your Document Directory";
FileOutputStream outStream = new FileOutputStream(dataDir + "mergedXPSfiles.xps");
```

> **نصيحة احترافية:** استخدم مسارًا مطلقًا أثناء التطوير لتجنب `FileNotFoundException`، ثم انتقل إلى مسار نسبي للإنتاج.

## الخطوة 3: تحميل ملف XPS الأول
حمّل ملف XPS الأول الذي سيعمل كأساس للدمج.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

تصبح خصائص المستند الأول (مثل حجم الصفحة والاتجاه) هي الإعدادات الافتراضية للملف المدمج النهائي.

## الخطوة 4: إنشاء مصفوفة من ملفات XPS
جهّز مصفوفة من ملفات XPS التي تريد دمجها مع الأول.

```java
String[] filesForMerge = new String[] { dataDir + "Demo.xps", dataDir + "sample.xps" };
```

يمكنك إضافة أي عدد من مسارات الملفات حسب الحاجة؛ يمكن بناء المصفوفة ديناميكيًا من قائمة دليل إذا رغبت.

## الخطوة 5: الدمج والحفظ
نفّذ عملية الدمج واحفظ النتيجة إلى تدفق الإخراج المحدد.

```java
document.merge(filesForMerge, outStream);
```

بعد هذا الاستدعاء، سيحتوي `mergedXPSfiles.xps` على جميع الصفحات من `input.xps` و `Demo.xps` و `sample.xps` بالترتيب الذي حددته.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **`FileNotFoundException`** | مسار `dataDir` غير صحيح | تحقق من وجود المجلد واستخدم شرطات مائلة مزدوجة (`\\`) على Windows. |
| **License not found** | التشغيل بدون ترخيص صالح | تطبيق ترخيص مؤقت من Aspose أو شراء ترخيص كامل. |
| **Merged file is empty** | لم يتم تفريغ/إغلاق تدفق الإخراج | استدعِ `outStream.close()` بعد `document.merge(...)`. |
| **Mismatched page sizes** | ملفات XPS المصدر لها أبعاد مختلفة | استخدم `document.setPageSize(...)` قبل الدمج لفرض حجم موحد. |

## الأسئلة المتكررة

**س:** هل يمكنني دمج ملفات XPS بأحجام مختلفة؟  
**ج:** نعم. يقوم Aspose.Page تلقائيًا بتطبيع أبعاد الصفحات، ولكن يمكنك أيضًا تعيين حجم صفحة مخصص قبل الدمج.

**س:** هل يتوفر ترخيص مؤقت لأغراض الاختبار؟  
**ج:** نعم، يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/) للاختبار.

**س:** أين يمكنني العثور على وثائق أكثر تفصيلاً؟  
**ج:** راجع وثائق Aspose.Page for Java [هنا](https://reference.aspose.com/page/java/).

**س:** هل توجد منتديات مجتمع لمناقشات Aspose.Page؟  
**ج:** نعم، زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتفاعل مع المجتمع.

**س:** كيف يمكنني شراء مكتبة Aspose.Page for Java؟  
**ج:** يمكنك شراء المكتبة [هنا](https://purchase.aspose.com/buy).

## الخاتمة
الآن لديك طريقة كاملة وجاهزة للإنتاج **كيفية دمج ملفات xps** باستخدام Aspose.Page for Java. باتباع الخطوات أعلاه يمكنك أتمتة دمج المستندات، تحسين كفاءة سير العمل، والحفاظ على تطبيقات Java الخاصة بك خفيفة وقوية.

---

**آخر تحديث:** 2025-11-29  
**تم الاختبار مع:** Aspose.Page for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}