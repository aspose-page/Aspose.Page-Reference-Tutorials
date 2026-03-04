---
date: 2025-12-23
description: بسهولة **حوّل XPS إلى PNG** في Java باستخدام Aspose.Page. يوضح هذا الدليل
  كيفية تحويل XPS إلى ملفات صور بحل موثوق وسهل للمطورين.
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: تحويل XPS إلى PNG في جافا
url: /ar/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل XPS إلى PNG في Java

## المقدمة
في عالم تطوير البرمجيات الديناميكي، تظهر الحاجة إلى **تحويل XPS إلى PNG** (XML Paper Specification إلى Portable Network Graphics) بشكل متكرر. لتحقيق هذه المهمة بسلاسة في Java، توفر Aspose.Page حلاً قويًا. في هذا البرنامج التعليمي، سنستعرض عملية تحويل XPS إلى PNG باستخدام Aspose.Page for Java.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع التحويل؟** Aspose.Page for Java  
- **ما الصيغ المتضمنة؟** XPS (المصدر) → PNG (الإخراج)  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم ترخيص تجاري  
- **هل يمكنني ضبط دقة الصورة؟** نعم، باستخدام `PngSaveOptions.setResolution()`  
- **هل يمكن اختيار صفحات محددة؟** بالتأكيد – قدم أرقام الصفحات في كائن الخيارات  

## لماذا تحويل XPS إلى PNG؟
إن تحويل XPS إلى ملفات صور مفيد عندما تحتاج إلى عرض المستندات على الويب، أو تضمينها في التقارير، أو إنشاء صور مصغرة للمعاينة. تقدم PNG ضغطًا غير فقداني ودعمًا واسعًا في المتصفحات، مما يجعلها خيارًا مثاليًا لتمثيلات بصرية عالية الجودة لمحتوى XPS.

## المتطلبات المسبقة
قبل الغوص في البرنامج التعليمي، تأكد من إعداد المتطلبات المسبقة التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.  
2. Aspose.Page for Java: قم بتحميل وتثبيت مكتبة Aspose.Page. يمكنك العثور على رابط التحميل [هنا](https://releases.aspose.com/page/java/).  
3. بيئة تطوير متكاملة (IDE): اختر IDE متوافق مع Java مثل IntelliJ IDEA أو Eclipse.  

## كيفية تحويل XPS إلى PNG في Java
فيما يلي دليل خطوة بخطوة يشرح **كيفية تحويل XPS** إلى صور PNG، بما في ذلك مقتطفات الشيفرة التي يمكنك نسخها مباشرةً إلى مشروعك.

### استيراد الحزم
في مشروع Java الخاص بك، استورد الحزم اللازمة لاستخدام وظائف Aspose.Page. أضف عبارات الاستيراد التالية في بداية ملف Java الخاص بك:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### الخطوة 1: تعيين دليل المستند
حدد المجلد الذي يحتوي على ملف XPS المصدر وأين سيتم حفظ ملفات PNG.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### الخطوة 2: تحميل مستند XPS
أنشئ كائن `XpsDocument` الذي يحمل ملف XPS المصدر.

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### الخطوة 3: تهيئة الخيارات
قم بتكوين خيارات إخراج PNG. هنا يمكنك ضبط التنعيم، الدقة، وتحديد الصفحات التي تريد تصييرها.

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### الخطوة 4: إنشاء جهاز التصيير
أنشئ `ImageDevice` الذي سيحتفظ ببيانات الصورة المصورة.

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### الخطوة 5: الحفظ والتكرار
قم بتصيير مستند XPS، ثم اكتب كل مصفوفة بايت PNG تم إنشاؤها إلى ملف على القرص.

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

باتباع هذه الخطوات، يمكنك بسهولة **تصيير XPS إلى ملفات صورة** بصيغة PNG باستخدام Aspose.Page for Java.

## الخلاصة
ختامًا، تُبسّط Aspose.Page for Java عملية تحويل XPS إلى PNG، مما يوفّر للمطورين أداة موثوقة وفعّالة. دمج هذه المكتبة في مشاريع Java الخاصة بك لتبسيط مهام معالجة المستندات.

## أسئلة شائعة إضافية

**س: هل يمكنني تحويل صفحات محددة فقط من ملف XPS؟**  
ج: بالتأكيد. استخدم طريقة `setPageNumbers` في `PngSaveOptions` لتحديد الصفحات التي تريد تصييرها.

**س: ما هي دقة الصورة الموصى بها للحصول على PNG عالية الجودة؟**  
ج: دقة 300 dpi تُعد توازنًا جيدًا بين الجودة وحجم الملف، ولكن يمكنك تعديلها عبر `options.setResolution()`.

**س: هل يدعم API التحويل متعدد الخيوط للمستندات الكبيرة؟**  
ج: نعم، يمكنك استدعاء منطق التحويل في خيوط متوازية، كل منها يتعامل مع صفحة مختلفة أو جزء من المستند.

**س: كيف أتعامل مع استهلاك الذاكرة عند تحويل ملفات XPS الكبيرة جدًا؟**  
ج: عالج الصفحات بشكل متسلسل وأفرج عن `FileOutputStream` بعد كل كتابة، كما هو موضح في الكود النموذجي.

**س: هل هناك طريقة لإضافة بيانات تعريف مخصصة إلى ملفات PNG المُولدة؟**  
ج: على الرغم من أن `PngSaveOptions` لا يتيح حقول بيانات تعريف مباشرة، يمكنك معالجة PNG لاحقًا باستخدام مكتبات الصور القياسية لإدراج بيانات التعريف.

**آخر تحديث:** 2025-12-23  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}