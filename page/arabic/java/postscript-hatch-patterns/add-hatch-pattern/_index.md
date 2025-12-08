---
date: 2025-12-08
description: تعلم كيفية إضافة أنماط التشطيب إلى مستندات Java PostScript باستخدام Aspose.Page
  Java. يوضح لك هذا الدليل خطوة بخطوة كيفية إضافة رسومات أنماط التشطيب بكفاءة.
language: ar
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: إضافة نمط التظليل في Java PostScript'
url: /java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة نمط Hatch في Java PostScript

## المقدمة
إذا كنت تعمل مع **Aspose.Page Java** وتحتاج إلى إثراء مخرجات PostScript برسومات ذات نسيج، فإن أنماط Hatch تُعد حلاً سريعًا ومرنًا. في هذا الدرس سنستعرض **كيفية إضافة تصاميم Hatch** إلى مستند PostScript، نشرح لماذا هي مفيدة، ونقدم لك مثالًا كاملاً وجاهزًا للتنفيذ. في النهاية، ستتمكن من إنشاء أشكال ونصوص مملوءة بنمط Hatch جذاب بصِfew سطور من Java فقط.

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.Page for Java (حزمة “aspose page java” SDK).  
- **ما التأثير البصري الذي نضيفه؟** أنماط Hatch (مثل الخطوط المائلة، التشريب المتقاطع).  
- **هل أحتاج إلى ترخيص لتشغيل العينة؟** النسخة التجريبية المجانية تكفي للتطوير؛ الترخيص مطلوب للإنتاج.  
- **كم عدد أسطر الكود؟** حوالي 70 سطرًا، مقسمة إلى خطوات واضحة.  
- **هل يمكنني استخدام نفس النهج لملفات PDF؟** نعم—Aspose.Page يدعم صيغ إخراج متعددة، بما في ذلك PDF.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود ما يلي:

- **بيئة تطوير Java** – JDK 8 أو أعلى وأي IDE تفضله.  
- **مكتبة Aspose.Page for Java** – حمّل أحدث ملف JAR من الموقع الرسمي [هنا](https://releases.aspose.com/page/java/).  
- **صلاحية كتابة** إلى مجلد سيتم حفظ ملف PostScript المُولد فيه.

## استيراد الحزم
أولاً، استورد الفئات المطلوبة إلى مشروعك. هذه الاستيرادات تمنحك الوصول إلى primitive الرسومات، ومعالجة الألوان، وAPI الخاص بـ Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## الخطوة 1: إعداد المعلمات الأولية
أنشئ تدفق الإخراج، اضبط حجم الصفحة (A4)، وحدد بعض المتغيرات التخطيطية التي ستُعاد استخدامها عند رسم كل مربع مملوء بنمط Hatch.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## الخطوة 2: حفظ حالة الرسومات والترجمة
حفظ حالة الرسومات يتيح لنا العودة إلى نظام الإحداثيات الأصلي لاحقًا، بينما `translate` ينقل الأصل إلى نقطة بداية مريحة.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## الخطوة 3: إنشاء مربع لكل نمط
عرّف مستطيلًا قابلًا لإعادة الاستخدام سيمثل كل خلية مملوءة بنمط Hatch.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## الخطوة 4: إعداد القلم لتحديد حدود مربع النمط
`BasicStroke` بسمك 2 نقطة يمنح حدًا واضحًا حول كل مربع.

```java
BasicStroke stroke = new BasicStroke(2);
```

## الخطوة 5: التكرار عبر أنماط Hatch
تجول عبر كل قيمة في تعداد `HatchStyle`، املأ كل مربع بالنسيج المقابل، ثم ارسم حدّه. هذه هي جوهر وظيفة **إضافة نمط Hatch**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## الخطوة 6: استعادة حالة الرسومات
ارجع إلى نظام الإحداثيات الأصلي بعد الانتهاء من رسم شبكة المربعات.

```java
document.writeGraphicsRestore();
```

## الخطوة 7: تعبئة النص بنمط Hatch
نوضح هنا كيفية تلوين النص باستخدام نسيج Hatch. المثال يملأ كلمة “ABC” بنمط تقاطع قطري.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## الخطوة 8: تحديد حدود النص بنمط Hatch
الآن نحدد حدود نفس النص، لكن هذه المرة باستخدام نمط Hatch بنسبة 70 % وضربة أقلم.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## الخطوة 9: إغلاق وحفظ المستند
أكمل الصفحة، اكتب الملف إلى القرص، وأفرغ الموارد.

```java
document.closePage();
document.save();
```

اتبع هذه الخطوات، وستحصل على ملف PostScript يعرض مجموعة كاملة من أنماط Hatch المطبقة على الأشكال والنصوص—كل ذلك بفضل **aspose page java**.

## لماذا نستخدم أنماط Hatch مع Aspose.Page Java؟
- **تمييز بصري** – تعبئات Hatch تعمل حتى عندما تكون الطابعات محدودة بإخراج أحادي اللون.  
- **الأداء** – يتم توليد النسيج عند الحاجة، مما يجنبك ملفات صور ضخمة.  
- **دعم صيغ متعددة** – يمكن لنفس الكود استهداف PDF أو EPS أو SVG مع تغييرات قليلة.

## الأخطاء الشائعة والنصائح
- **أخطاء مسار الملف** – تأكد من أن `dataDir` ينتهي بالفاصل المناسب (`/` أو `\`).  
- **ألوان غير مدعومة** – قد لا يتعامل بعض مفسري PostScript القديمين مع مساحات ألوان معينة؛ استخدم RGB الأساسي لأقصى توافق.  
- **تحذيرات الترخيص** – تشغيل العينة بدون ترخيص صالح سيضيف علامة مائية إلى المخرجات.

## الخلاصة
إدماج أنماط Hatch يمكن أن يحسن بشكل كبير من قابلية القراءة والجمالية للرسومات التقنية، الخرائط، أو أي رسومات تُولد بواسطة Java. مع **Aspose.Page Java**، تحصل على API مختصر يُجرد أوامر PostScript منخفضة المستوى، مما يتيح لك التركيز على التصميم بدلاً من تفاصيل تنسيق الملف.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page Java مع أطر عمل Java أخرى؟**  
ج: نعم، المكتبة مستقلة عن الأطر وتعمل مع Spring، Jakarta EE، Android (محدودة)، وJava SE العادي.

**س: هل تتوفر نسخة تجريبية من Aspose.Page Java؟**  
ج: بالتأكيد. حمّل نسخة تجريبية مجانية لمدة 30 يومًا [هنا](https://releases.aspose.com/).

**س: كيف أحصل على ترخيص مؤقت للتطوير؟**  
ج: اطلب ترخيصًا مؤقتًا [هنا](https://purchase.aspose.com/temporary-license/). سيزيل العلامة المائية التجريبية.

**س: أين يمكنني العثور على المزيد من الدروس والدعم المجتمعي؟**  
ج: زر المنتدى الرسمي [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) للحصول على أمثلة إضافية وأسئلة وأجوبة.

**س: هل هناك وثائق شاملة لجميع الفئات والطرق؟**  
ج: نعم، المرجع الكامل للـ API متاح [هنا](https://reference.aspose.com/page/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2025-12-08  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose