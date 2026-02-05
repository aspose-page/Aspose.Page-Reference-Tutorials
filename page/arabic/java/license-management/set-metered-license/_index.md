---
date: 2026-02-05
description: تعلم كيفية حفظ ملف EPS بصيغة PNG باستخدام Aspose.Page للغة Java مع تكوين
  ترخيص حسب الاستخدام. دليل خطوة بخطوة مع مثال كامل للكود.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: حفظ EPS كـ PNG باستخدام Aspose.Page Java (ترخيص حسب الاستهلاك)
url: /ar/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حفظ EPS كـ PNG باستخدام Aspose.Page Java (ترخيص مقاس)

## المقدمة
إذا كنت بحاجة إلى **حفظ EPS كـ PNG** في تطبيق Java وتريد طريقة خالية من المتاعب لإدارة الترخيص، فأنت في المكان الصحيح. يوضح هذا الدليل كيفية تكوين ترخيص مقاس لـ Aspose.Page، تحميل ملف PostScript (EPS)، وتحويله إلى صورة PNG—كل ذلك بخطوات واضحة ومختصرة يمكنك اتباعها فورًا. في النهاية ستفهم أيضًا كيفية **تحويل EPS إلى PNG** بكفاءة وكتابة كود **write PNG file Java** يعمل في بيئات الإنتاج.

## إجابات سريعة
- **ماذا يعني “حفظ EPS كـ PNG”؟** إنه يحول ملف EPS المتجه إلى صورة PNG نقطية.  
- **لماذا نستخدم ترخيصًا مقاسًا؟** يسمح لك بالدفع فقط مقابل الصفحات التي تعالجها، وهو مثالي لأحمال العمل المتغيرة.  
- **هل أحتاج إلى اتصال بالإنترنت؟** لا، يتم التحقق من مفاتيح الترخيص المقاس محليًا.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أعلى.  
- **كم يستغرق الإعداد؟** حوالي 10 دقائق لتطبيق أساسي.  

## ما هو “حفظ EPS كـ PNG”؟
تحويل EPS إلى PNG يغيّر مستند Encapsulated PostScript القابل للتوسيع إلى تنسيق bitmap مدعوم على نطاق واسع. يحتفظ PNG بالشفافية ويقدم ضغطًا بدون فقدان، مما يجعله مثاليًا لرسوم الويب، المصغرات، ومعاينات الطباعة.

## لماذا تحويل EPS إلى PNG باستخدام Aspose.Page؟
- **Pure Java API** – لا توجد تبعيات أصلية، لذا يمكنك تشغيله في أي بيئة تدعم JVM.  
- **High fidelity rendering** – يتم تحويل الرسومات المتجهة إلى نقطية بدقة، مع الحفاظ على جودة الخطوط.  
- **Metered licensing** – تدفع فقط مقابل ما تقوم بتحويله، مما يجعل التكلفة متوقعة.  
- **Multiple output options** – بالإضافة إلى PNG يمكنك أيضًا إنشاء JPEG، TIFF، وأكثر، مما يمنحك مرونة لمشاريع مختلفة.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود ما يلي:

- معرفة أساسية ببرمجة Java.  
- مكتبة Aspose.Page مثبتة – حمّلها من [here](https://releases.aspose.com/page/java/).  
- مفاتيح الترخيص العامة والخاصة المقاس، والتي يمكنك الحصول عليها عبر حساب Aspose الخاص بك.

## استيراد الحزم
أولاً، استورد الفئات التي سنحتاجها. حافظ على كتلة الاستيراد كما هي بالضبط حتى يتم تجميع الكود دون تغييرات.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## كيفية حفظ EPS كـ PNG باستخدام Aspose.Page Java
فيما يلي دليل خطوة بخطوة يجمع بين الترخيص، التحميل، التحويل، وكتابة ملف PNG النهائي.

### الخطوة 1: تهيئة المستند وتنسيق الصورة
هنا نضبط مفاتيح الترخيص المقاس ونحدد تنسيق الإخراج (PNG). هذه هي الأساس لعملية **حفظ EPS كـ PNG**.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### الخطوة 2: تهيئة تدفق إدخال PostScript
افتح ملف EPS الذي تريد تحويله. يزود هذا التدفق المستند إلى Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### الخطوة 3: التحقق من ترخيص المستند
دائمًا تحقق من أن ترخيص المقاس تم تطبيقه بشكل صحيح قبل المعالجة.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### الخطوة 4: تهيئة الخيارات وجهاز الصورة
أنشئ كائن الخيارات الذي يتحكم في إعدادات التحويل والجهاز الذي سيستقبل الصورة المرسومة.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### الخطوة 5: حفظ ملف EPS كصورة
هذه هي نداء **حفظ EPS كـ PNG** الأساسي. يتم رسم المستند إلى جهاز الصورة باستخدام الخيارات التي تم تكوينها.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### الخطوة 6: الحصول على بايتات الصورة وحفظها
استخرج بايتات PNG من الجهاز واكتبها إلى ملف على القرص. تُظهر هذه الخطوة كيفية **write PNG file Java** بأمان.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## المشكلات الشائعة والحلول
| المشكلة | لماذا يحدث | الحل |
|-------|----------------|-----|
| **الترخيص غير معترف به** | المفاتيح غير صحيحة أو موضوعة بالترتيب الخطأ. | تحقق من سلاسل المفاتيح العامة/الخاصة وتأكد من استدعاء `setMeteredKey` قبل أي معالجة للمستند. |
| **ملف الإخراج فارغ** | `device.getImagesBytes()` أعاد `null`. | تأكد من صحة ملف EPS وأن `ImageSaveOptions` لم تُضبط على لوحة قماش بحجم صفر. |
| **OutOfMemoryError عند EPS كبير** | معالجة ملفات متجهة كبيرة تستهلك الكثير من الذاكرة. | عالج الصفحات صفحةً بصفحة أو زد حجم heap للـ JVM (`-Xmx2g`). |

## الأسئلة المتكررة

**س: كيف أحصل على المفاتيح العامة والخاصة للترخيص المقاس؟**  
ج: يمكنك الحصول على هذه المفاتيح عبر حساب Aspose الخاص بك.

**س: هل مكتبة Aspose.Page مجانية؟**  
ج: توفر Aspose.Page إصدارات تجريبية مجانية وإصدارات مدفوعة. زر [here](https://releases.aspose.com/) للحصول على نسخة تجريبية مجانية.

**س: هل يمكنني استخدام Aspose.Page في مشاريع تجارية؟**  
ج: نعم، تقدم Aspose.Page تراخيص تجارية. يمكنك شراؤها [here](https://purchase.aspose.com/buy).

**س: أين يمكنني العثور على وثائق إضافية؟**  
ج: راجع الوثائق [here](https://reference.aspose.com/page/java/).

**س: كيف أحصل على تراخيص مؤقتة؟**  
ج: يمكن الحصول على تراخيص مؤقتة [here](https://purchase.aspose.com/temporary-license/).

**س: ماذا لو احتجت إلى تحويل ملفات EPS متعددة الصفحات؟**  
ج: قم بالتكرار عبر كل صفحة باستخدام `device.getImagesBytes()` واكتب كل مصفوفة بايت إلى ملف PNG منفصل.

**س: هل يمكنني تغيير جودة PNG أو عمق اللون؟**  
ج: نعم، اضبط `ImageSaveOptions` (مثلاً `options.setCompressionLevel(...)`) قبل استدعاء `document.save(...)`.

---

**آخر تحديث:** 2025-12-03  
**تم الاختبار مع:** Aspose.Page 24.12 for Java  
**المؤلف:** Aspose  

**آخر تحديث:** 2026-02-05  
**تم الاختبار مع:** Aspose.Page 24.12 for Java (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}