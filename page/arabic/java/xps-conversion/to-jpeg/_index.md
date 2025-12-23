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

## Introduction
في هذا الدرس، **ستتعلم كيفية تحويل XPS إلى JPEG** باستخدام مكتبة Aspose.Page القوية للغة Java. تحويل ملفات XPS إلى صيغ صور هو طلب شائع عندما تحتاج إلى عرض أو معاينة أو معالجة صفحات المستند في تطبيقات الويب أو سطح المكتب. سنستعرض كل خطوة، نشرح لماذا كل سطر مهم، ونقدم لك نصائح عملية حتى تتمكن من دمج منطق التحويل في مشاريعك بثقة.

## Quick Answers
- **ما المكتبة التي تتعامل مع التحويل؟** Aspose.Page for Java  
- **هل يمكنني اختيار صفحات محددة؟** نعم – استخدم `setPageNumbers` في `JpegSaveOptions`  
- **ما جودة الصورة التي يمكنني التحكم فيها؟** وضع التنعيم، الدقة، وإعدادات جودة JPEG  
- **هل أحتاج إلى رخصة للإنتاج؟** نعم، يلزم رخصة تجارية (يتوفر تجربة مجانية)  
- **هل الكود متوافق مع Java 8؟** بالتأكيد – الـ API يعمل مع Java 8 والإصدارات الأحدث  

## What is XPS and Why Convert it to JPEG?
PS (XML Paper Specification) هو تنسيق مستند ثابت التخطيط مشابه لـ PDF. تحويل XPS إلى JPEG مفيد عندما تحتاج إلى صور نقطية للصور المصغرة، مرفقات البريد الإلكتروني، أو عند التكامل مع أنظمة تقبل ملفات الصور فقط. JPEG يوفر توازناً جيداً بين جودة الصورة وحجم الملف، مما يجعله مثالياً للمعاينات على الويب.

## Prerequisites
قبل أن نغوص في الكود، تأكد من توفر ما يلي:

- **بيئة تطوير Java** – JDK 8 أو أحدث مثبت ومُكوَّن.  
- **Aspose.Page للغة Java** – حمّل أحدث مكتبة من الموقع الرسمي [here](https://releases.aspose.com/page/java/).  
- **ملف XPS تجريبي** – ملف XPS تريد تحويله إلى صور JPEG.  

## Import Packages
ابدأ باستيراد الفئات الضرورية إلى ملف المصدر Java الخاص بك:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Step 1: Initialize Paths and Load the XPS Document
حدد الدليل الذي يحتوي على ملف XPS المصدر وأنشئ مثيل `XpsDocument`:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **نصيحة احترافية:** استخدم `Paths.get()` من `java.nio.file` للتعامل مع المسارات بشكل مستقل عن النظام.

## Step 2: Configure JPEG Save Options
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

## Step 3: Create the Rendering Device
`ImageDevice` يلتقط الصفحات المصورة كمصفوفات بايت:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## Step 4: Render the XPS Document to JPEG
استدعِ طريقة `save`، مع تمرير الجهاز والخيارات التي قمت بتكوينها:

```java
document.save(device, options);
```

في هذه المرحلة، يحتوي `device` على مصفوفة ثنائية الأبعاد حيث يمثل كل عنصر صفحة مشفرة بصيغة JPEG.

## Step 5: Iterate Through the Result and Write Files
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

## Common Issues & Troubleshooting
| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| **ملفات JPEG فارغة** | عدم تفريغ أو إغلاق تدفق الإخراج بشكل صحيح | تأكد من استدعاء `imageStream.close()` داخل الحلقة الداخلية (كما هو موضح). |
| **أخطاء نفاد الذاكرة** عند ملفات XPS الكبيرة | تصيير جميع الصفحات مرة واحدة يستهلك الكثير من الذاكرة | عالج الصفحات على دفعات أصغر أو زد حجم heap للـ JVM (`-Xmx`). |
| **صفحات مفقودة** | `setPageNumbers` لا يتضمن الصفحة المطلوبة | تحقق من أن مصفوفة أرقام الصفحات تتطابق مع مؤشرات صفحات XPS الفعلية (بدءًا من 1). |

## Frequently Asked Questions

### Q: Is Aspose.Page suitable for commercial projects?
A: Yes, Aspose.Page is a commercial product with licensing options available. Check [here](https://purchase.aspose.com/buy) for details.
### Q: Can I try Aspose.Page before purchasing?
A: Yes, you can obtain a free trial [here](https://releases.aspose.com/).
### Q: Where can I find Aspose.Page documentation?
A: The documentation is available [here](https://reference.aspose.com/page/java/).
### Q: How can I get support for Aspose.Page?
A: Visit the [Aspose.Page Forum](https://forum.aspose.com/c/page/39) for community‑based support.
### Q: Do I need a temporary license for testing?
A: Yes, you can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

## Conclusion
لقد أصبحت الآن متمكناً من **كيفية تحويل XPS إلى JPEG** باستخدام Aspose.Page للغة Java. باتباعك للدليل خطوة بخطوة، يمكنك دمج خط أنابيب التحويل هذا في أي تطبيق Java — سواء كان أداة سطح مكتب، خدمة ويب، أو أداة معالجة دفعات. لا تتردد في تجربة دقات مختلفة، اختيار صفحات مختلفة، وصيغ صور متنوعة لتلبية احتياجات مشروعك.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Page 24.11 for Java (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}