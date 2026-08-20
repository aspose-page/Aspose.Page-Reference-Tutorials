---
date: 2026-03-13
description: تعلم كيفية تحويل XPS إلى JPEG في Java باستخدام Aspose.Page Java. يوضح
  لك هذا الدليل خطوة بخطوة كيفية تحويل XPS إلى JPEG بفعالية باستخدام مكتبة Aspose.Page
  Java.
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: كيفية تحويل XPS إلى JPEG في Java باستخدام Aspose.Page Java
url: /ar/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحويل XPS إلى JPEG في Java باستخدام Aspose.Page Java

## مقدمة عن Aspose.Page Java
في هذا البرنامج التعليمي **ستتعلم كيفية تحويل XPS إلى JPEG** باستخدام مكتبة **Aspose.Page Java**. تحويل ملفات XPS إلى صور JPEG هو طلب شائع عندما تحتاج إلى عرض صفحات المستند كرسومات نقطية في بوابات الويب أو عارضات سطح المكتب أو مرفقات البريد الإلكتروني. سنستعرض كل سطر من الشيفرة، نشرح لماذا كل إعداد مهم، ونشارك نصائح عملية حتى تتمكن من دمج خط أنابيب التحويل هذا في تطبيقات Java الخاصة بك بثقة.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع التحويل؟** Aspose.Page Java  
- **هل يمكنني اختيار صفحات محددة؟** نعم – استخدم `setPageNumbers` في `JpegSaveOptions`  
- **ما جودة الصورة التي يمكنني التحكم فيها؟** وضع التنعيم، الدقة، وإعدادات جودة JPEG  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم ترخيص تجاري (يتوفر نسخة تجريبية مجانية)  
- **هل الكود متوافق مع Java 8؟** بالتأكيد – الـ API يعمل مع Java 8 والإصدارات الأحدث  

## ما هو XPS ولماذا تحويل XPS إلى JPEG؟
XPS (XML Paper Specification) هو تنسيق مستند ثابت التخطيط مشابه لـ PDF. تحويل XPS إلى JPEG مفيد عندما تحتاج إلى صور نقطية للصور المصغرة، مرفقات البريد الإلكتروني، أو عند التكامل مع أنظمة لا تقبل سوى ملفات الصور. JPEG يقدم توازنًا جيدًا بين الجودة البصرية وحجم الملف، مما يجعله مثاليًا للمعاينات على الويب.

## المتطلبات المسبقة
قبل الغوص في الشيفرة، تأكد من توفر ما يلي:

- **بيئة تطوير Java** – JDK 8 أو أحدث مثبت ومُكوَّن.  
- **Aspose.Page for Java** – قم بتنزيل أحدث مكتبة من الموقع الرسمي [here](https://releases.aspose.com/page/java/).  
- **ملف XPS تجريبي** – ملف XPS ترغب في تحويله إلى صور JPEG.  

## استيراد الحزم
ابدأ باستيراد الفئات الضرورية إلى ملف مصدر Java الخاص بك:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## الخطوة 1: تهيئة المسارات وتحميل مستند XPS
حدد الدليل الذي يحتوي على ملف XPS المصدر وأنشئ مثيلًا من `XpsDocument`:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **نصيحة احترافية:** استخدم `Paths.get()` من `java.nio.file` لمعالجة المسارات بطريقة مستقلة عن النظام الأساسي.

## الخطوة 2: تكوين خيارات حفظ JPEG
حدد كيفية تصيير صور JPEG — الدقة، التنعيم، والصفحات التي سيتم تصديرها:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` ينتج مخرجات عالية الدقة مناسبة للطباعة.  
- `setPageNumbers` يتيح لك اختيار الصفحات التي تحتاجها فقط، مما يوفر الوقت والذاكرة.

## الخطوة 3: إنشاء جهاز التصيير
`ImageDevice` يلتقط الصفحات المصورة كمصفوفات بايت:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## الخطوة 4: تصيير مستند XPS إلى JPEG
استدعِ طريقة `save`، مع تمرير الجهاز والخيارات التي قمت بتكوينها:

```java
document.save(device, options);
```

في هذه المرحلة يحتوي `device` على مصفوفة ثنائية الأبعاد حيث يمثل كل عنصر صفحة مشفرة بصيغة JPEG.

## الخطوة 5: التكرار عبر النتيجة وكتابة الملفات
قم بالتكرار عبر الصفحات المصورة واكتب كل مصفوفة بايت إلى ملف JPEG منفصل:

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

سيُسمّى كل ملف بـ `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg`، مما يسهل التعرف على المستند الأصلي ورقم الصفحة.

## حالات الاستخدام الشائعة
- **إنشاء صور مصغرة** لأنظمة إدارة المستندات.  
- **إدراج معاينات الصفحات** في تطبيقات الويب التي تدعم فقط صيغ الصور.  
- **معالجة دفعة** لأرشيفات XPS الكبيرة إلى JPEG لأغراض الأرشفة أو التقارير.  

## المشكلات الشائعة وحلولها
| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| **ملفات JPEG فارغة** | عدم تفريغ أو إغلاق تدفق الإخراج بشكل صحيح | تأكد من استدعاء `imageStream.close()` داخل الحلقة الداخلية (كما هو موضح). |
| **أخطاء نفاد الذاكرة** في ملفات XPS الكبيرة | تصيير جميع الصفحات مرة واحدة يستهلك ذاكرة RAM كثيرة | قم بمعالجة الصفحات على دفعات أصغر أو زد حجم heap للـ JVM (`-Xmx`). |
| **صفحات مفقودة** | `setPageNumbers` لا يتضمن الصفحة المطلوبة | تحقق من أن مصفوفة أرقام الصفحات تتطابق مع مؤشرات صفحات XPS الفعلية (بدءًا من 1). |

## الأسئلة المتكررة

### س: هل Aspose.Page مناسب للمشاريع التجارية؟
نعم، Aspose.Page هو منتج تجاري مع خيارات ترخيص متاحة. تحقق من [here](https://purchase.aspose.com/buy) للتفاصيل.

### س: هل يمكنني تجربة Aspose.Page قبل الشراء؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية [here](https://releases.aspose.com/).

### س: أين يمكنني العثور على وثائق Aspose.Page؟
الوثائق متاحة [here](https://reference.aspose.com/page/java/).

### س: كيف يمكنني الحصول على دعم Aspose.Page؟
قم بزيارة [Aspose.Page Forum](https://forum.aspose.com/c/page/39) للحصول على دعم من المجتمع.

### س: هل أحتاج إلى ترخيص مؤقت للاختبار؟
نعم، يمكنك الحصول على ترخيص مؤقت [here](https://purchase.aspose.com/temporary-license/).

## الخاتمة
لقد أصبحت الآن متمكنًا من **كيفية تحويل XPS إلى JPEG** باستخدام **Aspose.Page Java**. باتباع الدليل خطوة بخطوة، يمكنك دمج خط أنابيب التحويل هذا في أي تطبيق Java — سواء كان أداة سطح مكتب، خدمة ويب، أو أداة معالجة دفعات. لا تتردد في تجربة دقات مختلفة، اختيار صفحات مختلفة، وصيغ صور مختلفة لتتناسب مع احتياجات مشروعك.

---

**آخر تحديث:** 2026-03-13  
**تم الاختبار مع:** Aspose.Page 24.11 for Java (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}