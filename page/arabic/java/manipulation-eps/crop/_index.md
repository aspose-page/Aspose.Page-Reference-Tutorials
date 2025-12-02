---
date: 2025-11-30
description: تعلم كيفية قص ملفات EPS في Java باستخدام Aspose.Page – دليل واضح خطوة
  بخطوة حول كيفية قص ملفات EPS باستخدام مكتبة Aspose.Page.
language: ar
linktitle: Crop EPS File in Java
second_title: Aspose.Page Java API
title: كيفية قص ملفات EPS في Java – دليل Aspose.Page
url: /java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قص ملفات EPS في Java – دليل خطوة بخطوة مع Aspose.Page

## المقدمة
إذا كنت بحاجة إلى **كيفية قص ملفات eps** برمجياً في تطبيق Java، فأنت في المكان الصحيح. في هذا الدرس سنستعرض العملية الكاملة لقص صورة EPS باستخدام مكتبة Aspose.Page for Java القوية. بنهاية الدليل ستفهم لماذا يعتبر قص EPS مهماً، وسترى الشيفرة الدقيقة التي تحتاجها، وستكون جاهزاً لدمج الحل في مشاريعك الخاصة.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع قص EPS في Java؟** Aspose.Page for Java.  
- **كم من الوقت يستغرق تنفيذ قص أساسي؟** تقريباً 5‑10 دقائق.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما إصدارات Java المدعومة؟** Java 8 وما بعدها.  
- **هل يمكنني تعريف أي صندوق حدّ مخصص؟** نعم – يمكنك توفير الإحداثيات التي تحتاجها.

## ما هو قص EPS ولماذا نستخدمه؟
Encapsulated PostScript (EPS) هو تنسيق رسومي يخزن صوراً متجهة مع صندوق حدّ (bounding box) يحدد المنطقة المرئية. قص ملف EPS يعني إنشاء صندوق حدّ جديد بحيث تُحتفظ فقط بالمنطقة التي تهمك. هذا مفيد عندما تريد إزالة الهوامش البيضاء، استخراج شعار، أو ملاءمة الرسمة في تخطيط أكثر ضيقاً دون الحاجة لإعادة إنشاء الملف الأصلي.

## المتطلبات المسبقة
قبل الغوص في الشيفرة، تأكد من وجود ما يلي:

- مكتبة **Aspose.Page for Java** مثبتة – حمّلها من الصفحة الرسمية [هنا](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** الإصدار 8 أو أحدث مثبت على جهازك.  
- **مجلد** لتخزين ملف EPS الإدخالي (`input.eps`) والملف الناتج بعد القص (`output_crop.eps`).

## استيراد الحزم
أولاً، استورد الفئات (classes) اللازمة في Java. يبقى هذا المقتطف كما هو في الدرس الأصلي:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

### الخطوة 1: تعيين دليل المستند وتدفق الإدخال
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
هنا نوجه الشيفرة إلى المجلد الذي يحتوي على ملف EPS المصدر ونفتح تدفقاً لقراءته.

### الخطوة 2: تهيئة كائن PsDocument
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
فئة `PsDocument` تمثل مستند EPS في الذاكرة، مما يسمح لنا بالاستعلام عن خصائصه وتعديلها.

### الخطوة 3: استخراج صندوق الحدّ الأصلي
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
استخراج صندوق الحدّ الأصلي يمنحك إحداثيات المنطقة المرئية الحالية – مفيد لتحديد مقدار القص الذي تحتاجه.

### الخطوة 4: إنشاء تدفق الإخراج
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
نفتح تدفقاً حيث سيُكتب ملف EPS المقصوص.

### الخطوة 5: تعريف صندوق حدّ جديد والقص
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
قدّم الإحداثيات الأربعة (x السفلية اليسرى، y السفلية اليسرى، x العليا اليمنى، y العليا اليمنى) التي تحدد المنطقة التي تريد الاحتفاظ بها. تقوم طريقة `cropEps` بتنفيذ القص وتكتب النتيجة إلى `output_crop.eps`.

## المشكلات الشائعة والحلول
- **إحداثيات غير صحيحة:** يستخدم EPS النقاط (1/72 بوصة). إذا كان القص غير دقيق، تحقق من تحويل الوحدات.  
- **أخطاء ملف غير موجود:** تأكد من أن `dataDir` ينتهي بفاصل المسار المناسب (`/` أو `\`).  
- **استثناءات الترخيص:** تشغيل الشيفرة بدون ترخيص صالح قد يضيف علامة مائية إلى الناتج. طبّق ترخيصك المؤقت أو الدائم قبل الاستخدام في الإنتاج.

## الأسئلة المتكررة

**س: هل Aspose.Page متوافق مع Java 8؟**  
ج: نعم، Aspose.Page يعمل مع Java 8 وأي إصدار لاحق.

**س: هل يمكنني استخدام Aspose.Page في مشاريع تجارية؟**  
ج: بالتأكيد. الترخيص التجاري مطلوب للنشر في بيئات الإنتاج. يمكنك الحصول على ترخيص [هنا](https://purchase.aspose.com/buy).

**س: أين يمكنني العثور على موارد إضافية ودعم المجتمع؟**  
ج: زر منتدى Aspose.Page الرسمي [هنا](https://forum.aspose.com/c/page/39) للمناقشات، عينات الشيفرة، ونصائح حل المشكلات.

**س: هل هناك نسخة تجريبية مجانية للاختبار؟**  
ج: نعم، يمكنك تحميل نسخة تجريبية مجانية من Aspose.Page من صفحة الإصدارات [هنا](https://releases.aspose.com/).

**س: كيف أحصل على ترخيص مؤقت للتقييم قصير المدة؟**  
ج: يمكن طلب ترخيص مؤقت من بوابة الترخيص [هنا](https://purchase.aspose.com/temporary-license/).

## الخلاصة
أنت الآن تعرف **كيفية قص eps** في Java باستخدام Aspose.Page. عبر تعريف صندوق حدّ مخصص واستدعاء `cropEps`، يمكنك قص الهوامش غير المرغوبة أو عزل أجزاء محددة من رسمة EPS ببضع أسطر من الشيفرة فقط. دمج هذا المقتطف في خطوط معالجة المستندات الأكبر سيساعدك على أتمتة تعديل EPS والحفاظ على أصولك البصرية مرتبة.

---

**آخر تحديث:** 2025-11-30  
**تم الاختبار مع:** Aspose.Page for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}