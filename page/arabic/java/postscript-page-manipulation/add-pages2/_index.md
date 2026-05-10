---
date: 2026-02-18
description: تعلم كيفية تعيين حجم صفحة مخصص وإضافة صفحات إلى مستندات Java PostScript
  باستخدام Aspose.Page. اتبع دليلنا خطوة بخطوة لتعديل المستندات بسلاسة.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: دروس Aspose.Page للغة Java – تعيين حجم صفحة مخصص أثناء إضافة الصفحات في PostScript
url: /ar/java/postscript-page-manipulation/add-pages2/
weight: 11
---

"**Author:** Aspose" => "**المؤلف:** Aspose"

Then closing shortcodes.

Finally backtop button shortcode unchanged.

Make sure to keep blank lines as original.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Tutorial – تعيين حجم صفحة مخصص أثناء إضافة صفحات في PostScript

## المقدمة
في تطبيقات Java الحديثة، **تعيين حجم صفحة مخصص** لإخراج PostScript غالبًا ما يكون مطلوبًا—سواءً كنت تولد فواتير، تذاكر، أو رسومات مخصصة. في هذا الدرس ستتعلم كيفية **تعيين حجم صفحة مخصص** لكل صفحة، إضافة صفحات متعددة، وأخيرًا **إنشاء ملف PostScript** يتطابق مع احتياجات التخطيط الدقيقة الخاصة بك. سنستعرض الكود خطوة بخطوة حتى تتمكن من تطبيق التقنية بسرعة في مشاريعك.

## إجابات سريعة
- **هل يمكنني تعيين أحجام صفحات مختلفة لكل صفحة؟** نعم، يمكنك فتح الصفحات بأبعاد مخصصة باستخدام `document.openPage(width, height)`.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يلزم وجود ترخيص صالح لـ Aspose.Page للنشر غير التجريبي.  
- **ما إصدارات Java المدعومة؟** المكتبة تعمل مع Java 8 وما فوق.  
- **هل الـ API آمن للاستخدام المتعدد الخيوط؟** كائنات Document غير آمنة للمتعدد الخيوط؛ أنشئ `PsDocument` منفصل لكل خيط.  
- **ما هو الحد الأقصى لحجم ملف PostScript؟** Aspose.Page يتعامل مع ملفات متعددة الميجابايت بكفاءة؛ استهلاك الذاكرة يتناسب مع المحتوى، وليس عدد الصفحات.  
- **هل يمكنني استخدام الدالة المفتوحة للعرض/الارتفاع؟** بالتأكيد—`openPage(double width, double height)` يتيح لك تحديد أي أبعاد بالنقاط.  

## المتطلبات المسبقة
قبل الغوص في التفاصيل، تأكد من وجود:

- فهم أساسي لبرمجة Java.  
- إضافة Aspose.Page for Java إلى مشروعك (Maven/Gradle أو JAR يدوي).  
- بيئة تطوير Java (IDE، JDK 8+).  

## استيراد الحزم
لبدء العمل، استورد الفئات الضرورية من مكتبة Aspose.Page.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## الخطوة 1: إنشاء مستند PostScript متعدد الصفحات
أولاً، أنشئ `PsDocument` جديدًا مهيأً للصفحات المتعددة. هذا يضبط تدفق الإخراج ويخبر المكتبة أننا سنعمل على ملف متعدد الصفحات.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## الخطوة 2: إضافة محتوى إلى الصفحة الأولى
مع جاهزية المستند، يمكنك إضافة أي محتوى تحتاجه إلى الصفحة الأولى. عند الانتهاء، أغلق الصفحة لتثبيت محتواها.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## كيفية تعيين حجم صفحة مخصص
إذا لم يكن حجم الصفحة الافتراضي هو ما تحتاجه، يمكنك **تعيين حجم صفحة مخصص** عند فتح صفحة جديدة. هذا مفيد للإيصالات، الملصقات، أو أي تخطيط غير قياسي.

## الخطوة 3: إضافة صفحة ثانية بحجم مختلف
في الأسفل نفتح صفحة ثانية ونحدد صراحةً عرضًا وارتفاعًا مخصصين (بالنقاط). يوضح هذا كيفية تعيين حجم صفحة مخصص للصفحات الفردية، مما يمنحك القدرة على العمل بـ **أحجام صفحات مختلفة** داخل نفس المستند.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## الخطوة 4: حفظ المستند
أخيرًا، احفظ التغييرات عن طريق حفظ المستند. جميع الصفحات—بما فيها تلك ذات الأحجام المخصصة—تُكتب إلى ملف الإخراج.

```java
// Save the document
document.save();
```

باتباع هذه الخطوات، يمكنك إضافة صفحات بسهولة و**تعيين حجم صفحة مخصص** في مستند PostScript باستخدام Java وAspose.Page، مما يمنحك تحكمًا كاملًا في تخطيط كل صفحة.

## لماذا تستخدم Aspose.Page لتعيين حجم صفحة مخصص؟
- **الدقة:** تُعرّف الأبعاد بالنقاط، لذا تحصل على تحكم دقيق في عرض وارتفاع الصفحة.  
- **المرونة:** امزج واطلق **أحجام صفحات مختلفة** في ملف PostScript واحد.  
- **الأداء:** المكتبة تبث المحتوى مباشرة إلى ملف الإخراج، مما يجعلها مناسبة لسيناريوهات **إنشاء ملفات PostScript** على نطاق واسع.  
- **API غني:** يدعم رسم الرسومات، تضمين الصور، وإضافة النص—كل ذلك مع احترام الأبعاد المخصصة التي تحددها.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **أبعاد الصفحة تبدو مبدلة** | تذكر أن `openPage(width, height)` يتوقع العرض أولاً، ثم الارتفاع (كلاهما بالنقاط). |
| **المحتوى يتجاوز حدود الصفحة** | استخدم نظام إحداثيات `PsGraphics` لتحديد موضع العناصر داخل الحدود المخصصة، أو قم بتكبير/تصغير الرسم. |
| **أخطاء نفاد الذاكرة في المستندات الضخمة** | فعّل البث عن طريق الكتابة مباشرة إلى `FileOutputStream` كما هو موضح، وتجنب تحميل الصور الكبيرة إلى الذاكرة دفعة واحدة. |

## الأسئلة المتكررة
### هل يمكنني إضافة صفحات بأحجام مختلفة في مستند PostScript واحد؟
نعم، كما هو موضح في هذا الدرس، يمكنك إضافة صفحات بأحجام متباينة في مستند PostScript متعدد الصفحات.  

### هل هناك أي قيود على عدد الصفحات التي يمكنني إضافتها؟
Aspose.Page يدعم إضافة عدد غير محدود تقريبًا من الصفحات إلى المستند.  

### هل يمكنني إضافة محتوى مخصص، مثل الصور أو الرسومات، إلى الصفحات؟
بالطبع! Aspose.Page يتيح لك إضافة مجموعة واسعة من المحتويات، بما في ذلك النصوص، الصور، والعناصر الرسومية الأخرى.  

### هل Aspose.Page مناسب للتعامل مع المستندات الكبيرة؟
نعم، تم تصميم Aspose.Page للتعامل بكفاءة مع المستندات الصغيرة والكبيرة على حد سواء.  

### أين يمكنني العثور على موارد إضافية ودعم لـ Aspose.Page؟
استكشف [توثيق Aspose.Page](https://reference.aspose.com/page/java/)، أو زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع.  

**أسئلة وإجابات إضافية**

**س:** *ما صيغ الصور المدعومة عند الرسم على صفحة PostScript؟*  
**ج:** يمكنك تضمين صور PNG و JPEG و BMP و GIF مباشرةً باستخدام واجهة برمجة الرسم.  

**س:** *كيف أغيّر DPI الافتراضي للمستند؟*  
**ج:** اضبط `PsSaveOptions.setResolution(int dpi)` قبل إنشاء `PsDocument`.  

**س:** *هل يمكنني تشفير ملف PostScript بكلمة مرور؟*  
**ج:** لا يدعم PostScript نفسه التشفير، لكن يمكنك تغليف الناتج في PDF وتطبيق إعدادات الأمان إذا لزم الأمر.

---

**آخر تحديث:** 2026-02-18  
**تم الاختبار مع:** Aspose.Page for Java 24.10  
**المؤلف:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}