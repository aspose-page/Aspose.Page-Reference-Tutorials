---
date: 2025-12-25
description: تعلم كيفية إنشاء مستندات XPS في جافا وإضافة تدرج قطري مذهل باستخدام Aspose.Page.
  يغطي هذا الدليل كيفية إضافة التدرج، تطبيق التدرج الخطي، واستخدام Aspose بفعالية.
linktitle: Add Diagonal Gradient in Java XPS
second_title: Aspose.Page Java API
title: كيفية إنشاء مستند XPS بتدرج قطري في جافا
url: /ar/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة تدرج قطري في Java XPS

## المقدمة
في تطوير Java الحديث، إنشاء مستندات XPS ذات مظهر مصقول يُعد ميزة فارقة. في هذا البرنامج التعليمي ستتعلم **كيفية إنشاء ملفات XPS** وتعزيزها بتدرج قطري باستخدام Aspose.Page for Java. سنستعرض كل خطوة، نشرح لماذا كل جزء مهم، ونظهر لك كيفية **إضافة مسار التدرج**، **تطبيق تدرج خطي**، والحصول على نتيجة بصرية احترافية بسرعة.

## إجابات سريعة
- **ما هي المكتبة الأساسية؟** Aspose.Page for Java  
- **أي طريقة تُضيف التدرج؟** `createLinearGradientBrush` مع نقاط التدرج  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للتطوير؛ الترخيص التجاري مطلوب للإنتاج  
- **كم يستغرق التنفيذ؟** حوالي 10‑15 دقيقة لتدرج قطري أساسي  
- **هل يمكنني استخدامه مع أطر Java أخرى؟** نعم، الـ API مستقل عن الإطار  

## ما هو التدرج القطري في مستند XPS؟
التدرج القطري ينتقل بسلاسة بين الألوان على خط مائل، مما يمنح العمق والاهتمام البصري للأشكال. في XPS، تُعرَّف التدرجات بفرشاة تحتوي على عدة نقاط تدرج، كل منها يحدد لونًا وموقعه النسبي.

## لماذا نضيف تدرجًا قطريًا باستخدام Aspose.Page؟
- **جودة بصرية غنية** – يتم عرض التدرجات بدقة في صيغة XPS.  
- **اتساق عبر المنصات** – يظهر ملف XPS نفسه بصورة متطابقة على عارضات Windows و macOS و Linux.  
- **API بسيط** – Aspose.Page يُجَ abstracts المواصفات منخفضة المستوى لـ XPS، مما يتيح لك التركيز على التصميم.  

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:

- معرفة أساسية ببرمجة Java.  
- تثبيت JDK على جهازك.  
- مكتبة Aspose.Page for Java. يمكنك تنزيلها **[من هنا](https://releases.aspose.com/page/java/)**.  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.

## استيراد الحزم
ابدأ باستيراد الفئات التي ستحتاجها. هذه الاستيرادات تمنحك الوصول إلى الهندسة، معالجة التدرجات، وإنشاء مستند XPS.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## الخطوة 1: إعداد المشروع
أنشئ مشروع Java جديد في بيئة التطوير التي تفضلها وأضف ملفات JAR الخاصة بـ Aspose.Page إلى مسار بناء المشروع.

## الخطوة 2: تعريف دليل المستند
حدد المكان الذي سيتم حفظ ملف XPS المُولَّد فيه.

```java
String dataDir = "Your Document Directory";
```

## الخطوة 3: إنشاء مستند XPS
قم بإنشاء كائن XpsDocument – هذا هو الكائن الأساسي الذي ستعمل معه لإنشاء محتوى **مستند XPS**.

```java
XpsDocument doc = new XpsDocument();
```

## الخطوة 4: إضافة مسار التدرج القطري
أنشئ مسارًا مستطيليًا سيستقبل التدرج. يستخدم هندسة المسار أمرًا بسيطًا من نوع move‑line‑close.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## الخطوة 5: تعريف نقاط التدرج الخطي
قم بإعداد الألوان ومواقعها. كل نقطة تدرج تُعرّف نقطة في التدرج يظهر فيها لون معين.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## الخطوة 6: تطبيق التدرج الخطي على المسار
الآن **طبق التدرج الخطي** على المسار الذي أنشأته. تُعرَّف الفرشاة بنقطتين تحددان اتجاه التدرج، وتُرفق النقاط بالفرشاة.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## الخطوة 7: حفظ المستند
احفظ ملف XPS على القرص. سيحتوي الملف على المستطيل المملوء بالتدرج القطري الذي عرّفته.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## المشكلات الشائعة والنصائح
- **اتجاه التدرج** – تأكد من أن نقطتي البداية والنهاية للفرشاة تعكسان الاتجاه القطري المطلوب؛ تبديلهما يعكس التدرج.  
- **دقة اللون** – يستخدم Aspose صيغة ARGB؛ إذا كنت تحتاج إلى شفافية، أدرج قناة ألفا عند إنشاء الألوان.  
- **مسار الملف** – استخدم دائمًا مسارًا مطلقًا أو تحقق من أن المسار النسبي يشير إلى دليل قابل للكتابة موجود.

## الأسئلة المتكررة
### س: هل يمكنني استخدام Aspose.Page for Java مع أطر Java أخرى؟
Aspose.Page صُممت لتتكامل بسلاسة مع أطر Java المختلفة، مما يجعلها خيارًا مرنًا لمشاريعك.

### س: هل هناك اعتبارات ترخيص لـ Aspose.Page؟
نعم، تأكد من مراجعة تفاصيل الترخيص على **[صفحة شراء Aspose.Page](https://purchase.aspose.com/buy)**.

### س: هل يمكن تجربة Aspose.Page for Java قبل الشراء؟
بالطبع! يمكنك استكشاف **[نسخة تجريبية مجانية هنا](https://releases.aspose.com/)**.

### س: كيف يمكنني الحصول على الدعم أو التواصل مع مجتمع Aspose؟
زر **[منتدى Aspose.Page](https://forum.aspose.com/c/page/39)** للتفاعل مع المجتمع وطلب المساعدة.

### س: هل هناك خيار للحصول على تراخيص مؤقتة؟
نعم، يمكنك الحصول على **[ترخيص مؤقت هنا](https://purchase.aspose.com/temporary-license/)**.

## أسئلة إضافية (محسّنة بالذكاء الاصطناعي)

**س: كيف أضيف **تدرج** إلى شكل XPS موجود؟**  
ج: أنشئ `XpsLinearGradientBrush`، عرّف نقاط التدرج، وعيّنها لخاصية `Fill` الخاصة بالشكل كما هو موضح في الخطوة 6.

**س: ماذا يفعل **تطبيق التدرج الخطي** خلف الكواليس؟**  
ج: يولّد تعريف فرشاة في حزمة XPS يضم نقاط البداية/النهاية ومجموعة نقاط التدرج، والتي يقوم العارض بعرضها كتدرج لوني سلس.

**س: هل هناك طريقة سريعة لاستخدام **Aspose** لميزات XPS أخرى؟**  
ج: نعم، تتضمن API Aspose.Page طرقًا لإضافة صور، نصوص، وأشكال مخصصة—استكشف فئة `XpsDocument` للحصول على مساعدات إضافية.

**س: هل يمكنني **إضافة مسار تدرج** لأشكال غير مستطيلة؟**  
ج: بالتأكيد. عرّف أي هندسة باستخدام `createPathGeometry` ثم عيّن `Fill` إلى فرشاة تدرج.

**س: هل يؤثر التدرج على حجم الملف بشكل ملحوظ؟**  
ج: تأثيره طفيف فقط؛ تعريفات التدرج هي إدخالات XML خفيفة داخل حزمة XPS.

---

**آخر تحديث:** 2025-12-25  
**تم الاختبار مع:** Aspose.Page for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}