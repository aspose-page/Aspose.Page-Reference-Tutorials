---
date: 2026-05-25
description: تعلم كيفية تعديل XMP في مستندات EPS باستخدام Java مع Aspose.Page. قم
  بتحديث البيانات الوصفية بسرعة وبشكل موثوق.
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: تغيير القيم في XMP باستخدام Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: كيفية تعديل XMP باستخدام Aspose.Page – تغيير القيم في XMP باستخدام Java
url: /ar/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تغيير القيم في XMP باستخدام Java

## مقدمة
إذا كنت تبحث عن **كيفية تعديل xmp** داخل ملف EPS باستخدام Java، فقد وصلت إلى المكان الصحيح. يشرح هذا الدرس كل خطوة — قراءة كتلة XMP الحالية، تحديث الحقول مثل المُنشئ، العنوان، وتاريخ التعديل، وأخيرًا حفظ التغييرات مرة أخرى في مستند EPS. في النهاية ستحصل على مقتطف قابل لإعادة الاستخدام يمكن دمجه في أي سير عمل آلي، مما يضمن أن ملفاتك تحمل البيانات الوصفية الصحيحة للعلامة التجارية، والامتثال، أو فهرسة محركات البحث.

## إجابات سريعة
- **ماذا يفعل “aspose.page modify xmp”؟** يتيح لك قراءة وكتابة بيانات XMP الوصفية في ملفات EPS عبر Aspose.Page Java API.  
- **ما هو إصدار المكتبة المطلوب؟** أي إصدار حديث من Aspose.Page for Java (API ثابت عبر الإصدارات).  
- **هل أحتاج إلى ترخيص لتشغيل العينة؟** الإصدار التجريبي المجاني يعمل للتقييم؛ يتطلب الترخيص التجاري للإنتاج.  
- **هل يمكنني تغيير عدة حقول XMP في آن واحد؟** نعم — استدعِ `put` لكل حقل قبل حفظ المستند.  
- **هل هناك حاجة لمعالجة المنطقة الزمنية؟** ضبط المنطقة الزمنية الافتراضية (مثل UTC) يضمن قيم تاريخ متسقة.

## ما هو XMP ولماذا يتم تعديله؟
XMP (Extensible Metadata Platform) هو تنسيق موحد يعتمد على XML لتضمين بيانات وصفية غنية مباشرة داخل ملفات مثل EPS وPDF والصور. يتيح تحديث XMP التحكم في كيفية فهرسة المستندات وعرضها والبحث عنها — وهو أمر حاسم لتناسق العلامة التجارية، والامتثال التنظيمي، وأنابيب المحتوى الآلية.

## لماذا نستخدم Aspose.Page للـ Java؟
Aspose.Page توفر **واجهة برمجة تطبيقات كاملة الميزات، pure‑Java** تُلغي الحاجة إلى أدوات خارجية أو مكتبات أصلية. تدعم **أكثر من 50 صيغة إدخال وإخراج** ويمكنها معالجة ملفات EPS حتى **500 ميغابايت** دون تحميل المستند بالكامل في الذاكرة، مما يقدّم تعديل بيانات وصفية سريع ومنخفض الذاكرة على أي نظام تشغيل يدعم Java.

## المتطلبات المسبقة
قبل أن نبدأ هذا الدرس، تأكد من توفر المتطلبات التالية:
1. **بيئة تطوير Java** – JDK (8 أو أحدث) وIDE أو أداة بناء حسب اختيارك.  
2. **مكتبة Aspose.Page للـ Java** – قم بتنزيل وتثبيت مكتبة Aspose.Page للـ Java. يمكنك العثور على الحزمة اللازمة [هنا](https://releases.aspose.com/page/java/).

## استيراد الحزم
ابدأ باستيراد الحزم المطلوبة إلى مشروع Java الخاص بك. هذه الحزم ضرورية للتفاعل مع مستندات EPS ومعالجتها.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## كيفية تعديل XMP في EPS باستخدام Java؟
`Document` هو صف Aspose.Page الذي يمثل ملف EPS ويوفر الوصول إلى محتواه وبياناته الوصفية. `XmpMetadata` يمثل كتلة XMP المرفقة بالمستند ويسمح بقراءة وكتابة حقول البيانات الوصفية. `put` يضيف أو يحدّث إدخال بيانات وصفية في كائن XmpMetadata. `save` يكتب المستند المعدل، بما في ذلك أي بيانات XMP محدثة، إلى ملف.

حمّل ملف EPS باستخدام `new Document("input.eps")`، استخرج كائن `XmpMetadata` الخاص به، حدّث المفاتيح المطلوبة باستخدام `put`، وأخيرًا استدعِ `save` لكتابة التغييرات إلى ملف جديد. هذا التدفق المختصر يتعامل تلقائيًا مع كتل XMP المفقودة، ينشئ واحدة من تعليقات PostScript عند الحاجة، ويضمن تواريخ متسقة مع المنطقة الزمنية.

## الخطوة 1: الحصول على بيانات XMP الوصفية
الصف `XmpMetadata` يمثل كتلة XMP المرفقة بمستند EPS. عندما تستدعي `document.getXmpMetadata()`، إما أن تُعيد API الكتلة الموجودة أو تُنشئ واحدة جديدة من تعليقات PS مثل `%%Creator` و`%%CreateDate` و`%%Title`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## الخطوة 2: تغيير قيمة "ModifyDate"
حدّث إدخال "ModifyDate" ليعكس طابع الزمن الجديد للتعديل. استخدم `java.util.Date` مع `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` لضمان أن القيمة المخزنة لا تعتمد على المنطقة الزمنية.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## الخطوة 3: تغيير قيمة "Creator"
المفتاح "Creator" يخزن اسم التطبيق أو الشخص الذي أنشأ ملف EPS. استدعِ `xmp.put("dc:creator", "Your Company Name")` لاستبدال القيمة الحالية بمعرّف مخصص.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## الخطوة 4: تغيير قيمة "Title"
حقل "Title" يُعرض في العديد من أنظمة إدارة الأصول. ضبطه عبر `xmp.put("dc:title", "New Document Title")` يضمن ظهور المستند بشكل صحيح في الكتالوجات ونتائج البحث.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## الخطوة 5: حفظ المستند مع بيانات XMP الوصفية المعدلة
بعد جميع التعديلات، استدعِ `document.save("output.eps")`. المكتبة تكتب كتلة XMP المحدثة مرة أخرى في تدفق EPS مع الحفاظ على محتوى الرسومات الأصلي دون تغيير.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## المشكلات الشائعة والحلول
- **Missing XMP block** – تقوم API بإنشاء واحدة تلقائيًا من تعليقات PS، ولكن يمكنك أيضًا إنشاء `XmpMetadata` يدويًا إذا لزم الأمر.  
- **Timezone mismatches** – دائمًا قم بتعيين `TimeZone.setDefault` قبل إنشاء كائن `Date` لتجنب الانحرافات غير المتوقعة.  
- **File access errors** – تأكد من صحة مسارات الإدخال والإخراج وأن تطبيقك يمتلك أذونات القراءة/الكتابة.

## الأسئلة المتكررة

**س: كيف يمكنني التعامل مع اعتبارات المنطقة الزمنية عند تعديل قيم XMP؟**  
A: استخدم `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` لضمان التناسق في إعدادات المنطقة الزمنية.

**س: هل يمكنني تغيير عدة قيم XMP في عملية واحدة؟**  
A: نعم، باستخدام طريقة `put` لكل قيمة مرغوبة، يمكنك تعديل عدة قيم XMP في وقت واحد.

**س: أين يمكنني العثور على وثائق إضافية لـ Aspose.Page للـ Java؟**  
A: استكشف الوثائق الشاملة [هنا](https://reference.aspose.com/page/java/).

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page للـ Java؟**  
A: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page للـ Java؟**  
A: احصل على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: هل يؤثر تعديل XMP على المحتوى البصري للـ EPS؟**  
A: لا. تغييرات XMP هي بيانات وصفية فقط ولا تغير العناصر الرسومية لملف EPS.

**س: هل يمكنني قراءة القيم المحدثة برمجيًا للتحقق من التغيير؟**  
A: بالطبع — فقط استدعِ `xmp.get("dc:creator")` (أو المفتاح المناسب) بعد الحفظ وقبل إغلاق المستند.

## الخلاصة
تهانينا! لقد أتقنت **كيفية تعديل xmp** في مستندات EPS باستخدام Aspose.Page للـ Java. من خلال تضمين بيانات وصفية دقيقة للمُنشئ والعنوان وتاريخ التعديل، تضمن أن أصولك قابلة للبحث، ومتوافقة، ومتناسقة مع معايير علامتك التجارية. لا تتردد في دمج هذا النمط في خطوط معالجة الدُفعات، خطوات CI/CD، أو أي سير عمل آلي لتوليد المستندات.

---

**آخر تحديث:** 2026-05-25  
**تم الاختبار مع:** Aspose.Page for Java (latest release)  
**المؤلف:** Aspose

## الدروس ذات الصلة

- [دليل Aspose Page Java – إضافة بيانات XMP الوصفية إلى ملفات EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [كيفية قراءة بيانات XMP الوصفية باستخدام Java – دليل Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java - تغيير عناصر المصفوفة في XMP باستخدام Java](/page/java/xmp-metadata-manipulation/change-array-items/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}