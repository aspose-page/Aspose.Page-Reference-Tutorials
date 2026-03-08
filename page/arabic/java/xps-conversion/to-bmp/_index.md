---
date: 2026-03-08
description: تعلم كيفية تحويل XPS إلى BMP في Java وتعيين دقة BMP باستخدام مكتبة Aspose.Page
  لتحويل الصور في Java. يغطي هذا الدليل إخراجًا عالي الجودة ونصائح صديقة للذاكرة.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: تحويل XPS إلى BMP في Java – ضبط الدقة لإنتاج عالي الجودة
url: /ar/java/xps-conversion/to-bmp/
weight: 10
---

-backtop-button >}}

Make sure to keep all shortcodes unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل XPS إلى BMP في Java

## المقدمة
مرحبًا بك في هذا الدليل خطوة بخطوة حول كيفية **تحويل XPS إلى BMP** في Java وتعيين الدقة للحصول على جودة صورة مثالية باستخدام Aspose.Page. سواءً كنت تبني خط طباعة، أو تُنشئ صورًا مصغرة، أو تحتاج إلى رسومات عالية الدقة، فإن التحكم في DPI يمنحك المرونة لتلبية أي متطلب.

## إجابات سريعة
- **ما المكتبة التي يجب أن أستخدمها؟** Aspose.Page for Java هي أكثر مكتبة **java image conversion library** اكتمالًا لتحويل XPS → BMP.  
- **هل يمكنني التحكم في جودة الصورة؟** نعم – استخدم `BmpSaveOptions` لت **تعيين دقة BMP** ووضعية التنعيم.  
- **كيف أتجنب خطأ OutOfMemoryError في Java عند معالجة ملفات XPS الكبيرة؟** قم بتقسيم الصفحات إلى أقسام أو زد حجم ذاكرة JVM (`-Xmx`).  
- **هل أحتاج إلى تحويل صفحات محددة فقط؟** بالتأكيد، `options.setPageNumbers()` يتيح لك اختيار الصفحات المحددة.  
- **ما إصدارات Java المدعومة؟** جميع إصدارات Java الحديثة (8 وما فوق) تعمل بسلاسة.

## ما هو هدف تعيين الدقة؟
تحدد الدقة عدد النقاط في البوصة (DPI) في صورة BMP المُولدة. كلما ارتفعت قيمة DPI، زادت حدة الصور، وهو أمر أساسي للطباعة أو الأعمال الرسومية التفصيلية. تعديل الدقة يمنحك سيطرة كاملة على جودة المخرجات في سير عمل **convert xps to bmp** الخاص بك.

## لماذا تستخدم Aspose.Page لتحويل XPS → BMP؟
- **دقة عالية** – يحافظ على جودة المتجهات الأصلية في XPS.  
- **تحكم دقيق** – يمكنك تعيين DPI، والتنعيم، وحتى اختيار صفحات محددة للتحويل.  
- **بدون تبعيات خارجية** – جافا صافية، لا تحتاج إلى مكتبات أصلية.  
- **قابل للتوسع** – يعمل مع مستندات صفحة واحدة وكذلك ملفات XPS متعددة الصفحات الكبيرة.  

## المتطلبات المسبقة
قبل الغوص في عملية التحويل، تأكد من توفر المتطلبات التالية:
- **بيئة تطوير Java** – Java 8 أو أحدث مثبتة على جهازك.  
- **مكتبة Aspose.Page for Java** – قم بتنزيل وإدراج مكتبة Aspose.Page for Java في مشروعك. يمكنك العثور على المكتبة [هنا](https://releases.aspose.com/page/java/).  
- **ملف XPS تجريبي** – حضّر مستند XPS تجريبي تريد تحويله إلى BMP.

## استيراد الحزم
قم بتضمين حزم Aspose.Page اللازمة في كود Java الخاص بك:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## كيفية تعيين الدقة لتحويل XPS إلى BMP
فيما يلي دليل مختصر مرقم يوضح بالضبط أين وكيفية تعيين الدقة، بالإضافة إلى كيفية **تحويل صفحات محددة**.

### الخطوة 1: تحميل مستند XPS
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### الخطوة 2: تهيئة الخيارات (الدقة واختيار الصفحات)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### الخطوة 3: إنشاء جهاز العرض
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### الخطوة 4: حفظ المستند باستخدام الخيارات
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### الخطوة 5: التكرار عبر الصور المرسومة وكتابة الملفات
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

كرر هذه الخطوات لأي تخصيص أو تعديل إضافي قد تحتاجه في عملية التحويل.

## كيفية تجنب OutOfMemoryError في Java عند تحويل ملفات XPS الكبيرة
- **معالجة في أقسام** – المثال بالفعل يرسم المستند في أقسام (`device.getResult()`)، مما يقلل من ضغط الذاكرة.  
- **زيادة مساحة heap في JVM** – استخدم علامة `-Xmx` (مثال: `-Xmx2g`) لتخصيص المزيد من الذاكرة للمستندات الكبيرة.  
- **تحرير الموارد** – استدعِ `document.close()` عند الانتهاء لتحرير الموارد الأصلية.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **إخراج BMP منخفض الجودة** | تحقق من أن `options.setResolution()` مضبوطة على قيمة ≥ 300 DPI. |
| **تحويل جزء فقط من المستند** | تأكد من أن `options.setPageNumbers()` تشمل جميع فهارس الصفحات المطلوبة. |
| **OutOfMemoryError في ملفات XPS الكبيرة** | عالج المستند في أقسام أصغر أو زد حجم heap في JVM (`-Xmx`). |
| **الملف غير موجود** | تحقق مرة أخرى من مسار `dataDir` وأن ملف XPS المدخل موجود. |

## الأسئلة المتكررة
### س: هل يمكنني تخصيص دقة صور BMP؟
نعم، يمكنك تعديل الدقة عن طريق تعديل معامل `options.setResolution()` في الكود.

### س: هل Aspose.Page متوافق مع إصدارات Java المختلفة؟
نعم، Aspose.Page يدعم مجموعة واسعة من إصدارات Java. تأكد من تثبيت نسخة متوافقة.

### س: كيف يمكنني تحويل ملفات XPS من نطاق صفحات محدد؟
استخدم طريقة `options.setPageNumbers()` لتحديد أرقام الصفحات التي تريد تحويلها.

### س: هل هناك صيغ إخراج أخرى يدعمها Aspose.Page؟
نعم، Aspose.Page يدعم صيغ إخراج متعددة. راجع الوثائق للحصول على قائمة شاملة.

### س: أين يمكنني العثور على مساعدة أو دعم إضافي؟
قم بزيارة [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع والنقاشات.

---

**آخر تحديث:** 2026-03-08  
**تم الاختبار مع:** Aspose.Page for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}