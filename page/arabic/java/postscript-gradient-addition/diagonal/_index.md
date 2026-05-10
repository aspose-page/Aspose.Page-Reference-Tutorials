---
date: 2026-02-13
description: عزز مستندات Java PostScript الخاصة بك باستخدام التدرجات القطرية عبر Aspose.Page
  Java. تعلم كيفية إضافة تأثيرات التدرج باستخدام LinearGradientPaint في Java وإنشاء
  انتقالات ألوان حيوية بسهولة.
linktitle: 'How to Add Gradient: Diagonal Gradient in Java PostScript using Aspose.Page
  Java'
second_title: Aspose.Page Java API
title: 'كيفية إضافة تدرج: تدرج قطري في Java PostScript باستخدام Aspose.Page Java'
url: /ar/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة تدرج قطري في Java PostScript باستخدام Aspose.Page Java

## مقدمة
إذا كنت ترغب في إثراء ملف PostScript بتدرج لوني قطري سلس، فإن **Aspose.Page Java** يجعل ذلك سهلًا بشكل مفاجئ. في هذا الدرس سنستعرض **كيفية إضافة التدرج** خطوة بخطوة، باستخدام الفئة `LinearGradientPaint` من Java 2D. في النهاية ستحصل على مقطع جاهز للتنفيذ ينشئ مستند PostScript بتدرج قطري نابض بالحياة.

## كيفية إضافة التدرج في Java PostScript
قد يبدو إضافة تدرج مهمة تتعلق بالرسومات فقط، ولكن مع Aspose.Page تحصل على تحكم كامل في أوامر PostScript الأساسية مع البقاء في Java النقية. يشرح هذا القسم لماذا تعمل هذه الطريقة وما الذي ستحصل عليه مقارنةً بكتابة PostScript يدوياً.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java.  
- **أي فئة تنشئ التدرج؟** `LinearGradientPaint`.  
- **هل يمكنني تغيير الألوان؟** نعم – عدل مصفوفة `Color[]`.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يتطلب ترخيص تجاري؛ يتوفر نسخة تجريبية مجانية.  
- **كم من الوقت تستغرق التنفيذ؟** حوالي 10 دقائق لتدرج أساسي.

## ما هو Aspose.Page Java؟
Aspose.Page Java هو API قوي يتيح للمطورين إنشاء وتعديل وتحويل ملفات PostScript وPDF دون الحاجة إلى أي برنامج خارجي. يتيح كامل قدرات الرسومات في لغة PostScript من خلال واجهة Java نظيفة وموجهة للكائنات.

## لماذا نستخدم تدرجًا قطريًا؟
يضيف التدرج القطري عمقًا وجاذبية بصرية للمخططات، اللافتات، أو أي عنصر رسومي يحتاج إلى مظهر حديث. نظرًا لأن التدرج يمتد من زاوية إلى الزاوية المقابلة، فهو يعمل بشكل جيد للخلفيات، وتغليف الأزرار، والأشكال الزخرفية.

## المتطلبات المسبقة
- مجموعة تطوير Java (JDK) 8 أو أعلى.  
- بيئة تطوير متكاملة مثل Eclipse أو IntelliJ IDEA أو VS Code.  
- **Aspose.Page for Java** library – حمّل أحدث نسخة من [صفحة التحميل الرسمية](https://releases.aspose.com/page/java/).

## استيراد الحزم
أولاً، استورد حزم Java 2D وAspose التي ستحتاجها. هذه الاستيرادات تمنحك الوصول إلى تعريفات الألوان، الأشكال الهندسية، رسم التدرج، وAPI مستندات PostScript.

```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## الخطوة 1: إنشاء تدفق إخراج لمستند PostScript
نبدأ بتحديد المجلد الذي سيُحفظ فيه الملف وفتح `FileOutputStream`. سيستقبل هذا التدفق بيانات PostScript التي تم إنشاؤها.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## الخطوة 2: إنشاء خيارات الحفظ بحجم A4
`PsSaveOptions` يتيح لك تحديد حجم الصفحة، الدقة، وإعدادات الإخراج الأخرى. هنا نستخدم الحجم الافتراضي A4.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## الخطوة 3: إنشاء مستند PS جديد
أنشئ كائن `PsDocument` باستخدام تدفق الإخراج وخيارات الحفظ. علم `false` يخبر المُنشئ بعدم فتح صفحة جديدة تلقائيًا – سنقوم بذلك لاحقًا.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 4: إنشاء مستطيل
حدد المستطيل الذي سيتلقى تعبئة التدرج. تم اختيار موضع المستطيل (200, 100) وحجمه (200 × 100) لجعل التدرج واضحًا.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## الخطوة 5: إنشاء تحويل التدرج
`AffineTransform` يتيح لنا تدوير، تحجيم، وإزاحة التدرج بحيث يمتد قطريًا عبر المستطيل. الحسابات أدناه تحسب الوتر وتضبط نسبة التحجيم وفقًا لذلك.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## الخطوة 6: إنشاء تدرج خطي قطري
هذا هو جوهر **كيفية إضافة التدرج** – نقوم بإنشاء `LinearGradientPaint` يمتد من أعلى اليسار إلى أسفل اليمين للمستطيل، باستخدام التحويل المعرّف مسبقًا. يضمن `MultipleGradientPaint.CycleMethod.NO_CYCLE` عدم تكرار التدرج.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## الخطوة 7: تعيين اللون وتعبئة المستطيل
طبق لون التدرج على المستند واملأ شكل المستطيل. هذه الخطوة تُظهر الانتقال اللوني القطري على صفحة PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## الخطوة 8: إغلاق الصفحة الحالية وحفظ المستند
أخيرًا، أغلق الصفحة، أفرغ التدفق، واحفظ الملف. يمكن فتح الملف الناتج `DiagonalGradient_outPS.ps` بأي عارض PostScript.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## مشكلات شائعة ونصائح
- **التدرج يبدو مسطحًا** – تحقق مرة أخرى من زاوية الدوران؛ دوران 45° يخلق تدرجًا قطريًا حقيقيًا.  
- **الألوان تبدو باهتة** – تأكد من استخدام `MultipleGradientPaint.ColorSpaceType.SRGB` للحصول على تمثيل لوني دقيق.  
- **خطأ ملف غير موجود** – تحقق من أن `dataDir` يشير إلى مجلد موجود وأن التطبيق يمتلك أذونات كتابة.

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذه المكتبة لعمليات رسومية أخرى في Java؟**  
ج: نعم، توفر Aspose.Page for Java مجموعة كاملة من بدائل الرسم، عرض النص، وقدرات معالجة الصور.

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Page Java؟**  
ج: بالتأكيد. يمكنك تنزيل نسخة تجريبية كاملة الوظائف من [صفحة التجربة المجانية لـ Aspose](https://releases.aspose.com/).

**س: أين يمكنني العثور على وثائق Aspose.Page Java؟**  
ج: المرجع الرسمي للـ API متاح [هنا](https://reference.aspose.com/page/java/).

**س: كيف يمكنني شراء ترخيص لـ Aspose.Page Java؟**  
ج: يمكن شراء التراخيص مباشرة من [بوابة شراء Aspose](https://purchase.aspose.com/buy).

**س: هل تحتاج إلى مساعدة أو لديك أسئلة؟**  
ج: زر منتدى [Aspose.Page المجتمعي](https://forum.aspose.com/c/page/39) للحصول على مساعدة من مهندسي Aspose والزملاء المطورين.

---

**آخر تحديث:** 2026-02-13  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}