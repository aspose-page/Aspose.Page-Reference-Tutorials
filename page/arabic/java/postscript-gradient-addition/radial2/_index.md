---
date: 2025-12-08
description: تعلم كيفية إنشاء مثال لتدرج دائري في Java PostScript باستخدام Aspose.Page.
  دليل خطوة بخطوة مع الكود الكامل وحلول المشكلات.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'مثال على التدرج الشعاعي: جافا بوستسكريبت مع Aspose.Page'
url: /ar/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# مثال على التدرج الشعاعي: Java PostScript باستخدام Aspose.Page

## المقدمة
في هذا الدرس ستقوم بإنشاء **مثال على التدرج الشعاعي** لمستند PostScript باستخدام Aspose.Page for Java. سنستعرض كل خطوة — من إعداد المشروع إلى رسم دائرة مملوءة بتدرج شعاعي ناعم — حتى تتمكن من إضافة رسومات جذابة إلى تطبيقات Java الخاصة بك فورًا.

## إجابات سريعة
- **ماذا ينشئ هذا الدرس؟** ملف PostScript (`.ps`) يحتوي على دائرة مملوءة بتدرج شعاعي.  
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (أحدث إصدار).  
- **كم يستغرق التنفيذ؟** تقريبًا 10‑15 دقيقة للحصول على مثال يعمل.  
- **هل أحتاج إلى ترخيص؟** يلزم وجود ترخيص مؤقت أو كامل للاستخدام في الإنتاج؛ نسخة تجريبية مجانية تكفي للتطوير.  
- **هل يمكن إعادة استخدام الكود لـ PDF أو SVG؟** نعم — Aspose.Page يدعم صيغ إخراج متعددة مع تغييرات قليلة.

## ما هو التدرج الشعاعي؟
التدرج الشعاعي ينتقل بالألوان من نقطة مركزية إلى الخارج، مكوّنًا مزيجًا دائريًا ناعمًا. وهو مثالي للإضاءات، خلفيات الأزرار، أو أي عنصر بصري يحتاج إلى تأثير “توهج” طبيعي.

## لماذا نستخدم Aspose.Page للتدرجات الشعاعية؟
- **تصيير غير معتمد على الجهاز** – يعمل بنفس الطريقة على PostScript، PDF، SVG، وغيرها.  
- **تكامل كامل مع Java** – لا تحتاج إلى شفرة أصلية، فقط واجهات برمجة تطبيقات Java العادية.  
- **إخراج عالي الجودة** – يدعم مضاد التعرج والتحكم في مساحة الألوان.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

- إلمام أساسي ببرمجة Java.  
- JDK 8 أو أحدث مثبت على جهازك.  
- مكتبة Aspose.Page for Java (حمّلها من [توثيق Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## استيراد الحزم
أولاً، استورد الفئات التي سنحتاجها. تشمل هذه الأنواع الرسومية القياسية من AWT وواجهة Aspose.Page API.

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
عرّف المجلد الذي سيُحفظ فيه ملف PostScript المُولَّد. استبدل العنصر النائب بمسار فعلي على نظامك.

```java
String dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء تدفق الإخراج
افتح `FileOutputStream` يشير إلى ملف `.ps` الهدف. يزود هذا التدفق البيانات الثنائية التي تُنشئها Aspose.Page.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## الخطوة 3: إنشاء خيارات الحفظ
أنشئ كائن `PsSaveOptions`. يمكنك تخصيص حجم الصفحة، الضغط، إلخ، لكن الإعدادات الافتراضية كافية لهذا المثال.

```java
PsSaveOptions options = new PsSaveOptions();
```

## الخطوة 4: إنشاء مستند PS
أنشئ كائن `PsDocument`، مع تمرير تدفق الإخراج وخيارات الحفظ. العلم `false` يُخبر Aspose.Page بعدم فتح صفحة تلقائيًا (سنقوم بذلك يدويًا).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## الخطوة 5: إنشاء دائرة
سنرسم دائرة باستخدام `Ellipse2D.Float`. المعاملات هي `(x, y, width, height)`. ضبط `width = height` يُنتج دائرة مثالية.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## الخطوة 6: تعريف ألوان التدرج
حضّر مصفوفتين: واحدة للألوان التي ستظهر في التدرج وأخرى للمواقع النسبية (0 = المركز، 1 = الحافة).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## الخطوة 7: إنشاء AffineTransform
`AffineTransform` يقيِّم ويُحوِّل التدرج ليناسب دائرتنا. المصفوفة `(scaleX, 0, 0, scaleY, translateX, translateY)` تقوم بالمهمة.

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

## الخطوة 9: ضبط الطلاء وتعبئة الدائرة
طبق طلاء التدرج على المستند واملأ الدائرة التي عرّفناها مسبقًا. هذا هو جوهر **مثال التدرج الشعاعي**.

```java
document.setPaint(paint);
document.fill(circle);
```

## الخطوة 10: إغلاق الصفحة وحفظ المستند
أكمل الصفحة، اكتب المحتوى إلى القرص، وأغلق التدفق. الآن ملف PostScript جاهز للعرض بأي عارض PS.

```java
document.closePage();
document.save();
```

تهانينا! لقد أنشأت بنجاح مثالًا على التدرج الشعاعي في Java PostScript باستخدام Aspose.Page.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|---------|------|
| **FileNotFoundException** عند فتح تدفق الإخراج | تأكد من أن `dataDir` يشير إلى مجلد موجود وأن لديك صلاحيات كتابة. |
| التدرج يبدو مسطحًا أو مفقودًا | تأكد من أن مصفوفة `fractions` تتطابق مع طول مصفوفة `colors` وأن `AffineTransform` يقيِّم بشكل صحيح. |
| الألوان تظهر مقلوبة | غيّر ترتيب الألوان في مصفوفة `colors` أو عدّل إحداثيات نقطة `focus`. |

## الأسئلة المتكررة

**س: أين يمكنني العثور على توثيق Aspose.Page for Java؟**  
ج: مرجع API الكامل متوفر [هنا](https://reference.aspose.com/page/java/).

**س: كيف يمكنني تحميل Aspose.Page for Java؟**  
ج: احصل على أحدث JAR من [صفحة الإصدارات](https://releases.aspose.com/page/java/).

**س: هل هناك نسخة تجريبية مجانية؟**  
ج: نعم—حمّل نسخة التجربة [هنا](https://releases.aspose.com/).

**س: هل يمكنني الحصول على ترخيص مؤقت للاختبار؟**  
ج: بالتأكيد، اطلب واحدًا من [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني الحصول على دعم المجتمع؟**  
ج: انضم إلى النقاش في [منتدى Aspose.Page](https://forum.aspose.com/c/page/39).

## الخاتمة
في هذا الدليل بنينا مثالًا كاملًا على **التدرج الشعاعي** لمستند PostScript باستخدام Aspose.Page for Java. باتباع الخطوات لديك الآن نمط قابل لإعادة الاستخدام لإنشاء تدرجات متقدمة، ويمكنك تكييفه لـ PDF، SVG، أو أي صيغ مدعومة أخرى. جرّب ألوانًا، أنصاف أقطار، وأشكال مختلفة لإثراء مشاريع الرسوميات في Java.

---

**آخر تحديث:** 2025-12-08  
**تم الاختبار مع:** Aspose.Page for Java 24.11 (أحدث إصدار وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}