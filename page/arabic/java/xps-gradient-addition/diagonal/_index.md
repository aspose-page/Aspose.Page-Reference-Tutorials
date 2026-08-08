---
date: 2026-05-25
description: تعلم كيفية إضافة gradient إلى مستندات XPS في Java باستخدام Aspose.Page.
  يوضح هذا الدليل خطوة بخطوة كيفية إضافة diagonal gradient، وتطبيق linear gradient
  brushes، وإنتاج ملفات XPS احترافية.
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: إضافة Diagonal Gradient في Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'كيفية إضافة تدرج لوني: Diagonal Gradient في Java XPS'
url: /ar/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة تدرج لوني: تدرج قطري في Java XPS

## مقدمة
في تطوير Java الحديث، إتقان **how to add gradient** إلى مستندات XPS يمنح تقاريرك مظهرًا مصقولًا وجذابًا يبرز. يوضح هذا الدرس كيفية إنشاء ملف XPS من الصفر، إضافة تدرج قطري، وحفظ النتيجة — كل ذلك باستخدام Aspose.Page for Java. ستفهم لماذا التدرجات مهمة، وتطلع على استدعاءات API الدقيقة، وتحصل على نصائح عملية لتجنب الأخطاء الشائعة.

## إجابات سريعة
- **ما هي المكتبة الأساسية؟** Aspose.Page for Java  
- **أي طريقة تضيف التدرج اللوني؟** `createLinearGradientBrush` with gradient stops  
- **هل أحتاج إلى ترخيص؟** إصدار تجريبي يعمل للتطوير؛ يلزم ترخيص تجاري للإنتاج  
- **كم من الوقت تستغرق عملية التنفيذ؟** حوالي 10‑15 دقيقة لتدرج قطري أساسي  
- **هل يمكنني استخدام هذا مع أطر Java أخرى؟** نعم، الـ API غير مرتبط بإطار عمل  

## ما هو التدرج القطري في مستند XPS؟
التدرج القطري هو انتقال لوني سلس يمتد من أحد زوايا الشكل إلى الزاوية المقابلة، مما يخلق تأثيرًا بصريًا مائلًا. في XPS، يُعرّف هذا التأثير بفرشاة تدرج خطي تحتوي على نقاط توقف مرتبة تحدد الألوان والمواقع النسبية على طول الخط القطري.

## لماذا إضافة تدرج قطري باستخدام Aspose.Page؟
توفر Aspose.Page **100 % دقة عرض** للتدرجات عبر أكثر من 20 عارض XPS، وتدعم **30+ ميزة XPS** مثل النصوص، الصور، والأشكال المتجهة. تقوم الـ API بتجريد تعقيدات ترميز XPS، مما يتيح لك التركيز على التصميم مع ضمان أن الملف نفسه يبدو متطابقًا على أنظمة Windows و macOS و Linux.

## المتطلبات المسبقة
- معرفة أساسية ببرمجة Java.  
- JDK مثبت على جهازك.  
- مكتبة Aspose.Page for Java – قم بتنزيلها **[هنا](https://releases.aspose.com/page/java/)**.  
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## استيراد الحزم
ابدأ باستيراد الفئات التي ستحتاجها. تمنحك هذه الاستيرادات الوصول إلى الهندسة، معالجة التدرجات، وإنشاء مستند XPS.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## الخطوة 1: إعداد مشروعك
أنشئ مشروع Java جديد في بيئتك المفضلة وأضف ملفات JAR الخاصة بـ Aspose.Page إلى مسار بناء المشروع.

## الخطوة 2: تحديد دليل المستند
حدد المكان الذي سيُحفظ فيه ملف XPS المُولد.

```java
String dataDir = "Your Document Directory";
```

## الخطوة 3: إنشاء مستند XPS
`XpsDocument` هو الكائن الأساسي الذي يمثل ملف XPS في الذاكرة. إن إنشاؤه يمنحك لوحة لإضافة الصفحات، الأشكال، والفرش.

```java
XpsDocument doc = new XpsDocument();
```

## الخطوة 4: إضافة مسار تدرج قطري
أنشئ مسارًا مستطيلًا سيتلقى التدرج. يستخدم مسار الهندسة أمرًا بسيطًا move‑line‑close.  
XpsPath يعرّف شكلًا متجهيًا في مستند XPS، مثل مستطيل أو هندسة مخصصة.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## الخطوة 5: تعريف نقاط توقف التدرج الخطي
قم بإعداد الألوان ومواقعها. كل نقطة توقف تحدد نقطة في التدرج يظهر فيها لون معين.  
XpsGradientStop يمثل نقطة توقف لون واحدة في التدرج، تحدد اللون والإزاحة الخاصة به.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## الخطوة 6: تطبيق التدرج الخطي على المسار
`XpsLinearGradientBrush` هو نوع الفرشاة في Aspose.Page للانتقالات اللونية الخطية. يأخذ نقطتين تحددان اتجاه التدرج ومجموعة من نقاط التوقف التي تحدد الألوان على طول ذلك الخط.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## الخطوة 7: حفظ المستند
احفظ ملف XPS على القرص. سيحتوي الملف على المستطيل المملوء بالتدرج القطري الذي عرّفته.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## كيفية إضافة تدرج لوني في Java XPS؟
حمّل XpsDocument، أنشئ `XpsLinearGradientBrush` بنقطة البداية `(0,0)` ونقطة النهاية `(width,height)`, أضف نقاط التدرج، عيّن الفرشاة إلى خاصية `Fill` للشكل، وأخيرًا استدعِ `save`. يتيح لك هذا التدفق المختصر دمج تدرج قطري في عدد قليل من استدعاءات API، مع الحفاظ على نظافة الكود وقابليته للصيانة.

## المشكلات الشائعة والنصائح
- **اتجاه التدرج** – تأكد من أن نقطتي البداية والنهاية للفرشاة تعكس القطر الذي تريده؛ تبديلهما يعكس التدرج.  
- **دقة اللون** – Aspose يستخدم ARGB؛ أدرج قناة ألفا إذا كنت تحتاج إلى الشفافية.  
- **مسار الملف** – استخدم دائمًا مسارًا مطلقًا أو تحقق من أن المسار النسبي يشير إلى دليل قابل للكتابة موجود.

## أسئلة شائعة إضافية

**س: كيف أ**how to add gradient** إلى شكل XPS موجود؟**  
A: أنشئ `XpsLinearGradientBrush`، عرّف نقاط توقف التدرج، وعيّنها إلى خاصية `Fill` للشكلة كما هو موضح في الخطوة 6.

**س: ماذا يفعل **apply linear gradient** فعليًا خلف الكواليس؟**  
A: يولد تعريفًا للفرشاة في حزمة XPS يشير إلى نقطتي البداية/النهاية ومجموعة من نقاط توقف التدرج، والتي يقوم العارض بعرضها كتدرج لوني سلس.

**س: هل هناك طريقة سريعة لـ **how to use aspose** للميزات الأخرى في XPS؟**  
A: نعم، يتضمن Aspose.Page API طرقًا لإضافة الصور، النصوص، والأشكال المخصصة — فقط استكشف فئة `XpsDocument` للحصول على مساعدات إضافية.

**س: هل يمكنني **add gradient path** إلى أشكال غير مستطيلة؟**  
A: بالتأكيد. عرّف أي هندسة باستخدام `createPathGeometry` ثم عيّن `Fill` لها إلى فرشاة تدرج.

**س: هل يؤثر التدرج على حجم الملف بشكل كبير؟**  
A: فقط بشكل طفيف؛ تعريفات التدرج هي إدخالات XML خفيفة داخل حزمة XPS.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## دروس ذات صلة

- [إضافة تدرج XPS في Aspose Page](/page/java/xps-gradient-addition/)
- [إضافة نص XPS في Java - دليل Aspose.Page](/page/java/xps-text-manipulation/add-text/)
- [كيفية إضافة صورة إلى مستندات Java XPS – دليل بسيط مع Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}