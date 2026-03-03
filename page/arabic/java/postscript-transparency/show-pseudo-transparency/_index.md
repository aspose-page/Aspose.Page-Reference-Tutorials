---
date: 2025-12-17
description: تعلم كيفية إنشاء شفافية شبه في Java باستخدام Aspose.Page. اتبع دليلنا
  خطوة بخطوة لإضافة رسومات حيوية في ملفات PostScript.
linktitle: Show Pseudo-Transparency in Java PostScript
second_title: Aspose.Page Java API
title: كيفية إنشاء شفافية شبه في جافا باستخدام Aspose.Page
url: /ar/java/postscript-transparency/show-pseudo-transparency/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# الشفافية الزائفة في Java PostScript باستخدام Aspose.Page

## المقدمة
في هذا الدرس الشامل ستقوم **بإنشاء رسومات شفافية زائفة في Java** باستخدام Aspose.Page for Java. سنستعرض كل خطوة — من إعداد البيئة إلى رسم مستطيلين متداخلين يعطيان وهم الشفافية في ملف PostScript. في النهاية، ستفهم لماذا تُعد الشفافية الزائفة مفيدة، وكيفية تنفيذها، وكيفية تعديل المعلمات لتصاميمك الخاصة.

## إجابات سريعة
- **ماذا يعني مصطلح الشفافية الزائفة؟** يحاكي الشفافية عن طريق دمج تدرجات شبه شفافة.
- **ما المكتبة المطلوبة؟** Aspose.Page for Java.
- **هل أحتاج إلى ترخيص لتشغيل المثال؟** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.
- **ما بيئة التطوير المتكاملة التي يمكنني استخدامها؟** أي بيئة تطوير Java (IntelliJ IDEA، Eclipse، VS Code) تدعم Java 8+.
- **كم من الوقت تستغرق عملية التنفيذ؟** تقريبًا 10‑15 دقيقة لمثال أساسي.

## ما هي الشفافية الزائفة في Java PostScript؟
الشفافية الزائفة هي تقنية تستخدم تعبئة تدرجات شبه شفافة لإعطاء تأثير بصري لجسم يمكن رؤيته من خلاله. نظرًا لأن PostScript التقليدي لا يدعم قنوات ألفا الحقيقية، تقوم Aspose.Page بمحاكاة ذلك عن طريق تراكب أشكال شبه شفافة.

## لماذا نستخدم Aspose.Page للشفافية الزائفة؟
- **متعددة المنصات** – يولد PostScript صالح على أي نظام تشغيل.
- **بدون تبعيات خارجية** – API نقي بلغة Java.
- **تحكم دقيق** – تعديل الألوان، الشفافية، واتجاه التدرج برمجيًا.
- **نتائج متسقة** – يعمل بنفس الطريقة على الطابعات والعارضات.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود:
- معرفة أساسية بـ Java.
- إلمام بمفاهيم PostScript.
- مكتبة Aspose.Page for Java مثبتة. إذا لم تقم بتحميلها بعد، احصل عليها **[من هنا](https://releases.aspose.com/page/java/)**.
- بيئة تطوير Java أو أداة بناء (Maven/Gradle) جاهزة.

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
أولًا، ننشئ تدفق إخراج ونُهيئ كائن `PsDocument` جديد. هذا يُعد القماش الذي سنرسم عليه الأشكال.

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
نرسم المستطيل الأول باستخدام تدرج غير شفاف تمامًا. سيعمل هذا كخلفية للطبقة الشفافة الزائفة.

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
بعد ذلك، نضع مستطيلًا ثانيًا يستخدم تدرجًا بقيم ألفا. هذا يُنشئ تأثير **الشفافية الزائفة** عندما يتداخل مع الشكل الأول.

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
أخيرًا، نغلق الصفحة الحالية ونكتب ملف PostScript إلى القرص.

```java
document.closePage();
document.save();
```

## المشكلات الشائعة & استكشاف الأخطاء
- **FileNotFoundException** – تأكد من أن `dataDir` يشير إلى مجلد موجود وأن تطبيقك يملك صلاحيات الكتابة.
- **ألوان غير صحيحة** – تأكد من استخدام المُنشئ `Color(int r, int g, int b, int a)` للألوان شبه الشفافة؛ المعامل الرابع هو قيمة ألفا (0‑255).
- **التدرج غير مرئي** – تحقق من أن معلمات `AffineTransform` تُطابق التدرج بأبعاد المستطيل بشكل صحيح.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.Page for Java في المشاريع التجارية؟
نعم، Aspose.Page for Java متاح للاستخدام التجاري. يمكنك شراء ترخيص [من هنا](https://purchase.aspose.com/buy) .

### هل تتوفر نسخة تجريبية مجانية؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية [من هنا](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق إضافية؟
الوثائق التفصيلية متاحة [من هنا](https://reference.aspose.com/page/java/).

### كيف يمكنني الحصول على ترخيص مؤقت لأغراض الاختبار؟
يمكنك الحصول على ترخيص مؤقت [من هنا](https://purchase.aspose.com/temporary-license/).

### هل تحتاج مساعدة أو تريد مناقشة Aspose.Page؟
زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39).

---

**آخر تحديث:** 2025-12-17  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}