---
date: 2026-10-31
description: تعلم كيفية تعيين لون الطلاء وتعبئة الشكل البيضاوي في Java PostScript
  باستخدام Aspose.Page. يوضح هذا الدليل كيفية تعبئة الشكل البيضاوي، ورسم حدود الشكل
  البيضاوي، وتعيين سمك الخط باستخدام خطوات شفرة واضحة.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: إضافة الشكل البيضاوي في Java PostScript
og_description: تعلم كيفية تعبئة الشكل البيضاوي وتعيين لون الطلاء في Java PostScript
  باستخدام Aspose.Page. اتبع التعليمات البرمجية خطوة بخطوة لرسم أشكال بيضاوية مملوءة
  ومحددة الحدود في ثوانٍ.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: كيفية تعبئة الشكل البيضاوي وتعيين لون الطلاء في Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: كيفية تعبئة الشكل البيضاوي وتعيين لون الطلاء في Java PostScript
url: /ar/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعبئة القطع الناقص وتعيين لون الطلاء في Java PostScript

## مقدمة
إذا كنت بحاجة إلى **تعيين لون الطلاء** أثناء رسم الرسومات المتجهة، فإن مكتبة Aspose.Page for Java تمنحك تحكمًا كاملاً في كل خط وتعبئة. في هذا البرنامج التعليمي ستكتشف كيفية **تعيين لون الطلاء**، **تعبئة القطع الناقص**، و**رسم حدود القطع الناقص** باستخدام نهج بسيط خطوة بخطوة. في النهاية، ستكون قادرًا على إضافة قطع ناقصة عالية الجودة بصيغة PostScript إلى الفواتير، التقارير، أو أي مستند قابل للطباعة.

## إجابات سريعة
- **ما هي المكتبة الأفضل لرسم رسومات PostScript في Java؟** Aspose.Page for Java.  
- **هل يمكنني تعبئة قطع ناقص بلون صلب؟** نعم – استخدم `document.setPaint(Color.YOUR_COLOR)` قبل `fill`.  
- **كيف أرسم فقط حدود القطع الناقص؟** عيّن اللون والحد، ثم استدعِ `document.draw(...)`.  
- **هل أحتاج إلى ترخيص للاستخدام الإنتاجي؟** يلزم الحصول على ترخيص تجاري؛ يتوفر ترخيص مؤقت للاختبار.  
- **ما نسخة Java المدعومة؟** أي بيئة تشغيل Java 8+ تعمل مع إصدار Aspose.Page الحالي.

## ما هو القطع الناقص في PostScript؟
القطع الناقص في PostScript هو شكل متجه يُعرّف بواسطة مستطيل محيط. على عكس الصور النقطية، يمكن تكبيره دون فقدان الجودة، مما يجعله مثاليًا للطباعة عالية الدقة وتحويل PDF. نظرًا لأن الشكل موصوف رياضيًا، يمكن عرضه بأي حجم أو دقة مع الحفاظ على حواف حادة ومنحنيات ناعمة.

## لماذا نستخدم Aspose.Page لإنشاء قطع ناقص في PostScript؟
توفر لك Aspose.Page تحكمًا حتميًا في كل بدائية رسم. تدعم **3 أنظمة تشغيل رئيسية (Windows, Linux, macOS)**، **0 تبعيات أصلية**، ويمكنها إنتاج **أكثر من 50 بدائية متجهة** في الثانية على خادم عادي. المكتبة مكتوبة بلغة Java فقط، لذا يمكنك دمجها في أي تطبيق Java 8+ دون الحاجة إلى مكتبات أصلية إضافية.

## المتطلبات المسبقة
قبل البدء، تأكد من أن لديك:

1. بيئة تطوير Java وظيفية (JDK 8 أو أحدث).  
2. مكتبة Aspose.Page for Java مضافة إلى مشروعك. يمكنك تنزيلها **[من صفحة إصدار Aspose.Page for Java](https://releases.aspose.com/page/java/)**.  

## استيراد الحزم
في ملف مصدر Java الخاص بك، استورد الفئات المطلوبة للرسم وحفظ محتوى PostScript.

توفر حزمة `java.awt` أنواع الرسومات الأساسية مثل `Color` و `Ellipse2D` و `BasicStroke`. توفر حزمة `com.aspose.page` الفئة `PsDocument` التي تكتب مخرجات PostScript.

- **`Color`** – تمثل لون sRGB يُستخدم للطلاء.  
- **`Ellipse2D`** – تصف شكل القطع الناقص المحدد بمستطيل محيط.  
- **`BasicStroke`** – يحدد عرض الخط، نمط الشرط، ونمط الطرف النهائي لرسم الحدود.  
- **`PsDocument`** – تمثل مستند PostScript وتوفر طرقًا لرسم الرسومات وإدارة الصفحات.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## كيفية تعيين لون الطلاء لقطعة ناقص
الخطوة الأولى هي إبلاغ المستند بأي لون يستخدم للعملية الرسم التالية. طريقة `setPaint` تحدد لونًا صلبًا سيُطبق إما على تعبئة أو على حد، حسب الاستدعاء التالي.

### الخطوة 1: إعداد مستند PostScript
أنشئ تدفق إخراج، اضبط حجم الصفحة، وأنشئ كائنًا من `PsDocument`.

`PsDocument` هي الفئة الأساسية التي تمثل ملف PostScript في الذاكرة. جميع أوامر الرسم تُمرر عبر هذا الكائن، ويتولى تخطيط الصفحات، إدارة الموارد، وتوليد الملف النهائي.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### الخطوة 2: تعبئة القطع الناقص – استخدم تعيين لون الطلاء
لـ **تعبئة القطع الناقص**، يجب أولاً استدعاء `setPaint` باللون المرغوب للتعبئة، ثم استدعاء `fill` مع كائن `Ellipse2D`.

`setPaint` يحدد اللون الحالي المستخدم للعمليات اللاحقة من تعبئة أو حد.  
`Ellipse2D` يحدد الحدود الهندسية للقطع الناقص؛ مُنشئه يأخذ إحداثيات X‑Y للزاوية العلوية اليسرى بالإضافة إلى العرض والارتفاع.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### الخطوة 3: رسم حدود القطع الناقص وتعيين سمك الحد
بعد التعبئة، يمكنك تغيير اللون إلى لون مختلف، تعريف `BasicStroke` للتحكم في عرض الخط، ورسم حدود القطع الناقص.

`BasicStroke` يحدد عرض الخط، نمط الشرط، ونمط الطرف النهائي لرسم الحدود. من خلال تعديل خاصية `width` يمكنك التحكم في مدى سمك حد القطع الناقص.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### الخطوة 4: إغلاق وحفظ المستند
أكمل الصفحة واكتب ملف PostScript إلى القرص.

استدعاء `document.close()` يفرغ جميع أوامر الرسم المعلقة ويحرر الموارد. يمكن فتح ملف `.ps` الناتج بأي عارض PostScript أو تحويله إلى PDF.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

الآن لديك ملف PostScript يحتوي على قطع ناقصين — أحدهما مملوء بالبرتقالي والآخر محاط باللون الأحمر. لا تتردد في تجربة إحداثيات، أحجام، وألوان مختلفة لتتناسب مع احتياجات التصميم الخاصة بك.

## المشكلات الشائعة واستكشاف الأخطاء
- **مسار ملف غير صحيح** – تأكد من أن `dataDir` ينتهي بفاصل (`/` أو `\\`) المناسب لنظام التشغيل الخاص بك.  
- **ترخيص مفقود** – بدون ترخيص صالح، تعمل المكتبة في وضع التقييم وقد تضيف علامات مائية.  
- **اللون غير مطبق** – تذكر تعيين `document.setPaint(...)` *قبل* كل استدعاء `fill` أو `draw`؛ إعداد اللون لا يستمر عبر عمليات منفصلة تلقائيًا.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Page for Java مع مكتبات Java أخرى؟**  
ج: نعم، تم تصميم Aspose.Page for Java لتتكامل بسلاسة مع مكتبات Java الأخرى.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟**  
ج: احصل على ترخيص مؤقت **[من صفحة الترخيص المؤقت لـ Aspose](https://purchase.aspose.com/temporary-license/)** لأغراض الاختبار.

**س: هل Aspose.Page مناسبة للمشاريع التجارية؟**  
ج: بالتأكيد! زر **[صفحة شراء Aspose](https://purchase.aspose.com/buy)** لاستكشاف خيارات الترخيص للاستخدام التجاري.

**س: أين يمكنني طلب المساعدة أو مناقشة استفسارات متعلقة بـ Aspose.Page؟**  
ج: انضم إلى المجتمع في **[منتدى Aspose.Page](https://forum.aspose.com/c/page/39)** للمناقشات والمساعدة.

**س: هل هناك موارد مجانية لتعلم المزيد عن Aspose.Page for Java؟**  
ج: استخدم **[صفحة التجربة المجانية لـ Aspose](https://releases.aspose.com/)** واستكشف الأمثلة في الوثائق.

## الخاتمة
تجعل Aspose.Page for Java من السهل **تعيين لون الطلاء**، **تعبئة القطع الناقص**، و**رسم حدود القطع الناقص** — سواء كنت بحاجة إلى شكل مملوء بسيط أو رسم معقد. باستخدام الخطوات المذكورة أعلاه يمكنك بسرعة إضافة رسومات متجهة ذات جودة احترافية إلى أي مستند قابل للطباعة. للمزيد من الاستكشاف — مثل دمج أشكال متعددة، تطبيق التدرجات، أو التحويل إلى PDF — راجع **[وثائق Aspose.Page Java الرسمية](https://reference.aspose.com/page/java/)**.

---

**آخر تحديث:** 2026-10-31  
**تم الاختبار باستخدام:** Aspose.Page for Java 24.11  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية رسم مستطيل في Java PostScript باستخدام Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [كيفية إضافة نص Unicode في Java PostScript باستخدام Aspose.Page](/page/java/postscript-text-manipulation/add-text-unicode/)
- [إنشاء تدرج شعاعي في PostScript باستخدام Aspose.Page for Java](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}