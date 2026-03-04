---
date: 2025-12-23
description: تعلم كيفية تحويل XPS إلى PDF في Java باستخدام Aspose.Page. يوضح هذا الدليل
  خطوةً بخطوة عملية التحويل، وكيفية إنشاء PDF من XPS وتحديد أرقام صفحات PDF.
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: كيفية تحويل XPS إلى PDF في جافا
url: /ar/java/xps-conversion/to-pdf/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحويل XPS إلى PDF في جافا

## كيفية تحويل XPS إلى PDF في جافا
في مجال تطوير جافا، **كيفية تحويل XPS إلى PDF** هو سؤال شائع. سواء كنت تبني نظام إدارة مستندات أو تحتاج إلى إنشاء تقارير قابلة للطباعة، فإن تحويل ملفات XPS بشكل موثوق يمكن أن يكون نقطة تحول. لحسن الحظ، Aspose.Page for Java يجعل من السهل **إنشاء PDF من XPS** ببضع أسطر من الشيفرة.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع التحويل؟** Aspose.Page for Java.
- **كم من الوقت تستغرق عملية التنفيذ؟** تقريبًا 10‑15 دقيقة لإعداد أساسي.
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص مطلوب للإنتاج.
- **هل يمكنني تحويل صفحات محددة فقط؟** نعم – استخدم خيار *تحديد أرقام صفحات PDF*.
- **هل التحويل بدون فقدان؟** المكتبة تحافظ على الرسومات المتجهة ودقة النص.

## ما هو تحويل XPS إلى PDF؟
XPS (XML Paper Specification) هو تنسيق المستند الثابت الخاص بمايكروسوفت. تحويله إلى PDF يتيح لك مشاركة المستندات أو طباعتها أو أرشفتها باستخدام معيار PDF المقبول عالميًا.

## لماذا تستخدم Aspose.Page for Java لإنشاء PDF من XPS؟
- **دقة عالية** – يحتفظ بالرسومات المتجهة، الخطوط، والتخطيط.
- **تحكم دقيق** – يمكنك ضبط جودة الصورة، الضغط، وحتى اختيار صفحات محددة.
- **بدون تبعيات خارجية** – جافا صافية، تعمل على أي منصة تدعم JDK.

## المتطلبات المسبقة
قبل البدء، تأكد من توفر ما يلي:

- **Java Development Kit (JDK)** – أي نسخة حديثة (يوصى بالإصدار 8 أو أعلى).
- **Aspose.Page for Java** – قم بتنزيل المكتبة من [التوثيق](https://reference.aspose.com/page/java/).
- ملف XPS تريد تحويله.

## استيراد الحزم
في مشروع جافا الخاص بك، استورد الحزم المطلوبة للعمل مع Aspose.Page for Java. هذه الخطوة حاسمة للوصول إلى الوظائف اللازمة لتحويل XPS إلى PDF.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## دليل خطوة بخطوة

### الخطوة 1: تعيين دليل المستند
حدد المسار إلى المجلد الذي يحتوي على ملف XPS المصدر.

```java
String dataDir = "Your Document Directory";
```

### الخطوة 2: تهيئة تدفق إخراج PDF
أنشئ `FileOutputStream` سيستقبل ملف PDF المُولد.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

### الخطوة 3: تحميل مستند XPS
حمّل ملف XPS باستخدام Aspose.Page.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### الخطوة 4: تهيئة خيارات حفظ PDF  
أنشئ خيارات للتحويل. هنا يمكنك **تحديد أرقام صفحات PDF**، ضبط جودة الصورة، وتعيين الضغط.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### الخطوة 5: إنشاء جهاز عرض PDF  
قم بإعداد جهاز عرض سيكتب مخرجات PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### الخطوة 6: حفظ المستند  
أخيرًا، احفظ مستند XPS كملف PDF باستخدام الخيارات والجهاز الذي قمت بتكوينه.

```java
document.save(device, options);
```

كرر هذه الخطوات، مع تعديل مسارات الملفات والخيارات وفقًا لسيناريوك المحدد.

## كيفية تحديد أرقام صفحات PDF عند تحويل XPS
إذا كنت تحتاج فقط إلى مجموعة فرعية من الصفحات من XPS الأصلي، قم بملء مصفوفة `setPageNumbers` بأرقام الصفحات المطلوبة (بدءًا من 1). هذا يساعد على تقليل حجم الملف ووقت المعالجة.

## المشكلات الشائعة وإصلاح الأخطاء
- **FileNotFoundException** – تحقق من أن `dataDir` يشير إلى المجلد الصحيح وأن اسم ملف XPS مطابق.
- **LicenseException** – يلزم وجود ترخيص Aspose.Page صالح للاستخدام في الإنتاج؛ وإلا فإن المكتبة تعمل في وضع التقييم مع علامة مائية.
- **جودة صورة منخفضة** – زد `setJpegQualityLevel` أو انتقل إلى ضغط بدون فقد إذا لزم الأمر.

## الأسئلة المتكررة
### هل يمكنني تحويل ملفات XPS متعددة الصفحات باستخدام Aspose.Page for Java؟
نعم، يمكنك **تحديد أرقام صفحات PDF** في `PdfSaveOptions` (انظر الخطوة 4) لتضمين أي صفحات تحتاجها.

### أين يمكنني العثور على دعم إضافي أو مناقشة استفسارات متعلقة بـ Aspose.Page؟
زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع والمناقشات.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Page for Java؟
نعم، يمكنك استكشاف الميزات عبر [نسخة تجريبية مجانية](https://releases.aspose.com/).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟
زر [هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على تفاصيل الترخيص المؤقت.

### أين يمكنني شراء ترخيص Aspose.Page for Java؟
يمكنك شراء الترخيص [هنا](https://purchase.aspose.com/buy).

**آخر تحديث:** 2025-12-23  
**تم الاختبار مع:** Aspose.Page for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}