---
date: 2025-12-23
description: تعلم كيفية تحويل XPS إلى JPEG في Java واكتشف كيفية تحويل ملفات XPS بفعالية
  باستخدام Aspose.Page. دليل شامل مع تعليمات خطوة بخطوة للتكامل السلس.
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: كيفية تحويل XPS إلى JPEG في Java
url: /ar/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحويل XPS إلى JPEG في Java

## مقدمة
في هذا الدرس، **ستتعلم كيفية تحويل XPS إلى JPEG** باستخدام مكتبة Aspose.Page الشريرة لـ Java. يعد تحويل ملفات XPS إلى صيغ الصور أمرًا شائعًا عندما يلزم عرض أو معاينة أو تخزين صفحات المستند في تطبيقات الويب أو سطح المكتب. سنتناول كل خطوة، نشرح لماذا كل سطر مهم، ونقدم لك أفكارًا عملية حتى يتمكن من دمج فعلي للتحويل في مشاريعك بثقة.

## إجابات سريعة
- **ما المكتبة التي التنوع مع التحويل؟** Aspose.Page for Java
- **هل يمكنني اختيار مساحات محددة؟** نعم – استخدم `setPageNumbers` في `JpegSaveOptions`
- **ما جودة الصورة التي يمكنني التحكم فيها؟** وضع التنعيم، الدقة، وإعدادات جودة JPEG
- **هل أحتاج إلى الترخيص التجاري للإنتاج؟** نعم، طلب الترخيص (يتوفر تجربة مجانية)
- **هل الكود متوافق مع Java8؟** بالتأكيد – الـ API يعمل مع Java8 وإصدارات LAN

## ما هو XPS ولماذا يتم تحويله إلى JPEG؟
PS (مواصفات ورق XML) هو تنسيق تنسيق ثابت مماثل لـ PDF. يعد تحويل XPS إلى JPEG أمرًا مفيدًا عندما تحتاج إلى التقاط صور فوتوغرافية للمحكمين، وتوثيق ملفات البريد الإلكتروني، أو عند تكامل مع ملفات الصور فقط. يوفر JPEG مشروبًا كافيًا بين جودة الصورة وحجم الملف، مما يجعله مثاليًا للمعاينات على الويب.

## المتطلبات الأساسية
قبل أن نغوص في الكود، تأكد من توفر ما يلي:

- **بيئة تطوير Java** – JDK 8 أو أحدث ومُكو .
- **Aspose.Page for Java** - أحدثت مكتبة نتانياهو من الموقع الرسمي[هنا](https://releases.aspose.com/page/java/).
- **ملف XPS السعر** – ملف XPS يريد تحويله إلى صور JPEG.

## استيراد الحزم
البدء باستيراد العناصر المحددة إلى ملف المصدر Java الخاص بك:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## الخطوة 1: تهيئة المسارات وتحميل مستند XPS
حدد الدليل الذي يحتوي على ملف XPS المصدر وأنشئ مثيل `XpsDocument`:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **نصيحة احترافية:** استخدم `Paths.get()` من `java.nio.file` للتعامل مع المسارات بشكل مستقل عن النظام.

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

## الخطوة 3: إنشاء جهاز العرض
`ImageDevice` يلتقط الصفحات المصورة كمصفوفات بايت:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## الخطوة 4: قم بتحويل مستند XPS إلى JPEG
استدعِ طريقة `save`، مع تمرير الجهاز والخيارات التي قمت بتكوينها:

```java
document.save(device, options);
```

في هذه المرحلة، يحتوي `device` على مصفوفة ثنائية الأبعاد حيث يمثل كل عنصر صفحة مشفرة بصيغة JPEG.

## الخطوة 5: التكرار خلال النتيجة وكتابة الملفات
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

## المشكلات الشائعة واستكشاف الأخطاء وإصلاحها
| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| **ملفات JPEG فارغة** | عدم تفريغ أو إغلاق تدفق الإخراج بشكل صحيح | تأكد من استدعاء `imageStream.close()` داخل الحلقة الداخلية (كما هو موضح). |
| **أخطاء نفاد الذاكرة** عند ملفات XPS الكبيرة | تصيير جميع الصفحات مرة واحدة يستهلك الكثير من الذاكرة | عالج الصفحات على دفعات أصغر أو زد حجم heap للـ JVM (`-Xmx`). |
| **صفحات مفقودة** | `setPageNumbers` لا يتضمن الصفحة المطلوبة | تحقق من أن مصفوفة أرقام الصفحات تتطابق مع مؤشرات صفحات XPS الفعلية (بدءًا من 1). |

## الأسئلة الشائعة

### س: هل Aspose.Page مناسب للمشاريع التجارية؟

ج: نعم، Aspose.Page منتج تجاري مع خيارات ترخيص متاحة. راجع [هنا](https://purchase.aspose.com/buy) للمزيد من التفاصيل.

## س: هل يمكنني تجربة Aspose.Page قبل الشراء؟

ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

## س: أين يمكنني العثور على وثائق Aspose.Page؟

ج: الوثائق متاحة [هنا](https://reference.aspose.com/page/java/).

## س: كيف يمكنني الحصول على دعم لـ Aspose.Page؟

ج: تفضل بزيارة [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم من المجتمع.

## س: هل أحتاج إلى ترخيص مؤقت للاختبار؟


## س: ج: نعم، يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

## خاتمة
لقد أصبحت الآن متمكناً من **كيفية تحويل XPS إلى JPEG** باستخدام Aspose.Page للغة Java. باتباعك للدليل خطوة بخطوة، يمكنك دمج خط الأنابيب لتحويل هذا في أي تطبيق Java — سواء كان أداة مكتبية، أو خدمة الويب، أو أداة الدفع. لا تتردد في تجربة دقات مختلفة، اختيار صفحات مختلفة، وصيغ صور متنوعة لأساسيات مشروعك.

---

**آخر تحديث:** 2025-12-23
**تم الاختبار مع:** Aspose.Page 24.11 لـ Java (آخر وقت كتابة هذا التقرير)
**المؤلف:** اطرح  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}