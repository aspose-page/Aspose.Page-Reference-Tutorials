---
date: 2026-02-18
description: تعلم كيفية رسم أشكال المستطيلات في Java PostScript باستخدام Aspose.Page.
  يوضح هذا الدليل خطوة بخطوة كيفية تعيين الطلاء، وتحديد لون المستطيل في Java، وإنشاء
  رسومات حيوية مع شرح كيفية رسم المستطيل بكفاءة.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: كيفية رسم مستطيل في Java PostScript باستخدام Aspose.Page
url: /ar/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية رسم مستطيل في Java PostScript باستخدام Aspose.Page

## المقدمة
إذا كنت بحاجة إلى **how to draw rectangle** داخل ملف Java PostScript، فأنت في المكان الصحيح. في هذا الدرس سنستعرض كيفية استخدام Aspose.Page for Java لإضافة مستطيلات ملونة، والتحكم في تعبئتها وحدودها، وحفظ النتيجة كمستند PostScript. ستشاهد بالضبط **how to set paint**، وكيفية تعريف هندسة المستطيل، ولماذا يعتبر هذا النهج مثالياً لإنشاء رسومات قابلة للطباعة برمجياً. في نهاية الدليل ستفهم أيضاً السياق الأوسع لتقنيات **draw rectangle java** وكيف تتناسب مع سير عمل **java awt rectangle drawing**.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **هل يمكنني تغيير ألوان المستطيل؟** نعم – استخدم `setPaint` مع أي `java.awt.Color`  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تعمل للاختبار؛ الترخيص مطلوب للإنتاج  
- **ما حجم الصفحة المستخدم في المثال؟** A4 (الافتراضي `PsSaveOptions`)  
- **هل الكود متوافق مع Java 8+؟** بالتأكيد – يستخدم فئات AWT القياسية  

## ما هو “How to Draw Rectangle” في PostScript؟
رسم مستطيل في مستند PostScript يعني تعريف منطقة مستطيلة وإما تعبئتها، أو رسم حدودها، أو كليهما. باستخدام Aspose.Page يمكنك القيام بذلك باستخدام فئات **java awt rectangle drawing** المألوفة، مما يجعل الكود سهل القراءة والصيانة.

## لماذا نستخدم Aspose.Page للرسومات المستطيلة؟
- **متعدد المنصات**: يولد PostScript قياسي يعمل على أي طابعة.  
- **تحكم دقيق**: يمكنك ضبط ألوان التعبئة، ألوان الحدود، وعرض الخطوط بشكل مستقل.  
- **بدون تبعيات خارجية**: يستخدم فقط فئات الهندسة المدمجة في AWT، لذا لا تحتاج إلى مكتبات رسومات إضافية.  

## المتطلبات المسبقة
قبل الغوص في الدرس، تأكد من توفر المتطلبات التالية:
- فهم أساسي لبرمجة Java.  
- مكتبة Aspose.Page for Java مثبتة. إذا لم تكن مثبتة، قم بتحميلها من [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- بيئة تطوير Java مُعدّة على جهازك.

## استيراد الحزم
في مشروع Java الخاص بك، ابدأ باستيراد الحزم اللازمة. هذه الاستيرادات تمنحك الوصول إلى فئات AWT مثل `Color` و `BasicStroke` و `Rectangle2D`، وكذلك فئات معالجة المستندات الأساسية في Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## دليل خطوة بخطوة لرسم مستطيل في Java PostScript

### الخطوة 1: ضبط اللون للتعبئة  
**How to set paint** – نختار لون تعبئة برتقالي للمستطيل الأول. هذا يوضح قدرة **set rectangle color java**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### الخطوة 2: ضبط اللون لرسم حدود المستطيل  
**Set rectangle color java** – الآن نغيّر اللون إلى الأحمر ونحدد عرض الحد. هذا الجزء من المثال يوضح كيفية **draw rectangle java** بخط بسمك مخصص.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### الخطوة 3: إغلاق الصفحة الحالية وحفظ المستند  
بعد الرسم، نقوم بإغلاق الصفحة وحفظ الملف. إغلاق الصفحة يضمن أن جميع أوامر الرسم تُدفَـق إلى تدفق PostScript.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## حالات الاستخدام الشائعة لرسم المستطيلات
- **إنشاء الفواتير أو الإيصالات** – المستطيلات تعمل كحدود أو لتسليط الضوء على أقسام.  
- **إنشاء الملصقات** – رسم صناديق ملونة لفصل معلومات المنتج.  
- **مخططات بسيطة** – استخدم المستطيلات المملوءة كعناصر في مخطط الأعمدة.  
- **نماذج مطبوعة مخصصة** – دمج المستطيلات مع النص لإنشاء حقول النموذج.  

## المشكلات الشائعة والنصائح
- **أخطاء مسار الملف** – تأكد من أن `dataDir` ينتهي بفاصل ملف (`/` أو `\\`).  
- **استثناءات الترخيص** – النسخة التجريبية تضيف علامة مائية؛ احصل على ترخيص كامل للاستخدام في الإنتاج.  
- **رؤية اللون** – قد تفسر بعض الطابعات قيم RGB معينة بشكل مختلف؛ اختبر أولاً بمستطيل أسود بسيط.  
- **استخدام الذاكرة** – للمستندات الكبيرة، فكر في تفريغ التدفق بعد كل صفحة (`document.closePage()`).  

## الأسئلة المتكررة

**س:** *Can I use Aspose.Page for Java with other programming languages?*  
ج: Aspose.Page يدعم أساساً Java، لكن مكتبات مشابهة متوفرة للغات أخرى.

**س:** *Is there a trial version of Aspose.Page for Java available?*  
ج: نعم، يمكنك استكشاف ميزات Aspose.Page for Java عبر [free trial version](https://releases.aspose.com/).

**س:** *Where can I find additional help and discussions?*  
ج: زر [Aspose.Page forum](https://forum.aspose.com/c/page/39) للتفاعل مع المجتمع والحصول على المساعدة.

**س:** *How can I obtain a temporary license for Aspose.Page for Java?*  
ج: احصل على ترخيص مؤقت [here](https://purchase.aspose.com/temporary-license/).

**س:** *Where can I purchase a licensed version of Aspose.Page for Java?*  
ج: اشترِ نسخة مرخصة [here](https://purchase.aspose.com/buy).

### أسئلة وإجابات إضافية

**س:** *Can I change the rectangle size dynamically?*  
ج: نعم – فقط عدّل معلمات `Rectangle2D.Float(x, y, width, height)` قبل استدعاء `fill` أو `draw`.

**س:** *Is it possible to add text inside the rectangle?*  
ج: بالتأكيد. بعد رسم المستطيل، استخدم `document.drawString(...)` مع الخط والموقع المطلوبين.

**س:** *Does Aspose.Page support other shapes like circles or polygons?*  
ج: نعم، توفر API طرقاً مثل `drawEllipse` و `drawPolygon` لمجموعة متنوعة من الرسومات المتجهة.

## الخلاصة
في هذا الدليل عرضنا كيفية **how to draw rectangle** في مستند Java PostScript، وتناولنا **how to set paint**، وأظهرنا كيفية **set rectangle color java** باستخدام Aspose.Page. الآن لديك أساس قوي لإنشاء رسومات مطبوعة نابضة بالحياة، سواء كنت تبني فواتير، ملصقات، أو نماذج مخصصة. لا تتردد في تجربة ألوان مختلفة، وأنماط خطوط، وإضافة أشكال AWT إضافية لإثراء المخرجات.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}