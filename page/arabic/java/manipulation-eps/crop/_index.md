---
date: 2026-02-07
description: تعلم كيفية قص ملفات EPS في جافا باستخدام Aspose.Page – دليل خطوة بخطوة
  يوضح كيفية قص EPS، قص صورة EPS وتقليم ملف EPS باستخدام مكتبة Aspose.Page.
linktitle: Crop EPS File in Java
second_title: Aspose.Page Java API
title: كيفية قص ملفات EPS في Java – دليل Aspose.Page
url: /ar/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قص ملفات EPS في Java – دليل خطوة بخطوة مع Aspose.Page

## المقدمة
إذا كنت بحاجة إلى **how to crop eps** ملفات برمجياً في تطبيق Java، فقد وصلت إلى المكان الصحيح. في هذا الدرس سنستعرض العملية الكاملة لقص صورة EPS باستخدام مكتبة Aspose.Page for Java القوية. بحلول نهاية الدليل ستفهم لماذا يعتبر قص EPS مهمًا، وسترى الشيفرة الدقيقة التي تحتاجها، وستكون جاهزًا لدمج الحل في مشاريعك الخاصة.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع قص EPS في Java؟** Aspose.Page for Java.  
- **كم من الوقت يستغرق تنفيذ قص أساسي؟** تقريبًا 5‑10 دقائق.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما إصدارات Java المدعومة؟** Java 8 وما بعدها.  
- **هل يمكنني تعريف أي صندوق حد مخصص؟** نعم – تقوم بتوفير الإحداثيات التي تحتاجها.

## ما هو قص EPS ولماذا نستخدمه؟
Encapsulated PostScript (EPS) هو تنسيق رسومي يخزن الصور المتجهة مع صندوق حد يحدد المنطقة المرئية. قص ملف EPS يعني إنشاء صندوق حد جديد بحيث يتم الاحتفاظ فقط بالمنطقة التي تهتم بها. هذا مفيد عندما تريد إزالة الهوامش البيضاء، استخراج شعار، أو ملاءمة الرسم في تخطيط أكثر ضيقًا دون إعادة إنشاء ملف المصدر.

## لماذا قص ملفات EPS؟
- **تقليل حجم الملف** – قص المساحات الفارغة غير الضرورية يمكن أن يجعل الملف أخف.  
- **تحسين اتساق التخطيط** – EPS مقصوص ونظيف يندمج بشكل أفضل في ملفات PDF أو التقارير.  
- **أتمتة المعالجة الدفعية** – بمجرد معرفتك **how to crop eps**، يمكنك تطبيق نفس المنطق على العشرات من الملفات تلقائيًا.

## المتطلبات المسبقة
قبل أن نغوص في الشيفرة، تأكد من أن لديك:

- مكتبة **Aspose.Page for Java** مثبتة – حمّلها من الصفحة الرسمية [هنا](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** الإصدار 8 أو أحدث مثبت على جهازك.  
- **مجلد** لتخزين ملف EPS الإدخالي (`input.eps`) والملف المقصوص الناتج (`output_crop.eps`).

## استيراد الحزم
أولاً، استورد الفئات اللازمة في Java. هذه القطعة تبقى كما هي تمامًا كما في الدرس الأصلي:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

## كيفية قص صورة EPS في Java
فيما يلي شرح خطوة بخطوة. يتم شرح كل خطوة بلغة بسيطة قبل كتلة الشيفرة، حتى تعرف دائمًا *لماذا* نقوم بذلك.

### الخطوة 1: تعيين دليل المستند وتدفق الإدخال
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
هنا نوجه الشيفرة إلى المجلد الذي يحتوي على ملف EPS المصدر ونفتح تدفقًا لقراءته.

### الخطوة 2: تهيئة كائن PsDocument
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
فئة `PsDocument` تمثل مستند EPS في الذاكرة، مما يسمح لنا باستعلام خصائصه وتعديلها.

### الخطوة 3: استخراج صندوق الحد الأولي
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
استخراج صندوق الحد الأصلي يمنحك إحداثيات المنطقة المرئية الحالية – وهو مفيد لتحديد مقدار القص المطلوب.

### الخطوة 4: إنشاء تدفق الإخراج
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
نفتح تدفقًا حيث سيتم كتابة ملف EPS المقصوص.

### الخطوة 5: تعريف صندوق حد جديد والقص
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
قدّم الإحداثيات الأربعة (x السفلية‑اليسرى، y السفلية‑اليسرى، x العلوية‑اليمنى، y العلوية‑اليمنى) التي تحدد المنطقة التي تريد الاحتفاظ بها. طريقة `cropEps` تقوم بالقص وتكتب النتيجة إلى `output_crop.eps`.

## المشكلات الشائعة والحلول
- **إحداثيات غير صحيحة:** EPS يستخدم النقاط (1/72 بوصة). إذا كان القص غير دقيق، تحقق مرة أخرى من تحويل الوحدات.  
- **خطأ ملف غير موجود:** تأكد من أن `dataDir` ينتهي بفاصل المسار المناسب (`/` أو `\`).  
- **استثناءات الترخيص:** تشغيل الشيفرة بدون ترخيص صالح قد يضيف علامة مائية إلى الناتج. طبق ترخيصك المؤقت أو الدائم قبل الاستخدام في الإنتاج.

## الأسئلة المتكررة

**س: هل Aspose.Page متوافق مع Java 8؟**  
**ج:** نعم، Aspose.Page يعمل مع Java 8 وأي إصدار لاحق.

**س: هل يمكنني استخدام Aspose.Page في مشاريع تجارية؟**  
**ج:** بالتأكيد. الترخيص التجاري مطلوب للنشر في بيئات الإنتاج. يمكنك الحصول عليه [هنا](https://purchase.aspose.com/buy).

**س: أين يمكنني العثور على موارد إضافية ودعم المجتمع؟**  
**ج:** زر المنتدى الرسمي لـ [Aspose.Page](https://forum.aspose.com/c/page/39) للمناقشات، عينات الشيفرة، ونصائح حل المشكلات.

**س: هل هناك نسخة تجريبية مجانية متاحة للاختبار؟**  
**ج:** نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Page من صفحة الإصدارات [هنا](https://releases.aspose.com/).

**س: كيف أحصل على ترخيص مؤقت لتقييم قصير الأمد؟**  
**ج:** يمكن طلب ترخيص مؤقت من بوابة الترخيص [هنا](https://purchase.aspose.com/temporary-license/).

## الخلاصة
أنت الآن تعرف **how to crop eps** ملفات في Java باستخدام Aspose.Page. من خلال تعريف صندوق حد مخصص واستدعاء `cropEps`، يمكنك قص الهوامش غير المرغوب فيها أو عزل أجزاء محددة من رسم EPS ببضع أسطر من الشيفرة فقط. دمج هذه القطعة في خطوط معالجة المستندات الأكبر لت automating معالجة EPS، **crop eps image** الأصول، و **trim eps file** المحتوى بفعالية.

---

**آخر تحديث:** 2026-02-07  
**تم الاختبار مع:** Aspose.Page for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}