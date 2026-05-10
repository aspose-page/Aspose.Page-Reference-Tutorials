---
date: 2026-02-13
description: تعلم كيفية ملء الشكل بتدرج لوني ورسم دائرة بتدرج لوني في Java PostScript
  باستخدام Aspose.Page. دليل خطوة بخطوة مع الشيفرة والنصائح.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'ملء الشكل بالتدرج: مثال جافا بوستسكريبت للتدرج الدائري'
url: /ar/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ملء الشكل بالتدرج اللوني: مثال PostScript دائري في Java

## المقدمة
في هذا الدرس ستتعلم كيفية **ملء الشكل بالتدرج اللوني** من خلال بناء مثال لتدرج دائري لمستند PostScript باستخدام Aspose.Page for Java. سنتناول كل خطوة—من إعداد المشروع إلى عرض دائرة مملوءة بتدرج دائري سلس—حتى تتمكن من إضافة رسومات جذابة إلى تطبيقات Java الخاصة بك فورًا.

## إجابات سريعة
- **ماذا ينشئ هذا الدرس؟** ملف PostScript (`.ps`) يحتوي على دائرة مملوءة بتدرج دائري.  
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (أحدث إصدار).  
- **كم يستغرق التنفيذ؟** تقريبًا 10‑15 دقيقة للحصول على مثال يعمل.  
- **هل أحتاج إلى ترخيص؟** يلزم وجود ترخيص مؤقت أو كامل للاستخدام في الإنتاج؛ النسخة التجريبية مجانية للتطوير.  
- **هل يمكن إعادة استخدام الكود لـ PDF أو SVG؟** نعم—يدعم Aspose.Page صيغ إخراج متعددة مع تغييرات قليلة.

## كيفية ملء الشكل بالتدرج اللوني في PostScript
قبل الغوص في الكود، دعنا نوضح لماذا يهم “ملء الشكل بالتدرج اللوني”. يمنحك استخدام التدرجات مظهرًا احترافيًا ثلاثي الأبعاد دون الحاجة إلى صور نقطية. مع Aspose.Page يمكنك تطبيق نفس منطق التدرج على أي شكل متجه—دوائر، مستطيلات، أو مسارات مخصصة—عبر جميع صيغ الإخراج المدعومة (PostScript، PDF، SVG).

## ما هو التدرج الدائري؟
التدرج الدائري ينتقل بالألوان من نقطة مركزية إلى الخارج، مكونًا مزيجًا دائريًا ناعمًا. إنه مثالي للإضاءات، خلفيات الأزرار، أو أي عنصر بصري يحتاج إلى تأثير “توهج” طبيعي.

## لماذا نستخدم Aspose.Page للتدرجات الدائرية؟
- **عرض مستقل عن الجهاز** – يعمل بنفس الطريقة على PostScript، PDF، SVG، وأكثر.  
- **تكامل كامل مع Java** – لا يوجد كود أصلي، فقط واجهات برمجة تطبيقات Java العادية.  
- **إخراج عالي الجودة** – يدعم مضاد التعرج والتحكم في مساحة الألوان.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

- إلمام أساسي ببرمجة Java.  
- JDK 8 أو أحدث مثبت على جهازك.  
- مكتبة Aspose.Page for Java (حمّلها من [توثيق Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## استيراد الحزم
أولاً، استورد الفئات التي سنحتاجها. تشمل هذه أنواع رسومات AWT القياسية وواجهة Aspose.Page API.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## الخطوة 1: إعداد دليل المستند
حدد المجلد الذي سيُحفظ فيه ملف PostScript المُولَّد. استبدل العنصر النائب بمسار فعلي على نظامك.

```java
String dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء تدفق الإخراج
افتح `FileOutputStream` يشير إلى ملف `.ps` الهدف. يزود هذا التدفق البيانات الثنائية التي تُولدها Aspose.Page.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## الخطوة 3: إنشاء خيارات الحفظ
أنشئ كائن `PsSaveOptions`. يمكنك تخصيص حجم الصفحة، الضغط، إلخ، لكن الإعدادات الافتراضية كافية لهذا المثال.

```java
PsSaveOptions options = new PsSaveOptions();
```

## الخطوة 4: إنشاء مستند PS
أنشئ كائن `PsDocument`، مع تمرير تدفق الإخراج وخيارات الحفظ. العلامة `false` تخبر Aspose.Page بعدم فتح صفحة تلقائيًا (سنقوم بذلك يدويًا).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 5: إنشاء دائرة
سنرسم دائرة باستخدام `Ellipse2D.Float`. المعلمات هي `(x, y, width, height)`. ضبط العرض = الارتفاع ينتج دائرة مثالية.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## كيفية رسم دائرة بالتدرج اللوني
الآن بعد أن لدينا الشكل، الخطوة التالية هي **رسم دائرة بالتدرج اللوني**. عبر تطبيق `RadialGradientPaint` على الدائرة، ستستخدم عملية التعبئة التدرج الذي نحدده تلقائيًا.

## الخطوة 6: تعريف ألوان التدرج
حضّر مصفوفتين: واحدة للألوان التي ستظهر في التدرج وأخرى للمواقع النسبية المقابلة (0 = المركز، 1 = الحافة).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## الخطوة 7: إنشاء AffineTransform
يقوم `AffineTransform` بتكبير وتحويل التدرج ليناسب دائرتنا. المصفوفة `(scaleX, 0, 0, scaleY, translateX, translateY)` تقوم بالمهمة.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## الخطوة 8: إنشاء Radial Gradient Paint
الآن نبني كائن `RadialGradientPaint`. يأخذ نقطة المركز، نصف القطر، نقطة التركيز، كسور الألوان، مصفوفة الألوان، طريقة الدورة، مساحة اللون، والتحويل الذي عرفناه للتو.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## الخطوة 9: تعيين الطلاء وتعبئة الدائرة
طبق طلاء التدرج على المستند واملأ الدائرة المعرفة مسبقًا. هذا هو جوهر **مثال التدرج الدائري** ويظهر كيفية **ملء الشكل بالتدرج اللوني**.

```java
document.setPaint(paint);
document.fill(circle);
```

## الخطوة 10: إغلاق الصفحة وحفظ المستند
أكمل الصفحة، اكتب المحتوى إلى القرص، وأغلق التدفق. ملف PostScript الآن جاهز للعرض بأي عارض PS.

```java
document.closePage();
document.save();
```

تهانينا! لقد نجحت في إنشاء مثال لتدرج دائري في Java PostScript باستخدام Aspose.Page. لديك الآن نمط قابل لإعادة الاستخدام لـ **ملء الشكل بالتدرج اللوني** يمكن تكييفه مع أشكال أخرى وصيغ إخراج مختلفة.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|---------|------|
| **FileNotFoundException** عند فتح تدفق الإخراج | تحقق من أن `dataDir` يشير إلى مجلد موجود وأن لديك صلاحيات كتابة. |
| التدرج يبدو مسطحًا أو مفقودًا | تأكد من أن مصفوفة `fractions` تتطابق مع طول مصفوفة `colors` وأن `AffineTransform` يتم تكبيره بشكل صحيح. |
| الألوان تظهر مقلوبة | عكس ترتيب الألوان في مصفوفة `colors` أو ضبط إحداثيات نقطة `focus`. |

## الأسئلة المتكررة

**س: أين يمكنني العثور على توثيق Aspose.Page for Java؟**  
ج: المرجع الكامل للـ API متوفر [هنا](https://reference.aspose.com/page/java/).

**س: كيف يمكنني تحميل Aspose.Page for Java؟**  
ج: احصل على أحدث ملف JAR من [صفحة الإصدارات](https://releases.aspose.com/page/java/).

**س: هل هناك نسخة تجريبية مجانية؟**  
ج: نعم—حمّل نسخة تجريبية [هنا](https://releases.aspose.com/).

**س: هل يمكنني الحصول على ترخيص مؤقت للاختبار؟**  
ج: بالتأكيد، اطلب واحدًا من [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني الحصول على دعم المجتمع؟**  
ج: انضم إلى النقاش في [منتدى Aspose.Page](https://forum.aspose.com/c/page/39).

## الخاتمة
في هذا الدليل بنينا مثالًا كاملاً **لتدرج دائري** لمستند PostScript باستخدام Aspose.Page for Java. باتباع الخطوات لديك الآن نمط قابل لإعادة الاستخدام لـ **ملء الشكل بالتدرج اللوني**، ويمكنك تكييفه إلى PDF، SVG، أو أي صيغة أخرى يدعمها Aspose.Page. جرّب ألوانًا، أنصاف أقطار، وأشكال مختلفة لإثراء مشاريع رسومات Java الخاصة بك.

---

**آخر تحديث:** 2026-02-13  
**تم الاختبار مع:** Aspose.Page for Java 24.11 (أحدث إصدار وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}