---
title: إضافة مستطيل في Java XPS
linktitle: إضافة مستطيل في Java XPS
second_title: Aspose.Page جافا API
description: تعرف على كيفية إضافة مستطيلات في Java XPS باستخدام Aspose.Page. اتبع دليلنا خطوة بخطوة للتعامل السلس مع المستندات. #JavaXPS #AsposePage
weight: 11
url: /ar/java/xps-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مستطيل في Java XPS

## مقدمة
مرحبًا بك في هذا الدليل الشامل حول إضافة المستطيلات في Java XPS باستخدام Aspose.Page! سواء كنت مطورًا متمرسًا أو بدأت للتو في استخدام Java XPS، سيرشدك هذا البرنامج التعليمي خلال العملية من خلال تعليمات خطوة بخطوة، مما يضمن حصولك على فهم عميق للموضوع.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- المعرفة الأساسية بلغة البرمجة جافا.
-  تم تثبيت مكتبة Aspose.Page. إذا لم يكن الأمر كذلك، يمكنك تنزيله من[وثائق Aspose.Page جافا](https://reference.aspose.com/page/java/).
- بيئة تطوير جافا العاملة.
## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية إلى مشروع Java الخاص بك. تأكد من إضافة مكتبة Aspose.Page بشكل صحيح إلى مسار الفصل الدراسي الخاص بك. إليك مثال أساسي:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
الآن، دعونا نقسم المثال المقدم إلى خطوات متعددة لإضافة مستطيل في Java XPS.
## الخطوة 1: قم بتعيين دليل المستندات
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
```
استبدل "دليل المستندات الخاص بك" بالمسار إلى الدليل المطلوب.
## الخطوة 2: إنشاء مستند XPS جديد
```java
// قم بإنشاء مستند XPS جديد
XpsDocument doc = new XpsDocument();
```
يؤدي هذا إلى تهيئة مستند XPS جديد.
## الخطوة 3: إضافة مستطيل ذو لون خالص CMYK
```java
// مستطيل محدد بلون CMYK (أزرق) في أسفل اليسار
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
تضيف هذه الخطوة مستطيلًا محددًا بلون CMYK خالصًا.
## الخطوة 4: احفظ مستند XPS الناتج
```java
// احفظ مستند XPS الناتج
doc.save(dataDir + "AddRectangle_out.xps");
```
وأخيرًا، احفظ مستند XPS المعدل بالمستطيل المضاف.
كرر هذه الخطوات، واضبط المعلمات حسب الحاجة، لتخصيص مستطيلاتك بشكل أكبر.
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة مستطيلات في Java XPS باستخدام Aspose.Page. يوفر هذا البرنامج التعليمي أساسًا متينًا لمساعيك في معالجة مستندات XPS.
## الأسئلة الشائعة
### هل يمكنني إضافة مستطيلات متعددة في مستند XPS واحد؟
نعم، يمكنك إضافة أي عدد تريده من المستطيلات عن طريق تكرار الخطوات الموضحة في البرنامج التعليمي.
### كيف يمكنني تغيير لون المستطيل؟
 قم بتعديل قيم الألوان في`createColor` طريقة الحصول على اللون المطلوب .
### هل Aspose.Page مناسب للتعامل مع عمليات معالجة مستندات XPS المعقدة؟
قطعاً! يوفر Aspose.Page مجموعة قوية من الميزات للتعامل مع مهام مستندات XPS المختلفة.
### أين يمكنني العثور على أمثلة ودعم إضافيين؟
 اكتشف ال[منتدى Aspose.Page](https://forum.aspose.com/c/page/39)لمزيد من الأمثلة وطلب المساعدة من المجتمع.
### هل يمكنني تجربة Aspose.Page قبل الشراء؟
 نعم، يمكنك استكشاف أ[تجربة مجانية](https://releases.aspose.com/) لتجربة قدرات Aspose.Page.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
