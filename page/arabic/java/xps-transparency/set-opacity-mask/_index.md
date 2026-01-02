---
date: 2026-01-02
description: تعلم كيفية إضافة قناع الشفافية إلى مستندات XPS باستخدام Aspose.Page Java.
  دليل خطوة بخطوة لإنشاء مستطيل قناع الشفافية وتعزيز جودة الصورة.
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: تعيين قناع الشفافية في XPS باستخدام Aspose.Page Java
url: /ar/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين قناع الشفافية في Java XPS باستخدام Aspose.Page Java

## المقدمة
مرحبًا بكم في دليلنا الشامل حول **aspose page java** أقنعة الشفافية. في هذا البرنامج التعليمي ستتعلم كيفية إنشاء مستند XPS، إضافة لوحة رسم، وتطبيق قناع شفافية على مستطيل — كل ذلك باستخدام واجهة برمجة التطبيقات القوية Aspose.Page Java. في النهاية ستتمكن من إضافة مستطيلات قناع شفافية تعطي ملفات XPS مظهرًا مصقولًا شبه شفاف.

## إجابات سريعة
- **ما الذي يفعله قناع الشفافية؟** يحدد مستويات شفافية متغيرة لشكل ما، مما يسمح للمحتوى الأساسي بالظهور من خلاله.  
- **ما المكتبة المطلوبة؟** Aspose.Page for Java (aspose page java).  
- **هل أحتاج إلى ترخيص؟** الترخيص المؤقت يعمل للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **كم عدد أسطر الشيفرة؟** حوالي 20 سطرًا من Java بالإضافة إلى بعض عبارات الإعداد.  
- **هل يمكنني إعادة استخدام القناع على أشكال متعددة؟** نعم، يمكنك تعيين نفس ImageBrush لعدة مسارات.  

## ما هو قناع الشفافية في XPS؟
قناع الشفافية هو صورة نقطية أو متجهة تتحكم في قيمة ألفا (الشفافية) لكل بكسل في الشكل. عند تطبيقه على مستطيل، تصبح أجزاء من المستطيل غير شفافة تمامًا، أو شفافة جزئيًا، أو شفافة بالكامل، مما يخلق تأثيرات بصرية متقنة.

## لماذا نستخدم Aspose.Page Java لأقنعة الشفافية؟
- **واجهة برمجة تطبيقات Full .NET‑style في Java** – نموذج كائنات بديهي.  
- **بدون تبعيات خارجية** – يعمل مع Java النقي.  
- **عروض عالية الدقة** – القناع يُظهر بدقة كما هو في مواصفات XPS.  
- **متعدد المنصات** – يعمل على Windows أو Linux أو macOS دون تعديل.  

## المتطلبات المسبقة
- فهم أساسي لبرمجة Java.  
- مكتبة Aspose.Page for Java مثبتة. يمكنك تنزيلها **[هنا](https://releases.aspose.com/page/java/)**.  
- ترخيص صالح لـ Aspose.Page. إذا لم يكن لديك، احصل على ترخيص مؤقت **[هنا](https://purchase.aspose.com/temporary-license/)**.  
- بيئة تطوير قادرة على تجميع وتشغيل تطبيقات Java (مثل IntelliJ IDEA أو Eclipse أو VS Code).  

## استيراد الحزم
ابدأ باستيراد الفئات الضرورية من مكتبة Aspose.Page. يضمن ذلك توفر واجهة البرمجة لمشروعك.

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
أولاً، أنشئ كائن مستند XPS جديد سيحتوي على جميع الرسومات الخاصة بنا.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### الخطوة 2: إضافة لوحة رسم
لوحة الرسم تعمل كسطح رسم داخل صفحة XPS.

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
نحمّل صورة TIFF، نحدد المستطيلات المصدر والوجهة، ونضبط الفرشاة على وضع البلاط بحيث يتكرر القناع إذا لزم الأمر.

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

اتبع هذه الخطوات بعناية لتضمين وظيفة **add opacity mask** في مستند Java XPS الخاص بك باستخدام Aspose.Page.

## المشكلات الشائعة & استكشاف الأخطاء وإصلاحها
- **الصورة غير موجودة** – تحقق من أن `dataDir` يشير إلى المجلد الصحيح وأن ملف `R08SY_NN.tif` موجود.  
- **القناع يظهر صلبًا** – تأكد من أن الصورة المصدر تحتوي فعليًا على قيم ألفا متغيرة؛ الصورة الصلبة بالكامل لن تظهر شفافية.  
- **وضع البلاط غير مُطبق** – يجب أن يكون المستطيل الوجهة أصغر من المستطيل المصدر لتظهر عملية التبليط.  

## الأسئلة المتكررة

**س: هل Aspose.Page متوافق مع جميع بيئات تطوير Java؟**  
ج: نعم، تم تصميم Aspose.Page للعمل بسلاسة مع مختلف بيئات تطوير Java وأدوات البناء.

**س: هل يمكنني استخدام Aspose.Page بدون ترخيص؟**  
ج: بينما يمكنك تقييم المكتبة باستخدام ترخيص مؤقت، فإن الترخيص الكامل مطلوب للاستخدام في الإنتاج.

**س: هل هناك أي قيود على نسخة التجربة؟**  
ج: قد تفرض نسخة التجربة قيودًا على الحجم أو بعض الميزات؛ راجع الوثائق الرسمية للحصول على التفاصيل.

**س: كيف يمكنني الحصول على دعم لـ Aspose.Page؟**  
ج: زر **[منتدى Aspose.Page](https://forum.aspose.com/c/page/39)** للحصول على مساعدة المجتمع أو اشترِ ترخيصًا للحصول على دعم مميز.

**س: هل هناك ضمان استرداد المال لـ Aspose.Page؟**  
ج: راجع **[صفحة الشراء](https://purchase.aspose.com/buy)** للحصول على معلومات حول سياسات الاسترداد.

**آخر تحديث:** 2026-01-02  
**تم الاختبار مع:** Aspose.Page Java 24.11 (الأحدث وقت كتابة هذا الدليل)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}