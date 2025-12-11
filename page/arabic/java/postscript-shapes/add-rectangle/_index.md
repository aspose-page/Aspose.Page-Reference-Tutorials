---
date: 2025-12-11
description: تعلم كيفية رسم أشكال المستطيلات في Java PostScript باستخدام Aspose.Page.
  يوضح هذا الدليل خطوة بخطوة كيفية تعيين الطلاء، وتعيين لون المستطيل في جافا، وإنشاء
  رسومات حيوية.
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
إذا كنت بحاجة إلى **كيفية رسم مستطيل** داخل ملف Java PostScript، فقد وصلت إلى المكان الصحيح. في هذا الدليل سنستعرض كيفية استخدام Aspose.Page for Java لإضافة مستطيلات ملونة، والتحكم في تعبئتها وحدودها، وحفظ النتيجة كمستند PostScript. ستتعرف بالضبط على **كيفية تعيين اللون**، وكيفية تعريف هندسة المستطيل، ولماذا يعتبر هذا النهج مثالياً لإنشاء رسومات قابلة للطباعة برمجياً.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Page for Java  
- **هل يمكنني تغيير ألوان المستطيل؟** نعم – استخدم `setPaint` مع أي `java.awt.Color`  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للاختبار؛ الترخيص مطلوب للإنتاج  
- **ما حجم الصفحة المستخدم في المثال؟** A4 (الإعداد الافتراضي `PsSaveOptions`)  
- **هل الكود متوافق مع Java 8+؟** بالتأكيد – يستخدم فئات AWT القياسية  

## المتطلبات المسبقة
قبل الغوص في الدليل، تأكد من توفر المتطلبات التالية:
- فهم أساسي لبرمجة Java.  
- مكتبة Aspose.Page for Java مثبتة. إذا لم تكن مثبتة، قم بتحميلها من [توثيق Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- بيئة تطوير Java مُعدّة على جهازك.

## استيراد الحزم
في مشروع Java الخاص بك، ابدأ باستيراد الحزم اللازمة:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## كيفية رسم مستطيل في Java PostScript
فيما يلي سير العمل الكامل مقسّم إلى خطوات واضحة. كل خطوة تتضمن شرحاً مختصراً يليه كتلة الكود الأصلية (بدون تعديل).

### الخطوة 1: تعيين اللون لتعبئة المستطيل  
**كيفية تعيين اللون** – نختار لون تعبئة برتقالي للمستطيل الأول.

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

### الخطوة 2: تعيين اللون لتحديد حدود المستطيل  
**Set rectangle color java** – الآن نغيّر اللون إلى الأحمر ونحدد عرض الخط.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### الخطوة 3: إغلاق الصفحة الحالية وحفظ المستند  
بعد الرسم، نقوم بإغلاق الصفحة وحفظ الملف.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## لماذا نستخدم Aspose.Page للرسومات المستطيلة؟
- **متعدد المنصات**: يولّد PostScript قياسي يعمل على أي طابعة.  
- **تحكم دقيق**: يمكنك تعيين ألوان التعبئة، ألوان الحدود، وعرض الخطوط بشكل مستقل.  
- **بدون تبعيات خارجية**: يستخدم فقط فئات الهندسة المدمجة في AWT.  

## المشكلات الشائعة والنصائح
- **أخطاء مسار الملف** – تأكد من أن `dataDir` ينتهي بفاصل ملفات (`/` أو `\\`).  
- **استثناءات الترخيص** – النسخة التجريبية تضيف علامة مائية؛ احصل على ترخيص كامل للاستخدام الإنتاجي.  
- **رؤية اللون** – قد تفسّر بعض الطابعات قيم RGB معينة بشكل مختلف؛ اختبر أولاً بمستطيل أسود بسيط.  

## الخاتمة
في هذا الدليل عرضنا **كيفية رسم مستطيل** داخل مستند Java PostScript، وشرحنا **كيفية تعيين اللون**، وأظهرنا **كيفية تعيين لون المستطيل في Java** باستخدام Aspose.Page. لا تتردد في تجربة أشكال، ألوان، وأنماط خطوط مختلفة لإنشاء رسومات قابلة للطباعة غنية للتقارير، الفواتير، أو الطباعة المخصصة.

## الأسئلة المتكررة

### هل يمكنني استخدام Aspose.Page for Java مع لغات برمجة أخرى؟
Aspose.Page يدعم أساساً Java، لكن توجد مكتبات مشابهة للغات أخرى.

### هل هناك نسخة تجريبية من Aspose.Page for Java متاحة؟
نعم، يمكنك استكشاف ميزات Aspose.Page for Java عبر [الإصدار التجريبي المجاني](https://releases.aspose.com/).

### أين يمكنني العثور على مساعدة إضافية ومناقشات؟
زر [منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتفاعل مع المجتمع والحصول على الدعم.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Page for Java؟
احصل على ترخيص مؤقت [من هنا](https://purchase.aspose.com/temporary-license/).

### أين يمكنني شراء نسخة مرخصة من Aspose.Page for Java؟
اشترِ نسخة مرخصة [من هنا](https://purchase.aspose.com/buy).

**أسئلة وإجابات إضافية**

**س:** *هل يمكنني تغيير حجم المستطيل ديناميكياً؟*  
**ج:** نعم – ما عليك سوى تعديل معاملات `Rectangle2D.Float(x, y, width, height)` قبل استدعاء `fill` أو `draw`.

**س:** *هل يمكن إضافة نص داخل المستطيل؟*  
**ج:** بالتأكيد. بعد رسم المستطيل، استخدم `document.drawString(...)` مع الخط والموقع المطلوبين.

**س:** *هل يدعم Aspose.Page أشكالاً أخرى مثل الدوائر أو المضلع؟*  
**ج:** نعم، توفر الـ API طرقاً مثل `drawEllipse` و `drawPolygon` لمجموعة متنوعة من الرسومات المتجهة.

---

**آخر تحديث:** 2025-12-11  
**تم الاختبار مع:** Aspose.Page for Java 24.12 (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}