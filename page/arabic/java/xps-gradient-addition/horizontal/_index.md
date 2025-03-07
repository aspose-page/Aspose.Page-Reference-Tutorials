---
title: أضف التدرج الأفقي في Java XPS
linktitle: أضف التدرج الأفقي في Java XPS
second_title: Aspose.Page جافا API
description: تعرف على كيفية إضافة تدرج أفقي مذهل إلى مستندات XPS في Java باستخدام Aspose.Page. اتبع دليلنا خطوة بخطوة للتكامل السلس.
weight: 11
url: /ar/java/xps-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# أضف التدرج الأفقي في Java XPS

## مقدمة
مرحبًا بك في هذا الدليل التفصيلي خطوة بخطوة حول إضافة تدرج أفقي في Java XPS باستخدام Aspose.Page لـ Java. Aspose.Page for Java هي مكتبة قوية تتيح للمطورين العمل مع مستندات XPS (مواصفات ورق XML) بسلاسة.
في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء تطبيق Java لإضافة تدرج أفقي إلى مستند XPS. اتبع الخطوات أدناه لتحقيق ذلك بكل سهولة.
## المتطلبات الأساسية
قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:
1. بيئة تطوير Java: تأكد من تثبيت Java على نظامك. إذا لم يكن الأمر كذلك، فقم بتنزيل أحدث إصدار من Java وتثبيته من[java.com](https://www.java.com).
2.  Aspose.Page لمكتبة Java: يجب أن يكون لديك Aspose.Page لمكتبة Java. يمكنك تنزيله من[Aspose.Page لوثائق جافا](https://reference.aspose.com/page/java/).
## حزم الاستيراد
ابدأ باستيراد الحزم اللازمة لتطبيق Java الخاص بك. قم بتضمين مكتبة Aspose.Page لـ Java في مشروعك. يمكنك القيام بذلك عن طريق إضافة أسطر التعليمات البرمجية التالية:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## الخطوة 1: تهيئة المستند
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
//تهيئة المستند
XpsDocument doc = new XpsDocument();
```
## الخطوة 2: إنشاء التدرج الأفقي
```java
// التدرج الأفقي
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## الخطوة 3: إضافة مسار مع التدرج
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## الخطوة 4: احفظ المستند
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
كرر هذه الخطوات حسب الحاجة، واضبط المعلمات بناءً على متطلباتك المحددة.
## خاتمة
تهانينا! لقد نجحت في إضافة تدرج أفقي إلى مستند XPS باستخدام Aspose.Page لـ Java. قدم هذا البرنامج التعليمي دليلاً شاملاً للمطورين الذين يسعون إلى تحسين تطبيقات Java الخاصة بهم بتأثيرات متدرجة.
## الأسئلة الشائعة
### س: هل يمكنني تطبيق تدرجات متعددة في مستند XPS واحد؟
نعم، يمكنك إضافة مسارات متعددة بتدرجات مختلفة لإنشاء تصميمات معقدة.
### س: هل Aspose.Page متوافق مع أحدث إصدارات Java؟
يتم تحديث Aspose.Page for Java بانتظام لضمان التوافق مع أحدث إصدارات Java.
### س: هل هناك أنواع تدرج أخرى متوفرة في Aspose.Page؟
نعم، إلى جانب التدرجات الخطية، يدعم Aspose.Page التدرجات الشعاعية للحصول على تأثيرات أكثر تنوعًا.
### س: هل يمكنني تخصيص الألوان ومواضع التوقفات المتدرجة؟
قطعاً! لديك سيطرة كاملة على الألوان ومواضع كل نقطة توقف متدرجة.
### س: هل يوجد منتدى مجتمعي لـ Aspose.Page حيث يمكنني طلب المساعدة؟
 نعم يمكنك زيارة[منتدى Aspose.Page](https://forum.aspose.com/c/page/39) للتواصل مع المجتمع والحصول على المساعدة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
