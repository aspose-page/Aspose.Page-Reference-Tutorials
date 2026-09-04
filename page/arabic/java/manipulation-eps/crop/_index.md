---
date: 2026-09-04
description: تعلم كيفية تقليل حجم ملف EPS عن طريق قص ملفات EPS في Java باستخدام Aspose.Page
  – دليل خطوة بخطوة يوضح كيفية قص EPS، قص صورة EPS وتقليم ملف EPS.
keywords:
- reduce eps file size
- how to crop eps
- Aspose.Page Java
- EPS cropping Java
lastmod: 2026-09-04
linktitle: قص ملف EPS في Java
og_description: تعلم كيفية تقليل حجم ملف EPS عن طريق قص ملفات EPS في Java باستخدام
  Aspose.Page – دليل سريع يحتوي على الشيفرة والنصائح.
og_image_alt: 'Guide: cropping EPS files in Java to reduce file size with Aspose.Page'
og_title: كيفية قص ملفات EPS في Java لتقليل حجم ملف EPS
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  headline: How to crop EPS files in Java to reduce EPS file size
  type: TechArticle
- description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  name: How to crop EPS files in Java to reduce EPS file size
  steps:
  - name: set document directory and input stream
    text: Here we point the code to the folder that holds our source EPS file and
      open a stream for reading it.
  - name: initialize PsDocument object
    text: The `PsDocument` class represents an EPS file in memory, allowing you to
      read and modify its properties. The object gives you access to the original
      bounding box and other metadata.
  - name: extract initial bounding box
    text: Extracting the original bounding box gives you the coordinates of the current
      visible area – handy for deciding how much you need to trim.
  - name: create output stream
    text: We open a stream where the cropped EPS will be written.
  - name: define new bounding box and crop
    text: The `cropEps` method trims the document to a new bounding box and writes
      the result to an output stream. Provide the four coordinates (lower‑left x,
      lower‑left y, upper‑right x, upper‑right y) that define the area you want to
      keep. The method performs the cropping and writes the result to `output_cr
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works with Java 8 and any later version.
    question: Is Aspose.Page compatible with Java 8?
  - answer: Absolutely. A commercial license is required for production deployments.
      You can obtain one [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: Visit the official [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for discussions, code samples, and troubleshooting tips.
    question: Where can I find additional resources and community support?
  - answer: Yes, you can download a free trial of Aspose.Page from the releases page
      [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is there a free trial available for testing?
  - answer: A temporary license can be requested from the licensing portal [temporary
      license request page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for short‑term evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- reduce eps file size
- Aspose.Page
- Java EPS processing
- crop EPS
title: كيفية قص ملفات EPS في Java لتقليل حجم ملف EPS
url: /ar/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قص ملفات EPS في Java لتقليل حجم ملف EPS

## مقدمة
إذا كنت بحاجة إلى **قص ملفات EPS** برمجياً في تطبيق Java وتريد **تقليل حجم ملف EPS**، فقد وصلت إلى المكان الصحيح. في هذا الدليل سنستعرض العملية بالكامل لقص صورة EPS باستخدام مكتبة Aspose.Page for Java القوية. بحلول نهاية الدليل ستفهم لماذا يعتبر قص EPS مهمًا، وسترى الشيفرة الدقيقة التي تحتاجها، وستكون جاهزًا لدمج الحل في مشاريعك الخاصة.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع قص EPS في Java؟** Aspose.Page for Java.  
- **كم من الوقت يستغرق تنفيذ قص أساسي؟** تقريبًا 5‑10 دقائق.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للتقييم؛ يلزم ترخيص تجاري للإنتاج.  
- **ما إصدارات Java المدعومة؟** Java 8 وما فوق.  
- **هل يمكنني تعريف أي صندوق حدود مخصص؟** نعم – تقوم بتوفير الإحداثيات التي تحتاجها.

## ما هو قص EPS ولماذا نستخدمه؟
**إن قص EPS ينشئ صندوق حدود جديد يحدد المنطقة المرئية لملف EPS.**  
يقوم قص ملف EPS بإزالة المساحات البيضاء غير المرغوب فيها وتقليم الرسم إلى المنطقة التي تحتاجها فعليًا، مما يؤدي مباشرةً إلى **تقليل حجم ملف EPS** وتحسين اتساق التخطيط في المستندات اللاحقة مثل PDFs أو التقارير.

## لماذا قص ملفات EPS؟
يسمح لك قص ملفات EPS **بتقليل حجم الملف بنسبة تصل إلى 30 %**، وإزالة الهوامش الزائدة، وتوحيد الرسومات لخطوط معالجة الدفعات. يكون ذلك مفيدًا بشكل خاص عندما تحتاج إلى تضمين العديد من موارد EPS في ملف PDF واحد أو عندما تريد تسريع العرض على الأجهزة منخفضة الطاقة.

## المتطلبات المسبقة
قبل أن نغوص في الشيفرة، تأكد من أنك تمتلك:

- **Aspose.Page for Java** مكتبة مثبتة – قم بتحميلها من الصفحة الرسمية [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** 8 أو أحدث مثبت على جهازك.  
- **مجلد** لتخزين ملف EPS الإدخالي (`input.eps`) والملف المقصوص الناتج (`output_crop.eps`).

## استيراد الحزم
First, import the necessary Java classes. This snippet stays exactly the same as in the original tutorial:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

## كيفية قص صورة EPS في Java
حمّل ملف EPS المصدر، حدد صندوق حدود جديد، واستدعِ واجهة برمجة التطبيقات للقص – تُنجز العملية بالكامل في خمس خطوات مختصرة.

### الخطوة 1: تعيين دليل المستند وتدفق الإدخال
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
هنا نوجه الشيفرة إلى المجلد الذي يحتوي على ملف EPS المصدر ونفتح تدفقًا لقراءته.

### الخطوة 2: تهيئة كائن PsDocument
فئة `PsDocument` تمثل ملف EPS في الذاكرة، مما يتيح لك قراءة وتعديل خصائصه.  
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
يوفر لك الكائن الوصول إلى صندوق الحدود الأصلي وبيانات التعريف الأخرى.

### الخطوة 3: استخراج صندوق الحدود الأولي
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
استخراج صندوق الحدود الأصلي يمنحك إحداثيات المنطقة المرئية الحالية – وهو مفيد لتحديد مقدار القص المطلوب.

### الخطوة 4: إنشاء تدفق الإخراج
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
نفتح تدفقًا حيث سيتم كتابة ملف EPS المقصوص.

### الخطوة 5: تحديد صندوق حدود جديد والقص
طريقة `cropEps` تقص المستند إلى صندوق حدود جديد وتكتب النتيجة إلى تدفق الإخراج.  
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
قدّم الإحداثيات الأربعة (x السفلية‑اليسرى، y السفلية‑اليسرى، x العليا‑اليمنى، y العليا‑اليمنى) التي تحدد المنطقة التي تريد الاحتفاظ بها. تقوم الطريقة بتنفيذ القص وتكتب النتيجة إلى `output_crop.eps`.

## المشكلات الشائعة والحلول
- **إحداثيات غير صحيحة:** يستخدم EPS النقاط (1/72 بوصة). إذا كان القص غير دقيق، تحقق مرة أخرى من تحويل الوحدات.  
- **خطأ ملف غير موجود:** تأكد من أن `dataDir` ينتهي بفاصل المسار المناسب (`/` أو `\`).  
- **استثناءات الترخيص:** تشغيل الشيفرة بدون ترخيص صالح قد يضيف علامة مائية إلى الناتج. طبّق ترخيصك المؤقت أو الدائم قبل الاستخدام في الإنتاج.

## الأسئلة المتكررة

**س: هل Aspose.Page متوافق مع Java 8؟**  
ج: نعم، Aspose.Page يعمل مع Java 8 وأي إصدار لاحق.

**س: هل يمكنني استخدام Aspose.Page في المشاريع التجارية؟**  
ج: بالتأكيد. يلزم ترخيص تجاري للنشر في بيئات الإنتاج. يمكنك الحصول على واحد عبر [Aspose purchase page](https://purchase.aspose.com/buy).

**س: أين يمكنني العثور على موارد إضافية ودعم المجتمع؟**  
ج: زر المنتدى الرسمي لـ [Aspose.Page forum](https://forum.aspose.com/c/page/39) للمناقشات، عينات الشيفرة، ونصائح حل المشكلات.

**س: هل هناك نسخة تجريبية مجانية متاحة للاختبار؟**  
ج: نعم، يمكنك تحميل نسخة تجريبية مجانية من Aspose.Page من صفحة الإصدارات [Aspose.Page releases page](https://releases.aspose.com/).

**س: كيف أحصل على ترخيص مؤقت للتقييم قصير الأجل؟**  
ج: يمكن طلب ترخيص مؤقت من بوابة الترخيص عبر [temporary license request page](https://purchase.aspose.com/temporary-license/).

## الخلاصة
أنت الآن تعرف **كيفية قص ملفات EPS** في Java باستخدام Aspose.Page لت **تقليل حجم ملف EPS**. من خلال تعريف صندوق حدود مخصص واستدعاء `cropEps`، يمكنك قص الهوامش غير المرغوب فيها أو عزل أجزاء محددة من رسم EPS ببضع أسطر من الشيفرة فقط. دمج هذا المقتطف في خطوط معالجة المستندات الأكبر لت automatisation معالجة EPS، **قص صور EPS**، و **تقليم محتوى ملف EPS** بفعالية.

---

**Last Updated:** 2026-09-04  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## دروس ذات صلة

- [كيفية تغيير حجم ملفات EPS في Java باستخدام Aspose.Page](/page/java/manipulation-eps/resize/)
- [تحويل EPS إلى PNG باستخدام Aspose.Page Java (ترخيص مقنن)](/page/java/license-management/set-metered-license/)
- [دروس Aspose Page Java – إضافة بيانات XMP الوصفية إلى ملفات EPS](/page/java/xmp-metadata-manipulation/add-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}