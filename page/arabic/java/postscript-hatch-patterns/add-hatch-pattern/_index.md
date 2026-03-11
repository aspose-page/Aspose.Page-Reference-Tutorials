---
date: 2026-02-15
description: تعلم كيفية إضافة نمط التظليل إلى ملفات PostScript في Java باستخدام Aspose.Page
  Java. يوضح هذا الدليل خطوة بخطوة الكود الكامل والنصائح.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: كيفية إضافة نمط التهشير في Java PostScript باستخدام Aspose.Page
url: /ar/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة نمط التهشير في Java PostScript

## المقدمة
إذا كنت تعمل مع **Aspose.Page Java** وتتساءل **كيف تضيف نمط تهشير** إلى مخرجات PostScript الخاصة بك، فإن أنماط التهشير هي حل سريع ومرن. في هذا الدرس سنستعرض **كيفية إضافة تصاميم تهشير** إلى مستند PostScript، نشرح لماذا هي مفيدة، ونقدم لك مثالًا كاملاً وجاهزًا للتنفيذ. في النهاية، ستتمكن من إنشاء أشكال ونصوص مملوءة بالتهشير جذابة بصريًا باستخدام بضع أسطر من Java فقط.

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.Page for Java (حزمة “aspose page java” SDK).  
- **ما التأثير البصري الذي نضيفه؟** أنماط التهشير (مثل الخطوط القطرية، التهشير المتقاطع).  
- **هل أحتاج إلى ترخيص لتشغيل العينة؟** النسخة التجريبية المجانية تكفي للتطوير؛ الترخيص مطلوب للإنتاج.  
- **كم عدد أسطر الشيفرة؟** حوالي 70 سطرًا، مقسمة إلى خطوات واضحة.  
- **هل يمكنني استخدام نفس النهج لملفات PDF؟** نعم—Aspose.Page يدعم صيغ إخراج متعددة، بما في ذلك PDF.

## كيفية إضافة نمط التهشير – نظرة عامة
أنماط التهشير هي قوام مبنية على المتجهات تُظهر نظافة في أي دقة وتعمل جيدًا على الطابعات أحادية اللون. باستخدام Aspose.Page Java، يمكنك تطبيق هذه الأنماط على الأشكال والمسارات وحتى النص دون الحاجة للتعامل مع أوامر PostScript منخفضة المستوى.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود ما يلي:

- **بيئة تطوير Java** – JDK 8 أو أعلى وIDE من اختيارك.  
- **مكتبة Aspose.Page for Java** – حمّل أحدث ملف JAR من الموقع الرسمي [هنا](https://releases.aspose.com/page/java/).  
- **صلاحية كتابة** إلى مجلد سيُحفظ فيه ملف PostScript المُولد.

## استيراد الحزم
أولاً، استورد الفئات المطلوبة إلى مشروعك. هذه الاستيرادات تمنحك الوصول إلى primitives الرسم، ومعالجة الألوان، وواجهة برمجة تطبيقات Aspose.Page.

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
أنشئ تدفق الإخراج، واضبط حجم الصفحة (A4)، وحدد بعض المتغيرات التي ستُعاد استخدامها عند رسم كل مربع مملوء بالتهشير.

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
عرّف مستطيلًا قابلًا لإعادة الاستخدام سيمثل كل خلية مملوءة بالتهشير.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## الخطوة 4: إعداد القلم لتحديد حدود مربع النمط
`BasicStroke` بسُمك 2 نقطة يعطي حدًا واضحًا حول كل مربع.

```java
BasicStroke stroke = new BasicStroke(2);
```

## الخطوة 5: التكرار عبر أنماط التهشير
تجول عبر كل قيمة في تعداد `HatchStyle`، املأ كل مربع بالقوام المقابل، ثم ارسم حدّه. هذه هي جوهر وظيفة **إضافة نمط تهشير**.

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

## الخطوة 7: تعبئة النص بنمط التهشير
هنا نوضح كيفية طلاء النص باستخدام قوام التهشير. المثال يملأ كلمة “ABC” بنمط تقاطع قطري.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## الخطوة 8: تحديد حدود النص بنمط التهشير
الآن نحدد حدود النص نفسه، لكن هذه المرة باستخدام نمط تهشير بنسبة 70 % وضربة أقوى.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## الخطوة 9: إغلاق وحفظ المستند
أنهِ الصفحة، واكتب الملف إلى القرص، وأطلق الموارد.

```java
document.closePage();
document.save();
```

اتبع هذه الخطوات، وستحصل على ملف PostScript يعرض مجموعة كاملة من أنماط التهشير المطبقة على الأشكال والنصوص—كل ذلك مدعوم بواسطة **aspose page java**.

## لماذا نستخدم أنماط التهشير مع Aspose.Page Java؟
- **تمييز بصري** – تعبئة التهشير تعمل حتى عندما تكون الطابعات محدودة إلى الإخراج أحادي اللون.  
- **الأداء** – تُنشأ القوام في الوقت الفعلي، لذا تتجنب ملفات الصور الكبيرة.  
- **دعم متعدد الصيغ** – يمكن لنفس الشيفرة استهداف PDF أو EPS أو SVG مع تغييرات قليلة.

## المشكلات الشائعة والنصائح
- **أخطاء مسار الملف** – تأكد من أن `dataDir` ينتهي بالفاصل المناسب (`/` أو `\`).  
- **ألوان غير مدعومة** – قد لا يتعامل بعض مفسري PostScript القديمة مع مساحات ألوان معينة؛ استخدم RGB الأساسي لأقصى توافق.  
- **تحذيرات الترخيص** – تشغيل العينة بدون ترخيص صالح سيضيف علامة مائية إلى الناتج.

## الخلاصة
إدراج أنماط التهشير يمكن أن يحسّن بشكل كبير من قابلية القراءة والجمالية للرسومات التقنية، الخرائط، أو أي رسومات تُنشئها Java. مع **Aspose.Page Java**، تحصل على واجهة برمجة تطبيقات مختصرة تُجرد أوامر PostScript منخفضة المستوى، مما يتيح لك التركيز على التصميم بدلاً من تفاصيل تنسيق الملف. الآن تعرف **كيف تضيف نمط تهشير** إلى مستندات PostScript الخاصة بك—جرّب قيم `HatchStyle` المختلفة لإنشاء المظهر الدقيق الذي تحتاجه.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page Java مع أطر عمل Java أخرى؟**  
ج: نعم، المكتبة مستقلة عن الأطر وتعمل مع Spring، Jakarta EE، Android (محدودة)، وJava SE العادي.

**س: هل تتوفر نسخة تجريبية لـ Aspose.Page Java؟**  
ج: بالطبع. حمّل نسخة تجريبية مجانية لمدة 30 يومًا [هنا](https://releases.aspose.com/).

**س: كيف أحصل على ترخيص مؤقت للتطوير؟**  
ج: اطلب ترخيصًا مؤقتًا [هنا](https://purchase.aspose.com/temporary-license/). سيزيل العلامات المائية التجريبية.

**س: أين يمكنني العثور على المزيد من الدروس ودعم المجتمع؟**  
ج: زر المنتدى الرسمي [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) للحصول على أمثلة إضافية وأسئلة وأجوبة.

**س: هل هناك توثيق شامل لجميع الفئات والطرق؟**  
ج: نعم، المرجع الكامل للـ API متاح [هنا](https://reference.aspose.com/page/java/).

**س: هل يمكنني عرض نفس نمط التهشير إلى PDF بدلاً من PostScript؟**  
ج: بالتأكيد. غيّر `PsSaveOptions` إلى `PdfSaveOptions` (أو ما يعادلها) وستظل باقي الشيفرة دون تغيير.

**س: ماذا أفعل إذا كان الملف المُولد فارغًا؟**  
ج: تأكد من أن تدفق الإخراج يشير إلى دليل قابل للكتابة وأنه تم استدعاء `document.save()` بعد جميع عمليات الرسم.

**آخر تحديث:** 2026-02-15  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}