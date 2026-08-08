---
date: 2026-04-30
description: تعلم كيفية إنشاء مستند XPS باستخدام Java وإضافة قناع شفافية باستخدام
  Aspose.Page Java. دليل خطوة بخطوة مع أمثلة على الشيفرة.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: تعيين قناع الشفافية في Java XPS
second_title: Aspose.Page Java API
title: إنشاء مستند XPS بلغة Java – تعيين قناع الشفافية باستخدام Aspose.Page
url: /ar/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين قناع الشفافية في Java XPS باستخدام Aspose.Page Java

## مقدمة
في هذا الدرس ستقوم **create XPS document Java** بإنشاء ملفات XPS باستخدام Java وتتعلم كيفية تطبيق قناع شفافية يمنح رسوماتك مظهرًا مصقولًا شبه شفاف. سنستعرض العملية بالكامل — من تهيئة مستند XPS، إضافة لوحة رسم، رسم مستطيل، إلى إرفاق قناع شفافية قائم على صورة — باستخدام واجهة Aspose.Page Java API السهلة. في النهاية، ستكون قادرًا على إنشاء ملفات XPS احترافية برمجيًا وإعادة استخدام القناع على أي شكل تحتاجه.

## إجابات سريعة
- **ما هو دور قناع الشفافية؟** إنه يحدد مستويات شفافية متغيرة لشكل ما، مما يسمح للمحتوى الأساسي بالظهور من خلاله.  
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (aspose page java).  
- **هل أحتاج إلى ترخيص؟** ترخيص مؤقت يعمل للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **كم عدد أسطر الكود؟** حوالي 20 سطرًا من Java بالإضافة إلى بعض عبارات الإعداد.  
- **هل يمكنني إعادة استخدام القناع على أشكال متعددة؟** نعم، يمكنك تعيين نفس `ImageBrush` لعدة مسارات.

## ما هو قناع الشفافية في XPS؟
قناع الشفافية هو صورة نقطية (bitmap) أو متجهة تتحكم في قيمة ألفا (الشفافية) لكل بكسل في الشكل. عند تطبيقه على مستطيل، تصبح أجزاء من المستطيل غير شفافة تمامًا، أو شفافة جزئيًا، أو شفافة بالكامل، مما يخلق تأثيرات بصرية متقنة دون الحاجة إلى طبقات رسم إضافية.

## لماذا تستخدم Aspose.Page Java لـ **create XPS document java**؟
- **Pure Java API** – لا توجد تبعيات أصلية، لذا يعمل نفس الكود على Windows أو Linux أو macOS.  
- **Full XPS spec compliance** – القناع يُعرض بدقة كما هو معرف في معيار XPS.  
- **Object‑oriented design** – مشابه لـ .NET، مما يجعل من السهل تعلمه إذا كنت قد استخدمت Aspose بلغات أخرى.  
- **High performance** – مُحسّن للوثائق الكبيرة ومعالجة الدُفعات.

## حالات الاستخدام الشائعة
- **Watermarking** – تطبيق شعار شبه شفاف عبر الصفحات.  
- **Dynamic theming** – تغيير النمط البصري لعناصر واجهة المستخدم في التقارير المُولدة.  
- **Print‑ready previews** – عرض كيف سيظهر التصميم مع شفافية متغيرة قبل إرساله إلى الطابعة.

## المتطلبات المسبقة
قبل البدء، تأكد من أن لديك:
- فهم أساسي لبرمجة Java.  
- مكتبة Aspose.Page for Java مثبتة. يمكنك تنزيلها **[هنا](https://releases.aspose.com/page/java/)**.  
- ترخيص صالح لـ Aspose.Page. إذا لم يكن لديك، احصل على ترخيص مؤقت **[هنا](https://purchase.aspose.com/temporary-license/)**.  
- بيئة تطوير قادرة على تجميع وتشغيل تطبيقات Java (مثل IntelliJ IDEA أو Eclipse أو VS Code).

## استيراد الحزم
ابدأ باستيراد الفئات الضرورية من مكتبة Aspose.Page. يضمن ذلك توفر الـ API لمشروعك.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## دليل خطوة بخطوة

### الخطوة 1: إنشاء مستند XPS جديد
أولاً، أنشئ مستند XPS جديد سيحتوي على جميع رسوماتنا.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### الخطوة 2: إضافة لوحة رسم
تعمل لوحة الرسم كسطح للرسم داخل صفحة XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### الخطوة 3: إضافة مستطيل وتطبيق تعبئة صلبة
هنا نقوم بإنشاء مسار مستطيل ونمنحه تعبئة حمراء صلبة. سيستقبل هذا المستطيل لاحقًا قناع الشفافية.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### الخطوة 4: إضافة قناع شفافية باستخدام ImageBrush
نحمّل صورة TIFF، نحدد مستطيلات المصدر والوجهة، ونضبط الفرشاة على وضع التكرار بحيث يتكرر القناع إذا لزم الأمر.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### الخطوة 5: حفظ مستند XPS الناتج
أخيرًا، احفظ المستند على القرص. سيحتوي ملف الإخراج على المستطيل مع قناع الشفافية المطبق.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

اتبع هذه الخطوات بعناية لإدراج وظيفة **add opacity mask** في مستند XPS الخاص بـ Java باستخدام Aspose.Page.

## المشكلات الشائعة & استكشاف الأخطاء
- **Image not found** – تحقق من أن `dataDir` يشير إلى المجلد الصحيح وأن ملف `R08SY_NN.tif` موجود.  
- **Mask appears solid** – تأكد من أن صورة المصدر تحتوي فعليًا على قيم ألفا متغيرة؛ الصورة غير شفافة بالكامل لن تظهر شفافية.  
- **Tile mode not respected** – يجب أن يكون مستطيل الوجهة أصغر من مستطيل المصدر لكي يكون التكرار ملحوظًا.

## الأسئلة المتكررة

**س: هل Aspose.Page متوافق مع جميع بيئات تطوير Java؟**  
ج: نعم، تم تصميم Aspose.Page للعمل بسلاسة مع مختلف بيئات تطوير Java وأدوات البناء.

**س: هل يمكنني استخدام Aspose.Page بدون ترخيص؟**  
ج: يمكنك تقييم المكتبة باستخدام ترخيص مؤقت، لكن الترخيص الكامل مطلوب للاستخدام في الإنتاج.

**س: هل هناك أي قيود على نسخة التجربة؟**  
ج: قد تفرض نسخة التجربة قيودًا على الحجم أو الميزات؛ راجع الوثائق الرسمية للتفاصيل.

**س: كيف يمكنني الحصول على دعم لـ Aspose.Page؟**  
ج: زر **[منتدى Aspose.Page](https://forum.aspose.com/c/page/39)** للحصول على مساعدة المجتمع أو اشترِ ترخيصًا للحصول على دعم مميز.

**س: هل هناك ضمان استرداد المال لـ Aspose.Page؟**  
ج: راجع **[صفحة الشراء](https://purchase.aspose.com/buy)** للحصول على معلومات حول سياسات الاسترداد.

---

**آخر تحديث:** 2026-04-30  
**تم الاختبار باستخدام:** Aspose.Page Java 24.11 (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}