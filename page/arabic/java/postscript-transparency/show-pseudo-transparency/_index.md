---
date: 2026-05-05
description: تعلم كيفية إنشاء شفافية شبه في جافا باستخدام Aspose.Page. اتبع دليلنا
  خطوة بخطوة لإضافة رسومات زاهية في ملفات PostScript.
keywords:
- create pseudo transparency java
- Aspose.Page Java
- PostScript pseudo transparency
linktitle: إظهار الشفافية الزائفة في Java PostScript
second_title: Aspose.Page Java API
title: كيفية إنشاء شفافية زائفة في جافا باستخدام Aspose.Page
url: /ar/java/postscript-transparency/show-pseudo-transparency/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript الشفافية الزائفة مع Aspose.Page

## مقدمة
في هذا الدرس الشامل ستقوم **create pseudo transparency java** الرسومات باستخدام Aspose.Page للـ Java. سنستعرض كل خطوة — من إعداد البيئة إلى رسم مستطيلين متداخلين يعطيان وهم الشفافية في ملف PostScript. في النهاية، ستفهم لماذا الشفافية الزائفة مفيدة، وكيفية تنفيذها، وكيفية تعديل المعلمات لتصاميمك الخاصة.

## إجابات سريعة
- **What does pseudo‑transparency mean?** إنها تحاكي الشفافية عن طريق دمج تدرجات شبه شفافة.  
- **Which library is required?** Aspose.Page for Java.  
- **Do I need a license to run the example?** هل أحتاج إلى ترخيص لتشغيل المثال؟ نسخة تجريبية مجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **What IDE can I use?** ما بيئة التطوير المتكاملة التي يمكنني استخدامها؟ أي IDE للـ Java (IntelliJ IDEA، Eclipse، VS Code) يدعم Java 8+.  
- **How long does the implementation take?** كم من الوقت تستغرق العملية؟ تقريبًا 10‑15 دقيقة لمثال أساسي.  

## كيفية إنشاء pseudo transparency java باستخدام Aspose.Page
فهم “السبب” وراء كل خطوة يساعدك على تكييف التقنية مع سيناريوهات رسومية أخرى. أدناه نقسم العملية إلى مراحل واضحة وقابلة للتنفيذ حتى تتمكن من المتابعة حتى وإن كنت جديدًا في إنشاء ملفات PostScript.

## ما هي الشفافية الزائفة في Java PostScript؟
الشفافية الزائفة هي تقنية تستخدم تعبئات تدرجية شبه شفافة لتوفير التأثير البصري للأجسام الشفافة. نظرًا لأن PostScript التقليدي لا يدعم قنوات ألفا الحقيقية، تقوم Aspose.Page بمحاكاة ذلك عن طريق تراكب أشكال شبه شفافة.

## لماذا استخدام Aspose.Page للشفافية الزائفة؟
- **Cross‑platform** – يولد PostScript صالح على أي نظام تشغيل.  
- **No external dependencies** – API جافا نقي.  
- **Fine‑grained control** – تعديل الألوان، الشفافية، واتجاه التدرج برمجيًا.  
- **Consistent output** – يعمل بنفس الشكل عبر الطابعات وعارضات الملفات.  

## المتطلبات المسبقة
قبل الغوص في التفاصيل، تأكد من أن لديك:
- معرفة أساسية بـ Java.  
- إلمام بمفاهيم PostScript.  
- مكتبة Aspose.Page للـ Java مثبتة. إذا لم تقم بتنزيلها بعد، احصل عليها **[here](https://releases.aspose.com/page/java/)**.  
- بيئة تطوير Java IDE أو أداة بناء (Maven/Gradle) جاهزة.  

## استيراد الحزم
ابدأ باستيراد الفئات الضرورية لتتمكن من العمل مع الألوان، التدرجات، وكائن وثيقة PostScript.

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

## الخطوة 1: إنشاء مستند PS
أولاً، نقوم بإنشاء تدفق إخراج ونُهيئ كائن `PsDocument` جديد. هذا يُعد القماش الذي سنرسم عليه الأشكال.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "ShowPseudoTransparency_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 2: تعريف مستطيل بتعبئة تدرج غير شفاف
نرسم المستطيل الأول باستخدام تدرج غير شفاف بالكامل. سيعمل هذا كخلفية للطبقة الشفافة الزائفة.

```java
float offsetX = 50;
float offsetY = 100;
float width = 200;
float height = 100;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create opaque gradient fill
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0), new Color(40, 128, 70)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## الخطوة 3: تعريف مستطيل بتعبئة تدرج شبه شفاف
بعد ذلك، نضع مستطيلًا ثانيًا يستخدم تدرجًا بقيم ألفا. هذا يخلق تأثير **pseudo transparency** عندما يتداخل مع الشكل الأول.

```java
offsetX = 350;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create translucent gradient fill
paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## الخطوة 4: إغلاق الصفحة وحفظ المستند
أخيرًا، نقوم بإغلاق الصفحة الحالية وكتابة ملف PostScript إلى القرص.

```java
document.closePage();
document.save();
```

## المشكلات الشائعة وإصلاح الأخطاء
- **FileNotFoundException** – تحقق من أن `dataDir` يشير إلى مجلد موجود وأن تطبيقك يمتلك صلاحيات الكتابة.  
- **Incorrect colors** – تأكد من استخدام المُنشئ `Color(int r, int g, int b, int a)` للألوان شبه الشفافة؛ المعامل الرابع هو قيمة الألفا (0‑255).  
- **Gradient not visible** – تحقق من أن معلمات `AffineTransform` تُطابق التدرج مع أبعاد المستطيل بشكل صحيح.  

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Page للـ Java في المشاريع التجارية؟
نعم، Aspose.Page للـ Java متاح للاستخدام التجاري. يمكنك شراء ترخيص [here](https://purchase.aspose.com/buy).

### هل تتوفر نسخة تجريبية مجانية؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية [here](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق إضافية؟
توفر وثائق مفصلة [here](https://reference.aspose.com/page/java/).

### كيف يمكنني الحصول على ترخيص مؤقت لأغراض الاختبار؟
يمكنك الحصول على ترخيص مؤقت [here](https://purchase.aspose.com/temporary-license/).

### هل تحتاج إلى مساعدة أو ترغب في مناقشة Aspose.Page؟
قم بزيارة [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**آخر تحديث:** 2026-05-05  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}