---
date: 2025-12-03
description: تعلم كيفية حفظ ملفات EPS بصيغة PNG باستخدام Aspose.Page للغة Java مع
  تكوين ترخيص مترّف. دليل خطوة بخطوة مع مثال كامل للكود.
language: ar
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: حفظ EPS كـ PNG باستخدام Aspose.Page Java (ترخيص مقاس)
url: /java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حفظ EPS كـ PNG باستخدام Aspose.Page Java (ترخيص حسب الاستخدام)

## المقدمة
إذا كنت بحاجة إلى **حفظ EPS كـ PNG** في تطبيق Java وتريد طريقة خالية من المتاعب لإدارة الترخيص، فأنت في المكان الصحيح. يوضح لك هذا الدليل كيفية تكوين ترخيص حسب الاستخدام لـ Aspose.Page، وتحميل ملف PostScript (EPS)، وتحويله إلى صورة PNG—كل ذلك بخطوات واضحة ومختصرة يمكنك اتباعها فورًا.

## إجابات سريعة
- **ماذا يعني “حفظ EPS كـ PNG”?** إنه يحول ملف EPS المتجه إلى صورة PNG نقطية.  
- **لماذا تستخدم ترخيصًا حسب الاستخدام؟** يتيح لك الدفع فقط للصفحات التي تعالجها، وهو مثالي لأحمال العمل المتغيرة.  
- **هل أحتاج إلى اتصال بالإنترنت؟** لا، يتم التحقق من مفاتيح الترخيص محليًا.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أعلى.  
- **كم من الوقت يستغرق الإعداد؟** حوالي 10 دقائق لتنفيذ أساسي.

## ما هو “حفظ EPS كـ PNG”؟
تحويل EPS إلى PNG يحول مستند Encapsulated PostScript القابل للتوسع إلى تنسيق نقطي مدعوم على نطاق واسع. يحتفظ PNG بالشفافية ويقدم ضغطًا بدون فقدان، مما يجعله مثاليًا للرسومات على الويب، والصور المصغرة، ومعاينات الطباعة.

## لماذا تستخدم Aspose.Page لهذه المهمة؟
- **واجهة برمجة تطبيقات Java صافية** – لا توجد تبعيات أصلية.  
- **دقة عالية** – يتم عرض الرسومات المتجهة بدقة.  
- **ترخيص حسب الاستخدام** – تدفع فقط مقابل ما تقوم بتحويله.  
- **دعم تنسيقات إخراج متعددة** – PNG، JPEG، TIFF، إلخ.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من أن لديك:

- معرفة أساسية ببرمجة Java.  
- مكتبة Aspose.Page مثبتة – قم بتنزيلها من [here](https://releases.aspose.com/page/java/).  
- مفاتيح الترخيص حسب الاستخدام العامة والخاصة، والتي يمكنك الحصول عليها عبر حساب Aspose الخاص بك.

## استيراد الحزم
أولاً، استورد الفئات التي سنحتاجها. احتفظ بكتلة الاستيراد كما هي تمامًا حتى يتم تجميع الكود دون تغييرات.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## الخطوة 1: تهيئة المستند وتنسيق الصورة
هنا نقوم بتعيين مفاتيح الترخيص حسب الاستخدام وتعريف تنسيق الإخراج (PNG). هذا هو الأساس لعملية **حفظ EPS كـ PNG**.

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

## الخطوة 2: تهيئة تدفق إدخال PostScript
افتح ملف EPS الذي تريد تحويله. يزود هذا التدفق المستند إلى Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## الخطوة 3: التحقق من ترخيص المستند
تحقق دائمًا من أن ترخيص الاستخدام حسب المقياس تم تطبيقه بشكل صحيح قبل المعالجة.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## الخطوة 4: تهيئة الخيارات وجهاز الصورة
أنشئ كائن الخيارات الذي يتحكم في إعدادات التحويل والجهاز الذي سيتلقى الصورة المرسومة.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## الخطوة 5: حفظ ملف EPS كصورة
هذه هي الدعوة الأساسية لـ **حفظ EPS كـ PNG**. يتم رسم المستند إلى جهاز الصورة باستخدام الخيارات التي قمنا بتكوينها.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## الخطوة 6: الحصول على بايتات الصورة وحفظها
استخرج بايتات PNG من الجهاز واكتبها إلى ملف على القرص.

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
| **الترخيص غير معترف به** | المفاتيح غير صحيحة أو موضوعة بالترتيب الخطأ. | تحقق مرة أخرى من سلاسل المفاتيح العامة/الخاصة وتأكد من استدعاء `setMeteredKey` قبل أي معالجة للمستند. |
| **ملف الإخراج فارغ** | `device.getImagesBytes()` أعاد `null`. | تحقق من أن ملف EPS صالح وأن `ImageSaveOptions` لم يتم تعيينه إلى لوحة قماش بحجم صفر. |
| **خطأ OutOfMemoryError على EPS كبير** | معالجة ملفات متجهة كبيرة تستهلك الكثير من الذاكرة. | قم بمعالجة الصفحات واحدةً تلو الأخرى أو زد حجم ذاكرة JVM (`-Xmx2g`). |

## الأسئلة المتكررة

**س: كيف أحصل على المفاتيح العامة والخاصة للترخيص حسب الاستخدام؟**  
ج: يمكنك الحصول على هذه المفاتيح عبر حساب Aspose الخاص بك.

**س: هل مكتبة Aspose.Page مجانية؟**  
ج: تقدم Aspose.Page إصدارات تجريبية مجانية وإصدارات مدفوعة. زر [here](https://releases.aspose.com/) للحصول على نسخة تجريبية مجانية.

**س: هل يمكنني استخدام Aspose.Page في المشاريع التجارية؟**  
ج: نعم، تقدم Aspose.Page تراخيص تجارية. يمكنك شراؤها [here](https://purchase.aspose.com/buy).

**س: أين يمكنني العثور على وثائق إضافية؟**  
ج: راجع الوثائق [here](https://reference.aspose.com/page/java/).

**س: كيف يمكنني الحصول على تراخيص مؤقتة؟**  
ج: يمكن الحصول على تراخيص مؤقتة [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2025-12-03  
**تم الاختبار باستخدام:** Aspose.Page 24.12 for Java  
**المؤلف:** Aspose