---
title: تكامل الترخيص المقنن بسهولة مع Aspose.Page Java
linktitle: قم بتعيين الترخيص المقنن في Java
second_title: Aspose.Page جافا API
description: اكتشف التكامل السلس لـ Aspose.Page مع Java. قم بإعداد التراخيص المقننة دون عناء وعزز قدرات معالجة المستندات لديك.
weight: 10
url: /ar/java/license-management/set-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تكامل الترخيص المقنن بسهولة مع Aspose.Page Java

## مقدمة
مرحبًا بك في دليلنا الشامل حول إعداد ترخيص مقنن في Java باستخدام Aspose.Page. إذا كنت تتطلع إلى تحسين قدرات معالجة المستندات لديك وضمان التكامل السلس مع Aspose.Page، فأنت في المكان الصحيح. في هذا البرنامج التعليمي، سنرشدك خلال العملية، وسنقسم كل خطوة إلى أجزاء سهلة الهضم.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
-  تم تثبيت مكتبة Aspose.Page. يمكنك تنزيله من[هنا](https://releases.aspose.com/page/java/).
- المفاتيح العامة والخاصة المقدرة، والتي يمكنك الحصول عليها من خلال حساب Aspose الخاص بك.
## حزم الاستيراد
لنبدأ باستيراد الحزم اللازمة لبرنامج Java الخاص بنا. تأكد من دمج مكتبة Aspose.Page في مشروعك.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## الخطوة 1: تهيئة تنسيق المستند والصورة
الخطوة الأولى هي إعداد المستند وتحديد تنسيق الصورة المطلوب.
```java
// تعيين المفاتيح العامة والخاصة المقننة
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// قم بالوصول إلى خاصية setMeteredKey وتمرير المفاتيح العامة والخاصة كمعلمات
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## الخطوة 2: تهيئة دفق إدخال PostScript
في هذه الخطوة، نقوم بتهيئة دفق إدخال PostScript للمعالجة.
```java
// تهيئة دفق إدخال بوستسكريبت
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## الخطوة 3: التحقق من ترخيص المستند
قبل المتابعة، من الضروري التحقق مما إذا كان المستند مرخصًا بشكل صحيح.
```java
// تحقق مما إذا كانت الوثيقة مرخصة
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## الخطوة 4: تهيئة الخيارات وجهاز الصورة
الآن، دعونا نقوم بتهيئة الخيارات وجهاز الصورة بالمعلمات الافتراضية.
```java
// تهيئة كائن الخيارات بالمعلمات الافتراضية.
ImageSaveOptions options = new ImageSaveOptions();
// تهيئة كائن ImageDevice باستخدام المعلمات الافتراضية.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## الخطوة 5: حفظ ملف EPS كصورة
احفظ ملف EPS كصورة باستخدام الخيارات والجهاز المحدد.
```java
// حفظ ملف EPS كصورة
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## الخطوة 6: الحصول على وحفظ بايتات الصورة
استرداد بايتات الصورة وحفظها في ملف.
```java
// الحصول على بايت الصور. مجموعة بايت واحدة لصفحة واحدة. في حالتنا، لدينا صفحة واحدة.
byte[][] imagesBytes = device.getImagesBytes();
// حفظ بايت الصورة إلى ملف
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## خاتمة
تهانينا! لقد قمت بنجاح بإعداد ترخيص مقنن في Java باستخدام Aspose.Page. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة لضمان عملية التكامل السلسة.
## الأسئلة الشائعة
### س: كيف يمكنني الحصول على المفاتيح العامة والخاصة المقيسة؟
يمكنك الحصول على هذه المفاتيح من خلال حساب Aspose الخاص بك.
### س: هل مكتبة Aspose.Page مجانية؟
 يقدم Aspose.Page كلا من الإصدارات التجريبية المجانية والإصدارات المدفوعة. يزور[هنا](https://releases.aspose.com/) للتجربة المجانية.
### س: هل يمكنني استخدام Aspose.Page للمشاريع التجارية؟
 نعم، Aspose.Page يقدم تراخيص تجارية. يمكنك شرائها[هنا](https://purchase.aspose.com/buy).
### س: أين يمكنني العثور على وثائق إضافية؟
 الرجوع إلى الوثائق[هنا](https://reference.aspose.com/page/java/).
### س: كيف يمكنني الحصول على تراخيص مؤقتة؟
 يمكن الحصول على تراخيص مؤقتة[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
