---
date: 2025-12-21
description: تعلم كيفية تعديل XMP في مستندات EPS باستخدام Java مع Aspose.Page. حسّن
  البيانات الوصفية بسرعة باستخدام Aspose.Page للـ Java.
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page تعديل xmp – تغيير القيم في XMP باستخدام Java
url: /ar/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تغيير القيم في XMP باستخدام Java

## المقدمة
إذا كنت بحاجة إلى **aspose.page modify xmp** البيانات داخل ملف EPS، فقد وصلت إلى المكان الصحيح. في هذا الدرس سنستعرض الخطوات الدقيقة المطلوبة لقراءة، وتحديث، وحفظ قيم XMP (Extensible Metadata Platform) باستخدام مكتبة Aspose.Page للغة Java. في النهاية، ستكون قادرًا على تخصيص بيانات تعريف المستند—مثل المُنشئ، العنوان، وتاريخ التعديل—لتتناسب مع متطلبات مشروعك.

## إجابات سريعة
- **ماذا يفعل “aspose.page modify xmp”؟** يتيح لك قراءة وكتابة بيانات XMP التعريفية في ملفات EPS عبر Aspose.Page Java API.  
- **ما هو إصدار المكتبة المطلوب؟** أي إصدار حديث من Aspose.Page للغة Java (واجهة البرمجة مستقرة عبر الإصدارات).  
- **هل أحتاج إلى ترخيص لتشغيل العينة؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص التجاري مطلوب للإنتاج.  
- **هل يمكنني تغيير عدة حقول XMP في آنٍ واحد؟** نعم—استدعِ `put` لكل حقل قبل حفظ المستند.  
- **هل هناك حاجة لمعالجة المنطقة الزمنية؟** ضبط المنطقة الزمنية الافتراضية (مثال: UTC) يضمن قيم تواريخ متسقة.

## ما هو XMP ولماذا نعدّله؟
XMP (Extensible Metadata Platform) هو طريقة معيارية لإدراج بيانات تعريف غنية مباشرة داخل ملفات مثل EPS، PDF، والصور. تحديث XMP يتيح لك التحكم في كيفية فهرسة المستندات، عرضها، والبحث عنها—وذلك أمر حاسم للعلامة التجارية، الامتثال، وأتمتة سير العمل.

## لماذا نستخدم Aspose.Page للغة Java؟
- **واجهة برمجة تطبيقات كاملة الميزات** – لا حاجة لأدوات خارجية؛ كل شيء يتم داخل العملية.  
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java.  
- **بدون تبعيات أصلية** – تنفيذ Java نقي يبسط عملية النشر.  
- **دعم قوي** – يتعامل مع كتل XMP الموجودة ويُنشئ كتلًا جديدة من تعليقات PS إذا كانت مفقودة.

## المتطلبات المسبقة
قبل أن نبدأ هذا الدرس، تأكد من توفر المتطلبات التالية:
1. **بيئة تطوير Java** – JDK (الإصدار 8 أو أحدث) ومحرر أو أداة بناء من اختيارك.  
2. **مكتبة Aspose.Page للغة Java** – قم بتحميل وتثبيت مكتبة Aspose.Page للغة Java. يمكنك العثور على الحزمة المطلوبة [هنا](https://releases.aspose.com/page/java/).

## استيراد الحزم
ابدأ باستيراد الحزم المطلوبة إلى مشروع Java الخاص بك. هذه الحزم أساسية للتفاعل مع مستندات EPS ومعالجتها.

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

## الخطوة 1: الحصول على بيانات XMP التعريفية
استرجع بيانات XMP التعريفية من مستند EPS. إذا لم يحتوي ملف EPS على بيانات XMP، سيتم إنشاء واحدة جديدة بالقيم المستخرجة من تعليقات بيانات PS مثل %%Creator، %%CreateDate، و%%Title.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## الخطوة 2: تغيير قيمة “ModifyDate”
عدّل قيمة “ModifyDate” في بيانات XMP لتعكس التاريخ المطلوب.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## الخطوة 3: تغيير قيمة “Creator”
حدّث قيمة “Creator” في بيانات XMP لتحديد مُنشئ المستند.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## الخطوة 4: تغيير قيمة “Title”
عدّل قيمة “Title” في بيانات XMP لتعيين عنوان مناسب للمستند.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## الخطوة 5: حفظ المستند مع بيانات XMP المعدلة
احفظ المستند مع بيانات XMP المحدثة إلى ملف EPS جديد.

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
- **عدم وجود كتلة XMP** – تقوم الواجهة البرمجية بإنشاء واحدة تلقائيًا من تعليقات PS، لكن يمكنك أيضًا إنشاء كائن `XmpMetadata` يدويًا إذا لزم الأمر.  
- **اختلاف المناطق الزمنية** – احرص دائمًا على ضبط `TimeZone.setDefault` قبل إنشاء كائن `Date` لتجنب الفروقات غير المتوقعة.  
- **أخطاء الوصول إلى الملفات** – تأكد من صحة مسارات الإدخال والإخراج وأن تطبيقك يمتلك صلاحيات القراءة/الكتابة.

## الأسئلة المتكررة

**س: كيف يمكنني التعامل مع اختلاف المناطق الزمنية عند تعديل قيم XMP؟**  
ج: استخدم `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` لضمان اتساق إعدادات المنطقة الزمنية.

**س: هل يمكنني تغيير عدة قيم XMP في عملية واحدة؟**  
ج: نعم، باستخدام طريقة `put` لكل قيمة مرغوبة يمكنك تعديل عدة قيم XMP في آنٍ واحد.

**س: أين يمكنني العثور على وثائق إضافية لـ Aspose.Page للغة Java؟**  
ج: استكشف الوثائق الشاملة [هنا](https://reference.aspose.com/page/java/).

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page للغة Java؟**  
ج: نعم، يمكنك الوصول إلى النسخة التجريبية [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page للغة Java؟**  
ج: احصل على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: هل تعديل XMP يؤثر على المحتوى المرئي للـ EPS؟**  
ج: لا. تغييرات XMP هي تعريفية فقط ولا تغير العناصر الرسومية لملف EPS.

**س: هل يمكنني قراءة القيم المحدثة برمجيًا للتحقق من التعديل؟**  
ج: بالتأكيد—ما عليك سوى استدعاء `xmp.get("dc:creator")` (أو المفتاح المناسب) بعد الحفظ وقبل إغلاق المستند.

## الخاتمة
تهانينا! لقد نجحت في تعديل قيم **aspose.page modify xmp** في مستندات EPS باستخدام Aspose.Page للغة Java. لقد زودك هذا الدرس بالمعرفة اللازمة لتعديل البيانات التعريفية، مما يضمن توافق مستنداتك مع متطلباتك الخاصة بسلاسة.

---

**آخر تحديث:** 2025-12-21  
**تم الاختبار مع:** Aspose.Page للغة Java (أحدث إصدار)  
**المؤلف:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
