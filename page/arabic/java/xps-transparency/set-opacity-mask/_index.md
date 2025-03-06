---
title: قم بتعيين قناع العتامة في Java XPS
linktitle: قم بتعيين قناع العتامة في Java XPS
second_title: Aspose.Page جافا API
description: اكتشف قوة إعداد أقنعة العتامة في Java XPS باستخدام Aspose.Page. اتبع دليلنا خطوة بخطوة للحصول على تجربة مستندات محسنة بصريًا.
weight: 11
url: /ar/java/xps-transparency/set-opacity-mask/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بتعيين قناع العتامة في Java XPS

## مقدمة
مرحبًا بك في دليلنا الشامل حول إعداد أقنعة العتامة في Java XPS باستخدام Aspose.Page. في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مستند XPS، وإضافة لوحة قماشية، وتطبيق قناع العتامة على مستطيل باستخدام الميزات القوية في Aspose.Page لـ Java.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:
- الفهم الأساسي لبرمجة جافا.
-  تم تثبيت Aspose.Page لمكتبة Java. يمكنك تنزيله[هنا](https://releases.aspose.com/page/java/).
-  ترخيص صالح لـ Aspose.Page. إذا لم يكن لديك واحد، يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
- بيئة تطوير تم إعدادها لتشغيل تطبيقات Java.
## حزم الاستيراد
ابدأ باستيراد الحزم الضرورية إلى مشروع Java الخاص بك. تأكد من دمج مكتبة Aspose.Page بشكل صحيح. وفيما يلي مقتطف لإرشادك:
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
الآن، دعونا نقسم رمز المثال إلى خطوات متعددة:
## الخطوة 1: إنشاء مستند XPS جديد
```java
// قم بإنشاء مستند XPS جديد
XpsDocument doc = new XpsDocument();
```
## الخطوة 2: إضافة قماش
```java
// قماش جديد
XpsCanvas canvas = doc.addCanvas();
```
## الخطوة 3: إضافة مستطيل مع قناع العتامة
```java
// مستطيل في منتصف اليسار مع عتامة مقنعة بواسطة ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## الخطوة 4: قم بتعيين قناع العتامة باستخدام ImageBrush
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## الخطوة 5: احفظ مستند XPS الناتج
```java
// احفظ مستند XPS الناتج
doc.save(dataDir + "OpacityMask_out.xps"); 
```
اتبع هذه الخطوات بعناية لدمج أقنعة العتامة في مستند Java XPS الخاص بك باستخدام Aspose.Page.
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تعيين أقنعة العتامة في Java XPS باستخدام Aspose.Page. تضيف هذه الميزة طبقة من الثراء البصري إلى مستنداتك، مما يجعلها أكثر جاذبية وديناميكية.
## الأسئلة الشائعة
### هل Aspose.Page متوافق مع جميع بيئات تطوير Java؟
نعم، تم تصميم Aspose.Page للعمل بسلاسة مع بيئات تطوير Java المختلفة.
### هل يمكنني استخدام Aspose.Page بدون ترخيص؟
على الرغم من أنه يمكنك استخدام Aspose.Page بدون ترخيص، فمن المستحسن الحصول على ترخيص للحصول على مجموعة كاملة من الميزات والدعم.
### هل هناك أي قيود على النسخة التجريبية؟
قد يكون للإصدار التجريبي بعض القيود على الميزات. من المستحسن التحقق من الوثائق للحصول على التفاصيل.
### كيف يمكنني الحصول على الدعم لـ Aspose.Page؟
 يمكنك زيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للحصول على دعم المجتمع أو شراء ترخيص للمساعدة المميزة.
### هل هناك ضمان استعادة الأموال لـ Aspose.Page؟
 الرجوع إلى[صفحة الشراء](https://purchase.aspose.com/buy) للحصول على معلومات حول سياسات استرداد الأموال.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
